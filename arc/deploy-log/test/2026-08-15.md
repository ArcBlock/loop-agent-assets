## ✅ Deploy test · `91531c7a3` · success

- **时间**: 2026-08-15T17:22:40Z
- **版本**: `91531c7a3289dd7d8578275ca7cf9fca8bd7e3e2`
- **改动窗口**: 最近 24 小时
- **Run**: https://github.com/ArcBlock/arc/actions/runs/31897648613

**12 个 blocklet 有改动**

### 改动摘要

- 12 个 blocklet 同受一次共享依赖改动影响：arc、chain-explorer、did-space、showcase、todo、observability-explorer、aistro、arch-qa、discuss-kit、blocklet-manager、mailbox-demo、settings-cascade（web-device 组件强制转换 MD 字符串属性，修复 chart/map shell 渲染异常，`3109e82b9`，#4013）
- **did-space** / **showcase** / **aistro**：Web 侧新增 serve-time 访问闸，挡在 `.web-cache` 前面（`4c127b02a`，#4036）
- **discuss-kit**：帖子列表新增按分类的 server-side 查询下推，并补充中英文页面文案（i18n Phase 1）（#4073、#4068）
