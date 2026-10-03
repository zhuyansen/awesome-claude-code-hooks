# Awesome Claude Code Hooks

[English](README.md)

开源的 **Claude Code hooks、subagents 和 statusline**:Hook 守卫与格式化、专家 Agent 合集、用量与上下文状态栏,以及管理它们的工具。共 97 个仓库,每个都由 [Agent Skills Hub](https://agentskillshub.top?utm_source=github&utm_medium=awesome-list) 读过 README 并做了安全评级。

带类型筛选的在线页面:**[https://agentskillshub.top/best/claude-code-hooks/](https://agentskillshub.top/best/claude-code-hooks/?utm_source=github&utm_medium=awesome-list)** · 每 8 小时刷新

## 这些项目长什么样

<table>
<tr>
<td align="center" valign="top" width="33%"><b>🪝 Hooks 钩子</b><br><sub>19 个仓库</sub><br><br><sub>在工具调用、提问、结束等事件上运行的脚本:守卫、格式化、通知。</sub><br><a href="#type-hooks"><b>查看列表 →</b></a></td>
<td align="center" valign="top" width="33%"><b>🤖 Subagents 子代理</b><br><sub>7 个仓库</sub><br><br><sub>带独立提示词和工具的专家 Agent,以及编排方式。</sub><br><a href="#type-subagents"><b>查看列表 →</b></a></td>
<td align="center" valign="top" width="33%"><b>📊 Statusline 状态栏</b><br><sub>37 个仓库</sub><br><br><sub>状态栏显示的内容:用量、花费、上下文、git、模型。</sub><br><a href="#type-statusline"><b>查看列表 →</b></a></td>
</tr>
<tr>
<td align="center" valign="top" width="33%"><b>📚 合集</b><br><sub>21 个仓库</sub><br><br><sub>打包了大量 hooks、agents、命令和配置的合集。</sub><br><a href="#type-collection"><b>查看列表 →</b></a></td>
<td align="center" valign="top" width="33%"><b>🛠 管理与生成工具</b><br><sub>13 个仓库</sub><br><br><sub>创建、安装、测试和管理 hooks、subagents、statusline 的工具。</sub><br><a href="#type-tooling"><b>查看列表 →</b></a></td>
</tr>
</table>

## 目录

- [🪝 Hooks 钩子](#type-hooks) (19)
- [🤖 Subagents 子代理](#type-subagents) (7)
- [📊 Statusline 状态栏](#type-statusline) (37)
- [📚 合集](#type-collection) (21)
- [🛠 管理与生成工具](#type-tooling) (13)

## 什么样的仓库能上榜

1. 它提供或管理 Claude Code 的 hooks、subagents 或 statusline。不涉及这三样的一般插件、skill 不算。
2. 它是能安装或运行的软件,不是链接合集或空仓库。
3. 它有 README。没有 README 就没法评级。
4. 50 星及以上只看是否切题;50 星以下还要过 README 质量线(展示效果、一条命令上手、说清产出、文档完整),并且至少 5 星。

这些问题由决策模型逐个读 README 回答,不是人工挑选。卡在线上的仓库可能判到任一边,归错了请提 issue。

<a id="type-hooks"></a>
## 🪝 Hooks 钩子

[在在线页面打开这一类,按星数排序 →](https://agentskillshub.top/best/claude-code-hooks/?utm_source=github&utm_medium=awesome-list#type-hooks)

| 仓库 | 星数 | 做什么 | 安全评级 |
|---|---:|---|---|
| [shanraisshan/claude-code-hooks](https://github.com/shanraisshan/claude-code-hooks) | 552 | claude code hooks - adding voice on each hook | [SAFE](https://agentskillshub.top/skill/shanraisshan/claude-code-hooks/?utm_source=github&utm_medium=awesome-list) |
| [karanb192/claude-code-hooks](https://github.com/karanb192/claude-code-hooks) | 528 | 🪝 Claude Code hooks + an installable plugin marketplace: safety, cost, observability, productivity. | [SAFE](https://agentskillshub.top/skill/karanb192/claude-code-hooks/?utm_source=github&utm_medium=awesome-list) |
| [IyadhKhalfallah/clauditor](https://github.com/IyadhKhalfallah/clauditor) | 429 | Stop Claude Code from burning through your quota in 20 minutes. Auto-rotates oversized sessions and preserves context. | [SAFE](https://agentskillshub.top/skill/IyadhKhalfallah/clauditor/?utm_source=github&utm_medium=awesome-list) |
| [alexfazio/plankton](https://github.com/alexfazio/plankton) | 370 | Write-time code quality enforcement system for Claude Code. Every file edit triggers automated formatting and linting through fast Rust-based linters… | [SAFE](https://agentskillshub.top/skill/alexfazio/plankton/?utm_source=github&utm_medium=awesome-list) |
| [nesaminua/claude-code-lsp-enforcement-kit](https://github.com/nesaminua/claude-code-lsp-enforcement-kit) | 328 | Hooks that force Claude Code to use LSP instead of Grep for code navigation. Saves ~80% tokens | [SAFE](https://agentskillshub.top/skill/nesaminua/claude-code-lsp-enforcement-kit/?utm_source=github&utm_medium=awesome-list) |
| [ldayton/Dippy](https://github.com/ldayton/Dippy) | 243 | 🐤 Less permission fatigue, more momentum. Dippy knows what’s safe to run and keeps Claude on track when plans change. | [SAFE](https://agentskillshub.top/skill/ldayton/Dippy/?utm_source=github&utm_medium=awesome-list) |
| [cso1z/claude-ip-guard](https://github.com/cso1z/claude-ip-guard) | 196 | A Claude Code hook plugin for IP-based access control · 防 Claude 封号 · Claude IP 检测 · IP 地理位置拦截 · Claude 账号保护 | [SAFE](https://agentskillshub.top/skill/cso1z/claude-ip-guard/?utm_source=github&utm_medium=awesome-list) |
| [juanandresgs/claude-ctrl](https://github.com/juanandresgs/claude-ctrl) | 193 | DEPRECATED / UNMAINTAINED — historical reference only. Do not install or rely on this project. | [SAFE](https://agentskillshub.top/skill/juanandresgs/claude-ctrl/?utm_source=github&utm_medium=awesome-list) |
| [GowayLee/cchooks](https://github.com/GowayLee/cchooks) | 132 | A Python SDK for claude-code hooks | [CAUTION](https://agentskillshub.top/skill/GowayLee/cchooks/?utm_source=github&utm_medium=awesome-list) |
| [tzachbon/claude-model-router-hook](https://github.com/tzachbon/claude-model-router-hook) | 93 | Claude Code hooks that auto-switch model tier based on task complexity | [SAFE](https://agentskillshub.top/skill/tzachbon/claude-model-router-hook/?utm_source=github&utm_medium=awesome-list) |
| [Vvkmnn/claude-emporium](https://github.com/Vvkmnn/claude-emporium) | 82 | 🏛 [UNDER CONSTRUCTION] A (roman) claude plugin marketplace | [SAFE](https://agentskillshub.top/skill/Vvkmnn/claude-emporium/?utm_source=github&utm_medium=awesome-list) |
| [johnzfitch/claude-warden](https://github.com/johnzfitch/claude-warden) | 60 | Security hooks and monitoring for Claude Code — quiet overrides, SSRF protection, MCP compression, OTEL tracing | [SAFE](https://agentskillshub.top/skill/johnzfitch/claude-warden/?utm_source=github&utm_medium=awesome-list) |
| [0-to-1-Labs/claude-code-prompt-optimizer](https://github.com/0-to-1-Labs/claude-code-prompt-optimizer) | 47 | AI-powered prompt optimization hook for Claude Code. Transforms simple prompts into comprehensive, structured instructions using Claude Opus 4.6's ad… | [SAFE](https://agentskillshub.top/skill/0-to-1-Labs/claude-code-prompt-optimizer/?utm_source=github&utm_medium=awesome-list) |
| [SihyeonJeon/why-was-fable-banned](https://github.com/SihyeonJeon/why-was-fable-banned) | 45 | Fable-style spec + evidence gate for Claude Code + Codex. Makes Opus/Codex work under Fable-like discipline: blocks every edit until a deterministic… | [SAFE](https://agentskillshub.top/skill/SihyeonJeon/why-was-fable-banned/?utm_source=github&utm_medium=awesome-list) |
| [recomby-ai/promptly-prompt](https://github.com/recomby-ai/promptly-prompt) | 37 | Claude Code skill that forces AI to understand before executing. Three disciplines: cognition check, requirement understanding, method search. | [SAFE](https://agentskillshub.top/skill/recomby-ai/promptly-prompt/?utm_source=github&utm_medium=awesome-list) |
| [yeisonrestrepo/code-conductor](https://github.com/yeisonrestrepo/code-conductor) | 15 | A governance layer for Claude Code sessions: hooks that check an agent's commands before they run, a spec-first workflow, and project memory the next… | [SAFE](https://agentskillshub.top/skill/yeisonrestrepo/code-conductor/?utm_source=github&utm_medium=awesome-list) |
| [renefichtmueller/claude-code-hardened](https://github.com/renefichtmueller/claude-code-hardened) | 11 | 🛡️ Stop your AI from pushing secrets to GitHub. Security hooks, battle-tested rules, and a live validator for Claude Code. 5 hooks · 6 rules · 1 inst… | [SAFE](https://agentskillshub.top/skill/renefichtmueller/claude-code-hardened/?utm_source=github&utm_medium=awesome-list) |
| [shaominngqing/bark-claude-code-hook](https://github.com/shaominngqing/bark-claude-code-hook) | 8 | 🐕 AI-Powered Risk Assessment for Claude Code — 7-layer pipeline, native notifications, menu bar dashboard. One line install. | [SAFE](https://agentskillshub.top/skill/shaominngqing/bark-claude-code-hook/?utm_source=github&utm_medium=awesome-list) |
| [MohammedAtya/guardrail-forge](https://github.com/MohammedAtya/guardrail-forge) | 7 | Correct Claude once. It stays corrected. A Claude Code skill that turns corrections into tested, tamper-proof hook guardrails. | [CAUTION](https://agentskillshub.top/skill/MohammedAtya/guardrail-forge/?utm_source=github&utm_medium=awesome-list) |

<a id="type-subagents"></a>
## 🤖 Subagents 子代理

[在在线页面打开这一类,按星数排序 →](https://agentskillshub.top/best/claude-code-hooks/?utm_source=github&utm_medium=awesome-list#type-subagents)

| 仓库 | 星数 | 做什么 | 安全评级 |
|---|---:|---|---|
| [VoltAgent/awesome-claude-code-subagents](https://github.com/VoltAgent/awesome-claude-code-subagents) | 25.5k | A collection of 100+ specialized Claude Code subagents covering a wide range of development use cases | [SAFE](https://agentskillshub.top/skill/VoltAgent/awesome-claude-code-subagents/?utm_source=github&utm_medium=awesome-list) |
| [lst97/claude-code-sub-agents](https://github.com/lst97/claude-code-sub-agents) | 1.7k | Collection of specialized AI subagents for Claude Code for personal use (full-stack development). | [SAFE](https://agentskillshub.top/skill/lst97/claude-code-sub-agents/?utm_source=github&utm_medium=awesome-list) |
| [zhsama/claude-sub-agent](https://github.com/zhsama/claude-sub-agent) | 590 | AI-driven development workflow system built on Claude Code Sub-Agents. | [SAFE](https://agentskillshub.top/skill/zhsama/claude-sub-agent/?utm_source=github&utm_medium=awesome-list) |
| [NEWBIE0413/gemini-gpt-hybrid](https://github.com/NEWBIE0413/gemini-gpt-hybrid) | 153 | Multi-model orchestration subagents for Claude Code — delegates by task scope to Gemini's 1M-token context or GPT's fast iteration, then routes every… | [SAFE](https://agentskillshub.top/skill/NEWBIE0413/gemini-gpt-hybrid/?utm_source=github&utm_medium=awesome-list) |
| [undeadlist/claude-code-agents](https://github.com/undeadlist/claude-code-agents) | 149 | Claude Code Agents Prompt templates for Claude Code's subagent system. Run parallel code audits, automate fix cycles, get stuff reviewed. Built for t… | [SAFE](https://agentskillshub.top/skill/undeadlist/claude-code-agents/?utm_source=github&utm_medium=awesome-list) |
| [mischasigtermans/laravel-altitude](https://github.com/mischasigtermans/laravel-altitude) | 122 | Claude Code agents for the TALL stack, powered by Laravel Boost. | [SAFE](https://agentskillshub.top/skill/mischasigtermans/laravel-altitude/?utm_source=github&utm_medium=awesome-list) |
| [minetechnic2012-lang/claude-ops-inspector](https://github.com/minetechnic2012-lang/claude-ops-inspector) | 120 | Subagent Verification for Claude AI Code Networks 2026 | [SAFE](https://agentskillshub.top/skill/minetechnic2012-lang/claude-ops-inspector/?utm_source=github&utm_medium=awesome-list) |

<a id="type-statusline"></a>
## 📊 Statusline 状态栏

[在在线页面打开这一类,按星数排序 →](https://agentskillshub.top/best/claude-code-hooks/?utm_source=github&utm_medium=awesome-list#type-statusline)

| 仓库 | 星数 | 做什么 | 安全评级 |
|---|---:|---|---|
| [jarrodwatts/claude-hud](https://github.com/jarrodwatts/claude-hud) | 28.3k | A Claude Code plugin that shows what's happening - context usage, active tools, running agents, and todo progress | [SAFE](https://agentskillshub.top/skill/jarrodwatts/claude-hud/?utm_source=github&utm_medium=awesome-list) |
| [sirmalloc/ccstatusline](https://github.com/sirmalloc/ccstatusline) | 13.2k | 🚀 Beautiful highly customizable statusline for Claude Code CLI with powerline support, themes, and more. | [SAFE](https://agentskillshub.top/skill/sirmalloc/ccstatusline/?utm_source=github&utm_medium=awesome-list) |
| [Owloops/claude-powerline](https://github.com/Owloops/claude-powerline) | 1.2k | Beautiful vim-style powerline for Claude Code | [SAFE](https://agentskillshub.top/skill/Owloops/claude-powerline/?utm_source=github&utm_medium=awesome-list) |
| [GaoSSR/best-claude-hud](https://github.com/GaoSSR/best-claude-hud) | 1.1k | Minimal Claude Code statusline HUD powered by Rust. | [SAFE](https://agentskillshub.top/skill/GaoSSR/best-claude-hud/?utm_source=github&utm_medium=awesome-list) |
| [daniel3303/ClaudeCodeStatusLine](https://github.com/daniel3303/ClaudeCodeStatusLine) | 611 | Custom status line for Claude Code showing model, tokens, rate limits, and git info in real-time | [SAFE](https://agentskillshub.top/skill/daniel3303/ClaudeCodeStatusLine/?utm_source=github&utm_medium=awesome-list) |
| [Nanako0129/coralline](https://github.com/Nanako0129/coralline) | 547 | 🪸 Powerlevel10k-inspired statusline for Claude Code — paste one prompt and your AI interviews you, then installs it | [SAFE](https://agentskillshub.top/skill/Nanako0129/coralline/?utm_source=github&utm_medium=awesome-list) |
| [rz1989s/claude-code-statusline](https://github.com/rz1989s/claude-code-statusline) | 480 | Transform your Claude Code terminal with atomic precision statusline. Features flexible layouts, real-time cost tracking, MCP monitoring, prayer time… | [SAFE](https://agentskillshub.top/skill/rz1989s/claude-code-statusline/?utm_source=github&utm_medium=awesome-list) |
| [stephenleo/cship](https://github.com/stephenleo/cship) | 424 | ⚡ A beautiful, fully customizable statusline for Claude Code - Starship-style TOML config, themeable colours, Nerd Font glyphs, and tunable cost/cont… | [SAFE](https://agentskillshub.top/skill/stephenleo/cship/?utm_source=github&utm_medium=awesome-list) |
| [leeguooooo/claude-code-usage-bar](https://github.com/leeguooooo/claude-code-usage-bar) | 376 | Lightweight Claude Code statusLine: 5h/7d rate-limit usage, reset countdowns, model + context window, prompt-cache age — one line, 3 styles × 9 theme… | [SAFE](https://agentskillshub.top/skill/leeguooooo/claude-code-usage-bar/?utm_source=github&utm_medium=awesome-list) |
| [NYCU-Chung/cc-statusline](https://github.com/NYCU-Chung/cc-statusline) | 263 | A comprehensive statusline dashboard for Claude Code — session info, quota bars, agent tracker, MCP health, message history, and more. | [SAFE](https://agentskillshub.top/skill/NYCU-Chung/cc-statusline/?utm_source=github&utm_medium=awesome-list) |
| [Wangnov/claude-code-statusline-pro](https://github.com/Wangnov/claude-code-statusline-pro) | 237 | Pro statusline for Claude Code \| 功能强大的 Claude Code 状态栏 | [SAFE](https://agentskillshub.top/skill/Wangnov/claude-code-statusline-pro/?utm_source=github&utm_medium=awesome-list) |
| [Astro-Han/claude-lens](https://github.com/Astro-Han/claude-lens) | 234 | Claude Code statusline and rate limit tracker with pace-aware quota monitoring. Pure Bash + jq, single file. | [SAFE](https://agentskillshub.top/skill/Astro-Han/claude-lens/?utm_source=github&utm_medium=awesome-list) |
| [Astro-Han/claude-pace](https://github.com/Astro-Han/claude-pace) | 234 | Claude Code statusline and rate limit tracker with pace-aware quota monitoring. Pure Bash + jq, single file. | [SAFE](https://agentskillshub.top/skill/Astro-Han/claude-pace/?utm_source=github&utm_medium=awesome-list) |
| [AwesomeJun/CC-statusline](https://github.com/AwesomeJun/CC-statusline) | 191 | An aesthetic statusline for Claude Code by awesomejun | [SAFE](https://agentskillshub.top/skill/AwesomeJun/CC-statusline/?utm_source=github&utm_medium=awesome-list) |
| [AwesomeJun/awesome-claude-plugins](https://github.com/AwesomeJun/awesome-claude-plugins) | 191 | An aesthetic statusline for Claude Code by awesomejun | [SAFE](https://agentskillshub.top/skill/AwesomeJun/awesome-claude-plugins/?utm_source=github&utm_medium=awesome-list) |
| [AwesomeZun/CC-statusline](https://github.com/AwesomeZun/CC-statusline) | 191 | An aesthetic statusline for Claude Code by awesomejun | [SAFE](https://agentskillshub.top/skill/AwesomeZun/CC-statusline/?utm_source=github&utm_medium=awesome-list) |
| [ilia-pluzhnikov/claude-code-statusline](https://github.com/ilia-pluzhnikov/claude-code-statusline) | 117 | A feature-rich, dependency-free Node.js statusline for Claude Code with model, task, git state, context window, rate limits, and Anthropic peak-hours… | [SAFE](https://agentskillshub.top/skill/ilia-pluzhnikov/claude-code-statusline/?utm_source=github&utm_medium=awesome-list) |
| [aiedwardyi/claude-usage-monitor](https://github.com/aiedwardyi/claude-usage-monitor) | 56 | Claude Code statusline plugin for 5-hour/7-day quota, context usage, tokens, and reset countdowns in your terminal. | [SAFE](https://agentskillshub.top/skill/aiedwardyi/claude-usage-monitor/?utm_source=github&utm_medium=awesome-list) |
| [fredrikaverpil/claudeline](https://github.com/fredrikaverpil/claudeline) | 55 | Minimalistic Go statusline for Claude Code | [SAFE](https://agentskillshub.top/skill/fredrikaverpil/claudeline/?utm_source=github&utm_medium=awesome-list) |
| [glauberlima/claude-code-statusline](https://github.com/glauberlima/claude-code-statusline) | 50 | Supercharge your Claude Code CLI experience with a powerful statusline that displays key session metrics (Git state, context usage, model info and co… | [SAFE](https://agentskillshub.top/skill/glauberlima/claude-code-statusline/?utm_source=github&utm_medium=awesome-list) |
| [canack/claude-usage-line](https://github.com/canack/claude-usage-line) | 40 | Custom status line for Claude Code — rate limits, git branch, cost, diff stats | [SAFE](https://agentskillshub.top/skill/canack/claude-usage-line/?utm_source=github&utm_medium=awesome-list) |
| [hagan/claudia-statusline](https://github.com/hagan/claudia-statusline) | 36 | Rust statusline for Claude Code — hook-based compaction detection, SQLite session persistence, multi-console-safe session tracking. Listed in Awesome… | [SAFE](https://agentskillshub.top/skill/hagan/claudia-statusline/?utm_source=github&utm_medium=awesome-list) |
| [deluo/glm-quota-line](https://github.com/deluo/glm-quota-line) | 33 | A lightweight CLI for showing GLM Coding Plan quota in the Claude Code status line. | [SAFE](https://agentskillshub.top/skill/deluo/glm-quota-line/?utm_source=github&utm_medium=awesome-list) |
| [Ventuss-OvO/cc-costline](https://github.com/Ventuss-OvO/cc-costline) | 28 | Enhanced statusline for Claude Code — see your 7d/30d spend at a glance | [SAFE](https://agentskillshub.top/skill/Ventuss-OvO/cc-costline/?utm_source=github&utm_medium=awesome-list) |
| [vbcherepanov/claude-statusbar](https://github.com/vbcherepanov/claude-statusbar) | 28 | 🖥️ A rich, two-line status bar for Claude Code CLI — real-time model, context usage, tokens, cost, duration, git branch, cache stats and more in your… | [SAFE](https://agentskillshub.top/skill/vbcherepanov/claude-statusbar/?utm_source=github&utm_medium=awesome-list) |
| [hell0github/claude-statusline](https://github.com/hell0github/claude-statusline) | 27 | A Lightweight Statusline plugin for Claude Code CLI to track context, cost usage and session reset time | [SAFE](https://agentskillshub.top/skill/hell0github/claude-statusline/?utm_source=github&utm_medium=awesome-list) |
| [bartleby/claude-statusline](https://github.com/bartleby/claude-statusline) | 26 | Custom statusline for Claude Code CLI with 18 themes, rate limits, context tracking and ASCII Claude avatar | [SAFE](https://agentskillshub.top/skill/bartleby/claude-statusline/?utm_source=github&utm_medium=awesome-list) |
| [felipeelias/claude-statusline](https://github.com/felipeelias/claude-statusline) | 22 | Configurable status line for Claude Code | [SAFE](https://agentskillshub.top/skill/felipeelias/claude-statusline/?utm_source=github&utm_medium=awesome-list) |
| [briansmith80/claude-code-status-bar](https://github.com/briansmith80/claude-code-status-bar) | 18 | Configurable status bar for Claude Code: usage limits with pacing markers, context window, git state, live activity, session cost, and 8 colour theme… | [SAFE](https://agentskillshub.top/skill/briansmith80/claude-code-status-bar/?utm_source=github&utm_medium=awesome-list) |
| [blushdas/claude-code-statusline](https://github.com/blushdas/claude-code-statusline) | 17 | Real-time Claude Code statusline with cost tracking and Obsidian logging | [SAFE](https://agentskillshub.top/skill/blushdas/claude-code-statusline/?utm_source=github&utm_medium=awesome-list) |
| [webkubor/claude-usage-statusline](https://github.com/webkubor/claude-usage-statusline) | 17 | Claude Code 状态栏：会话花费、上下文占用、5h/7d 限额，并区分订阅制与按量付费、预警无兜底硬停。单文件 Python，零依赖零配置。 | [SAFE](https://agentskillshub.top/skill/webkubor/claude-usage-statusline/?utm_source=github&utm_medium=awesome-list) |
| [ssenart/oh-my-claude](https://github.com/ssenart/oh-my-claude) | 16 | A fully customized status line for Claude Code | [CAUTION](https://agentskillshub.top/skill/ssenart/oh-my-claude/?utm_source=github&utm_medium=awesome-list) |
| [zander-zyx/claude-mini-hud](https://github.com/zander-zyx/claude-mini-hud) | 10 | 对标 claude-hud 核心功能，控制在 7 行以内更轻量。内置 13 个国产大模型平台用量查询 (智谱 GLM / MiniMax / DeepSeek / Kimi / StepFun / SiliconFlow 等)，第三方代理用户也能实时看到额度消耗。 | [SAFE](https://agentskillshub.top/skill/zander-zyx/claude-mini-hud/?utm_source=github&utm_medium=awesome-list) |
| [moon1ite/claude-statusline](https://github.com/moon1ite/claude-statusline) | 9 | Real-time statusline for Claude Code showing tools, agents, and todos | [SAFE](https://agentskillshub.top/skill/moon1ite/claude-statusline/?utm_source=github&utm_medium=awesome-list) |
| [moonD4rk/ccstatus](https://github.com/moonD4rk/ccstatus) | 8 | Customizable status line formatter for Claude Code CLI, written in Go | [SAFE](https://agentskillshub.top/skill/moonD4rk/ccstatus/?utm_source=github&utm_medium=awesome-list) |
| [aleksander-dytko/claude-code-statusline](https://github.com/aleksander-dytko/claude-code-statusline) | 7 | Enhanced status line for Claude Code - model, git, context window, session cost, and live usage limits in one bash script | [CAUTION](https://agentskillshub.top/skill/aleksander-dytko/claude-code-statusline/?utm_source=github&utm_medium=awesome-list) |
| [bart-turczynski/cc-cream](https://github.com/bart-turczynski/cc-cream) | 5 | Read-only mirror of gitlab.com/bart-turczynski/cc-cream. See cache health, context fill, token burn, rate limits, and peak hours in Claude Code CLI.… | [SAFE](https://agentskillshub.top/skill/bart-turczynski/cc-cream/?utm_source=github&utm_medium=awesome-list) |

<a id="type-collection"></a>
## 📚 合集

[在在线页面打开这一类,按星数排序 →](https://agentskillshub.top/best/claude-code-hooks/?utm_source=github&utm_medium=awesome-list#type-collection)

| 仓库 | 星数 | 做什么 | 安全评级 |
|---|---:|---|---|
| [diet103/claude-code-infrastructure-showcase](https://github.com/diet103/claude-code-infrastructure-showcase) | 10.0k | Examples of my Claude Code infrastructure with skill auto-activation, hooks, and agents | [SAFE](https://agentskillshub.top/skill/diet103/claude-code-infrastructure-showcase/?utm_source=github&utm_medium=awesome-list) |
| [WorldFlowAI/everything-claude-code](https://github.com/WorldFlowAI/everything-claude-code) | 3.9k | Claude Code toolkit - agents, commands, skills, rules, and hooks for productive AI-assisted development | [SAFE](https://agentskillshub.top/skill/WorldFlowAI/everything-claude-code/?utm_source=github&utm_medium=awesome-list) |
| [parcadei/Continuous-Claude-v3](https://github.com/parcadei/Continuous-Claude-v3) | 3.9k | Context management for Claude Code. Hooks maintain state via ledgers and handoffs. MCP execution without context pollution. Agent orchestration with… | [SAFE](https://agentskillshub.top/skill/parcadei/Continuous-Claude-v3/?utm_source=github&utm_medium=awesome-list) |
| [0xSteph/pentest-ai-agents](https://github.com/0xSteph/pentest-ai-agents) | 2.3k | Turn Claude Code into your offensive security research assistant. Specialized AI subagents for authorized penetration testing plan engagements, analy… | [SAFE](https://agentskillshub.top/skill/0xSteph/pentest-ai-agents/?utm_source=github&utm_medium=awesome-list) |
| [sangrokjung/claude-forge](https://github.com/sangrokjung/claude-forge) | 845 | oh-my-zsh for Claude Code — 16 agents, 35 commands, 32 skills, 21 safety hooks in one install. v4.0 adds an adversarial review loop: a second agent t… | [SAFE](https://agentskillshub.top/skill/sangrokjung/claude-forge/?utm_source=github&utm_medium=awesome-list) |
| [ruvnet/agentic-flow](https://github.com/ruvnet/agentic-flow) | 816 | Easily switch between alternative low-cost AI models in Claude Code/Agent SDK. For those comfortable using Claude agents and commands, it lets you ta… | [SAFE](https://agentskillshub.top/skill/ruvnet/agentic-flow/?utm_source=github&utm_medium=awesome-list) |
| [vanzan01/claude-code-sub-agent-collective](https://github.com/vanzan01/claude-code-sub-agent-collective) | 521 | 🧠 Context Engineering Research - Not just another agent collection, but using research and context engineering to function as a collective. Hub-and-s… | [SAFE](https://agentskillshub.top/skill/vanzan01/claude-code-sub-agent-collective/?utm_source=github&utm_medium=awesome-list) |
| [NYCU-Chung/my-claude-devteam](https://github.com/NYCU-Chung/my-claude-devteam) | 269 | An engineering team in a box for Claude Code — 12 specialized agents, 15 automation hooks, and the P7/P9/P10 methodology. | [SAFE](https://agentskillshub.top/skill/NYCU-Chung/my-claude-devteam/?utm_source=github&utm_medium=awesome-list) |
| [sd0xdev/sd0x-dev-flow](https://github.com/sd0xdev/sd0x-dev-flow) | 191 | The harness layer for Claude Code — a reference implementation of harness engineering with hook-enforced dual review, state-machine gates that surviv… | [SAFE](https://agentskillshub.top/skill/sd0xdev/sd0x-dev-flow/?utm_source=github&utm_medium=awesome-list) |
| [sd0xdev/sd0x-harness](https://github.com/sd0xdev/sd0x-harness) | 191 | The harness layer for Claude Code — a reference implementation of harness engineering with hook-enforced dual review, state-machine gates that surviv… | [SAFE](https://agentskillshub.top/skill/sd0xdev/sd0x-harness/?utm_source=github&utm_medium=awesome-list) |
| [KimYx0207/Kim_Service](https://github.com/KimYx0207/Kim_Service) | 172 | 面向 Claude Code、Codex 等 AI 编码助手的 Hook 与 Agent Skill 开源合集。 | [SAFE](https://agentskillshub.top/skill/KimYx0207/Kim_Service/?utm_source=github&utm_medium=awesome-list) |
| [ayush-that/sub-agents.directory](https://github.com/ayush-that/sub-agents.directory) | 148 | 🐒 Sub-Agents Directory is a curated collection of 100+ sub-agent prompts and MCP servers for Claude Code. | [SAFE](https://agentskillshub.top/skill/ayush-that/sub-agents.directory/?utm_source=github&utm_medium=awesome-list) |
| [Bande-a-Bonnot/Boucle-framework](https://github.com/Bande-a-Bonnot/Boucle-framework) | 124 | Autonomous agent framework with structured memory, safety hooks, and loop management. Built by the agent that runs on it. | [SAFE](https://agentskillshub.top/skill/Bande-a-Bonnot/Boucle-framework/?utm_source=github&utm_medium=awesome-list) |
| [solanabr/ai-kit](https://github.com/solanabr/ai-kit) | 107 | Claude Code / Codex / AI configs for the expert Solana builder. CLAUDE.md, agents, commands, hooks, rules, skills and settings across Web, Anchor, Pi… | [SAFE](https://agentskillshub.top/skill/solanabr/ai-kit/?utm_source=github&utm_medium=awesome-list) |
| [solanabr/solana-ai-kit](https://github.com/solanabr/solana-ai-kit) | 107 | Claude Code / Codex / AI configs for the expert Solana builder. CLAUDE.md, agents, commands, hooks, rules, skills and settings across Web, Anchor, Pi… | [SAFE](https://agentskillshub.top/skill/solanabr/solana-ai-kit/?utm_source=github&utm_medium=awesome-list) |
| [solanabr/solana-claude](https://github.com/solanabr/solana-claude) | 107 | Claude Code / Codex / AI configs for the expert Solana builder. CLAUDE.md, agents, commands, hooks, rules, skills and settings across Web, Anchor, Pi… | [SAFE](https://agentskillshub.top/skill/solanabr/solana-claude/?utm_source=github&utm_medium=awesome-list) |
| [tony/claude-code-riper-5](https://github.com/tony/claude-code-riper-5) | 94 | Claude Code (Sub-agent, Custom Commands) for RIPER-5 | [SAFE](https://agentskillshub.top/skill/tony/claude-code-riper-5/?utm_source=github&utm_medium=awesome-list) |
| [arpitnath/claude-capsule-kit](https://github.com/arpitnath/claude-capsule-kit) | 93 | A toolkit that makes Claude Code better at engineering — session memory, dependency analysis, large file navigation, 18 specialist agents, and crew t… | [SAFE](https://agentskillshub.top/skill/arpitnath/claude-capsule-kit/?utm_source=github&utm_medium=awesome-list) |
| [ChanMeng666/claude-code-audio-hooks](https://github.com/ChanMeng666/claude-code-audio-hooks) | 87 | 【Every star you give feeds a hungry developer's motivation!⭐️】 🔊 echook — AI-operated audio notifications for Claude Code, Cursor IDE & Codex CLI — 2… | [SAFE](https://agentskillshub.top/skill/ChanMeng666/claude-code-audio-hooks/?utm_source=github&utm_medium=awesome-list) |
| [0ldh/claude-code-agents-orchestra](https://github.com/0ldh/claude-code-agents-orchestra) | 84 | Turn Claude Code into a coordinated team of 40+ specialized AI agents that work together like a world-class engineering organization. | [SAFE](https://agentskillshub.top/skill/0ldh/claude-code-agents-orchestra/?utm_source=github&utm_medium=awesome-list) |
| [Filip-Podstavec/claude-leverage](https://github.com/Filip-Podstavec/claude-leverage) | 68 | Make any repo AI-first - write sustainable code from the start, or refactor a legacy codebase to prepare it for agent-driven development.Building blo… | [SAFE](https://agentskillshub.top/skill/Filip-Podstavec/claude-leverage/?utm_source=github&utm_medium=awesome-list) |

<a id="type-tooling"></a>
## 🛠 管理与生成工具

[在在线页面打开这一类,按星数排序 →](https://agentskillshub.top/best/claude-code-hooks/?utm_source=github&utm_medium=awesome-list#type-tooling)

| 仓库 | 星数 | 做什么 | 安全评级 |
|---|---:|---|---|
| [Ido-Levi/claude-code-tamagotchi](https://github.com/Ido-Levi/claude-code-tamagotchi) | 433 | Real-time behavioral enforcement for Claude Code. Monitors AI actions, detects violations, and interrupts misbehavior. Also has a cute pet. | [SAFE](https://agentskillshub.top/skill/Ido-Levi/claude-code-tamagotchi/?utm_source=github&utm_medium=awesome-list) |
| [leonardsellem/codex-subagents-mcp](https://github.com/leonardsellem/codex-subagents-mcp) | 161 | Claude-style sub-agents (reviewer, debugger, security) for Codex CLI via a tiny MCP server. Each call spins up a clean context in a temp workdir, inj… | [SAFE](https://agentskillshub.top/skill/leonardsellem/codex-subagents-mcp/?utm_source=github&utm_medium=awesome-list) |
| [martinemde/starship-claude](https://github.com/martinemde/starship-claude) | 150 | ✳ claude statusline via starship | [SAFE](https://agentskillshub.top/skill/martinemde/starship-claude/?utm_source=github&utm_medium=awesome-list) |
| [ghy196830-del/agent-watch-approve](https://github.com/ghy196830-del/agent-watch-approve) | 120 | ⌚ 在 Apple Watch 上批准 Claude Code / Codex 的危险操作,任务完成自动提醒 \| Approve your AI coding agent's risky actions from your Apple Watch, get buzzed when tasks f… | [SAFE](https://agentskillshub.top/skill/ghy196830-del/agent-watch-approve/?utm_source=github&utm_medium=awesome-list) |
| [cozytab/fable5-mode](https://github.com/cozytab/fable5-mode) | 106 | Make Opus 4.8 (or any Claude model) work like Claude Fable 5 — a Claude Code skill + guard hooks (plan gate, model ceiling, per-task enforcement) for… | [SAFE](https://agentskillshub.top/skill/cozytab/fable5-mode/?utm_source=github&utm_medium=awesome-list) |
| [qkal/Canny](https://github.com/qkal/Canny) | 105 | Stops AI coding agents from claiming work is done without evidence. Deterministic hooks decide, TypeSafe's Jev advises. Append-only ledger, zero runt… | [SAFE](https://agentskillshub.top/skill/qkal/Canny/?utm_source=github&utm_medium=awesome-list) |
| [abhisekjha/pith](https://github.com/abhisekjha/pith) | 98 | Pith is the hook that makes Claude Code sessions last 3x longer. | [SAFE](https://agentskillshub.top/skill/abhisekjha/pith/?utm_source=github&utm_medium=awesome-list) |
| [shinpr/sub-agents-mcp](https://github.com/shinpr/sub-agents-mcp) | 98 | Define task-specific AI sub-agents in Markdown for any MCP-compatible tool. | [SAFE](https://agentskillshub.top/skill/shinpr/sub-agents-mcp/?utm_source=github&utm_medium=awesome-list) |
| [Evolutionairy-AI/MINDLAS](https://github.com/Evolutionairy-AI/MINDLAS) | 31 | Mindlas catches your coding agent drifting before the bad code lands. Real-time tracking and correction for context rot, unverified done claims, patc… | [SAFE](https://agentskillshub.top/skill/Evolutionairy-AI/MINDLAS/?utm_source=github&utm_medium=awesome-list) |
| [safe-agentic-world/nomos](https://github.com/safe-agentic-world/nomos) | 19 | Deny-wins policy hook for Claude Code and Codex. Checks every shell, file, and fetch call against rules you keep in Git, holds under --dangerously-sk… | [SAFE](https://agentskillshub.top/skill/safe-agentic-world/nomos/?utm_source=github&utm_medium=awesome-list) |
| [lefProg/claudial](https://github.com/lefProg/claudial) | 10 | ⚽ Live football for your teams in the status bar of Claude Code, Cursor, VS Code and Antigravity, plus a terminal dashboard with goal & red-card take… | [SAFE](https://agentskillshub.top/skill/lefProg/claudial/?utm_source=github&utm_medium=awesome-list) |
| [sravan27/context-os](https://github.com/sravan27/context-os) | 10 | Claude Code's first turn opens the right file instead of grepping — a local static-analysis repo graph injected before turn 1 (no embeddings/server,… | [SAFE](https://agentskillshub.top/skill/sravan27/context-os/?utm_source=github&utm_medium=awesome-list) |
| [jig21nesh/model-switcher](https://github.com/jig21nesh/model-switcher) | 5 | Per-prompt model routing and offline cost tracking for Claude Code — keep simple prompts cheap, delegate complex work to a stronger model. | [SAFE](https://agentskillshub.top/skill/jig21nesh/model-switcher/?utm_source=github&utm_medium=awesome-list) |

**安全评级**是 Agent Skills Hub 对仓库 README 和安装步骤的评级。*待评级*表示目录还没评到它。

预览图是各项目 README 里图片的缩小副本,只收录采用宽松许可证的项目,版权归原作者所有。来源和许可证见 [assets/previews/NOTICE.md](assets/previews/NOTICE.md)。如需移除请提 issue。

## 相关合集

- [zhuyansen/awesome-claude-video-skills](https://github.com/zhuyansen/awesome-claude-video-skills), [zhuyansen/awesome-codex-ppt-skills](https://github.com/zhuyansen/awesome-codex-ppt-skills) —— 同样做法的合集。

## 推荐仓库

提一个 issue 附上 GitHub 链接。它会走和每个条目一样的评审;决定上不上榜的是上面的规则,不是星数。

---

机器可读版本:[`data/skills.json`](data/skills.json)。生成于 2026-10-03。
