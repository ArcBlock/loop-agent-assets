## ✅ Deploy test · `e9b2258fd` · success

- **时间**: 2026-10-01T08:24:36Z
- **版本**: `e9b2258fd1ecf323ee81c0ac26702fb78c3f8206`
- **Run**: https://github.com/ArcBlock/arc/actions/runs/36835727471
- **改动窗口**: 24 hours ago

**2 个 blocklet 有改动**

### 改动摘要

- **did-space**：个人空间和带品牌的公开页（#7462），工作区加宽（`66e7f6a09`），已登录访客留在首页（`d2cd1e16c`），匿名打开 `/my` 会转到登录（#7477），测试环境发布协调失败时 `/my` 公开站仍可读（#7512），挂载框跟随 arc space 的主题（#7478），只有显式开关才写入 web-mode（#7499）。
- **todo**：`/my` 补上头像回退、显式 locale 和路由标题（#7475）。个人空间与工作区宽度也落到了 todo（#7462、`66e7f6a09`）。

这次部署的头 `e9b2258fd`（#7537）只改 AUP 客户端的 `exec /.actions/query` 传输，没有改任何 blocklet 自己的文件，所以它是头提交，不进上面的摘要。
