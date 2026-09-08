# 全局约定

- 必须使用简体中文与我对话。
- 创建新会话时，使用如下格式的标题：`MMDD | type | Title`，便于快速索引会话
  - `MMDD` 代表创建会话时的月、日，例如 `0909`
  - `Type` 推荐使用列表：配置、探讨、设计、功能、优化 等二字词汇
  - `Title` 根据对话内容精简提炼，不要过度抽象、引入新概念
- 所有对话的所有答复必须使用 `caveman` skill 的 `default` 强度回复，除非我显式高速你停止使用 caveman，若没有安装则安装此 skill
- 优先拆解简单、确定性的任务给 SubAgent
  - SubAgent 使用 `GPT 5.6 Luna`（若有）、`DeepSeek V4 Flash`（若有）模型
  - 规划、探索、验收等深度思考、探索的任务使用 `GPT 6 Astra`、`DeepSeek V4 Pro` 模型（有哪个用哪个）
- 每次对话优先读取对话工作区下的 AGENTS.md 作为 AI 约定，若处理的上下文有更接近的 AGENTS.md 则更优先遵守
- 使用 RTK 工具
  - 若当前是 CodeX，RTK 工具的资料见 `~/.codex/RTK.md`


# 开发约定

- 若我没有明确要求，禁止自动执行 lint、test，禁止自动提交、push 代码
- 创建代码仓库时，要一起创建 README.md、AGENTS.md，使用简体中文
- 开发过程中要根据内容按需及时更新 README.md 和 AGENTS.md
  - 若文档太长，README.md 拆分到 ./docs 下，AGENTS.md 拆分到 ./.agents 下
- 所有提交信息遵守 `commit-type(scope): msg` 格式
  - `commit-type` 使用常见类型，根据提交内容推断
  - `scope` 可选，根据对话内容和仓库约定决定
  - `msg` 必须使用简体中文，可以适当加 emoji，若内容较多可以附多行消息
- 若对话的工作目录是 git 仓库，及时补上（若没有）`.gitattributes` 文件，若有则补齐规则，必须使用 lf 换行符

# 本机环境和工具

- 若当前操作系统是 MacOS/Linux（含 WSL），使用 `sh`
- 若当前操作系统是 Windows，使用 `nushell`，若没有安装，回退使用 pwsh（7+）或 gitbash，若仍没有，回退使用 cmd
- 本机安装了 `mise` 管理 `nodejs`、`golang` 语言 SDK
- 本机安装了 `bun`

# 创建 NodeJS 包的约定

参考 [./references/create-node-package-rules.md](`./references/create-node-package-rules.md`)

# TypeScript 代码习惯

参考 [./references/dev-typescript-rules.md](`./references/dev-typescript-rules.md`)

# Vue.js 代码习惯

查阅 [./references/dev-vuejs-rules.md](`./references/dev-vuejs-rules.md`)
