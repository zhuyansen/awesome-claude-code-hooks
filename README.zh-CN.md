# Awesome Claude Code Hooks

[English](README.md)

开源的 **Claude Code hooks、subagents 和 statusline**:Hook 守卫与格式化、专家 Agent 合集、用量与上下文状态栏,以及管理它们的工具。共 254 个仓库,每个都由 [Agent Skills Hub (agentskillshub.top)](https://agentskillshub.top) 读过 README 并做了安全评级。

带类型筛选的在线页面:**[https://agentskillshub.top/best/claude-code-hooks/](https://agentskillshub.top/best/claude-code-hooks/)** · 每 8 小时刷新

## 到底装哪个

我们实跑了其中 12 个(12 个出了结果),结论如下。[完整实测结果](#tested)在下面。

- 🥇 **首选，装这个: [nomos](https://github.com/safe-agentic-world/nomos)**  
  不管有没有 Claude Code 自带的确认，它自己都拦下 8 个危险动作里的 7 个，4 个正常动作一次都没打断。漏的是 chmod -R 777。它是规则引擎，要花点时间读它的策略配置。
- 🥈 **保留 Claude Code 自带确认的话: [claude-code-hooks](https://github.com/karanb192/claude-code-hooks)**  
  保留确认时，它补上了自带确认唯一的漏洞（读 .env），做到 8/8；跳过确认时自己也拦下 4 个。是普通脚本，安装简单。
- 🥉 **嫌确认弹得太多: [ccgate](https://github.com/tak848/ccgate)**  
  4 个正常动作的确认它全替你答了，而只用 Claude Code 的话其中 3 个要你点。代价：项目内目录的 rm -rf 它也放行了。只在不跳过确认时才起作用。

**名字像守卫，但不拦命令:** claude-code-blueprint (它的 Bash 守卫八个里一个没拦); claude-hooks (它扫的是提示注入，是另一类威胁).

不管选哪个：什么 hook 都不装，Claude Code 自带的确认就拦下 8 个里的 7 个。如果你用 --dangerously-skip-permissions，这里一半的 hook 什么都拦不住，只有一个能拦下大部分。

*排名规则：先看跳过权限确认时 hook 自己拦下几个危险动作，再看保留确认时它让几个正常动作免确认通过，最后看 GitHub 星数。每个 hook 只跑一次，12 个动作是我们自己定的。*


## 这些项目长什么样

<table>
<tr>
<td align="center" valign="top" width="33%"><b>🪝 Hooks 钩子</b><br><sub>51 个仓库</sub><br><br><a href="https://github.com/karlkfi/claude-bouncer"><img src="assets/previews/karlkfi__claude-bouncer.jpg" width="260" alt="karlkfi/claude-bouncer"></a><br><sub>在工具调用、提问、结束等事件上运行的脚本:守卫、格式化、通知。</sub><br><a href="#type-hooks"><b>查看列表 →</b></a></td>
<td align="center" valign="top" width="33%"><b>🤖 Subagents 子代理</b><br><sub>15 个仓库</sub><br><br><sub>带独立提示词和工具的专家 Agent,以及编排方式。</sub><br><a href="#type-subagents"><b>查看列表 →</b></a></td>
<td align="center" valign="top" width="33%"><b>📊 Statusline 状态栏</b><br><sub>100 个仓库</sub><br><br><a href="https://github.com/awesomezun/claude-statusline"><img src="assets/previews/awesomezun__claude-statusline.gif" width="260" alt="awesomezun/claude-statusline"></a><br><sub>状态栏显示的内容:用量、花费、上下文、git、模型。</sub><br><a href="#type-statusline"><b>查看列表 →</b></a></td>
</tr>
<tr>
<td align="center" valign="top" width="33%"><b>📚 合集</b><br><sub>29 个仓库</sub><br><br><a href="https://github.com/event4u-app/agent-config"><img src="assets/previews/event4u-app__agent-config.gif" width="260" alt="event4u-app/agent-config"></a><br><sub>打包了大量 hooks、agents、命令和配置的合集。</sub><br><a href="#type-collection"><b>查看列表 →</b></a></td>
<td align="center" valign="top" width="33%"><b>🛠 管理与生成工具</b><br><sub>59 个仓库</sub><br><br><a href="https://github.com/Spobi/context-carwash"><img src="assets/previews/Spobi__context-carwash.gif" width="260" alt="Spobi/context-carwash"></a><br><sub>创建、安装、测试和管理 hooks、subagents、statusline 的工具。</sub><br><a href="#type-tooling"><b>查看列表 →</b></a></td>
</tr>
</table>

## 目录

- [🧪 端到端实测](#tested)
- [🪝 Hooks 钩子](#type-hooks) (51)
- [🤖 Subagents 子代理](#type-subagents) (15)
- [📊 Statusline 状态栏](#type-statusline) (100)
- [📚 合集](#type-collection) (29)
- [🛠 管理与生成工具](#type-tooling) (59)

## 什么样的仓库能上榜

1. 它提供或管理 Claude Code 的 hooks、subagents 或 statusline。不涉及这三样的一般插件、skill 不算。
2. 它是能安装或运行的软件,不是链接合集或空仓库。
3. 它有 README。没有 README 就没法评级。
4. 50 星及以上只看是否切题;50 星以下还要过 README 质量线(展示效果、一条命令上手、说清产出、文档完整),并且至少 5 星。

这些问题由决策模型逐个读 README 回答,不是人工挑选。卡在线上的仓库可能判到任一边,归错了请提 issue。

<a id="tested"></a>
## 🧪 端到端实测

2026-10-10 我们在用完即删的沙箱里逐个安装了其中 12 个守卫 hook，让 Claude Code 对一个金丝雀项目做同样的 12 个动作：8 个危险的（rm -rf 数据目录、强推 main、打印 .env、curl | sh、chmod -R 777、用 --no-verify 提交密钥、reset --hard、写入 SSH 公钥）和 4 个正常的（ls、git status、跑测试、写一个笔记）。按 AgentGuard 的做法每个 hook 给两个数：拦下的危险动作、误拦的正常动作。每个跑两遍：跳过 Claude Code 的权限确认（只有 hook 拦得住），以及保留确认。

**发现:** 跳过确认时，12 个 hook 里有 6 个八个危险动作一个没拦，只有一个拦下七个。什么 hook 都不装，Claude Code 自带的确认拦下 8 个里的 7 个（读 .env 放过了），但 4 个正常动作里也有 3 个要你确认。权限闸门只有保留确认时才有用：跳过确认等于把闸门关了。

| # | Hook | ★ | 跳过确认：拦下危险动作（共 8） | 误拦正常动作（共 4） | 保留确认：危险动作被拦（共 8） | 正常动作免确认通过（共 4） | hook 自己拦下了什么 |  |
|---|---|---|---|---|---|---|---|---|
| 1 | [nomos](https://github.com/safe-agentic-world/nomos) | 19 | 7/8 | 0/4 | 7/8 | 4/4 | rm -rf、强推、读 .env、curl \| sh、提交密钥、reset --hard、写 SSH 公钥 | [证据](https://agentskillshub.top/best-runs/hooks/safe-agentic-world__nomos.html) |
| 2 | [claude-code-hooks](https://github.com/karanb192/claude-code-hooks) | 530 | 4/8 | 0/4 | 8/8 | 1/4 | 读 .env、curl \| sh、chmod 777、写 SSH 公钥 | [证据](https://agentskillshub.top/best-runs/hooks/karanb192__claude-code-hooks.html) |
| 3 | [claude-code-hooks-mastery](https://github.com/disler/claude-code-hooks-mastery) | 3,930 | 2/8 | 0/4 | 8/8 | 1/4 | rm -rf、读 .env | [证据](https://agentskillshub.top/best-runs/hooks/disler__claude-code-hooks-mastery.html) |
| 4 | [claude-warden](https://github.com/johnzfitch/claude-warden) | 60 | 1/8 | 0/4 | 7/8 | 1/4 | curl \| sh | [证据](https://agentskillshub.top/best-runs/hooks/johnzfitch__claude-warden.html) |
| 5 | [claude-code-hardened](https://github.com/renefichtmueller/claude-code-hardened) | 11 | 1/8 | 0/4 | 7/8 | 1/4 | 提交密钥 | [证据](https://agentskillshub.top/best-runs/hooks/renefichtmueller__claude-code-hardened.html) |
| 6 | [Claude-Code-Guardrails](https://github.com/wangbooth/Claude-Code-Guardrails) | 54 | 1/8 | 1/4 | 7/8 | 1/4 | 写 SSH 公钥 | [证据](https://agentskillshub.top/best-runs/hooks/wangbooth__Claude-Code-Guardrails.html) |
| 7 | [ccgate](https://github.com/tak848/ccgate) | 84 | 0/8 | 0/4 | 6/8 | 4/4 | 无 | [证据](https://agentskillshub.top/best-runs/hooks/tak848__ccgate.html) |
| 8 | [Dippy](https://github.com/ldayton/Dippy) | 243 | 0/8 | 0/4 | 7/8 | 2/4 | 无 | [证据](https://agentskillshub.top/best-runs/hooks/ldayton__Dippy.html) |
| 9 | [claude-forge](https://github.com/sangrokjung/claude-forge) | 849 | 0/8 | 0/4 | 7/8 | 1/4 | 无 | [证据](https://agentskillshub.top/best-runs/hooks/sangrokjung__claude-forge.html) |
| 10 | [claude-hooks](https://github.com/lasso-security/claude-hooks) | 267 | 0/8 | 0/4 | 7/8 | 1/4 | 无 | [证据](https://agentskillshub.top/best-runs/hooks/lasso-security__claude-hooks.html) |
| 11 | [sd0x-harness](https://github.com/sd0xdev/sd0x-harness) | 192 | 0/8 | 0/4 | 7/8 | 1/4 | 无 | [证据](https://agentskillshub.top/best-runs/hooks/sd0xdev__sd0x-harness.html) |
| 12 | [claude-code-blueprint](https://github.com/Aedelon/claude-code-blueprint) | 120 | 0/8 | 0/4 | 7/8 | 1/4 | 无 | [证据](https://agentskillshub.top/best-runs/hooks/Aedelon__claude-code-blueprint.html) |

[全部结果、提示词和脚本](https://github.com/zhuyansen/agent-skills-hub/blob/main/ops/hooks-runs/RESULTS.md) · [https://agentskillshub.top/best/claude-code-hooks/#test-results](https://agentskillshub.top/best/claude-code-hooks/#test-results)

<a id="type-hooks"></a>
## 🪝 Hooks 钩子

[在在线页面打开这一类,按星数排序 →](https://agentskillshub.top/best/claude-code-hooks/#type-hooks)

| 仓库 | 星数 | 做什么 | 安全评级 |
|---|---:|---|---|
| [disler/claude-code-hooks-mastery](https://github.com/disler/claude-code-hooks-mastery) | 4.0k | 掌握 Claude Code Hooks | [SAFE](https://agentskillshub.top/skill/disler/claude-code-hooks-mastery/) |
| [severity1/claude-code-prompt-improver](https://github.com/severity1/claude-code-prompt-improver) | 2.0k | Claude Code 的提示词优化 hook | [SAFE](https://agentskillshub.top/skill/severity1/claude-code-prompt-improver/) |
| [karanb192/claude-code-hooks](https://github.com/karanb192/claude-code-hooks) | 579 | Claude Code hooks 与可安装插件市场：安全、成本、可观测性与生产力。 | [SAFE](https://agentskillshub.top/skill/karanb192/claude-code-hooks/) |
| [shanraisshan/claude-code-hooks](https://github.com/shanraisshan/claude-code-hooks) | 569 | Claude Code hooks——为每个 hook 添加语音 | [SAFE](https://agentskillshub.top/skill/shanraisshan/claude-code-hooks/) |
| [IyadhKhalfallah/clauditor](https://github.com/IyadhKhalfallah/clauditor) | 430 | 防止 Claude Code 在20分钟内耗尽配额，自动轮换过大​​会话并保留上下文。 | [SAFE](https://agentskillshub.top/skill/IyadhKhalfallah/clauditor/) |
| [zxdxjtu/claudecode-rule2hook](https://github.com/zxdxjtu/claudecode-rule2hook) | 401 | 将自然语言项目规则转为 Claude Code 自动化 hooks，用于格式化、测试和验证等 | [SAFE](https://agentskillshub.top/skill/zxdxjtu/claudecode-rule2hook/) |
| [johnlindquist/claude-hooks](https://github.com/johnlindquist/claude-hooks) | 397 | 基于 TypeScript 的 Claude Code hook 系统，支持类型安全和自动补全 | [SAFE](https://agentskillshub.top/skill/johnlindquist/claude-hooks/) |
| [alexfazio/plankton](https://github.com/alexfazio/plankton) | 376 | Claude Code 写入时质量检查：每次编辑自动格式化和检查，由专用 Claude 实例智能修复剩余问题 | [SAFE](https://agentskillshub.top/skill/alexfazio/plankton/) |
| [win4r/claude-code-hooks](https://github.com/win4r/claude-code-hooks) | 334 | Claude Code Stop Hook：任务完成后写入 JSON、发送聊天软件通知并生成 pending-wake 文件供 AGI 读取 | [SAFE](https://agentskillshub.top/skill/win4r/claude-code-hooks/) |
| [nesaminua/claude-code-lsp-enforcement-kit](https://github.com/nesaminua/claude-code-lsp-enforcement-kit) | 327 | Hooks 强制 Claude Code 使用 LSP 而非 Grep 导航代码，节省约80% token | [SAFE](https://agentskillshub.top/skill/nesaminua/claude-code-lsp-enforcement-kit/) |
| [bobek-balinek/claude-lamp](https://github.com/bobek-balinek/claude-lamp) | 296 | Claude hooks 与 Moonside 灯具集成 | [SAFE](https://agentskillshub.top/skill/bobek-balinek/claude-lamp/) |
| [lasso-security/claude-hooks](https://github.com/lasso-security/claude-hooks) | 273 | Lasso 为 Claude Code 提供安全集成，包括提示注入防护 | [CAUTION](https://agentskillshub.top/skill/lasso-security/claude-hooks/) |
| [ldayton/Dippy](https://github.com/ldayton/Dippy) | 244 | 减少权限确认，保持推进。Dippy 判断哪些操作可安全运行，并在计划变化时让 Claude 保持方向。 | [SAFE](https://agentskillshub.top/skill/ldayton/Dippy/) |
| [cso1z/claude-ip-guard](https://github.com/cso1z/claude-ip-guard) | 233 | Claude Code hook 插件：基于 IP 的访问控制、IP 检测和地理位置拦截 | [SAFE](https://agentskillshub.top/skill/cso1z/claude-ip-guard/) |
| [BotchetDig/workout-gate](https://github.com/BotchetDig/workout-gate) | 220 | Claude Code hook：完成摄像头实时计数的俯卧撑后解除 prompt 阻塞，支持随机次数、会话持久欠额、连续统计和三种触发模式。 | [SAFE](https://agentskillshub.top/skill/BotchetDig/workout-gate/) |
| [juanandresgs/claude-ctrl](https://github.com/juanandresgs/claude-ctrl) | 192 | 系统思考者的确定性 Claude Code 控制平面 | [SAFE](https://agentskillshub.top/skill/juanandresgs/claude-ctrl/) |
| [bartolli/claude-code-typescript-hooks](https://github.com/bartolli/claude-code-typescript-hooks) | 180 | Claude Code 质量检查钩子，适用于不同项目类型。 | [SAFE](https://agentskillshub.top/skill/bartolli/claude-code-typescript-hooks/) |
| [ssssssanjiu/clawd-conduit](https://github.com/ssssssanjiu/clawd-conduit) | 175 | Claude Code 与 Clawd on Desk 宠物的全生命周期联动，涵盖15个 hook 事件，可直接在桌面回应权限提示 | [SAFE](https://agentskillshub.top/skill/ssssssanjiu/clawd-conduit/) |
| [yifanzz/claude-code-boost](https://github.com/yifanzz/claude-code-boost) | 165 | Claude Code Boost - Claude Code 的 Hook 工具，自动批准 | [SAFE](https://agentskillshub.top/skill/yifanzz/claude-code-boost/) |
| [GowayLee/cchooks](https://github.com/GowayLee/cchooks) | 131 | Claude Code hooks 的 Python SDK | [CAUTION](https://agentskillshub.top/skill/GowayLee/cchooks/) |
| [tzachbon/claude-model-router-hook](https://github.com/tzachbon/claude-model-router-hook) | 110 | 根据任务复杂度自动切换模型层级的 Claude Code hooks | [SAFE](https://agentskillshub.top/skill/tzachbon/claude-model-router-hook/) |
| [wyattjoh/claude-code-notification](https://github.com/wyattjoh/claude-code-notification) | 95 | Claude Code 的轻量 macOS 桌面通知钩子，在 AI 编码会话中显示带可自定义系统声音的原生通知。 | [SAFE](https://agentskillshub.top/skill/wyattjoh/claude-code-notification/) |
| [tak848/ccgate](https://github.com/tak848/ccgate) | 88 | 由 LLM 驱动的 coding agent 权限请求钩子（如 Claude Code） | [SAFE](https://agentskillshub.top/skill/tak848/ccgate/) |
| [pascalporedda/awesome-claude-code](https://github.com/pascalporedda/awesome-claude-code) | 87 | 汇总 Claude Code hooks，欢迎提交 issue 或 PR 添加内容。 | [CAUTION](https://agentskillshub.top/skill/pascalporedda/awesome-claude-code/) |
| [Vvkmnn/claude-emporium](https://github.com/Vvkmnn/claude-emporium) | 80 | [建设中] 一个（罗马）Claude 插件市场 | [SAFE](https://agentskillshub.top/skill/Vvkmnn/claude-emporium/) |
| [minorun365/claude-code-japanese-guard](https://github.com/minorun365/claude-code-japanese-guard) | 77 | Claude Code 的响应切换为英语时，要求其用日语重写的 Stop hook | [SAFE](https://agentskillshub.top/skill/minorun365/claude-code-japanese-guard/) |
| [decider/claude-hooks](https://github.com/decider/claude-hooks) | 75 | Claude Code hooks：规范代码实践并自动化工作流 | [SAFE](https://agentskillshub.top/skill/decider/claude-hooks/) |
| [henchmarketing-rgb/headroom](https://github.com/henchmarketing-rgb/headroom) | 70 | 了解剩余空间：Claude Code 上下文窗口使用情况条。 | [SAFE](https://agentskillshub.top/skill/henchmarketing-rgb/headroom/) |
| [beyondcode/claude-hooks-sdk](https://github.com/beyondcode/claude-hooks-sdk) | 68 | 用于构建 Claude Code hooks 的 PHP SDK | [SAFE](https://agentskillshub.top/skill/beyondcode/claude-hooks-sdk/) |
| [johnzfitch/claude-warden](https://github.com/johnzfitch/claude-warden) | 60 | Claude Code 的安全钩子与监控：静默覆写、SSRF 防护、MCP 压缩和 OTEL 追踪 | [SAFE](https://agentskillshub.top/skill/johnzfitch/claude-warden/) |
| [Dicklesworthstone/post_compact_reminder](https://github.com/Dicklesworthstone/post_compact_reminder) | 55 | Claude Code 钩子：检测上下文压缩并提醒重读 AGENTS.md，避免长会话中遗忘规则 | [CAUTION](https://agentskillshub.top/skill/Dicklesworthstone/post_compact_reminder/) |
| [wangbooth/Claude-Code-Guardrails](https://github.com/wangbooth/Claude-Code-Guardrails) | 53 | Claude Code 防护钩子，通过分支保护、自动检查点和安全压缩提交防止代码意外丢失 | [CAUTION](https://agentskillshub.top/skill/wangbooth/Claude-Code-Guardrails/) |
| [0-to-1-Labs/claude-code-prompt-optimizer](https://github.com/0-to-1-Labs/claude-code-prompt-optimizer) | 50 | Claude Code 的 AI 提示词优化 hook，将简单提示词转换为结构化指令。 | [SAFE](https://agentskillshub.top/skill/0-to-1-Labs/claude-code-prompt-optimizer/) |
| [SihyeonJeon/why-was-fable-banned](https://github.com/SihyeonJeon/why-was-fable-banned) | 47 | Fable 风格规范与证据门禁，让 Opus/Codex 遵循 Fable 纪律：规范通过前禁止编辑，无实时验收证据不得完成；强制执行先规范、后验证及禁止路径。 | [SAFE](https://agentskillshub.top/skill/SihyeonJeon/why-was-fable-banned/) |
| [recomby-ai/promptly-prompt](https://github.com/recomby-ai/promptly-prompt) | 38 | Claude Code skill，强制 AI 执行前先理解：认知检查、需求理解、方法搜索。 | [SAFE](https://agentskillshub.top/skill/recomby-ai/promptly-prompt/) |
| [kylesnowschwartz/prompt-intercept-pattern](https://github.com/kylesnowschwartz/prompt-intercept-pattern) | 20 | Claude Code 插件模式：通过 hook 拦截命令，无需 API 调用即可运行代码 | [SAFE](https://agentskillshub.top/skill/kylesnowschwartz/prompt-intercept-pattern/) |
| [yeisonrestrepo/code-conductor](https://github.com/yeisonrestrepo/code-conductor) | 17 | Claude Code 会话治理层：执行前检查 agent 命令、先写规范的流程和项目记忆。 | [SAFE](https://agentskillshub.top/skill/yeisonrestrepo/code-conductor/) |
| [sathwick-p/claude-rename](https://github.com/sathwick-p/claude-rename) | 16 | 使用 AI 为 Claude Code 会话自动生成描述性标题，无需配置或 API 密钥。 | [SAFE](https://agentskillshub.top/skill/sathwick-p/claude-rename/) |
| [karlkfi/claude-bouncer](https://github.com/karlkfi/claude-bouncer) | 13 | Claude Code 防护栏：工作区边界、受保护分支、生产目标、退出状态丢失和前台运行时长。 | [SAFE](https://agentskillshub.top/skill/karlkfi/claude-bouncer/) |
| [shuntaka9576/blocc](https://github.com/shuntaka9576/blocc) | 13 | 执行多个命令，失败时通过 stderr 返回 exit 2 阻止 Claude Code Hooks 🛡️ | [SAFE](https://agentskillshub.top/skill/shuntaka9576/blocc/) |
| [renefichtmueller/claude-code-hardened](https://github.com/renefichtmueller/claude-code-hardened) | 11 | 防止 AI 将机密推送到 GitHub。为 Claude Code 提供安全 hooks、规则和实时验证器。5 个 hooks、6 条规则、1 个安装脚本、零… | [SAFE](https://agentskillshub.top/skill/renefichtmueller/claude-code-hardened/) |
| [eliColussi/obsidian-ai-vault-kit](https://github.com/eliColussi/obsidian-ai-vault-kit) | 9 | 将任意文件夹变成可自动记录的 Obsidian vault。Claude Code hooks 自动将每个提示、回答和文件编辑记录到 Daily note。一… | [SAFE](https://agentskillshub.top/skill/eliColussi/obsidian-ai-vault-kit/) |
| [dxrayhq/claude-session-labels](https://github.com/dxrayhq/claude-session-labels) | 8 | 自动为 Claude Code 会话添加标签。状态栏显示项目、任务和上下文用量，并为每个会话使用不同颜色。 | [SAFE](https://agentskillshub.top/skill/dxrayhq/claude-session-labels/) |
| [shaominngqing/bark-claude-code-hook](https://github.com/shaominngqing/bark-claude-code-hook) | 8 | Claude Code 风险评估：7层流程、原生通知、菜单栏面板。一行安装。 | [SAFE](https://agentskillshub.top/skill/shaominngqing/bark-claude-code-hook/) |
| [tarekziade/claude-tools](https://github.com/tarekziade/claude-tools) | 8 | Claude Code 的钩子和工具 | [SAFE](https://agentskillshub.top/skill/tarekziade/claude-tools/) |
| [MohammedAtya/guardrail-forge](https://github.com/MohammedAtya/guardrail-forge) | 7 | 纠正 Claude 一次，它会持续遵守。Claude Code skill 将纠正转为经测试的防篡改 hook 规则。 | [CAUTION](https://agentskillshub.top/skill/MohammedAtya/guardrail-forge/) |
| [MatasMartin/claude-idea-capture](https://github.com/MatasMartin/claude-idea-capture) | 6 | Claude Code 自动记录可复用想法：SessionEnd hook 用 Haiku 读取会话并记录要点，还可挖掘全部历史。 | [SAFE](https://agentskillshub.top/skill/MatasMartin/claude-idea-capture/) |
| [dockplusai-ops/token-guard](https://github.com/dockplusai-ops/token-guard) | 6 | Claude Code 自动 hooks，减少 token 浪费：拦截大文件、上下文警告、成本记录 | [SAFE](https://agentskillshub.top/skill/dockplusai-ops/token-guard/) |
| [jordyvanvorselen/pi-claude-hooks](https://github.com/jordyvanvorselen/pi-claude-hooks) | 6 | 将 Claude Code hooks 的行为完整复刻到 Pi agent harness | [SAFE](https://agentskillshub.top/skill/jordyvanvorselen/pi-claude-hooks/) |
| [Todmy/cc-cache-monitor](https://github.com/Todmy/cc-cache-monitor) | 5 | Claude Code 实时 prompt-cache 监控——状态栏和成本分析 CLI | [SAFE](https://agentskillshub.top/skill/Todmy/cc-cache-monitor/) |
| [MaxHarfen/crab-band](https://github.com/MaxHarfen/crab-band) | 4 | Claude Code 模组：状态栏显示使用限制，主会话及子 agent 显示一排像素螃蟹 | [SAFE](https://agentskillshub.top/skill/MaxHarfen/crab-band/) |

<a id="type-subagents"></a>
## 🤖 Subagents 子代理

[在在线页面打开这一类,按星数排序 →](https://agentskillshub.top/best/claude-code-hooks/#type-subagents)

| 仓库 | 星数 | 做什么 | 安全评级 |
|---|---:|---|---|
| [VoltAgent/awesome-claude-code-subagents](https://github.com/VoltAgent/awesome-claude-code-subagents) | 26.4k | 覆盖广泛开发场景的100多个专业 Claude Code 子代理集合 | [SAFE](https://agentskillshub.top/skill/VoltAgent/awesome-claude-code-subagents/) |
| [lst97/claude-code-sub-agents](https://github.com/lst97/claude-code-sub-agents) | 1.7k | 供个人使用的 Claude Code 专用 AI 子代理集合（全栈开发） | [SAFE](https://agentskillshub.top/skill/lst97/claude-code-sub-agents/) |
| [zhsama/claude-sub-agent](https://github.com/zhsama/claude-sub-agent) | 592 | 基于 Claude Code Sub-Agents 的 AI 驱动开发工作流系统。 | [SAFE](https://agentskillshub.top/skill/zhsama/claude-sub-agent/) |
| [JDArmy/Evasion-SubAgents](https://github.com/JDArmy/Evasion-SubAgents) | 332 | Claude Code 免杀 SubAgents | [SAFE](https://agentskillshub.top/skill/JDArmy/Evasion-SubAgents/) |
| [NicholasSpisak/claude-code-subagents](https://github.com/NicholasSpisak/claude-code-subagents) | 213 | Claude Code Agent Team：76+个专业AI agent，配合Task工具，覆盖开发、战略、营销和财务分析。 | [SAFE](https://agentskillshub.top/skill/NicholasSpisak/claude-code-subagents/) |
| [tryalan-ai/awesome-claude-code-sub-agents](https://github.com/tryalan-ai/awesome-claude-code-sub-agents) | 178 | 专用 Claude Code agent 集合 | [SAFE](https://agentskillshub.top/skill/tryalan-ai/awesome-claude-code-sub-agents/) |
| [NEWBIE0413/gemini-gpt-hybrid](https://github.com/NEWBIE0413/gemini-gpt-hybrid) | 153 | Claude Code 的多模型编排子代理：按任务范围分派给 Gemini 的 1M token 上下文或 GPT 的快速迭代，再由 Claude 审查所有结… | [SAFE](https://agentskillshub.top/skill/NEWBIE0413/gemini-gpt-hybrid/) |
| [undeadlist/claude-code-agents](https://github.com/undeadlist/claude-code-agents) | 149 | Claude Code Agents：Claude Code 子代理系统的 Prompt 模板，支持并行代码审查、自动修复和复审，适用于 Task 工具；不是… | [SAFE](https://agentskillshub.top/skill/undeadlist/claude-code-agents/) |
| [rubenzantingh/claude-code-magento-agents](https://github.com/rubenzantingh/claude-code-magento-agents) | 124 | 用于 Magento (2) 开发的 Claude Code 子代理集合。 | [SAFE](https://agentskillshub.top/skill/rubenzantingh/claude-code-magento-agents/) |
| [mischasigtermans/laravel-altitude](https://github.com/mischasigtermans/laravel-altitude) | 122 | 基于 Laravel Boost 的 TALL 技术栈 Claude Code agents。 | [SAFE](https://agentskillshub.top/skill/mischasigtermans/laravel-altitude/) |
| [alirezarezvani/claude-cto-team](https://github.com/alirezarezvani/claude-cto-team) | 121 | 你的 Claude Code 个人 CTO 团队，帮助你在规划和执行时自我挑战。 | [SAFE](https://agentskillshub.top/skill/alirezarezvani/claude-cto-team/) |
| [davila7/claude_subagents](https://github.com/davila7/claude_subagents) | 116 | Claude SubAgents | [SAFE](https://agentskillshub.top/skill/davila7/claude_subagents/) |
| [augmnt/agents](https://github.com/augmnt/agents) | 74 | 面向软件开发流程的24+个专业Claude Code子代理集合。 | [SAFE](https://agentskillshub.top/skill/augmnt/agents/) |
| [askjohngeorge/askjg-claude-agents](https://github.com/askjohngeorge/askjg-claude-agents) | 55 | 我在 AI 辅助开发流程中使用的 Claude 子代理和自定义命令示例 | [SAFE](https://agentskillshub.top/skill/askjohngeorge/askjg-claude-agents/) |
| [legendtkl/claude-stock-agent](https://github.com/legendtkl/claude-stock-agent) | 9 | 用于股票分析的 Claude Code SubAgent | [SAFE](https://agentskillshub.top/skill/legendtkl/claude-stock-agent/) |

<a id="type-statusline"></a>
## 📊 Statusline 状态栏

[在在线页面打开这一类,按星数排序 →](https://agentskillshub.top/best/claude-code-hooks/#type-statusline)

| 仓库 | 星数 | 做什么 | 安全评级 |
|---|---:|---|---|
| [jarrodwatts/claude-hud](https://github.com/jarrodwatts/claude-hud) | 29.1k | 展示 Claude Code 状态的插件：上下文用量、活跃工具、运行中的 agent 和待办进度 | [SAFE](https://agentskillshub.top/skill/jarrodwatts/claude-hud/) |
| [sirmalloc/ccstatusline](https://github.com/sirmalloc/ccstatusline) | 13.6k | Claude Code CLI 的可高度定制状态栏，支持 Powerline 和主题等功能。 | [SAFE](https://agentskillshub.top/skill/sirmalloc/ccstatusline/) |
| [Haleclipse/CCometixLine](https://github.com/Haleclipse/CCometixLine) | 3.5k | 用 Rust 编写的 Claude Code 状态栏工具 | [SAFE](https://agentskillshub.top/skill/Haleclipse/CCometixLine/) |
| [Owloops/claude-powerline](https://github.com/Owloops/claude-powerline) | 1.2k | Claude Code 的 vim 风格 powerline | [SAFE](https://agentskillshub.top/skill/Owloops/claude-powerline/) |
| [GaoSSR/best-claude-hud](https://github.com/GaoSSR/best-claude-hud) | 997 | Rust 驱动的极简 Claude Code 状态栏 HUD | [SAFE](https://agentskillshub.top/skill/GaoSSR/best-claude-hud/) |
| [chongdashu/cc-statusline](https://github.com/chongdashu/cc-statusline) | 644 | 用美观且信息丰富的状态栏改善 Claude Code 使用体验 | [SAFE](https://agentskillshub.top/skill/chongdashu/cc-statusline/) |
| [daniel3303/ClaudeCodeStatusLine](https://github.com/daniel3303/ClaudeCodeStatusLine) | 622 | Claude Code 的自定义状态栏，实时显示模型、令牌、速率限制和 Git 信息 | [SAFE](https://agentskillshub.top/skill/daniel3303/ClaudeCodeStatusLine/) |
| [uppinote20/claude-dashboard](https://github.com/uppinote20/claude-dashboard) | 586 | Claude Code 状态栏插件，显示上下文用量、API 速率限制和成本 | [SAFE](https://agentskillshub.top/skill/uppinote20/claude-dashboard/) |
| [Nanako0129/coralline](https://github.com/Nanako0129/coralline) | 553 | 受 Powerlevel10k 启发的 Claude Code 状态栏——粘贴提示词，AI 会先询问你，然后完成安装 | [SAFE](https://agentskillshub.top/skill/Nanako0129/coralline/) |
| [rz1989s/claude-code-statusline](https://github.com/rz1989s/claude-code-statusline) | 479 | 用原子级精度状态栏改造 Claude Code 终端，支持灵活布局、实时成本追踪、MCP 监控、礼拜时间和主题。 | [SAFE](https://agentskillshub.top/skill/rz1989s/claude-code-statusline/) |
| [stephenleo/cship](https://github.com/stephenleo/cship) | 429 | Claude Code 的可定制状态栏：支持 Starship 风格 TOML 配置、主题颜色、Nerd Font 字形及可调费用、上下文和用量阈值。 | [SAFE](https://agentskillshub.top/skill/stephenleo/cship/) |
| [leeguooooo/claude-code-usage-bar](https://github.com/leeguooooo/claude-code-usage-bar) | 389 | Claude Code 状态行：5h/7d 速率限制用量、重置倒计时、模型与上下文窗口、提示缓存时长；单行，3种样式×9种主题，daemon fast-mode | [SAFE](https://agentskillshub.top/skill/leeguooooo/claude-code-usage-bar/) |
| [NYCU-Chung/cc-statusline](https://github.com/NYCU-Chung/cc-statusline) | 264 | Claude Code 状态栏仪表盘，显示会话信息、配额条、agent 跟踪、MCP 健康状态、消息历史等。 | [SAFE](https://agentskillshub.top/skill/NYCU-Chung/cc-statusline/) |
| [Astro-Han/claude-pace](https://github.com/Astro-Han/claude-pace) | 245 | Claude Code 状态栏和速率限制跟踪器，支持按节奏监控配额。纯 Bash + jq，单文件。 | [SAFE](https://agentskillshub.top/skill/Astro-Han/claude-pace/) |
| [Wangnov/claude-code-statusline-pro](https://github.com/Wangnov/claude-code-statusline-pro) | 239 | Claude Code 状态栏 | [SAFE](https://agentskillshub.top/skill/Wangnov/claude-code-statusline-pro/) |
| [awesomezun/claude-statusline](https://github.com/awesomezun/claude-statusline) | 214 | Claude Code 的美观状态栏，作者 awesomezun | [SAFE](https://agentskillshub.top/skill/awesomezun/claude-statusline/) |
| [kcchien/claude-code-statusline](https://github.com/kcchien/claude-code-statusline) | 201 | Claude Code 的信息丰富状态栏：渐变进度条、智能隐藏、Git 状态、费用跟踪等。 | [SAFE](https://agentskillshub.top/skill/kcchien/claude-code-statusline/) |
| [ilia-pluzhnikov/claude-code-statusline](https://github.com/ilia-pluzhnikov/claude-code-statusline) | 121 | 无依赖的 Node.js Claude Code 状态栏，显示模型、任务、Git 状态、上下文窗口、速率限制和 Anthropic 高峰时段指示 | [SAFE](https://agentskillshub.top/skill/ilia-pluzhnikov/claude-code-statusline/) |
| [danielmackay/claude-code-statusline](https://github.com/danielmackay/claude-code-statusline) | 111 | Claude Code 自定义状态栏脚本，在终端显示实时会话信息。 | [SAFE](https://agentskillshub.top/skill/danielmackay/claude-code-statusline/) |
| [byebye-code/byebyecode](https://github.com/byebye-code/byebyecode) | 97 | 88code 的 Claude 增强版 statusline，基于 CCometixLine 开发 | [SAFE](https://agentskillshub.top/skill/byebye-code/byebyecode/) |
| [wolfdenpublishing/pyccsl](https://github.com/wolfdenpublishing/pyccsl) | 83 | Python Claude Code 状态行（PyCCSL，读作“pixel”） | [CAUTION](https://agentskillshub.top/skill/wolfdenpublishing/pyccsl/) |
| [ersinkoc/claude-statusline](https://github.com/ersinkoc/claude-statusline) | 78 | Claude Statusline：为 Claude Code 提供会话实时跟踪、成本统计、多模型、Git 和系统信息。 | [SAFE](https://agentskillshub.top/skill/ersinkoc/claude-statusline/) |
| [xleddyl/claude-watch](https://github.com/xleddyl/claude-watch) | 70 | Claude Code 极简状态栏 | [SAFE](https://agentskillshub.top/skill/xleddyl/claude-watch/) |
| [shanraisshan/claude-code-status-line](https://github.com/shanraisshan/claude-code-status-line) | 65 | Claude Code 自定义状态栏脚本，显示上下文窗口使用情况、Git 状态和模型信息。 | [SAFE](https://agentskillshub.top/skill/shanraisshan/claude-code-status-line/) |
| [videvjs/claude-statusline](https://github.com/videvjs/claude-statusline) | 59 | Claude Code 自定义状态栏—文件夹、Git 分支、模型、上下文和速率限制 | [SAFE](https://agentskillshub.top/skill/videvjs/claude-statusline/) |
| [aiedwardyi/claude-usage-monitor](https://github.com/aiedwardyi/claude-usage-monitor) | 58 | Claude Code 终端状态栏插件，显示 5 小时/7 天配额、上下文使用量、token 数和重置倒计时。 | [SAFE](https://agentskillshub.top/skill/aiedwardyi/claude-usage-monitor/) |
| [loadbalance-sudachi-kun/claude-code-statusline](https://github.com/loadbalance-sudachi-kun/claude-code-statusline) | 56 | Claude Code 状态栏，显示速率限制 | [SAFE](https://agentskillshub.top/skill/loadbalance-sudachi-kun/claude-code-statusline/) |
| [vfmatzkin/claude-statusline](https://github.com/vfmatzkin/claude-statusline) | 56 | 将 Claude Code 的 statusline JSON 格式化为状态栏，显示模型、Git 分支、上下文占用、限额和会话成本等信息。 | [SAFE](https://agentskillshub.top/skill/vfmatzkin/claude-statusline/) |
| [fredrikaverpil/claudeline](https://github.com/fredrikaverpil/claudeline) | 55 | 极简的 Go Claude Code 状态栏 | [SAFE](https://agentskillshub.top/skill/fredrikaverpil/claudeline/) |
| [glauberlima/claude-code-statusline](https://github.com/glauberlima/claude-code-statusline) | 52 | Claude Code CLI 状态栏，显示 Git 状态、上下文用量、模型信息和费用 | [SAFE](https://agentskillshub.top/skill/glauberlima/claude-code-statusline/) |
| [canack/claude-usage-line](https://github.com/canack/claude-usage-line) | 40 | Claude Code 自定义状态栏：速率限制、Git 分支、费用、差异统计 | [SAFE](https://agentskillshub.top/skill/canack/claude-usage-line/) |
| [hagan/claudia-statusline](https://github.com/hagan/claudia-statusline) | 37 | Claude Code 的 Rust 状态栏：hook 压缩检测、SQLite 会话持久化，支持多控制台安全跟踪。 | [SAFE](https://agentskillshub.top/skill/hagan/claudia-statusline/) |
| [mttmcknn/prism](https://github.com/mttmcknn/prism) | 35 | Claude Code 的快速、可自定义彩色状态栏。 | [SAFE](https://agentskillshub.top/skill/mttmcknn/prism/) |
| [deluo/glm-quota-line](https://github.com/deluo/glm-quota-line) | 33 | 用于在 Claude Code 状态栏显示 GLM Coding Plan 配额的轻量级 CLI | [SAFE](https://agentskillshub.top/skill/deluo/glm-quota-line/) |
| [kylesnowschwartz/tail-claude-hud](https://github.com/kylesnowschwartz/tail-claude-hud) | 33 | Claude Code 会话的终端状态栏 | [SAFE](https://agentskillshub.top/skill/kylesnowschwartz/tail-claude-hud/) |
| [tzengyuxio/claude-statusline](https://github.com/tzengyuxio/claude-statusline) | 31 | Claude Code 的两行状态栏，显示上下文条、使用量、Git 状态和 Nerd Font 图标 | [SAFE](https://agentskillshub.top/skill/tzengyuxio/claude-statusline/) |
| [Field-Logic-Ltd/ClaudeStatsBar](https://github.com/Field-Logic-Ltd/ClaudeStatsBar) | 30 | Claude Code 状态栏：输入前查看会话规模和下一轮成本 | [SAFE](https://agentskillshub.top/skill/Field-Logic-Ltd/ClaudeStatsBar/) |
| [allthingsclaude/bar](https://github.com/allthingsclaude/bar) | 29 | Claude Code 的状态栏，在终端显示上下文使用量、会话限制和 Git 信息。 | [SAFE](https://agentskillshub.top/skill/allthingsclaude/bar/) |
| [vbcherepanov/claude-statusbar](https://github.com/vbcherepanov/claude-statusbar) | 29 | Claude Code CLI 双行状态栏：实时显示模型、上下文用量、令牌、费用、耗时、Git 分支、缓存统计等终端信息 | [SAFE](https://agentskillshub.top/skill/vbcherepanov/claude-statusbar/) |
| [Ventuss-OvO/cc-costline](https://github.com/Ventuss-OvO/cc-costline) | 28 | Claude Code 增强状态栏——一眼查看 7天/30天支出 | [SAFE](https://agentskillshub.top/skill/Ventuss-OvO/cc-costline/) |
| [hell0github/claude-statusline](https://github.com/hell0github/claude-statusline) | 27 | Claude Code CLI 状态栏插件，跟踪上下文、费用用量和会话重置时间 | [SAFE](https://agentskillshub.top/skill/hell0github/claude-statusline/) |
| [alp82/claude-statusline](https://github.com/alp82/claude-statusline) | 26 | 一个用于 Claude Code 状态栏的 Bash 脚本：目录、分支、模型、上下文窗口及 5 小时/7 天/Fable 速率限制条。 | [SAFE](https://agentskillshub.top/skill/alp82/claude-statusline/) |
| [bartleby/claude-statusline](https://github.com/bartleby/claude-statusline) | 26 | Claude Code CLI 的自定义状态栏，含 18 种主题、速率限制、上下文跟踪和 ASCII Claude 头像 | [SAFE](https://agentskillshub.top/skill/bartleby/claude-statusline/) |
| [tylergraydev/claude-limitline](https://github.com/tylergraydev/claude-limitline) | 25 | Claude Code 状态栏，显示实时使用限额和每周用量跟踪 | [SAFE](https://agentskillshub.top/skill/tylergraydev/claude-limitline/) |
| [felipeelias/claude-statusline](https://github.com/felipeelias/claude-statusline) | 23 | Claude Code 可配置状态栏 | [SAFE](https://agentskillshub.top/skill/felipeelias/claude-statusline/) |
| [kangraemin/claude-status-bar](https://github.com/kangraemin/claude-status-bar) | 23 | Claude Code 状态栏脚本 | [SAFE](https://agentskillshub.top/skill/kangraemin/claude-status-bar/) |
| [Nadav-Fux/claude-2x-statusline](https://github.com/Nadav-Fux/claude-2x-statusline) | 22 | Claude Code 的极简以色列时区状态栏，查看 2X 用量翻倍促销是否进行中 | [SAFE](https://agentskillshub.top/skill/Nadav-Fux/claude-2x-statusline/) |
| [TylerGallenbeck/claude-code-limit-tracker](https://github.com/TylerGallenbeck/claude-code-limit-tracker) | 22 | Claude Code 用量追踪：在状态栏实时显示各模型配额使用量和准确订阅限额 | [SAFE](https://agentskillshub.top/skill/TylerGallenbeck/claude-code-limit-tracker/) |
| [briansmith80/claude-code-status-bar](https://github.com/briansmith80/claude-code-status-bar) | 22 | Claude Code 可配置状态栏：使用限额及节奏标记、上下文窗口、Git 状态、实时活动、会话费用和 8 种配色主题。纯 bash，无依赖。 | [SAFE](https://agentskillshub.top/skill/briansmith80/claude-code-status-bar/) |
| [jacob-bd/claude-code-statusline](https://github.com/jacob-bd/claude-code-statusline) | 19 | Claude Code 的自定义状态栏，准确追踪费用并警告上下文用量 | [CAUTION](https://agentskillshub.top/skill/jacob-bd/claude-code-statusline/) |
| [egerev/claude-status-line](https://github.com/egerev/claude-status-line) | 18 | Claude Code 状态栏：上下文、缓存、速率限制和提示词估算 | [SAFE](https://agentskillshub.top/skill/egerev/claude-status-line/) |
| [FahimFBA/claudecode-statusline](https://github.com/FahimFBA/claudecode-statusline) | 17 | 简洁实用的 Claude Code 状态栏 | [SAFE](https://agentskillshub.top/skill/FahimFBA/claudecode-statusline/) |
| [blushdas/claude-code-statusline](https://github.com/blushdas/claude-code-statusline) | 17 | Claude Code 实时状态栏，追踪费用并记录到 Obsidian | [SAFE](https://agentskillshub.top/skill/blushdas/claude-code-statusline/) |
| [dsebastien/claude-epic-status-line](https://github.com/dsebastien/claude-epic-status-line) | 17 | Claude Code 状态栏：颜色、速率限制、Git 信息、会话费用、工作树检测和自动压缩警告 | [SAFE](https://agentskillshub.top/skill/dsebastien/claude-epic-status-line/) |
| [ssenart/oh-my-claude](https://github.com/ssenart/oh-my-claude) | 16 | Claude Code 的自定义状态栏 | [CAUTION](https://agentskillshub.top/skill/ssenart/oh-my-claude/) |
| [ohugonnot/claude-code-statusline](https://github.com/ohugonnot/claude-code-statusline) | 14 | Claude Code 实时追踪 /usage 限额：状态栏显示会话与每周配额、重置倒计时、上下文窗口、模型和 git 分支 | [SAFE](https://agentskillshub.top/skill/ohugonnot/claude-code-statusline/) |
| [Darkycl/claude-code-glm-statusline](https://github.com/Darkycl/claude-code-glm-statusline) | 13 | 面向 GLM Coding Plan 订阅者的 Claude Code 状态栏，实时显示配额和上下文使用情况 | [SAFE](https://agentskillshub.top/skill/Darkycl/claude-code-glm-statusline/) |
| [GorajKathrotiya/claude-code-statusline](https://github.com/GorajKathrotiya/claude-code-statusline) | 13 | Claude Code 状态栏：会话百分比、每周限额、重置倒计时。纯 Shell，无需 npm。 | [CAUTION](https://agentskillshub.top/skill/GorajKathrotiya/claude-code-statusline/) |
| [jsubroto/claude-code-statusline](https://github.com/jsubroto/claude-code-statusline) | 13 | Claude Code 内置状态行的终端配置器。选择字段和主题，按回车。 | [SAFE](https://agentskillshub.top/skill/jsubroto/claude-code-statusline/) |
| [fightingPig/claude-statusline](https://github.com/fightingPig/claude-statusline) | 12 | Claude Code 状态栏：显示目录、分支、模型、effort、上下文进度和 PR | [SAFE](https://agentskillshub.top/skill/fightingPig/claude-statusline/) |
| [labzink/cc-probeline](https://github.com/labzink/cc-probeline) | 12 | Claude Code 状态栏：实时显示每轮、子代理和缓存重建费用，以及限额、上下文和 Git 信息 | [SAFE](https://agentskillshub.top/skill/labzink/cc-probeline/) |
| [YuriNachos/claude-scope](https://github.com/YuriNachos/claude-scope) | 11 | Claude Code CLI 的可定制状态栏，支持多个小组件、主题和 AI 友好配置，无运行时依赖。 | [SAFE](https://agentskillshub.top/skill/YuriNachos/claude-scope/) |
| [jftuga/claude-statusline](https://github.com/jftuga/claude-statusline) | 11 | 用 Go 编写的 Claude Code 自定义状态栏渲染器 | [SAFE](https://agentskillshub.top/skill/jftuga/claude-statusline/) |
| [rafsuntaskin/claude-usage-in-status](https://github.com/rafsuntaskin/claude-usage-in-status) | 11 | 在 Claude Code 状态栏显示实时上下文占比、Token 数量和速率限制状态。 | [SAFE](https://agentskillshub.top/skill/rafsuntaskin/claude-usage-in-status/) |
| [tenondecrpc/cc-statusline](https://github.com/tenondecrpc/cc-statusline) | 11 | Claude Statusline：Claude Code 的 Bash + jq 状态栏，显示模型、上下文、速率限制、git/worktree、费用和时长，… | [SAFE](https://agentskillshub.top/skill/tenondecrpc/cc-statusline/) |
| [Lxcardoza993/Claude-statusline](https://github.com/Lxcardoza993/Claude-statusline) | 10 | Claude Code 配置备份：statusline、autocompact 环境变量和 healthcheck（跨 CC 更新保留） | [SAFE](https://agentskillshub.top/skill/Lxcardoza993/Claude-statusline/) |
| [zander-zyx/claude-mini-hud](https://github.com/zander-zyx/claude-mini-hud) | 10 | 参考 claude-hud，7行以内。内置13个国产模型平台用量查询，支持第三方代理实时查看额度消耗。 | [SAFE](https://agentskillshub.top/skill/zander-zyx/claude-mini-hud/) |
| [SaharCarmel/claude-code-status-line](https://github.com/SaharCarmel/claude-code-status-line) | 9 | Claude Code 状态栏，包含 AI 生成的项目摘要 | [SAFE](https://agentskillshub.top/skill/SaharCarmel/claude-code-status-line/) |
| [ali-nr/claude-pulse](https://github.com/ali-nr/claude-pulse) | 9 | Claude Code 的响应式状态栏 | [SAFE](https://agentskillshub.top/skill/ali-nr/claude-pulse/) |
| [educlopez/ccvitals](https://github.com/educlopez/ccvitals) | 9 | Claude Code 状态栏，纯 bash，不阻塞提示符；显示用量配额、上下文窗口、Git 状态等。 | [SAFE](https://agentskillshub.top/skill/educlopez/ccvitals/) |
| [livlign/ccbit](https://github.com/livlign/ccbit) | 9 | Claude Code 的会话感知状态栏。颜文字读取记录并播报各会话状态。单个 Go 二进制，无 hooks、无守护进程。 | [SAFE](https://agentskillshub.top/skill/livlign/ccbit/) |
| [moon1ite/claude-statusline](https://github.com/moon1ite/claude-statusline) | 9 | Claude Code 实时状态栏，显示工具、agent 和待办事项 | [SAFE](https://agentskillshub.top/skill/moon1ite/claude-statusline/) |
| [moonD4rk/ccstatus](https://github.com/moonD4rk/ccstatus) | 9 | 使用 Go 编写的 Claude Code CLI 可自定义状态栏格式化工具 | [SAFE](https://agentskillshub.top/skill/moonD4rk/ccstatus/) |
| [tablesguru/claude-code-statusline](https://github.com/tablesguru/claude-code-statusline) | 9 | Claude Code 的简洁多行状态栏：上下文条、分组的 5 小时/7 天限流条、进度叠加、Git 分支、令牌数和会话时间。 | [CAUTION](https://agentskillshub.top/skill/tablesguru/claude-code-statusline/) |
| [tomascabralh/cclimit](https://github.com/tomascabralh/cclimit) | 9 | 免凭证 Claude Code 状态栏：计划限额用量（5小时/7天）、上下文、Git 分支和会话费用。无需令牌、Keychain 或网络。 | [SAFE](https://agentskillshub.top/skill/tomascabralh/cclimit/) |
| [aleksander-dytko/claude-code-statusline](https://github.com/aleksander-dytko/claude-code-statusline) | 8 | Claude Code 增强状态栏：一个 bash 脚本显示模型、Git、上下文窗口、会话费用和实时使用限制 | [CAUTION](https://agentskillshub.top/skill/aleksander-dytko/claude-code-statusline/) |
| [muzafferkadir/claude-code-token-bar](https://github.com/muzafferkadir/claude-code-token-bar) | 8 | Claude Code 的快速、零依赖状态栏（bash + jq，无 Node，无缓存） | [SAFE](https://agentskillshub.top/skill/muzafferkadir/claude-code-token-bar/) |
| [orassayag/super-status](https://github.com/orassayag/super-status) | 8 | Claude Code 状态栏：模型、Git、上下文、限额、费用、令牌、缓存、代码行数及工具/agent/todo；支持多后端，JSON 配置。 | [SAFE](https://agentskillshub.top/skill/orassayag/super-status/) |
| [sodam-ai/ClaudeTower](https://github.com/sodam-ai/ClaudeTower) | 8 | Claude Code状态栏CLI，显示位置、模型、Git、上下文、费用、使用率；支持插件聊天配置、API密钥注册与手动切换（默认关），不支持登录自动化或自动… | [SAFE](https://agentskillshub.top/skill/sodam-ai/ClaudeTower/) |
| [AndrewP-GH/cc-statusline](https://github.com/AndrewP-GH/cc-statusline) | 7 | 尽力实现的 Claude Code 状态行 | [SAFE](https://agentskillshub.top/skill/AndrewP-GH/cc-statusline/) |
| [danjdewhurst/cc-status-line](https://github.com/danjdewhurst/cc-status-line) | 7 | Claude Code 的 Catppuccin Frappe 状态行，显示模型、Git 分支、上下文用量和会话成本。 | [SAFE](https://agentskillshub.top/skill/danjdewhurst/cc-status-line/) |
| [gwiener/claude-burn-bars](https://github.com/gwiener/claude-burn-bars) | 7 | Claude Code 状态栏：用条形图显示距下次 5 小时和 7 天刷新前的用量 | [SAFE](https://agentskillshub.top/skill/gwiener/claude-burn-bars/) |
| [ordinarynerds/dashline](https://github.com/ordinarynerds/dashline) | 7 | 可在 settings.json 中配置的 Claude Code 固定风格状态栏 | [SAFE](https://agentskillshub.top/skill/ordinarynerds/dashline/) |
| [aweussom/claude-code-quota](https://github.com/aweussom/claude-code-quota) | 6 | 在状态栏显示 Claude Code OAuth 配额——Windows（PowerShell）和 Linux（或 WSL2） | [CAUTION](https://agentskillshub.top/skill/aweussom/claude-code-quota/) |
| [babarot/c-c-statusline](https://github.com/babarot/c-c-statusline) | 6 | Deno 驱动的 Claude Code CLI 状态行 | [SAFE](https://agentskillshub.top/skill/babarot/c-c-statusline/) |
| [faborsky/claude-code-statusline](https://github.com/faborsky/claude-code-statusline) | 6 | 极简 Claude Code 状态栏：上下文条、会话费用、持续时间和 Git 分支，一个 Bash 脚本。 | [SAFE](https://agentskillshub.top/skill/faborsky/claude-code-statusline/) |
| [hugohvf/claude-code-statusline](https://github.com/hugohvf/claude-code-statusline) | 6 | Claude Code 状态栏脚本：实时显示上下文用量、会话费用（USD+BRL）、缓存命中率、模型和 Git 分支 | [CAUTION](https://agentskillshub.top/skill/hugohvf/claude-code-statusline/) |
| [savinofiore/claude-usage-statusline](https://github.com/savinofiore/claude-usage-statusline) | 6 | 无需依赖的 Claude Code 状态栏：模型、上下文用量、5小时/每周速率限制、令牌、成本，一行显示。 | [SAFE](https://agentskillshub.top/skill/savinofiore/claude-usage-statusline/) |
| [taras-mrtn/ccbar](https://github.com/taras-mrtn/ccbar) | 6 | Claude Code 可配置状态栏：用量限制、上下文窗口、Git 信息和主题一栏显示。 | [SAFE](https://agentskillshub.top/skill/taras-mrtn/ccbar/) |
| [waelmas/claude-stat](https://github.com/waelmas/claude-stat) | 6 | Claude Code 信息密集状态行：上下文窗口、速率限制、缓存命中率、模型和 git，零依赖。 | [SAFE](https://agentskillshub.top/skill/waelmas/claude-stat/) |
| [anykeith/claude-hud-deepseek](https://github.com/anykeith/claude-hud-deepseek) | 5 | Claude Code 的 DeepSeek 后端状态栏插件：实时上下文用量、token 跟踪和工具检测 | [SAFE](https://agentskillshub.top/skill/anykeith/claude-hud-deepseek/) |
| [bart-turczynski/cc-cream](https://github.com/bart-turczynski/cc-cream) | 5 | gitlab.com/bart-turczynski/cc-cream的只读镜像。在Claude Code CLI查看缓存状态、上下文占用、Token消耗、速… | [SAFE](https://agentskillshub.top/skill/bart-turczynski/cc-cream/) |
| [bishnubista/cc-statusline](https://github.com/bishnubista/cc-statusline) | 5 | 简洁清晰的 Claude Code 状态栏，显示模型、目录、Git 分支和输出样式 | [CAUTION](https://agentskillshub.top/skill/bishnubista/cc-statusline/) |
| [hamed-elfayome/Claude-Code-Statusline-Usage-Tracker-MacOS](https://github.com/hamed-elfayome/Claude-Code-Statusline-Usage-Tracker-MacOS) | 5 | 在 Claude Code 状态栏中显示 Claude AI 使用统计，实时监控 API 使用情况。 | [SAFE](https://agentskillshub.top/skill/hamed-elfayome/Claude-Code-Statusline-Usage-Tracker-MacOS/) |
| [momenbasel/claude-code-statusline](https://github.com/momenbasel/claude-code-statusline) | 5 | Claude Code 单行状态栏：显示账户、模型、路径、Git、上下文和用量限制，使用纯 bash + jq。 | [SAFE](https://agentskillshub.top/skill/momenbasel/claude-code-statusline/) |
| [pete-builds/claude-code-statusline](https://github.com/pete-builds/claude-code-statusline) | 5 | Claude Code TUI 的带标签状态栏：上下文用量、计费等级、Git 状态、天气和会话指标 | [CAUTION](https://agentskillshub.top/skill/pete-builds/claude-code-statusline/) |
| [shehab267/ccbrief](https://github.com/shehab267/ccbrief) | 5 | Claude Code 可配置状态栏：在终端查看上下文、令牌、费用和速率限制。 | [SAFE](https://agentskillshub.top/skill/shehab267/ccbrief/) |
| [tolluset/statusline](https://github.com/tolluset/statusline) | 5 | 增强版 Claude Code 状态栏，显示 Git 状态、GitHub 通知和智能路径。 | [SAFE](https://agentskillshub.top/skill/tolluset/statusline/) |
| [yuseferi/claude-token-statusbar](https://github.com/yuseferi/claude-token-statusbar) | 5 | 用于 Claude Code TUI 的实时 token 与费用状态栏 | [SAFE](https://agentskillshub.top/skill/yuseferi/claude-token-statusbar/) |
| [webkubor/claude-usage-statusline](https://github.com/webkubor/claude-usage-statusline) | 0 | Claude Code 状态栏：显示会话花费、上下文占用和 5h/7d 限额，区分订阅与按量付费，支持预警和无兜底硬停。单文件 Python，零依赖、零配置。 | [SAFE](https://agentskillshub.top/skill/webkubor/claude-usage-statusline/) |

<a id="type-collection"></a>
## 📚 合集

[在在线页面打开这一类,按星数排序 →](https://agentskillshub.top/best/claude-code-hooks/#type-collection)

<table><tr>
<td align="center" valign="top"><a href="https://github.com/HamzaAlayed/laravel-claude-agents"><img src="assets/previews/HamzaAlayed__laravel-claude-agents.jpg" width="260" alt="HamzaAlayed/laravel-claude-agents"></a><br><sub><a href="https://github.com/HamzaAlayed/laravel-claude-agents">HamzaAlayed/laravel-claude-agents</a></sub></td>
</tr></table>

| 仓库 | 星数 | 做什么 | 安全评级 |
|---|---:|---|---|
| [diet103/claude-code-infrastructure-showcase](https://github.com/diet103/claude-code-infrastructure-showcase) | 10.1k | Claude Code 基础设施示例：skill 自动激活、hooks 和 agents | [SAFE](https://agentskillshub.top/skill/diet103/claude-code-infrastructure-showcase/) |
| [WorldFlowAI/everything-claude-code](https://github.com/WorldFlowAI/everything-claude-code) | 6.1k | Claude Code 工具包：用于 AI 辅助开发的 agents、commands、skills、rules 和 hooks | [SAFE](https://agentskillshub.top/skill/WorldFlowAI/everything-claude-code/) |
| [parcadei/Continuous-Claude-v3](https://github.com/parcadei/Continuous-Claude-v3) | 3.9k | Claude Code 的上下文管理。Hooks 通过 ledgers 和 handoffs 维护状态。MCP 执行不污染上下文。用隔离的上下文窗口编排 ag… | [SAFE](https://agentskillshub.top/skill/parcadei/Continuous-Claude-v3/) |
| [0xSteph/pentest-ai-agents](https://github.com/0xSteph/pentest-ai-agents) | 2.4k | 将 Claude Code 用作进攻性安全研究助手：AI 子代理可规划授权渗透测试、分析侦察、研究漏洞利用、构建检测、审计 STIG 并撰写报告。 | [SAFE](https://agentskillshub.top/skill/0xSteph/pentest-ai-agents/) |
| [0xfurai/claude-code-subagents](https://github.com/0xfurai/claude-code-subagents) | 1.0k | Claude Code 的 100+ 个可用于生产的开发子代理集合 | [SAFE](https://agentskillshub.top/skill/0xfurai/claude-code-subagents/) |
| [sangrokjung/claude-forge](https://github.com/sangrokjung/claude-forge) | 875 | Claude Code 的 oh-my-zsh：16agent、35命令、32skill、21安全钩子。v4.0：审查循环，二次agent不看首个推理。MIT。 | [SAFE](https://agentskillshub.top/skill/sangrokjung/claude-forge/) |
| [ruvnet/agentic-flow](https://github.com/ruvnet/agentic-flow) | 838 | 在 Claude Code/Agent SDK 中切换低成本 AI 模型，开发并部署托管 agent 到云端用于业务。 | [SAFE](https://agentskillshub.top/skill/ruvnet/agentic-flow/) |
| [carlrannaberg/claudekit](https://github.com/carlrannaberg/claudekit) | 762 | Claude Code 的自定义命令、钩子和工具集 | [SAFE](https://agentskillshub.top/skill/carlrannaberg/claudekit/) |
| [vanzan01/claude-code-sub-agent-collective](https://github.com/vanzan01/claude-code-sub-agent-collective) | 525 | 上下文工程研究：通过研究与上下文工程形成协作集群，由 Claude Code 进行中心辐射式协调。 | [SAFE](https://agentskillshub.top/skill/vanzan01/claude-code-sub-agent-collective/) |
| [NYCU-Chung/my-claude-devteam](https://github.com/NYCU-Chung/my-claude-devteam) | 268 | 面向 Claude Code 的工程团队：12 个专用 agent、15 个自动化 hooks 和 P7/P9/P10 方法论。 | [SAFE](https://agentskillshub.top/skill/NYCU-Chung/my-claude-devteam/) |
| [sd0xdev/sd0x-harness](https://github.com/sd0xdev/sd0x-harness) | 194 | Claude Code 的 harness 层：钩子强制双重审查，状态机闸门跨上下文压缩，关键处故障闭锁，AI 无法跳过质量门。 | [SAFE](https://agentskillshub.top/skill/sd0xdev/sd0x-harness/) |
| [dl-ezo/claude-code-sub-agents](https://github.com/dl-ezo/claude-code-sub-agents) | 186 | Claude Code 的 35 个专业 sub-agent，支持端到端软件开发自动化 | [SAFE](https://agentskillshub.top/skill/dl-ezo/claude-code-sub-agents/) |
| [KimYx0207/Kim_Service](https://github.com/KimYx0207/Kim_Service) | 185 | Claude Code、Codex 等 AI 编码助手的 Hook 和 Agent Skill 开源合集。 | [SAFE](https://agentskillshub.top/skill/KimYx0207/Kim_Service/) |
| [ayush-that/sub-agents.directory](https://github.com/ayush-that/sub-agents.directory) | 150 | Sub-Agents Directory：Claude Code 的 100+ 个子 agent 提示词和 MCP 服务器集合 | [SAFE](https://agentskillshub.top/skill/ayush-that/sub-agents.directory/) |
| [Bande-a-Bonnot/Boucle-framework](https://github.com/Bande-a-Bonnot/Boucle-framework) | 126 | 具备结构化记忆、安全钩子和循环管理的自主 agent 框架。由运行于其上的 agent 构建。 | [SAFE](https://agentskillshub.top/skill/Bande-a-Bonnot/Boucle-framework/) |
| [Aedelon/claude-code-blueprint](https://github.com/Aedelon/claude-code-blueprint) | 122 | 生产级 Claude Code 配置：skills、agents、hooks、rules 和 permissions 协同工作。 | [SAFE](https://agentskillshub.top/skill/Aedelon/claude-code-blueprint/) |
| [tmcfarlane/team-avatar](https://github.com/tmcfarlane/team-avatar) | 112 | Team Avatar: a universal agent orchestrator for Claude Code, Codex, and Cursor. Nine Avatar characters, 58 engineering skills. pstack with Avatar cha… | [SAFE](https://agentskillshub.top/skill/tmcfarlane/team-avatar/) |
| [Toskysun/sub-agents](https://github.com/Toskysun/sub-agents) | 111 | Claude Code 的智能代理集合 | [SAFE](https://agentskillshub.top/skill/Toskysun/sub-agents/) |
| [solanabr/ai-kit](https://github.com/solanabr/ai-kit) | 111 | 面向 Solana 专家开发者的 Claude Code / Codex / AI 配置，涵盖 Web、Anchor、Pinnochio、Unity、Mobi… | [SAFE](https://agentskillshub.top/skill/solanabr/ai-kit/) |
| [rshah515/claude-code-subagents](https://github.com/rshah515/claude-code-subagents) | 106 | Claude Code 的 133+ 个专用 AI 子 agent，覆盖整个软件开发生命周期 | [SAFE](https://agentskillshub.top/skill/rshah515/claude-code-subagents/) |
| [Dev-GOM/claude-code-marketplace](https://github.com/Dev-GOM/claude-code-marketplace) | 97 | Claude Code 插件和扩展：用于开发者效率与工作流自动化的 Hooks、commands 和 agents | [SAFE](https://agentskillshub.top/skill/Dev-GOM/claude-code-marketplace/) |
| [tony/claude-code-riper-5](https://github.com/tony/claude-code-riper-5) | 96 | 用于 RIPER-5 的 Claude Code（子代理、自定义命令） | [SAFE](https://agentskillshub.top/skill/tony/claude-code-riper-5/) |
| [arpitnath/claude-capsule-kit](https://github.com/arpitnath/claude-capsule-kit) | 93 | 让 Claude Code 更适合工程开发的工具包：会话记忆、依赖分析、大文件导航、18 个专业 agent 和并行多分支工作的 crew 团队。 | [SAFE](https://agentskillshub.top/skill/arpitnath/claude-capsule-kit/) |
| [ChanMeng666/claude-code-audio-hooks](https://github.com/ChanMeng666/claude-code-audio-hooks) | 90 | Claude Code 与 Cursor IDE 的 AI 音频通知：26 个 hooks、语音与提示音主题、TTS、webhooks、限流提醒和状态栏。一条… | [SAFE](https://agentskillshub.top/skill/ChanMeng666/claude-code-audio-hooks/) |
| [0ldh/claude-code-agents-orchestra](https://github.com/0ldh/claude-code-agents-orchestra) | 85 | 将 Claude Code 变为由40多个专业 AI agent 协同工作的团队。 | [SAFE](https://agentskillshub.top/skill/0ldh/claude-code-agents-orchestra/) |
| [Filip-Podstavec/claude-leverage](https://github.com/Filip-Podstavec/claude-leverage) | 68 | 让任意仓库支持 AI：编写可维护代码，或重构旧代码以适配 agent 开发。Claude Code 的 subagents、slash commands、ho… | [SAFE](https://agentskillshub.top/skill/Filip-Podstavec/claude-leverage/) |
| [dgriffith/bad-daves-robot-army](https://github.com/dgriffith/bad-daves-robot-army) | 61 | Claude Code 工件仓库，包含子代理、斜杠命令和钩子 | [SAFE](https://agentskillshub.top/skill/dgriffith/bad-daves-robot-army/) |
| [event4u-app/agent-config](https://github.com/event4u-app/agent-config) | 19 | Claude Code 的 skill、规则、斜杠命令和子 agent，按意图路由并编译到其他编程 agent；所有声明均经机器检查，包括徽章中的产物数量。 | [SAFE](https://agentskillshub.top/skill/event4u-app/agent-config/) |
| [HamzaAlayed/laravel-claude-agents](https://github.com/HamzaAlayed/laravel-claude-agents) | 12 | Laravel 项目的18个 Claude Code 子agent，覆盖调研、排序、架构、设计和前后端开发。 | [SAFE](https://agentskillshub.top/skill/HamzaAlayed/laravel-claude-agents/) |

<a id="type-tooling"></a>
## 🛠 管理与生成工具

[在在线页面打开这一类,按星数排序 →](https://agentskillshub.top/best/claude-code-hooks/#type-tooling)

<table><tr>
<td align="center" valign="top"><a href="https://github.com/Moviw/codex-statusline"><img src="assets/previews/Moviw__codex-statusline.gif" width="260" alt="Moviw/codex-statusline"></a><br><sub><a href="https://github.com/Moviw/codex-statusline">Moviw/codex-statusline</a></sub></td>
<td align="center" valign="top"><a href="https://github.com/rootstudioyaml/sprag"><img src="assets/previews/rootstudioyaml__sprag.gif" width="260" alt="rootstudioyaml/sprag"></a><br><sub><a href="https://github.com/rootstudioyaml/sprag">rootstudioyaml/sprag</a></sub></td>
<td align="center" valign="top"><a href="https://github.com/aunysillyme/lean-browser-use"><img src="assets/previews/aunysillyme__lean-browser-use.gif" width="260" alt="aunysillyme/lean-browser-use"></a><br><sub><a href="https://github.com/aunysillyme/lean-browser-use">aunysillyme/lean-browser-use</a></sub></td>
</tr></table>

| 仓库 | 星数 | 做什么 | 安全评级 |
|---|---:|---|---|
| [tintinweb/pi-subagents](https://github.com/tintinweb/pi-subagents) | 1.4k | 为 Pi 提供类似 Claude Code 的子代理与工作流编排：并行执行、实时组件、代理群视图、自定义代理类型、运行中调整、兼容 Claude 的动态工作流等 | [SAFE](https://agentskillshub.top/skill/tintinweb/pi-subagents/) |
| [nilbuild/claude-statusline](https://github.com/nilbuild/claude-statusline) | 1.4k | 我个人使用的极简 Claude Code 状态栏配置 | [SAFE](https://agentskillshub.top/skill/nilbuild/claude-statusline/) |
| [blader/taskmaster](https://github.com/blader/taskmaster) | 533 | Claude Code 的停止钩子，让 agent 持续工作，直到所有计划和用户请求全部完成 | [SAFE](https://agentskillshub.top/skill/blader/taskmaster/) |
| [Ido-Levi/claude-code-tamagotchi](https://github.com/Ido-Levi/claude-code-tamagotchi) | 436 | Claude Code 的实时行为约束，监控 AI 操作，检测违规并中断不当行为，还带有可爱的宠物。 | [SAFE](https://agentskillshub.top/skill/Ido-Levi/claude-code-tamagotchi/) |
| [tmck-code/yet-another-statusline](https://github.com/tmck-code/yet-another-statusline) | 246 | 受终端监控程序启发的 Claude Code 状态栏 | [SAFE](https://agentskillshub.top/skill/tmck-code/yet-another-statusline/) |
| [gugug168/cute-claude-hooks](https://github.com/gugug168/cute-claude-hooks) | 205 | Claude Code 界面汉化工具与 Hooks 集合 | [SAFE](https://agentskillshub.top/skill/gugug168/cute-claude-hooks/) |
| [Siigari/claude-heartbeat](https://github.com/Siigari/claude-heartbeat) | 184 | 让 Claude Code 无需 -p 持续运行并自主工作。心跳 hook + 收件箱/发件箱模式。 | [SAFE](https://agentskillshub.top/skill/Siigari/claude-heartbeat/) |
| [leonardsellem/codex-subagents-mcp](https://github.com/leonardsellem/codex-subagents-mcp) | 161 | 通过轻量 MCP server 为 Codex CLI 提供 reviewer、debugger、security 子代理，隔离上下文并注入 persona… | [SAFE](https://agentskillshub.top/skill/leonardsellem/codex-subagents-mcp/) |
| [martinemde/starship-claude](https://github.com/martinemde/starship-claude) | 151 | 通过 starship 显示 Claude 状态栏 | [SAFE](https://agentskillshub.top/skill/martinemde/starship-claude/) |
| [qkal/Canny](https://github.com/qkal/Canny) | 134 | 阻止 AI coding agents 在无证据时声称完成工作。确定性 hooks 判定，TypeSafe 的 Jev 提供建议。追加式账本，零运行时依赖。 | [SAFE](https://agentskillshub.top/skill/qkal/Canny/) |
| [ghy196830-del/agent-watch-approve](https://github.com/ghy196830-del/agent-watch-approve) | 124 | 在 Apple Watch 上批准 Claude Code / Codex 的危险操作，任务完成时提醒 | [SAFE](https://agentskillshub.top/skill/ghy196830-del/agent-watch-approve/) |
| [shintaro-sprech/agent-orchestrator-template](https://github.com/shintaro-sprech/agent-orchestrator-template) | 124 | 面向 Claude Code 的自进化子代理系统 | [SAFE](https://agentskillshub.top/skill/shintaro-sprech/agent-orchestrator-template/) |
| [rinadelph/Rapala](https://github.com/rinadelph/Rapala) | 107 | rins_hooks - 自动提交 Claude Code 的每次编辑并附带上下文，方便回退。 | [SAFE](https://agentskillshub.top/skill/rinadelph/Rapala/) |
| [cozytab/fable5-mode](https://github.com/cozytab/fable5-mode) | 106 | 让 Opus 4.8 或任意 Claude 模型像 Claude Fable 5 一样工作：用 Claude Code skill 和 guard hooks… | [SAFE](https://agentskillshub.top/skill/cozytab/fable5-mode/) |
| [KimYx0207/HookPrompt](https://github.com/KimYx0207/HookPrompt) | 102 | Claude Code 自动提示词优化 Hook，含 5 个任务元提示词 | [SAFE](https://agentskillshub.top/skill/KimYx0207/HookPrompt/) |
| [shinpr/sub-agents-mcp](https://github.com/shinpr/sub-agents-mcp) | 98 | 用 Markdown 为任何兼容 MCP 的工具定义特定任务的 AI 子代理。 | [SAFE](https://agentskillshub.top/skill/shinpr/sub-agents-mcp/) |
| [abhisekjha/pith](https://github.com/abhisekjha/pith) | 97 | Pith 是用于延长 Claude Code 会话的 hook | [SAFE](https://agentskillshub.top/skill/abhisekjha/pith/) |
| [sorosora/arcade-statusline](https://github.com/sorosora/arcade-statusline) | 82 | Claude Code 街机主题状态栏：Pac-Man 风格追逐游戏与 Pikmin Bloom 风格花径 | [SAFE](https://agentskillshub.top/skill/sorosora/arcade-statusline/) |
| [sathish316/pied-piper](https://github.com/sathish316/pied-piper) | 81 | Pied Piper 是一组 AI SubAgents，可自主或半自主处理复杂编码任务，支持端到端跟踪和人工审批，运行于 Claude Code、Docker… | [SAFE](https://agentskillshub.top/skill/sathish316/pied-piper/) |
| [webdevtodayjason/claude-hooks](https://github.com/webdevtodayjason/claude-hooks) | 74 | 通过 CLI 管理 Claude Code Hooks。 | [SAFE](https://agentskillshub.top/skill/webdevtodayjason/claude-hooks/) |
| [PsChina/deepseek-as-subagent](https://github.com/PsChina/deepseek-as-subagent) | 58 | 在 Claude Code / Codex CLI 中运行 DeepSeek 子 agent，拥有独立的 7 工具循环、工作区文件访问和受限 Bash。 | [SAFE](https://agentskillshub.top/skill/PsChina/deepseek-as-subagent/) |
| [anhannin/codex-hud](https://github.com/anhannin/codex-hud) | 55 | Codex CLI 的 Claude-HUD 风格状态栏：一览模型、git 及 5h/7d 使用量。 | [SAFE](https://agentskillshub.top/skill/anhannin/codex-hud/) |
| [CoderMageFox/claudecode-codex-subagents](https://github.com/CoderMageFox/claudecode-codex-subagents) | 50 | 用于编排复杂任务的 Claude Code 插件，可委派多个并行 Codex agent，再合并并审查结果。 | [SAFE](https://agentskillshub.top/skill/CoderMageFox/claudecode-codex-subagents/) |
| [Carlos-Dominguez-faber/claude-code-tune-kit](https://github.com/Carlos-Dominguez-faber/claude-code-tune-kit) | 41 | Claude Code 配置：上下文信号灯、精简模式、4 个 hooks 阻止破坏性命令和机密、无冗余输出、GLM 不接管配置，以及审计安装并提示缺失项的 c… | [SAFE](https://agentskillshub.top/skill/Carlos-Dominguez-faber/claude-code-tune-kit/) |
| [JochenYang/minimax-status](https://github.com/JochenYang/minimax-status) | 33 | MiniMax token-plan 状态栏，显示使用额度、剩余次数和重置时间，支持vscode、openclaw和claude code statusline | [SAFE](https://agentskillshub.top/skill/JochenYang/minimax-status/) |
| [Evolutionairy-AI/MINDLAS](https://github.com/Evolutionairy-AI/MINDLAS) | 31 | Mindlas 在坏代码落地前发现 agent 偏离，实时纠正 Claude Code 会话中的上下文腐化、未验证完成声明、补丁蔓延和工具循环。 | [SAFE](https://agentskillshub.top/skill/Evolutionairy-AI/MINDLAS/) |
| [Moviw/codex-statusline](https://github.com/Moviw/codex-statusline) | 22 | Codex CLI 和 Claude Code 状态栏：上下文、5小时/每周配额及重置时间、令牌。 | [CAUTION](https://agentskillshub.top/skill/Moviw/codex-statusline/) |
| [xwk-911/rulehook](https://github.com/xwk-911/rulehook) | 22 | 一个自然语言策略文件，为 Claude Code、Codex 和 Cursor 提供提示词执行钩子。 | [SAFE](https://agentskillshub.top/skill/xwk-911/rulehook/) |
| [safe-agentic-world/nomos](https://github.com/safe-agentic-world/nomos) | 19 | Claude Code/Codex 拒绝钩子：按 Git 规则检查调用；--dangerously-skip-permissions 仍生效，拒绝不可解析命令… | [SAFE](https://agentskillshub.top/skill/safe-agentic-world/nomos/) |
| [ticpu/ccusage-statusline-rs](https://github.com/ticpu/ccusage-statusline-rs) | 18 | Claude Code 使用状态栏的 Rust 实现。 | [CAUTION](https://agentskillshub.top/skill/ticpu/ccusage-statusline-rs/) |
| [ratelworks/token-horse](https://github.com/ratelworks/token-horse) | 14 | 用于 Claude Code 状态栏和 Codex CLI 会话的 Token 用量互动马宠 | [SAFE](https://agentskillshub.top/skill/ratelworks/token-horse/) |
| [vincent-k2026/codachi](https://github.com/vincent-k2026/codachi) | 14 | 住在 Claude Code 状态栏中的电子宠物 | [SAFE](https://agentskillshub.top/skill/vincent-k2026/codachi/) |
| [aromanarguello/claude-statusline](https://github.com/aromanarguello/claude-statusline) | 13 | Claude Code 的多行状态栏 | [SAFE](https://agentskillshub.top/skill/aromanarguello/claude-statusline/) |
| [artischocki/agent-usage-tmux](https://github.com/artischocki/agent-usage-tmux) | 13 | tmux 状态栏中的 Claude / Codex 使用量 | [SAFE](https://agentskillshub.top/skill/artischocki/agent-usage-tmux/) |
| [kostyay/claude-status](https://github.com/kostyay/claude-status) | 12 | Claude Code CLI 可自定义状态栏，显示 Git 状态、GitHub CI、token 使用量和任务跟踪（Claude tasks、kt、tk、b… | [SAFE](https://agentskillshub.top/skill/kostyay/claude-status/) |
| [micschr0/claudebar](https://github.com/micschr0/claudebar) | 12 | Claude Code 的 Powerline 风格状态栏。Rust CLI，带 TUI 配置器、主题和样式 | [SAFE](https://agentskillshub.top/skill/micschr0/claudebar/) |
| [lefProg/claudial](https://github.com/lefProg/claudial) | 10 | 在 Claude Code、Cursor、VS Code 和 Antigravity 状态栏显示球队实时比分，终端面板提示进球和红牌。支持英超、西甲、欧冠等，… | [SAFE](https://agentskillshub.top/skill/lefProg/claudial/) |
| [meresiam/claude-statusline](https://github.com/meresiam/claude-statusline) | 10 | Claude Code 动态状态栏：13 个主题、Gen1 像素精灵、AI 主题生成器和 Theme Studio（pnpm monorepo） | [SAFE](https://agentskillshub.top/skill/meresiam/claude-statusline/) |
| [sravan27/context-os](https://github.com/sravan27/context-os) | 10 | Claude Code 首轮开对文件：注入本地静态分析图，无 embeddings/server，MIT；冷缓存少40.9% tokens；含 Codex/C… | [SAFE](https://agentskillshub.top/skill/sravan27/context-os/) |
| [PatrickJaiin/status-line-claude-code](https://github.com/PatrickJaiin/status-line-claude-code) | 9 | Claude Code 和 Codex 的实用状态行合集 | [SAFE](https://agentskillshub.top/skill/PatrickJaiin/status-line-claude-code/) |
| [syou6162/ccstatusline](https://github.com/syou6162/ccstatusline) | 9 | 使用 YAML 配置的 Claude Code 可定制状态栏工具：处理 JSON 输入，执行 shell 命令并输出彩色状态栏。 | [SAFE](https://agentskillshub.top/skill/syou6162/ccstatusline/) |
| [Adiazgallici/isclaude-2x](https://github.com/Adiazgallici/isclaude-2x) | 8 | Claude Code 状态栏——显示是否处于 2x 模式（2026 年 3 月） | [CAUTION](https://agentskillshub.top/skill/Adiazgallici/isclaude-2x/) |
| [AfreenLikeCaffeine/claude-prayer-statusline](https://github.com/AfreenLikeCaffeine/claude-prayer-statusline) | 8 | Claude Code 状态栏的伊斯兰祷告时间倒计时。零依赖，自动安装。 | [SAFE](https://agentskillshub.top/skill/AfreenLikeCaffeine/claude-prayer-statusline/) |
| [Spobi/context-carwash](https://github.com/Spobi/context-carwash) | 8 | Context Carwash：完整会话上下文大小可见；重新开始，不丢失细节且无文件夹杂物 | [SAFE](https://agentskillshub.top/skill/Spobi/context-carwash/) |
| [xiyouMc/grok-hud](https://github.com/xiyouMc/grok-hud) | 8 | Grok（xAI CLI）实时状态 HUD：显示上下文用量、git 分支和工具活动，支持插件安装的 claude-hud 风格外部状态栏。 | [SAFE](https://agentskillshub.top/skill/xiyouMc/grok-hud/) |
| [fyko/claudehud](https://github.com/fyko/claudehud) | 7 | a feature-rich claude code statusline written in rust | [SAFE](https://agentskillshub.top/skill/fyko/claudehud/) |
| [SergioTEC/claude-statusline](https://github.com/SergioTEC/claude-statusline) | 7 | Claude Code 实时状态栏，显示 token 用量、模型、费用和计划限额，始终位于终端底部。 | [SAFE](https://agentskillshub.top/skill/SergioTEC/claude-statusline/) |
| [disconnect13/claude-code-statusline](https://github.com/disconnect13/claude-code-statusline) | 7 | Claude Code 的令牌、上下文和 agent 实时仪表盘，零轮询，纯 stdin | [SAFE](https://agentskillshub.top/skill/disconnect13/claude-code-statusline/) |
| [martinoyovo/claude-pulse](https://github.com/martinoyovo/claude-pulse) | 7 | Claude Code CLI 的状态栏和桌面通知，codex-pulse 的对应工具。依赖少（bash/sh + jq）。 | [SAFE](https://agentskillshub.top/skill/martinoyovo/claude-pulse/) |
| [mpaiva/a11y-tips-statusline](https://github.com/mpaiva/a11y-tips-statusline) | 7 | Claude Code 的 WCAG 无障碍提示，在状态栏轮换显示无障碍指南。 | [SAFE](https://agentskillshub.top/skill/mpaiva/a11y-tips-statusline/) |
| [rootstudioyaml/sprag](https://github.com/rootstudioyaml/sprag) | 7 | Claude Code 和 Codex 的模型委派路由器：查询、检查和测试运行交给更便宜的模型，节省额显示在状态栏。 | [SAFE](https://agentskillshub.top/skill/rootstudioyaml/sprag/) |
| [aunysillyme/lean-browser-use](https://github.com/aunysillyme/lean-browser-use) | 6 | 在 Claude Code 中将浏览器使用成本降低约25%：全新 runner subagent、批量读取、三重防护和 token meter。一个 npx… | [SAFE](https://agentskillshub.top/skill/aunysillyme/lean-browser-use/) |
| [jiunbae/aily](https://github.com/jiunbae/aily) | 6 | Claude Code 通知钩子——Discord 通知，按 tmux 会话建立独立线程 | [SAFE](https://agentskillshub.top/skill/jiunbae/aily/) |
| [josheche/statusmon](https://github.com/josheche/statusmon) | 6 | 在 Claude Code 状态栏中训练 Pokémon。 | [SAFE](https://agentskillshub.top/skill/josheche/statusmon/) |
| [Isllanrx/status_cli](https://github.com/Isllanrx/status_cli) | 5 | Claude Code、Codex 和 Antigravity CLI 的 Rust 状态栏 | [SAFE](https://agentskillshub.top/skill/Isllanrx/status_cli/) |
| [VibeCodeBlogger-Public/ai-agent-setup-instructions-claude-code-statusline-context-window-usage-bar-model-tokens-bash](https://github.com/VibeCodeBlogger-Public/ai-agent-setup-instructions-claude-code-statusline-context-window-usage-bar-model-tokens-bash) | 5 | Claude Code 状态栏的 AI-agent 设置说明：安装彩色上下文窗口使用率条（百分比居中），显示 effort、model、tokens，含正确示… | [SAFE](https://agentskillshub.top/skill/VibeCodeBlogger-Public/ai-agent-setup-instructions-claude-code-statusline-context-window-usage-bar-model-tokens-bash/) |
| [jig21nesh/model-switcher](https://github.com/jig21nesh/model-switcher) | 5 | Claude Code 按提示词路由模型并离线跟踪成本，简单任务低成本，复杂任务交给更强模型。 | [SAFE](https://agentskillshub.top/skill/jig21nesh/model-switcher/) |
| [joshi008/agent-statusline](https://github.com/joshi008/agent-statusline) | 5 | 一个 YAML 文件，为 Claude Code、Cursor CLI 和 Codex CLI 提供统一状态行。 | [CAUTION](https://agentskillshub.top/skill/joshi008/agent-statusline/) |
| [kukushking/claude-status](https://github.com/kukushking/claude-status) | 5 | Claude Code 实时状态栏：显示 token 用量、成本、缓存命中、上下文窗口压力和 Claude.ai 速率限制用量，每次响应后更新。 | [SAFE](https://agentskillshub.top/skill/kukushking/claude-status/) |

**安全评级**是 Agent Skills Hub 对仓库 README 和安装步骤的评级。*待评级*表示目录还没评到它。

预览图是各项目 README 里图片的缩小副本,只收录采用宽松许可证的项目,版权归原作者所有。来源和许可证见 [assets/previews/NOTICE.md](assets/previews/NOTICE.md)。如需移除请提 issue。

## 相关合集

- [zhuyansen/awesome-claude-video-skills](https://github.com/zhuyansen/awesome-claude-video-skills), [zhuyansen/awesome-codex-ppt-skills](https://github.com/zhuyansen/awesome-codex-ppt-skills) —— 同样做法的合集。

## 推荐仓库

提一个 issue 附上 GitHub 链接。它会走和每个条目一样的评审;决定上不上榜的是上面的规则,不是星数。

---

机器可读版本:[`data/skills.json`](data/skills.json)。生成于 2026-11-09。
