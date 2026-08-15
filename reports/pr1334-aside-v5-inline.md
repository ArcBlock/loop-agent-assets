# test-sweep QA Report — aside（PR #1334 v5，内联截图版）

> 🤖 AI Agent @ vm · runner:Claude — 本文件用 **git push**（非 gh、非 MCP）提交，故 `![]()` 未被过滤，GitHub 直接内联渲染。对应 issue #1391 / PR #1334。gh 对 ArcBlock org 全部 API 403，MCP 会吃 `![]()` 的 `!`——只有 git 这条路能出真·内联图。

<!-- test-sweep-blocklet: aside -->
## ✅ aside

**URL**: https://aside.afsd.dev
**测试时间**: 2026-07-13T01:15:08Z

### 后端探针

| 探针 | 结果 |
|---|---|
| http-reachable | ✅ HTTP 200 |
| afs-rpc-list | ✅ ok:true (11 .aup pages) |
| afs-rpc-authed-list-/user | ✅ ok:true (Bearer 可读) |

### UI 走查

| 路由 | 认证 | 结果 | 数据加载ms | 总耗时ms | 截图 | 详情 |
|---|---|---|---|---|---|---|
| / | anon | ✅ | 6064 | 7661 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-root.png) | — |
| /app | anon | ✅ | 7333 | 8672 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app.png) | — |
| /app | authed | ✅ | 18538 | 74460 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-authed.png) | Failed to load resource: the server responded with a status of 404 () ×10 |
| /app/collections | anon | ✅ | 7369 | 8967 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-collections.png) | — |
| /app/collections | authed | ✅ | 9272 | 63264 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-collections-authed.png) | Failed to load resource: the server responded with a status of 404 () ×7 |
| /app/collection-detail 🔗动态 | anon | ✅ | 7656 | 9190 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-collection-detail.png) | — |
| /app/collection-detail 🔗动态 | authed | ✅ | 11679 | 20900 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-collection-detail-authed.png) | Failed to load resource: the server responded with a status of 404 () ×3 |
| /app/item-detail 🔗动态 | anon | ✅ | 7291 | 8790 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-item-detail.png) | — |
| /app/item-detail 🔗动态 | authed | ✅ | 18246 | 27016 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-item-detail-authed.png) | Failed to load resource: the server responded with a status of 404 () ×6 |
| /app/tags | anon | ✅ | 7342 | 8968 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-tags.png) | — |
| /app/tags | authed | ✅ | 16722 | 35902 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-tags-authed.png) | Failed to load resource: the server responded with a status of 404 () |
| /app/publish | anon | ✅ | 7630 | 9455 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-publish.png) | — |
| /app/explore | anon | ✅ | 6393 | 8955 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-explore.png) | — |
| /app/tag-detail 🔗动态 | anon | ✅ | 7560 | 9277 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-tag-detail.png) | — |
| /app/tag-detail 🔗动态 | authed | ✅ | 18296 | 27551 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-tag-detail-authed.png) | Failed to load resource: the server responded with a status of 404 () ×6 |
| /app/clipper | anon | ✅ | 7060 | 8730 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-clipper.png) | — |
| /app/clipper | authed | ✅ | 7693 | 28593 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-clipper-authed.png) | — |
| /app/clip | anon | ✅ | 8343 | 12153 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-clip.png) | — |
| /app/clip | authed | ✅ | 7409 | 15682 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-clip-authed.png) | — |
| /app/settings | anon | ✅ | 7787 | 9127 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-settings.png) | — |
| /app/settings | authed | ✅ | 8154 | 32263 | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-settings-authed.png) | — |

### 交互走查（authed，安全无写）

| 路由 | 交互 | 结果 | 截图 | 说明 |
|---|---|---|---|---|
| /app | drill:first-item | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-authed-drill.png) | 点进列表项 → 详情已打开（/app?item=26A7390C-47DF-4E57-9DC0-DF1DC9B7ED69&presentation=card）✓ |
| /app | act:Language | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-authed-int-1.png) | 打开 overlay/菜单/对话框 |
| /app | act:Toggle theme | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-authed-int-2.png) | 打开 overlay/菜单/对话框 |
| /app | act:Test Fixture User | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-authed-int-3.png) | 打开 overlay/菜单/对话框 |
| /app | act:Semantic search | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-authed-int-4.png) | 打开 overlay/菜单/对话框 |
| /app | act:All | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-authed-int-5.png) | 打开 overlay/菜单/对话框 |
| /app | act:Articles | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-authed-int-6.png) | 打开 overlay/菜单/对话框 |
| /app | act:Websites | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-authed-int-7.png) | 打开 overlay/菜单/对话框 |
| /app | act:Videos | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-authed-int-8.png) | 打开 overlay/菜单/对话框 |
| /app | act:Products | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-authed-int-9.png) | 打开 overlay/菜单/对话框 |
| /app | act:Repos | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-authed-int-10.png) | 打开 overlay/菜单/对话框 |
| /app | act:Social | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-authed-int-11.png) | 打开 overlay/菜单/对话框 |
| /app | act:Media | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-authed-int-12.png) | 打开 overlay/菜单/对话框 |
| /app | act:Text | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-authed-int-13.png) | 打开 overlay/菜单/对话框 |
| /app | act:Contacts | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-authed-int-14.png) | 打开 overlay/菜单/对话框 |
| /app/collections | act:New Collection | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-collections-authed-int-1.png) | 打开 overlay/菜单/对话框 |
| /app/collections | aside.aside.afsd.dev-app-collections-authed-int-1:empty-validate | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-collections-authed-int-1-emptyvalidate.png) | empty submit blocked by validation (no write) ✓ |
| /app/collections | aside.aside.afsd.dev-app-collections-authed-int-1:write | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-collections-authed-int-1-write.png) | 填值提交真实写入「[test-sweep] tsweep-1783905435923」（权威判定：数据源确有此条）→ 已清理 ✓（RPC） |
| /app/collections | act:Language | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-collections-authed-int-2.png) | 打开 overlay/菜单/对话框 |
| /app/collections | act:Toggle theme | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-collections-authed-int-3.png) | 打开 overlay/菜单/对话框 |
| /app/collections | act:Test Fixture User | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-collections-authed-int-4.png) | 打开 overlay/菜单/对话框 |
| /app/collections | act:Aside Assistant | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-collections-authed-int-5.png) | 打开 overlay/菜单/对话框 |
| /app/collection-detail | drill:first-item | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-collection-detail-authed-drill.png) | 点进列表项 → 详情已打开（/app/collection-detail?item=26A7390C-47DF-4E57-9DC0-DF1DC9B7ED69&presentation=card）✓ |
| /app/item-detail | drill:first-item | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-item-detail-authed-drill.png) | 点进列表项 → 详情已打开（/app/item-detail?item=26A7390C-47DF-4E57-9DC0-DF1DC9B7ED69&presentation=card）✓ |
| /app/tags | act:Create tag | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-tags-authed-int-1.png) | 点击（无导航/overlay 变化） |
| /app/tags | act:Language | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-tags-authed-int-2.png) | 打开 overlay/菜单/对话框 |
| /app/tags | act:Toggle theme | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-tags-authed-int-3.png) | 打开 overlay/菜单/对话框 |
| /app/tags | act:Test Fixture User | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-tags-authed-int-4.png) | 打开 overlay/菜单/对话框 |
| /app/tags | act:Aside Assistant | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-tags-authed-int-5.png) | 打开 overlay/菜单/对话框 |
| /app/tag-detail | drill:first-item | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-tag-detail-authed-drill.png) | 点进列表项 → 详情已打开（/app/tag-detail?item=26A7390C-47DF-4E57-9DC0-DF1DC9B7ED69&presentation=card）✓ |
| /app/clipper | act:Language | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-clipper-authed-int-1.png) | 打开 overlay/菜单/对话框 |
| /app/clipper | act:Toggle theme | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-clipper-authed-int-2.png) | 打开 overlay/菜单/对话框 |
| /app/clipper | act:Test Fixture User | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-clipper-authed-int-3.png) | 打开 overlay/菜单/对话框 |
| /app/clipper | act:Copy bookmarklet code | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-clipper-authed-int-4.png) | 打开 overlay/菜单/对话框 |
| /app/clipper | act:Aside Assistant | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-clipper-authed-int-5.png) | 打开 overlay/菜单/对话框 |
| /app/clip | act:Save to Aside | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-clip-authed-int-1.png) | 点击（无导航/overlay 变化） |
| /app/clip | act:Dismiss | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-clip-authed-int-2.png) | 点击（无导航/overlay 变化） |
| /app/settings | act:Language | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-settings-authed-int-1.png) | 打开 overlay/菜单/对话框 |
| /app/settings | act:Toggle theme | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-settings-authed-int-2.png) | 打开 overlay/菜单/对话框 |
| /app/settings | act:Test Fixture User | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-settings-authed-int-3.png) | 打开 overlay/菜单/对话框 |
| /app/settings | act:Behavior | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-settings-authed-int-4.png) | 打开 overlay/菜单/对话框 |
| /app/settings | act:General | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-settings-authed-int-5.png) | 打开 overlay/菜单/对话框 |
| /app/settings | act:Aside Assistant | ✅ | ![截图](https://cdn.jsdelivr.net/gh/ArcBlock/loop-agent-assets@main/arc/arc-pr1334-v5-20260713T012336Z/aside.aside.afsd.dev-app-settings-authed-int-6.png) | 打开 overlay/菜单/对话框 |

**汇总**: ✅ 路由 pass=21 fail=0 skip(动态需:id)=0 · 交互走查 43 项

