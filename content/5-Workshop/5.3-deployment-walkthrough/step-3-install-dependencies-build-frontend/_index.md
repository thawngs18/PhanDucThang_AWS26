---
title : "Install Dependencies & Build Frontend"
date : "2025-10-10"
weight : 3
chapter : false
pre : " <b> Step 3 </b> "
---
# Step 3: Install Dependencies & Build Frontend

---

## Commands

```powershell
cd C:\Users\ADMIN\Desktop\BC\DEMO
npm install
```

---

## Expected Output

```
up to date, audited 300+ packages in 5s
```

---

## Build Frontend

```powershell
npm run build
```

---

## Build Output

```
dist/ generated successfully:
  index.html
  assets/index-xxxx.js
  assets/index-xxxx.css
```

---

## Verify Build

```powershell
Test-Path dist/index.html
# → True
```

---

## Screenshot Verification Guide

📸 **Screenshot 1: npm install completed**

**How to capture:**
1. Run `npm install` in the DEMO folder
2. Screenshot the terminal showing successful installation

**Expected result:** "audited XXX packages" message

---

📸 **Screenshot 2: npm run build completed**

**How to capture:**
1. Run `npm run build`
2. Screenshot the output showing dist/ folder created

**Expected result:** Build output with `dist/` folder containing `index.html`
