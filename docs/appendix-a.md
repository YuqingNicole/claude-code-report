# 附录A · 54个工具完整清单

经过深入分析，最终确认 Claude Code 包含 **54 个工具**（含特性标志门控的条件工具），超出初步统计的 44 个。

| # | 工具名 | 实现类 | 门控条件 | 功能描述 |
|---|--------|--------|---------|---------|
| 1 | Agent | AgentTool | 无 | 启动子 Agent 执行复杂任务 |
| 2 | AskUserQuestion | AskUserQuestionTool | 无 | 向用户提问并获取答案 |
| 3 | Bash | BashTool | 无 | 执行 Shell 命令 |
| 4 | Brief | BriefTool | `KAIROS \|\| KAIROS_BRIEF` | 状态感知的精简消息 |
| 5 | Config | ConfigTool | 无 | 读写配置 |
| 6 | CronCreate | CronCreateTool | `AGENT_TRIGGERS` | 创建定时触发器 |
| 7 | CronDelete | CronDeleteTool | `AGENT_TRIGGERS` | 删除定时触发器 |
| 8 | CronList | CronListTool | `AGENT_TRIGGERS` | 列出定时触发器 |
| 9 | CtxInspect | CtxInspectTool | `CONTEXT_COLLAPSE` | 上下文检查 |
| 10 | Edit | FileEditTool | 无 | 编辑文件（精确字符串替换）|
| 11 | EnterPlanMode | EnterPlanModeTool | 无 | 进入计划模式（只读）|
| 12 | EnterWorktree | EnterWorktreeTool | Worktree 模式 | 进入 Git Worktree 隔离 |
| 13 | ExitPlanMode | ExitPlanModeTool | 无 | 退出计划模式 |
| 14 | ExitWorktree | ExitWorktreeTool | Worktree 模式 | 退出 Worktree |
| 15 | Glob | GlobTool | 无（嵌入式搜索替代）| 文件模式匹配 |
| 16 | Grep | GrepTool | 无（嵌入式搜索替代）| 内容搜索（基于 ripgrep）|
| 17 | ListMcpResources | ListMcpResourcesTool | 无 | 列出 MCP 资源 |
| 18 | ListPeers | ListPeersTool | `UDS_INBOX` | 列出对等节点 |
| 19 | LSP | LSPTool | `ENABLE_LSP_TOOL` 环境变量 | 语言服务器协议工具 |
| 20 | Monitor | MonitorTool | `MONITOR_TOOL` | 监控工具 |
| 21 | NotebookEdit | NotebookEditTool | 无 | 编辑 Jupyter Notebook |
| 22 | OverflowTest | OverflowTestTool | `OVERFLOW_TEST_TOOL` | 溢出测试（内部）|
| 23 | PowerShell | PowerShellTool | `isPowerShellToolEnabled()` | PowerShell 命令执行 |
| 24 | PushNotification | PushNotificationTool | `KAIROS \|\| KAIROS_PUSH_NOTIFICATION` | 系统推送通知 |
| 25 | Read | FileReadTool | 无 | 读取文件 |
| 26 | ReadMcpResource | ReadMcpResourceTool | 无 | 读取 MCP 资源 |
| 27 | REPL | REPLTool | `USER_TYPE=ant` | REPL 交互执行（VM 沙箱）|
| 28 | RemoteTrigger | RemoteTriggerTool | `AGENT_TRIGGERS_REMOTE` | 远程触发器 |
| 29 | SendMessage | SendMessageTool | 无 | 发送消息给其他 Agent |
| 30 | SendUserFile | SendUserFileTool | `KAIROS` | 向用户主动发送文件 |
| 31 | Skill | SkillTool | 无 | 执行技能 |
| 32 | Sleep | SleepTool | `PROACTIVE \|\| KAIROS` | AI 主动睡眠（节奏控制）|
| 33 | Snip | SnipTool | `HISTORY_SNIP` | 历史消息裁剪 |
| 34 | StructuredOutput | SyntheticOutputTool | 无 | 结构化输出 |
| 35 | SubscribePR | SubscribePRTool | `KAIROS_GITHUB_WEBHOOKS` | GitHub PR 订阅 |
| 36 | SuggestBackgroundPR | SuggestBackgroundPRTool | `USER_TYPE=ant` | 建议后台 PR |
| 37 | Task | TaskOutputTool | 无 | 获取任务输出 |
| 38 | TaskCreate | TaskCreateTool | Todo V2 | 创建任务 |
| 39 | TaskGet | TaskGetTool | Todo V2 | 获取任务详情 |
| 40 | TaskList | TaskListTool | Todo V2 | 列出任务 |
| 41 | TaskStop | TaskStopTool | 无 | 停止任务 |
| 42 | TaskUpdate | TaskUpdateTool | Todo V2 | 更新任务 |
| 43 | TeamCreate | TeamCreateTool | `AGENT_SWARMS` | 创建多 Agent 团队 |
| 44 | TeamDelete | TeamDeleteTool | `AGENT_SWARMS` | 删除团队 |
| 45 | TerminalCapture | TerminalCaptureTool | `TERMINAL_PANEL` | 终端截获 |
| 46 | TodoWrite | TodoWriteTool | 无 | 写入待办事项 |
| 47 | ToolSearch | ToolSearchTool | 乐观工具搜索启用 | 搜索可用工具（延迟加载枢纽）|
| 48 | Tungsten | TungstenTool | `USER_TYPE=ant` | 内部工具 |
| 49 | VerifyPlanExecution | VerifyPlanExecutionTool | `CLAUDE_CODE_VERIFY_PLAN` 环境变量 | 计划执行验证 |
| 50 | WebBrowser | WebBrowserTool | `WEB_BROWSER_TOOL` | 浏览器操作 |
| 51 | WebFetch | WebFetchTool | 无 | 网页内容获取（含摘要）|
| 52 | WebSearch | WebSearchTool | 无 | 网络搜索 |
| 53 | Workflow | WorkflowTool | `WORKFLOW_SCRIPTS` | 工作流脚本执行 |
| 54 | Write | FileWriteTool | 无 | 写入文件 |
