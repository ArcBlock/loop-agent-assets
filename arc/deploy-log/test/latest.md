## ✅ Deploy test · `3a8e9518b` · success

- **时间**: 2026-10-01T21:40:56Z
- **版本**: `3a8e9518b091becdb8146cdcc7b81e33e361b460`
- **Run**: https://github.com/ArcBlock/arc/actions/runs/36929788052
- **改动窗口**: 24 hours ago

**2 个 blocklet 有改动**

### 改动摘要

- **did-space**：测试环境发布协调失败时 `/my` 公开站仍可读（#7512）。只有显式开关才写入 web-mode，系统站跟随操作系统（#7499）。工作区加宽（`66e7f6a09`）。已登录访客留在首页（`d2cd1e16c`）。
- **todo**：工作区宽度同一改动（`66e7f6a09`）。

这次部署的头 `3a8e9518b`（#7553）是 `perf(did-space): read schema on a primary bookmark`。它改的是 DID Space schema 读，没有改任何 blocklet 自己的文件，所以不进上面的摘要。
