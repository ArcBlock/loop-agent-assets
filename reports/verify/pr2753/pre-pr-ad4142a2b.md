> 🤖 AI Agent Verification @ vm · runner:yechao · agentloop@0.28.0+018eaf53 · skill:verification

## Verification Report — `pre-pr` (affected base `92912c8e0`) sha `ad4142a2b`

| Check | Result | Stats | Duration |
|-------|--------|-------|----------|
| Build | ✅ PASS | — | 7.6s |
| Format | ⚠️ WARN | files=6961 | 5.2s |
| Biome lint | ✅ PASS | errors=0 warnings=35 | 12.4s |
| Architecture (AFS/AUP discipline) | ✅ PASS | — | 8.0s |
| Metadata consistency (pkg files / MCP parity / AUP widgets) | ⚠️ WARN | pkgFilesErrors=0 mcpParityErrors=8 aupWidgetErrors=0 | 0.1s |
| Native Parity | ✅ PASS | swift_constants=ok kotlin_constants=ok swift_tables=ok kotlin_tables=ok | 0.0s |
| Native Conformance | ⊘ SKIP | — | 0.0s |
| Type check (affected) | ✅ PASS | tasks=75 | 1.3s |
| Tests (affected) | ✅ PASS | passed=22107 failed=0 tasks=87 cached=85 | 280.7s |
| Plugin publish drift (source vs marketplace mirror) | ⊘ SKIP | — | 0.0s |

**Overall: ✅ PASS** (315.3s total)

### Failures

<details><summary>Format ⚠️ WARN</summary>

```
     46    │ - ····const·first·=·await·cli.run(
     47    │ - ······"afs",
     48    │ - ······"write",
     49    │ - ······"/json/if-match/key2",
     50    │ - ······"--content",
     51    │ - ······"v1",
     52    │ - ······"--json",
     53    │ - ····);
        46 │ + ····const·first·=·await·cli.run("afs",·"write",·"/json/if-match/key2",·"--content",·"v1",·"--json");
     54 47 │       const v1 = JSON.parse(first.stdout).version as string;
     55 48 │   
    ······ │ 
     73 66 │   
     74 67 │     test("write with a STALE --if-match token is rejected (AFS_CONFLICT) and leaves the winning write intact", async () => {
     75    │ - ····const·first·=·await·cli.run(
     76    │ - ······"afs",
     77    │ - ······"write",
     78    │ - ······"/json/if-match/key3",
     79    │ - ······"--content",
     80    │ - ······"v1",
     81    │ - ······"--json",
     82    │ - ····);
        68 │ + ····const·first·=·await·cli.run("afs",·"write",·"/json/if-match/key3",·"--content",·"v1",·"--json");
     83 69 │       const staleVersion = JSON.parse(first.stdout).version as string;
     84 70 │   
  

format ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  × Some errors were emitted while running checks.
```
</details>

<details><summary>Metadata consistency (pkg files / MCP parity / AUP widgets) ⚠️ WARN</summary>

```
Tool "afs_read" present in AOS (packages/aos/src/mcp/tools.ts) but missing from node (runtimes/node/src/mcp/tools.ts)
Tool "afs_list" present in AOS (packages/aos/src/mcp/tools.ts) but missing from node (runtimes/node/src/mcp/tools.ts)
Tool "afs_write" present in AOS (packages/aos/src/mcp/tools.ts) but missing from node (runtimes/node/src/mcp/tools.ts)
Tool "afs_delete" present in AOS (packages/aos/src/mcp/tools.ts) but missing from node (runtimes/node/src/mcp/tools.ts)
Tool "afs_search" present in AOS (packages/aos/src/mcp/tools.ts) but missing from node (runtimes/node/src/mcp/tools.ts)
Tool "afs_exec" present in AOS (packages/aos/src/mcp/tools.ts) but missing from node (runtimes/node/src/mcp/tools.ts)
Tool "afs_stat" present in AOS (packages/aos/src/mcp/tools.ts) but missing from node (runtimes/node/src/mcp/tools.ts)
Tool "afs_explain" present in AOS (packages/aos/src/mcp/tools.ts) but missing from node (runtimes/node/src/mcp/tools.ts)
```
</details>

### Full Logs

<details><summary>Build — output</summary>

```
…(truncated — last 6428 of 1162534 chars)…
         ╰─────── Module not found, treating it as an external dependency
@aigne/arc-cli:build: [38;5;246m─────╯[0m
@aigne/arc-cli:build: 
@aigne/arc-cli:build: ../../node_modules/.pnpm/urlpattern-polyfill@10.1.0/node_modules/urlpattern-polyfill/dist/index.d.ts (3:38) [33m[IMPORT_IS_UNDEFINED] Warning:[0m Import `URLPatternInit` will always be undefined because there is no matching export in '../../node_modules/.pnpm/urlpattern-polyfill@10.1.0/node_modules/urlpattern-polyfill/dist/types.d.ts'
@aigne/arc-cli:build:    [38;5;246m╭[0m[38;5;246m─[0m[38;5;246m[[0m ../../node_modules/.pnpm/urlpattern-polyfill@10.1.0/node_modules/urlpattern-polyfill/dist/index.d.ts:3:39 [38;5;246m][0m
@aigne/arc-cli:build:    [38;5;246m│[0m
@aigne/arc-cli:build:  [38;5;246m3 │[0m [38;5;249mv[0m[38;5;249ma[0m[38;5;249mr[0m[38;5;249m [0m[38;5;249m_[0m[38;5;249m0[0m[38;5;249m [0m[38;5;249m=[0m[38;5;249m [0m[38;5;249m[[0m[38;5;249m0[0m[38;5;249m,[0m[38;5;249m [0m[38;5;249m([0m[38;5;249m)[0m[38;5;249m [0m[38;5;249m=[0m[38;5;249m>[0m[38;5;249m [0m[38;5;249m[[0m[38;5;249mT[0m[38;5;249my[0m[38;5;249mp[0m[38;5;249me[0m[38;5;249ms[0m[38;5;249m.[0m[38;5;249mU[0m[38;5;249mR[0m[38;5;249mL[0m[38;5;249mP[0m[38;5;249ma[0m[38;5;249mt[0m[38;5;249mt[0m[38;5;249me[0m[38;5;249mr[0m[38;5;249mn[0m[38;5;249m,[0m[38;5;249m [0mTypes.URLPatternInit[38;5;249m,[0m[38;5;249m [0m[38;5;249mT[0m[38;5;249my[0m[38;5;249mp[0m[38;5;249me[0m[38;5;249ms[0m[38;5;249m.[0m[38;5;249mU[0m[38;5;249mR[0m[38;5;249mL[0m[38;5;249mP[0m[38;5;249ma[0m[38;5;249mt[0m[38;5;249mt[0m[38;5;249me[0m[38;5;249mr[0m[38;5;249mn[0m[38;5;249mR[0m[38;5;249me[0m[38;5;249ms[0m[38;5;249mu[0m[38;5;249ml[0m[38;5;249mt[0m[38;5;249m,[0m[38;5;249m [0m[38;5;249mT[0m[38;5;249my[0m[38;5;249mp[0m[38;5;249me[0m[38;5;249ms[0m[38;5;249m.[0m[38;5;249mU[0m[38;5;249mR[0m[38;5;249mL[0m[38;5;249mP[0m[38;5;249ma[0m[38;5;249mt[0m[38;5;249mt[0m[38;5;249me[0m[38;5;249mr[0m[38;5;249mn[0m[38;5;249mC[0m[38;5;249mo[0m[38;5;249mm[0m[38;5;249mp[0m[38;5;249mo[0m[38;5;249mn[0m[38;5;249me[0m[38;5;249mn[0m[38;5;249mt[0m[38;5;249mR[0m[38;5;249me[0m[38;5;249ms[0m[38;5;249mu[0m[38;5;249ml[0m[38;5;249mt[0m[38;5;249m][0m[38;5;249m,[0m[38;5;249m [0m[38;5;249m[[0m[38;5;249m"[0m[38;5;249m"[0m[38;5;249m,[0m[38;5;249m [0m[38;5;249m"[0m[38;5;249m"[0m[38;5;249m,[0m[38;5;249m [0m[38;5;249m"[0m[38;5;249m"[0m[38;5;249m,[0m[38;5;249m [0m[38;5;249m"[0m[38;5;249m"[0m[38;5;249m,[0m[38;5;249m [0m[38;5;249m"[0m[38;5;249m"[0m[38;5;249m,[0m[38;5;249m [0m[38;5;249m"[0m[38;5;249m"[0m[38;5;249m,[0m[38;5;249m [0m[38;5;249m"[0m[38;5;249m"[0m[38;5;249m,[0m[38;5;249m [0m[38;5;249m"[0m[38;5;249m"[0m[38;5;249m,[0m[38;5;249m [0m[38;5;249m"[0m[38;5;249m"[0m[38;5;249m,[0m[38;5;249m [0m[38;5;249m"[0m[38;5;249m"[0m[38;5;249m,[0m[38;5;249m [0m[38;5;249m"[0m[38;5;249m"[0m[38;5;249m,[0m[38;5;249m [0m[38;5;249m"[0m[38;5;249m"[0m[38;5;249m,[0m[38;5;249m [0m[38;5;249m"[0m[38;5;249m"[0m[38;5;249m][0m[38;5;249m,[0m[38;5;249m [0m[38;5;249ms[0m[38;5;249mi[0m[38;5;249md[0m[38;5;249me[0m[38;5;249mE[0m[38;5;249mf[0m[38;5;249mf[0m[38;5;249me[0m[38;5;249mc[0m[38;5;249mt[0m[38;5;249m([0m[38;5;249m_[0m[38;5;249m0[0m[38;5;249m)[0m[38;5;249m][0m[38;5;249m;[0m
@aigne/arc-cli:build:  [38;5;240m  │[0m                                       ──────────┬─────────  
@aigne/arc-cli:build:  [38;5;240m  │[0m                                                 ╰─────────── 
@aigne/arc-cli:build: [38;5;246m───╯[0m
@aigne/arc-cli:build: 
@aigne/arc-cli:build: [33m[PLUGIN_TIMINGS] Warning:[0m Your build spent significant time in plugins. Here is a breakdown:
@aigne/arc-cli:build:   - rolldown-plugin-dts:generate (44%)
@aigne/arc-cli:build:   - tsdown:external (33%)
@aigne/arc-cli:build: See https://rolldown.rs/options/checks#plugintimings for more details.
@aigne/arc-cli:build: 
@aigne/arc-cli:build: ✔ Build complete in 6805ms
@aigne/arc-cli:build: 
@aigne/arc-cli:build: > @aigne/arc-cli@2.0.0-beta.15 postbuild /home/user/arc/runtimes/node
@aigne/arc-cli:build: > node scripts/copy-recipe-assets.mjs
@aigne/arc-cli:build: 
@aigne/arc-cli:build: [copy-recipe-assets] copied 5 recipe(s): agent, agent-workspace, blog, minimal-app, support-community
@aigne/arc-cli:build: [copy-recipe-assets] copied web-device asset(s): themes, widgets
@aigne/afs-integration-tests:build: cache hit, replaying logs abdc49e3a358df1e
@aigne/afs-integration-tests:build: 
@aigne/afs-integration-tests:build: > @aigne/afs-integration-tests@1.11.0-beta.6 build /home/user/arc/integration-tests
@aigne/afs-integration-tests:build: > tsdown
@aigne/afs-integration-tests:build: 
@aigne/afs-integration-tests:build: ℹ tsdown v0.20.0-beta.3 powered by rolldown v1.0.0-beta.60
@aigne/afs-integration-tests:build: ℹ config file: /home/user/arc/integration-tests/tsdown.config.ts 
@aigne/afs-integration-tests:build: ℹ entry: src/index.ts
@aigne/afs-integration-tests:build: ℹ tsconfig: tsconfig.json
@aigne/afs-integration-tests:build: ℹ Build start
@aigne/afs-integration-tests:build: ℹ Cleaning 7 files
@aigne/afs-integration-tests:build: ℹ [CJS] dist/index.cjs  50.25 kB │ gzip: 6.79 kB
@aigne/afs-integration-tests:build: ℹ [CJS] 1 files, total: 50.25 kB
@aigne/afs-integration-tests:build: ℹ [CJS] dist/index.d.cts.map  1.40 kB │ gzip: 0.52 kB
@aigne/afs-integration-tests:build: ℹ [CJS] dist/index.d.cts      4.09 kB │ gzip: 1.31 kB
@aigne/afs-integration-tests:build: ℹ [CJS] 2 files, total: 5.49 kB
@aigne/afs-integration-tests:build: ✔ Build complete in 1787ms
@aigne/afs-integration-tests:build: ℹ [ESM] dist/index.mjs        43.05 kB │ gzip:  6.63 kB
@aigne/afs-integration-tests:build: ℹ [ESM] dist/index.mjs.map    89.69 kB │ gzip: 13.62 kB
@aigne/afs-integration-tests:build: ℹ [ESM] dist/index.d.mts.map   1.40 kB │ gzip:  0.52 kB
@aigne/afs-integration-tests:build: ℹ [ESM] dist/index.d.mts       4.09 kB │ gzip:  1.31 kB
@aigne/afs-integration-tests:build: ℹ [ESM] 4 files, total: 138.24 kB
@aigne/afs-integration-tests:build: ✔ Build complete in 1793ms

 Tasks:    108 successful, 108 total
Cached:    108 cached, 108 total
  Time:    751ms >>> FULL TURBO


Done: 0 generated, 0 unchanged
• turbo 2.9.14

```
</details>

<details><summary>Format — output</summary>

```

> afs@2.0.0-beta.15 format:check /home/user/arc
> biome format

Checked 6961 files in 4s. No fixes applied.
Found 5 errors.
 ELIFECYCLE  Command failed with exit code 1.
.claude/skills/blocklet-test-walker/scripts/test-flow-driver.mjs format ━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  × Formatter would have printed the following content:
  
    120 120 │   ];
    121 121 │   let ip = buildDrivePlan(inlineFlows, {});
    122     │ - check("input+submit+writes·无·via·→·inline·可执行步骤（非·narrative）",·ip[0].inline·===·true·&&·ip[0].skipped·===·undefined);
    123     │ - check("inline·步骤·nodeId=null、open=false、非破坏性",·ip[0].nodeId·===·null·&&·ip[0].open·===·false·&&·ip[0].destructive·===·false);
    124     │ - check("inline·步骤带出·input/submit",·ip[0].input.field·===·"tags-new-name"·&&·ip[0].submit·===·"tags-new-create");
        122 │ + check(
        123 │ + ··"input+submit+writes·无·via·→·inline·可执行步骤（非·narrative）",
        124 │ + ··ip[0].inline·===·true·&&·ip[0].skipped·===·undefined,
        125 │ + );
        126 │ + check(
        127 │ + ··"inline·步骤·nodeId=null、open=false、非破坏性",
        128 │ + ··ip[0].nodeId·===·null·&&·ip[0].open·===·false·&&·ip[0].destructive·===·false,
        129 │ + );
        130 │ + check(
        131 │ + ··"inline·步骤带出·input/submit",
        132 │ + ··ip[0].input.field·===·"tags-new-name"·&&·ip[0].submit·===·"tags-new-create",
        133 │ + );
    125 134 │   check("两开关都关 → inline 不 commit", ip[0].willCommit === false);
    126 135 │   check("有 input 无 submit → 仍 narrative skipped", ip[1].skipped === "narrative");
    127 136 │   ip = buildDrivePlan(inlineFlows, { commitWrites: true });
    128 137 │   check("commitWrites → inline 写 commit", ip[0].willCommit === true);
    129     │ - check("commitDestructive·不影响·inline（inline·恒非破坏性）",·buildDrivePlan(inlineFlows,·{·commitDestructive:·true·})[0].willCommit·===·false);
        138 │ + check(
        139 │ + ··"commitDestructive·不影响·inline（inline·恒非破坏性）",
        140 │ + ··buildDrivePlan(inlineFlows,·{·commitDestructive:·true·})[0].willCommit·===·false,
        141 │ + );
    130 142 │   
    131 143 │   console.log(
  

blocklets/todo/agents/concierge/agent.json format ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  × Formatter would have printed the following content:
  
     8  8 │       {
     9  9 │         "path": "/user/todo",
    10    │ - ······"ops":·[
    11    │ - ········"read",
    12    │ - ········"list"
    13    │ - ······]
       10 │ + ······"ops":·["read",·"list"]
    14 11 │       },
    15 12 │       {
    16 13 │         "path": "/user/todo/items",
    17    │ - ······"ops":·[
    18    │ - ········"read",
    19    │ - ········"list"
    20    │ - ······]
       14 │ + ······"ops":·["read",·"list"]
    21 15 │       },
    22 16 │       {
    23 17 │         "path": "/user/todo/items/**",
    24    │ - ······"ops":·[
    25    │ - ········"read",
    26    │ - ········"list",
    27    │ - ········"write",
    28    │ - ········"delete"
    29    │ - ······],
       18 │ + ······"ops":·["read",·"list",·"write",·"delete"],
    30 19 │         "maxDepth": 2
    31 20 │       }
  

providers/ai/ai-gateway/src/ai-gateway.ts format ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  × Formatter would have printed the following content:
  
     388  388 │     if (fn && typeof fn.name === "string") {
     389  389 │       // Already nested — canonicalize the envelope, keep arguments as-is.
     390      │ - ····return·{·id:·tc.id,·type:·tc.type·??·"function",·function:·{·name:·fn.name,·arguments:·fn.arguments·}·};
          390 │ + ····return·{
          391 │ + ······id:·tc.id,
          392 │ + ······type:·tc.type·??·"function",
          393 │ + ······function:·{·name:·fn.name,·arguments:·fn.arguments·},
          394 │ + ····};
     391  395 │     }
     392  396 │     // Flat `{id, name, arguments}` — wrap into the nested canonical form.
  

providers/ai/ai-gateway/test/exec.test.ts format ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  × Formatter would have printed the following content:
  
    125 125 │             content: "",
    126 126 │             tool_calls: [
    127     │ - ············{·id:·"c2",·type:·"function",·function:·{·name:·"afs_read",·arguments:·{·path:·"/x"·}·}·},
        127 │ + ············{
        128 │ + ··············id:·"c2",
        129 │ + ··············type:·"function",
        130 │ + ··············function:·{·name:·"afs_read",·arguments:·{·path:·"/x"·}·},
        131 │ + ············},
    128 132 │             ],
    129 133 │           },
  

runtimes/node/test/e2e/tests/write-if-match.test.ts format ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  × Formatter would have printed the following content:
  
     44 44 │   
     45 45 │     test("write with the CURRENT --if-match token succeeds and returns a new version", async () => {
     46    │ - ····const·first·=·await·cli.run(
     47    │ - ······"afs",
     48    │ - ······"write",
     49    │ - ······"/json/if-match/key2",
     50    │ - ······"--content",
     51    │ - ······"v1",
     52    │ - ······"--json",
     53    │ - ····);
        46 │ + ····const·first·=·await·cli.run("afs",·"write",·"/json/if-match/key2",·"--content",·"v1",·"--json");
     54 47 │       const v1 = JSON.parse(first.stdout).version as string;
     55 48 │   
    ······ │ 
     73 66 │   
     74 67 │     test("write with a STALE --if-match token is rejected (AFS_CONFLICT) and leaves the winning write intact", async () => {
     75    │ - ····const·first·=·await·cli.run(
     76    │ - ······"afs",
     77    │ - ······"write",
     78    │ - ······"/json/if-match/key3",
     79    │ - ······"--content",
     80    │ - ······"v1",
     81    │ - ······"--json",
     82    │ - ····);
        68 │ + ····const·first·=·await·cli.run("afs",·"write",·"/json/if-match/key3",·"--content",·"v1",·"--json");
     83 69 │       const staleVersion = JSON.parse(first.stdout).version as string;
     84 70 │   
  

format ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  × Some errors were emitted while running checks.
  


```
</details>

<details><summary>Biome lint — output</summary>

```
…(truncated — last 6428 of 19089 chars)…
━━━━━━━

  ! Change to an optional chain.
  
    57 │     if (tag === "button" || tag === "a") return true;
    58 │     if (el.getAttribute && el.getAttribute("role") === "button") return true;
  > 59 │     if (el.hasAttribute && el.hasAttribute("data-aup-action")) return true;
       │         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    60 │     if (el.querySelector && el.querySelector("button, a, [role=button], [data-aup-action]"))
    61 │       return true;
  
  i Unsafe fix: Change to an optional chain.
  
     57  57 │       if (tag === "button" || tag === "a") return true;
     58  58 │       if (el.getAttribute && el.getAttribute("role") === "button") return true;
     59     │ - ····if·(el.hasAttribute·&&·el.hasAttribute("data-aup-action"))·return·true;
         59 │ + ····if·(el.hasAttribute?.("data-aup-action"))·return·true;
     60  60 │       if (el.querySelector && el.querySelector("button, a, [role=button], [data-aup-action]"))
     61  61 │         return true;
  

.claude/skills/blocklet-test-walker/scripts/man-eval.mjs:60:9 lint/complexity/useOptionalChain  FIXABLE  ━━━━━━━━━━

  ! Change to an optional chain.
  
    58 │     if (el.getAttribute && el.getAttribute("role") === "button") return true;
    59 │     if (el.hasAttribute && el.hasAttribute("data-aup-action")) return true;
  > 60 │     if (el.querySelector && el.querySelector("button, a, [role=button], [data-aup-action]"))
       │         ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    61 │       return true;
    62 │     return false;
  
  i Unsafe fix: Change to an optional chain.
  
     58  58 │       if (el.getAttribute && el.getAttribute("role") === "button") return true;
     59  59 │       if (el.hasAttribute && el.hasAttribute("data-aup-action")) return true;
     60     │ - ····if·(el.querySelector·&&·el.querySelector("button,·a,·[role=button],·[data-aup-action]"))
         60 │ + ····if·(el.querySelector?.("button,·a,·[role=button],·[data-aup-action]"))
     61  61 │         return true;
     62  62 │       return false;
  

.claude/skills/blocklet-test-walker/scripts/man-eval.mjs:280:18 lint/complexity/useOptionalChain  FIXABLE  ━━━━━━━━━━

  ! Change to an optional chain.
  
    278 │     const tally = Object.create(null);
    279 │     for (const run of runs) {
  > 280 │       const s = (run[i] && run[i].status) || "inconclusive";
        │                  ^^^^^^^^^^^^^^^^^^^^^^^
    281 │       tally[s] = (tally[s] || 0) + 1;
    282 │     }
  
  i Unsafe fix: Change to an optional chain.
  
    278 278 │       const tally = Object.create(null);
    279 279 │       for (const run of runs) {
    280     │ - ······const·s·=·(run[i]·&&·run[i].status)·||·"inconclusive";
        280 │ + ······const·s·=·(run[i]?.status)·||·"inconclusive";
    281 281 │         tally[s] = (tally[s] || 0) + 1;
    282 282 │       }
  

.claude/skills/blocklet-test-walker/scripts/man-eval.mjs:322:18 lint/complexity/useOptionalChain  FIXABLE  ━━━━━━━━━━

  ! Change to an optional chain.
  
    320 │   if (!runAuth || !results) return results;
    321 │   return results.map((r, i) => {
  > 322 │     const gate = assertions && assertions[i] && assertions[i].authGate;
        │                  ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    323 │     if (gate && gate !== runAuth && r.status === "fail") {
    324 │       return {
  
  i Unsafe fix: Change to an optional chain.
  
    320 320 │     if (!runAuth || !results) return results;
    321 321 │     return results.map((r, i) => {
    322     │ - ····const·gate·=·assertions·&&·assertions[i]·&&·assertions[i].authGate;
        322 │ + ····const·gate·=·assertions?.[i]?.authGate;
    323 323 │       if (gate && gate !== runAuth && r.status === "fail") {
    324 324 │         return {
  

.claude/skills/blocklet-test-walker/scripts/man-eval.mjs:382:23 lint/complexity/useOptionalChain  FIXABLE  ━━━━━━━━━━

  ! Change to an optional chain.
  
    380 │  */
    381 │ export async function evalManCoverage(page, plan, opts = {}) {
  > 382 │   const assertions = (plan && plan.assertions) || [];
        │                       ^^^^^^^^^^^^^^^^^^^^^^^
    383 │   const quorum = Math.max(1, opts.quorum || 1);
    384 │   let results = [];
  
  i Unsafe fix: Change to an optional chain.
  
    380 380 │    */
    381 381 │   export async function evalManCoverage(page, plan, opts = {}) {
    382     │ - ··const·assertions·=·(plan·&&·plan.assertions)·||·[];
        382 │ + ··const·assertions·=·(plan?.assertions)·||·[];
    383 383 │     const quorum = Math.max(1, opts.quorum || 1);
    384 384 │     let results = [];
  

.claude/skills/blocklet-test-walker/scripts/man-eval.mjs:403:12 lint/complexity/useOptionalChain  FIXABLE  ━━━━━━━━━━

  ! Change to an optional chain.
  
    401 │             typeof window.afs.getNodeTree === "function" &&
    402 │             window.afs.getNodeTree()) ||
  > 403 │           (window.__AUP_BOOT__ && window.__AUP_BOOT__.root) ||
        │            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    404 │           null,
    405 │       );
  
  i Unsafe fix: Change to an optional chain.
  
    401 401 │               typeof window.afs.getNodeTree === "function" &&
    402 402 │               window.afs.getNodeTree()) ||
    403     │ - ··········(window.__AUP_BOOT__·&&·window.__AUP_BOOT__.root)·||
        403 │ + ··········(window.__AUP_BOOT__?.root)·||
    404 404 │             null,
    405 405 │         );
  

.claude/skills/blocklet-test-walker/scripts/man-eval.mjs:428:21 lint/complexity/useOptionalChain  FIXABLE  ━━━━━━━━━━

  ! Change to an optional chain.
  
    426 │   const stateJudged = results.filter((r) => r.layer === "state").length;
    427 │   const domJudged = results.filter((r) => r.layer === "dom").length;
  > 428 │   const hasMan = !!(plan && plan.hasMan);
        │                     ^^^^^^^^^^^^^^^^^^^
    429 │   return {
    430 │     page: (plan && plan.page) || null,
  
  i Unsafe fix: Change to an optional chain.
  
    426 426 │     const stateJudged = results.filter((r) => r.layer === "state").length;
    427 427 │     const domJudged = results.filter((r) => r.layer === "dom").length;
    428     │ - ··const·hasMan·=·!!(plan·&&·plan.hasMan);
        428 │ + ··const·hasMan·=·!!(plan?.hasMan);
    429 429 │     return {
    430 430 │       page: (plan && plan.page) || null,
  


```
</details>

<details><summary>Architecture (AFS/AUP discipline) — output</summary>

```

> afs@2.0.0-beta.15 lint:arch /home/user/arc
> pnpm lint:validation-coverage && pnpm lint:validation-doc-refs && pnpm lint:fsm-coverage && pnpm lint:afs-list-coverage && pnpm lint:exec-button-coverage && pnpm lint:instance-write-discipline && pnpm lint:agent-antipatterns && pnpm lint:login-link && pnpm lint:byo-seams && pnpm lint:zod-baseline && pnpm lint:sql-chunking


> afs@2.0.0-beta.15 lint:validation-coverage /home/user/arc
> bun run scripts/lint-validation-coverage.ts

[validation-coverage] scanned 40 blocklets
[validation-coverage] 4 blocklet(s) declare validation rules: aup-validation-fixture, showcase-dsl, showcase, todo
[validation-coverage] ✓ all rule-bearing pages have flow/sentinel coverage

> afs@2.0.0-beta.15 lint:validation-doc-refs /home/user/arc
> bun run scripts/check-validation-doc-refs.ts

[validation-doc-refs] ✓ all 10 cited files + their symbols resolve

> afs@2.0.0-beta.15 lint:fsm-coverage /home/user/arc
> bun run scripts/lint-fsm-coverage.ts

[fsm-coverage] scanned 41 blocklet(s)
[fsm-coverage] 1 FSM declaration(s) in: explorer
[fsm-coverage] 0 errors, 1 warnings
[fsm-coverage] note: P0 checks existence + coverage only — to-state semantic consistency is P1 edge-test generation's job

> afs@2.0.0-beta.15 lint:afs-list-coverage /home/user/arc
> bun run scripts/lint-afs-list-coverage.ts

[afs-list-coverage] scanned 41 blocklet(s)
[afs-list-coverage] 0 afs-list node(s) opted into the battery in: (none)
[afs-list-coverage] ✓ all battery-opted afs-list nodes handle every micro-state

> afs@2.0.0-beta.15 lint:exec-button-coverage /home/user/arc
> bun run scripts/lint-exec-button-coverage.ts

[exec-button-coverage] scanned 41 blocklet(s)
[exec-button-coverage] 0 exec-button(s) opted into the battery in: (none)
[exec-button-coverage] ✓ all battery-opted exec-buttons handle every micro-state

> afs@2.0.0-beta.15 lint:instance-write-discipline /home/user/arc
> bun run scripts/lint-instance-write-discipline.ts

[instance-write-discipline] scanned 196 page(s) in 41 blocklet(s)
[instance-write-discipline] ✓ no page writes base /instance/<non-settings> via /.actions/write|delete or bare dropzone

> afs@2.0.0-beta.15 lint:agent-antipatterns /home/user/arc
> bun run scripts/lint-agent-antipatterns.ts

[agent-antipatterns] scanned 13 agent.json file(s)
[agent-antipatterns] ✓ no agent.json grants /user/** write|delete|exec without declaring `memory`

> afs@2.0.0-beta.15 lint:login-link /home/user/arc
> bun run scripts/lint-login-link.ts

✅ login-link discipline: 0 violations.

> afs@2.0.0-beta.15 lint:byo-seams /home/user/arc
> node scripts/check-byo-seams.mjs

✓ BYO-seam gate: space (injected bindings), credential (no hardcoded hub host), vault (single-point secret reads) all pluggable.

> afs@2.0.0-beta.15 lint:zod-baseline /home/user/arc
> bun run scripts/lint-zod-baseline.ts

✅ zod-baseline: 0 new adopters; 94/95 baseline files still import zod (1 baseline file(s) migrated off zod — run --write-baseline to tighten).

> afs@2.0.0-beta.15 lint:sql-chunking /home/user/arc
> bun run scripts/lint-sql-chunking.ts

[sql-chunking] scanned 4812 source file(s)
[sql-chunking] ✓ no hand-rolled variable-length SQL placeholder construction outside chunkBy/manual chunk loops
  ⚠ explorer/index.flow: diamond: node "primary-list" content-source is written by 2 distinct selection sources (sidebar-list, tags-sidebar-list) — the cascade is not a single-upstream tree
  ⚠ ALLOWLISTED providers/basic/did-space/src/scope-migration-node.ts:52 — existingTables(): `names` is always a hardcoded literal array of ~6 table names (single call site passes a 6-entry literal) — a fixed identifier list, not data-size-driven; it can never approach a bind-parameter ceiling.

```
</details>

<details><summary>Metadata consistency (pkg files / MCP parity / AUP widgets) — output</summary>

```
Tool "afs_read" present in AOS (packages/aos/src/mcp/tools.ts) but missing from node (runtimes/node/src/mcp/tools.ts)
Tool "afs_list" present in AOS (packages/aos/src/mcp/tools.ts) but missing from node (runtimes/node/src/mcp/tools.ts)
Tool "afs_write" present in AOS (packages/aos/src/mcp/tools.ts) but missing from node (runtimes/node/src/mcp/tools.ts)
Tool "afs_delete" present in AOS (packages/aos/src/mcp/tools.ts) but missing from node (runtimes/node/src/mcp/tools.ts)
Tool "afs_search" present in AOS (packages/aos/src/mcp/tools.ts) but missing from node (runtimes/node/src/mcp/tools.ts)
Tool "afs_exec" present in AOS (packages/aos/src/mcp/tools.ts) but missing from node (runtimes/node/src/mcp/tools.ts)
Tool "afs_stat" present in AOS (packages/aos/src/mcp/tools.ts) but missing from node (runtimes/node/src/mcp/tools.ts)
Tool "afs_explain" present in AOS (packages/aos/src/mcp/tools.ts) but missing from node (runtimes/node/src/mcp/tools.ts)
```
</details>

<details><summary>Type check (affected) — output</summary>

```
…(truncated — last 6428 of 23290 chars)…
rer:check-types: cache hit, replaying logs 8b70b5a442df439a
@aigne/afs-explorer:check-types: 
@aigne/afs-explorer:check-types: > @aigne/afs-explorer@2.0.0-beta.15 check-types /home/user/arc/packages/explorer
@aigne/afs-explorer:check-types: > tsc --noEmit
@aigne/afs-explorer:check-types: 
@aigne/afs-sandbox:check-types: cache hit, replaying logs b9fbfe1e04b59ad5
@aigne/afs-sandbox:check-types: 
@aigne/afs-sandbox:check-types: > @aigne/afs-sandbox@2.0.0-beta.15 check-types /home/user/arc/providers/basic/sandbox
@aigne/afs-sandbox:check-types: > tsc --noEmit
@aigne/afs-sandbox:check-types: 
@aigne/afs-http:check-types: cache hit, replaying logs f3f70a7a4f72bd4f
@aigne/afs-http:check-types: 
@aigne/afs-http:check-types: > @aigne/afs-http@2.0.0-beta.15 check-types /home/user/arc/providers/basic/http
@aigne/afs-http:check-types: > tsc --noEmit
@aigne/afs-http:check-types: 
@aigne/afs-memory:check-types: cache hit, replaying logs 19f11c11c49234f5
@aigne/afs-memory:check-types: 
@aigne/afs-memory:check-types: > @aigne/afs-memory@2.0.0-beta.15 check-types /home/user/arc/providers/core/memory
@aigne/afs-memory:check-types: > tsc --noEmit
@aigne/afs-memory:check-types: 
@aigne/afs-scheduler:check-types: cache hit, replaying logs fbf1d8c8fa13bfbf
@aigne/afs-scheduler:check-types: 
@aigne/afs-scheduler:check-types: > @aigne/afs-scheduler@2.0.0-beta.15 check-types /home/user/arc/providers/basic/scheduler
@aigne/afs-scheduler:check-types: > tsc --noEmit
@aigne/afs-scheduler:check-types: 
@aigne/arc-services-worker:check-types: cache hit, replaying logs 32a7049ada4010bf
@aigne/arc-services-worker:check-types: 
@aigne/arc-services-worker:check-types: > @aigne/arc-services-worker@0.0.0 check-types /home/user/arc/services/cloudflare
@aigne/arc-services-worker:check-types: > tsc --noEmit
@aigne/arc-services-worker:check-types: 
@aigne/afs-presence:check-types: cache hit, replaying logs 24615d244e1529c7
@aigne/afs-presence:check-types: 
@aigne/afs-presence:check-types: > @aigne/afs-presence@2.0.0-beta.15 check-types /home/user/arc/providers/core/presence
@aigne/afs-presence:check-types: > tsc --noEmit
@aigne/afs-presence:check-types: 
@aigne/aos:check-types: cache hit, replaying logs ced194bc16c2cf4f
@aigne/aos:check-types: 
@aigne/aos:check-types: > @aigne/aos@0.2.0-beta check-types /home/user/arc/packages/aos
@aigne/aos:check-types: > tsc --noEmit
@aigne/aos:check-types: 
@aigne/afs-ash:check-types: cache hit, replaying logs eb4c8baf01e70638
@aigne/afs-ash:check-types: 
@aigne/afs-ash:check-types: > @aigne/afs-ash@2.0.0-beta.15 check-types /home/user/arc/providers/basic/ash
@aigne/afs-ash:check-types: > tsc --noEmit
@aigne/afs-ash:check-types: 
@aigne/arc:check-types: cache hit, replaying logs da961a8c43caafec
@aigne/arc:check-types: 
@aigne/arc:check-types: > @aigne/arc@0.1.1-beta check-types /home/user/arc/packages/arc
@aigne/arc:check-types: > tsc --noEmit
@aigne/arc:check-types: 
@aigne/afs-blocklets:check-types: cache hit, replaying logs db8beecf58a49cd8
@aigne/afs-blocklets:check-types: 
@aigne/afs-blocklets:check-types: > @aigne/afs-blocklets@1.11.0-beta.13 check-types /home/user/arc/providers/basic/blocklets
@aigne/afs-blocklets:check-types: > tsc --noEmit
@aigne/afs-blocklets:check-types: 
@aigne/afs-agent:check-types: cache hit, replaying logs 36d84e50584fada6
@aigne/afs-agent:check-types: 
@aigne/afs-agent:check-types: > @aigne/afs-agent@1.11.0-beta.13 check-types /home/user/arc/providers/basic/agent
@aigne/afs-agent:check-types: > tsc --noEmit
@aigne/afs-agent:check-types: 
@aigne/blocklet-manager:check-types: cache hit, replaying logs 81b6821d2d2f5b53
@aigne/blocklet-manager:check-types: 
@aigne/blocklet-manager:check-types: > @aigne/blocklet-manager@0.1.0 check-types /home/user/arc/packages/blocklet-manager
@aigne/blocklet-manager:check-types: > tsc --noEmit
@aigne/blocklet-manager:check-types: 
@aigne/afs-llm-bench:check-types: cache hit, replaying logs d77ad48c9e0bd793
@aigne/afs-llm-bench:check-types: 
@aigne/afs-llm-bench:check-types: > @aigne/afs-llm-bench@2.0.0-beta.15 check-types /home/user/arc/providers/ai/llm-bench
@aigne/afs-llm-bench:check-types: > tsc --noEmit
@aigne/afs-llm-bench:check-types: 
@aigne/agent-runtime:check-types: cache hit, replaying logs e6086e6280a0849e
@aigne/agent-runtime:check-types: 
@aigne/agent-runtime:check-types: > @aigne/agent-runtime@2.0.0-beta.15 check-types /home/user/arc/packages/agent-runtime
@aigne/agent-runtime:check-types: > tsc --noEmit
@aigne/agent-runtime:check-types: 
@aigne/afs-ui:check-types: cache hit, replaying logs 8eb80f26a70c6676
@aigne/afs-ui:check-types: 
@aigne/afs-ui:check-types: > @aigne/afs-ui@2.0.0-beta.15 check-types /home/user/arc/providers/runtime/ui
@aigne/afs-ui:check-types: > tsc --noEmit
@aigne/afs-ui:check-types: 
@aigne/afs-web-device:check-types: cache hit, replaying logs 70740c672b9934b9
@aigne/afs-web-device:check-types: 
@aigne/afs-web-device:check-types: > @aigne/afs-web-device@2.0.0-beta.15 check-types /home/user/arc/providers/runtime/web-device
@aigne/afs-web-device:check-types: > tsc --noEmit
@aigne/afs-web-device:check-types: 
@aigne/afs-ui-wm:check-types: cache hit, replaying logs b9f491d82ac1f0f1
@aigne/afs-ui-wm:check-types: 
@aigne/afs-ui-wm:check-types: > @aigne/afs-ui-wm@2.0.0-beta.15 check-types /home/user/arc/providers/runtime/ui-wm
@aigne/afs-ui-wm:check-types: > tsc --noEmit
@aigne/afs-ui-wm:check-types: 
@aigne/arc-worker:check-types: cache hit, replaying logs 7dc1147e762f9dc1
@aigne/arc-worker:check-types: 
@aigne/arc-worker:check-types: > @aigne/arc-worker@0.0.0 check-types /home/user/arc/runtimes/cloudflare
@aigne/arc-worker:check-types: > tsc --noEmit
@aigne/arc-worker:check-types: 
@aigne/arc-cli:check-types: cache hit, replaying logs 83c494bc36d8785a
@aigne/arc-cli:check-types: 
@aigne/arc-cli:check-types: > @aigne/arc-cli@2.0.0-beta.15 check-types /home/user/arc/runtimes/node
@aigne/arc-cli:check-types: > tsc --noEmit
@aigne/arc-cli:check-types: 
@aigne/afs-integration-tests:check-types: cache hit, replaying logs 5a811dd02e54791d
@aigne/afs-integration-tests:check-types: 
@aigne/afs-integration-tests:check-types: > @aigne/afs-integration-tests@1.11.0-beta.6 check-types /home/user/arc/integration-tests
@aigne/afs-integration-tests:check-types: > tsc --noEmit
@aigne/afs-integration-tests:check-types: 

 Tasks:    75 successful, 75 total
Cached:    75 cached, 75 total
  Time:    565ms >>> FULL TURBO

• turbo 2.9.14

```
</details>

<details><summary>Tests (affected) — output</summary>

```
…(truncated — last 6428 of 2666692 chars)…
ode/CF /user/index parity (issue #936 acceptance #2) > same index: declaration + same sample data → same entryPath SET on both runtimes [791.15ms]
@aigne/arc-worker:test: 
@aigne/arc-worker:test:  1 pass
@aigne/arc-worker:test:  0 fail
@aigne/arc-worker:test:  5 expect() calls
@aigne/arc-worker:test: Ran 1 test across 1 file. [1.78s]
@aigne/arc-worker:test: 
@aigne/arc-worker:test: ▶ miniflare: webcache-d1-budget.miniflare.test.ts
@aigne/arc-worker:test: bun test v1.3.11 (af24e281)
@aigne/arc-worker:test: 
@aigne/arc-worker:test: test/webcache-d1-budget.miniflare.test.ts:
@aigne/arc-worker:test: {"ts":"2026-07-31T06:58:26.137Z","level":"warn","service":"arc-worker","ns":"cf:fetch","requestId":"37a4510f-5201-4f82-ae6d-c356a3f817bf","host":"arcblock.afsd.io","message":"[system-mounts] /dev/chain/main: mount failed — Error: AFS_PROVIDER_RES_URL is not set. Every deployment must declare which Pages project owns its provider resources. Add it to wrangler.toml (top-level [vars] for staging, [env.<id>.vars] for named envs) o…"}
@aigne/arc-worker:test: {"ts":"2026-07-31T06:58:26.138Z","level":"warn","service":"arc-worker","ns":"cf:fetch","requestId":"37a4510f-5201-4f82-ae6d-c356a3f817bf","host":"arcblock.afsd.io","message":"[system-mounts] /dev/chain/beta: mount failed — Error: AFS_PROVIDER_RES_URL is not set. Every deployment must declare which Pages project owns its provider resources. Add it to wrangler.toml (top-level [vars] for staging, [env.<id>.vars] for named envs) o…"}
@aigne/arc-worker:test: {"ts":"2026-07-31T06:58:26.218Z","level":"info","service":"arc-worker","ns":"request","requestId":"37a4510f-5201-4f82-ae6d-c356a3f817bf","host":"arcblock.afsd.io","message":"request","method":"GET","path":"/","status":200,"durationMs":124}
@aigne/arc-worker:test: (pass) `.web-cache` serve D1/R2 budget (#808) > serves the pre-rendered page and stays within the COLD D1 budget [137.68ms]
@aigne/arc-worker:test: {"ts":"2026-07-31T06:58:26.232Z","level":"info","service":"arc-worker","ns":"request","requestId":"729bf9ee-7066-4595-a8a3-06c9e6613b58","host":"arcblock.afsd.io","message":"request","method":"GET","path":"/","status":200,"durationMs":1}
@aigne/arc-worker:test: (pass) `.web-cache` serve D1/R2 budget (#808) > stays within the tight WARM budget on the second hit (caches hot) [2.82ms]
@aigne/arc-worker:test: {"ts":"2026-07-31T06:58:26.246Z","level":"info","service":"arc-worker","ns":"request","requestId":"4ead2e8a-b9bb-406c-9027-57a5d2663fbf","host":"arcblock.afsd.io","message":"request","method":"GET","path":"/en/","status":200,"durationMs":13}
@aigne/arc-worker:test: (pass) `.web-cache` serve D1/R2 budget (#808) > serves an inner page within the same warm budget [18.49ms]
@aigne/arc-worker:test: 
@aigne/arc-worker:test:  3 pass
@aigne/arc-worker:test:  0 fail
@aigne/arc-worker:test:  11 expect() calls
@aigne/arc-worker:test: Ran 3 tests across 1 file. [4.16s]
@aigne/arc-worker:test: 
@aigne/arc-worker:test: ▶ miniflare: workers-ai-embedding-e2e.miniflare.test.ts
@aigne/arc-worker:test: bun test v1.3.11 (af24e281)
@aigne/arc-worker:test: 
@aigne/arc-worker:test: test/workers-ai-embedding-e2e.miniflare.test.ts:
@aigne/arc-worker:test: {"ts":"2026-07-31T06:58:27.127Z","level":"warn","service":"afs","ns":"cf:fetch","message":"[system-mounts] /dev/chain/main: mount failed — Error: AFS_PROVIDER_RES_URL is not set. Every deployment must declare which Pages project owns its provider resources. Add it to wrangler.toml (top-level [vars] for staging, [env.<id>.vars] for named envs) o…"}
@aigne/arc-worker:test: {"ts":"2026-07-31T06:58:27.127Z","level":"warn","service":"afs","ns":"cf:fetch","message":"[system-mounts] /dev/chain/beta: mount failed — Error: AFS_PROVIDER_RES_URL is not set. Every deployment must declare which Pages project owns its provider resources. Add it to wrangler.toml (top-level [vars] for staging, [env.<id>.vars] for named envs) o…"}
@aigne/arc-worker:test: (pass) workers-ai embedding end-to-end (real D1) > createAfsFromEnv threads env.AI into the workers-ai factory → embed works [34.38ms]
@aigne/arc-worker:test: (pass) workers-ai embedding end-to-end (real D1) > index autoEmbed routes through workers-ai → semantic recall returns the entry [252.93ms]
@aigne/arc-worker:test: {"ts":"2026-07-31T06:58:27.383Z","level":"warn","service":"afs","ns":"cf:fetch","message":"[mount-config] mount failed for /dev/ai/hubs/workers-ai (provider=workers-ai): Error: workers-ai mount requires the Cloudflare Workers AI binding (env.AI) — add `[ai] binding = \"AI\"` to wrangler.toml. Without it, semantic embedding degrades to FTS + anchor recall."}
@aigne/arc-worker:test: {"ts":"2026-07-31T06:58:27.394Z","level":"warn","service":"afs","ns":"cf:fetch","message":"[system-mounts] /dev/chain/main: mount failed — Error: AFS_PROVIDER_RES_URL is not set. Every deployment must declare which Pages project owns its provider resources. Add it to wrangler.toml (top-level [vars] for staging, [env.<id>.vars] for named envs) o…"}
@aigne/arc-worker:test: {"ts":"2026-07-31T06:58:27.395Z","level":"warn","service":"afs","ns":"cf:fetch","message":"[system-mounts] /dev/chain/beta: mount failed — Error: AFS_PROVIDER_RES_URL is not set. Every deployment must declare which Pages project owns its provider resources. Add it to wrangler.toml (top-level [vars] for staging, [env.<id>.vars] for named envs) o…"}
@aigne/arc-worker:test: (pass) workers-ai embedding end-to-end (real D1) > createAfsFromEnv WITHOUT env.AI → workers-ai mount fails soft (no crash, embed absent) [13.24ms]
@aigne/arc-worker:test: (pass) workers-ai embedding end-to-end (real D1) > embeddingEnabled but workers-ai unmounted → write + FTS work, semantic empty, no crash [68.98ms]
@aigne/arc-worker:test: (pass) workers-ai embedding end-to-end (real D1) > embeddingAfsRoot: embeds via base even when the mount afsRoot can't reach the hub [80.86ms]
@aigne/arc-worker:test: (pass) workers-ai embedding end-to-end (real D1) > control: WITHOUT embeddingAfsRoot, an index whose afsRoot can't reach the hub stores no vector [50.97ms]
@aigne/arc-worker:test: 
@aigne/arc-worker:test:  6 pass
@aigne/arc-worker:test:  0 fail
@aigne/arc-worker:test:  17 expect() calls
@aigne/arc-worker:test: Ran 6 tests across 1 file. [1319.00ms]
@aigne/arc-worker:test: 
@aigne/arc-worker:test: All 120 test files passed.

 Tasks:    87 successful, 87 total
Cached:    85 cached, 87 total
  Time:    4m39.96s 

• turbo 2.9.14

```
</details>

<sub>Generated by the `agentloop` verification engine — numbers measured by the scripts, not hand-filled.</sub>