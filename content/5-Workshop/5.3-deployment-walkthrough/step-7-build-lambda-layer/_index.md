---
title : "Build Lambda Layer"
date : "2025-10-10"
weight : 7
chapter : false
pre : " <b> Step 7 </b> "
---
# Step 7: Build Lambda Layer

---

## Purpose

Contains Python dependencies (google-genai, FastAPI, pydantic, etc.) for Lambda execution.

---

## 7.1 Download wheels for Python 3.12 ARM64

```powershell
$wheelDir = "C:\Users\ADMIN\AppData\Local\Temp\lambda-layer\wheels"
New-Item -ItemType Directory -Path $wheelDir -Force | Out-Null

pip download -r backend/requirements.txt --dest $wheelDir `
  --platform manylinux2014_aarch64 --python-version 3.12 --only-binary :all:
```

---

## 7.2 Extract and package Layer

```powershell
$baseDir = "C:\Users\ADMIN\AppData\Local\Temp\lambda-layer"
$extractDir = Join-Path $baseDir "python_tmp"
Remove-Item -Recurse -Force $extractDir -ErrorAction SilentlyContinue
New-Item -ItemType Directory -Path $extractDir -Force | Out-Null

Add-Type -Assembly "System.IO.Compression.FileSystem"
$wheels = Get-ChildItem "$wheelDir\*.whl"
foreach ($w in $wheels) {
    $zip = [System.IO.Compression.ZipFile]::OpenRead($w.FullName)
    foreach ($entry in $zip.Entries) {
        $name = $entry.FullName
        if ($name -match "\.dist-info/") { continue }
        if ($name.EndsWith("/")) { continue }
        if ($name -match "\.data/") { continue }
        $targetPath = Join-Path $extractDir $name
        $targetDir = Split-Path $targetPath -Parent
        if (!(Test-Path $targetDir)) { New-Item -ItemType Directory -Path $targetDir -Force | Out-Null }
        [System.IO.Compression.ZipFileExtensions]::ExtractToFile($entry, $targetPath, $true)
    }
    $zip.Dispose()
}

$layerDir = Join-Path $baseDir "_layer"
Remove-Item -Recurse -Force $layerDir -ErrorAction SilentlyContinue
New-Item -ItemType Directory -Path $layerDir -Force | Out-Null
Copy-Item -Recurse -Force $extractDir (Join-Path $layerDir "python")

$zipPath = Join-Path $baseDir "layer.zip"
Remove-Item $zipPath -Force -ErrorAction SilentlyContinue
Compress-Archive -Path "$layerDir\*" -DestinationPath $zipPath -Force
```

---

## 7.3 Publish Layer to AWS

```powershell
aws lambda publish-layer-version --layer-name CloudNexus-PythonDeps `
  --description "Python3.12 ARM64 deps" --zip-file "fileb://$zipPath" `
  --compatible-runtimes python3.12 --compatible-architectures arm64 `
  --query "LayerVersionArn" --output text
```

---

## Verify .so Files

```powershell
$zip = [System.IO.Compression.ZipFile]::OpenRead($zipPath)
$zip.Entries | Where-Object { $_.FullName -like "*.so*" } | Format-Table FullName, Length
$zip.Dispose()
```

**Expected:**
```
python/pydantic_core/_pydantic_core.cpython-312-aarch64-linux-gnu.so
python/_cffi_backend.cpython-312-aarch64-linux-gnu.so
python/websockets/speedups.cpython-312-aarch64-linux-gnu.so
```

---

## Screenshot Verification Guide

📸 **Screenshot 1: .so Files Verification**

**How to capture:**
1. Run the verification command to list .so files
2. Screenshot showing all native extension files

**What to verify:**
- Files are `cpython-312` (Python 3.12)
- Architecture is `aarch64` (ARM64)

---

📸 **Screenshot 2: Layer Published Successfully**

**How to capture:**
1. Run `aws lambda publish-layer-version`
2. Screenshot the LayerVersionArn output

**Expected result:** ARN in format `arn:aws:lambda:ap-southeast-1:<ACCOUNT>:layer:CloudNexus-PythonDeps:1`
