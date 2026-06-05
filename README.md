# Phan Duc Thang — Internship Report (AWS26)

Báo cáo thực tập Hugo site cho **Phan Đức Thắng**, lớp **AWS26**.

- **Repository:** https://github.com/thawngs18/PhanDucThang_AWS26
- **GitHub Pages:** https://thawngs18.github.io/PhanDucThang_AWS26/

## Deploy bằng GitHub Actions

1. Vào **Settings → Pages** của repo
2. **Build and deployment → Source:** chọn **GitHub Actions**
3. Push code lên nhánh `main`, hoặc vào tab **Actions** → **Deploy Hugo site to GitHub Pages** → **Run workflow**

Sau khi workflow chạy xong, link deploy hiện ngay trong job **deploy** (environment `github-pages`).

## Local preview

```bash
hugo server -D
```
