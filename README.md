# PhanDucThang_AWS26 — Báo cáo thực tập AWS FCJ

Site Hugo (theme Learn) deploy lên GitHub Pages qua GitHub Actions.

## Repository

- GitHub: https://github.com/thawngs18/PhanDucThang_AWS26
- Pages: https://thawngs18.github.io/PhanDucThang_AWS26/

## Cấu hình GitHub Pages

1. Vào **Settings → Pages**
2. **Source**: chọn **GitHub Actions**
3. Push lên nhánh `main` — workflow `.github/workflows/hugo.yml` sẽ build và deploy tự động

## Chạy local

```bash
hugo server -D
```

## Điền thông tin cá nhân

Chỉnh `content/_index.md` và `content/_index.vi.md`, thêm ảnh `static/images/profile.png`.
