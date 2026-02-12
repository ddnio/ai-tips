+++
title = "Day 01 - Claude Code 官方文档精读：最小可用学习闭环"
date = "2026-02-12T09:10:00+08:00"
draft = false
categories = ["AI学习", "Claude Code"]
tags = ["claude-code", "documentation", "workflow", "daily-note", "learning-system"]
summary = "第一篇先不追技巧，先搭学习闭环：官方文档 -> 最小实操 -> 可验证结果 -> 可复用模板。"
+++

这篇只做一件事：把 Claude Code 官方文档整理成一个可以每天复用的学习流程。

## TL;DR（先看这 7 条）

1. Claude Code 的定位是“终端里的代理式编码工具”，不是聊天问答助手。
2. 它的核心循环是：收集上下文 -> 采取行动 -> 验证结果。
3. 复杂任务先用 Plan Mode，再执行实现，成功率明显更高。
4. `CLAUDE.md` 是长期记忆，规则应写这里，不要只写在对话里。
5. 上下文是稀缺资源，任务切换要 `/clear`，长会话要 `/compact`。
6. 想规模化使用，优先学会 headless（`-p`）和结构化输出（`--output-format`）。
7. 学习要闭环：读文档 -> 当天实操 -> 验证 -> 沉淀模板。

## 1. 官方文档的能力地图（按“能不能落地”排序）

### A. 基础层：先跑起来

- 安装后进入项目目录执行 `claude` 即可开始会话。
- 常用入口命令：`/help`、`/resume`、`/login`。
- 安装方式有差异：Native 安装自动更新；Homebrew/WinGet 需要手动升级。

### B. 工作方式层：为什么它和普通聊天工具不一样

- Claude Code 可以直接编辑文件、运行命令、调用 git 与外部工具。
- 你给它任务后，它会持续在“理解 -> 修改 -> 验证”循环中推进。
- 这意味着写 prompt 的目标不是“让它回答得好看”，而是“让它可验证地完成任务”。

### C. 质量层：结果稳不稳，取决于两件事

1. 你是否给了明确的验证标准（测试、命令、可观察输出）。
2. 你是否控制了上下文体积（`/clear`、`/compact`、短而有效的 `CLAUDE.md`）。

### D. 规模层：怎么从“好用一次”变成“长期复用”

- Plan Mode：先分析与规划，避免直接改错方向。
- Headless：`claude -p` 便于接入脚本与 CI。
- Worktrees：并行任务隔离，避免上下文与文件状态互相污染。

## 2. Day 1 最小实操清单（45 分钟）

### 0-15 分钟：建立认知地图

阅读顺序建议：

1. Overview  
2. Quickstart  
3. How Claude Code Works  
4. Best Practices  
5. Common Workflows  
6. Troubleshooting

目标不是看完细节，而是回答：

- 我现在能立即用的命令是什么？
- 我今天最可能踩什么坑？

### 15-35 分钟：跑 5 条最小命令

```bash
# 1) 进入项目并启动
claude

# 2) 看帮助和历史会话
/help
/resume

# 3) 用 Plan Mode 做一次只读分析
claude --permission-mode plan -p "Analyze this repo structure and propose a 3-step implementation plan"

# 4) 用 headless 拿结构化输出
claude -p "List key modules and responsibilities" --output-format json > repo-map.json

# 5) 验证安装健康
/doctor
```

### 35-45 分钟：做一次“可验证”小任务

示例任务：让 Claude 帮你补一段 README，然后验证构建或测试通过。  
原则：没有验证步骤，就不算完成。

## 3. 今天我采用的写作套路（以后每篇复用）

以后每篇都按下面 5 段写：

1. 主题和问题（今天要解决什么）  
2. 文档结论（来自哪一页文档）  
3. 实操命令（我实际跑了什么）  
4. 验证结果（怎么确认是对的）  
5. 踩坑与模板（下次如何更快）

这个结构的价值是：三天后仍可复现，而不是只剩“我今天学了很多”。

## 4. 常见踩坑（文档 + 实战都高频）

1. 直接上来让它改代码  
修正：先 Plan Mode，确认方向再执行。

2. 不给验证标准  
修正：提示里必须写“运行什么命令/通过什么测试算完成”。

3. 对话越聊越散  
修正：任务切换 `/clear`，长会话 `/compact`，长期规则放 `CLAUDE.md`。

4. 权限提示反复弹窗  
修正：使用 `/permissions` 白名单可信操作；高风险场景仍保持人工确认。

## 5. 明天可直接复用的模板

### Prompt 模板（探索 -> 规划 -> 执行）

```text
你是我的工程助手。请按这个流程工作：
1) 先只读分析当前仓库，列出相关文件和风险点
2) 给出 3 步实现计划，每步都写验证命令
3) 我确认后再开始改代码
4) 每完成一步先执行验证，再进入下一步
5) 最后给出 commit message 与回滚建议
```

### `CLAUDE.md` 最小模板

```markdown
# Workflow
- 先计划后执行：复杂任务默认先给计划再改代码
- 变更后必须验证：至少运行对应测试或构建命令

# Testing
- 优先跑受影响模块测试，不先跑全量
- 失败时先报告根因，再给修复方案

# Style
- 改动最小化，不做无关重构
```

## 明日计划

1. 单开一篇：`CLAUDE.md` 的项目版模板（含我自己的规则）。  
2. 增加 `new-post` 脚本，自动生成“问题-操作-验证-模板”骨架。  
3. 做一次 headless 自动化实验：把 `claude -p` 接到本地检查脚本里。  

## 参考文档

- [Claude Code 概览](https://code.claude.com/docs/zh-CN/overview)  
- [快速入门](https://code.claude.com/docs/zh-CN/quickstart)  
- [Claude Code 如何工作](https://code.claude.com/docs/zh-CN/how-claude-code-works)  
- [常见工作流程](https://code.claude.com/docs/zh-CN/common-workflows)  
- [最佳实践](https://code.claude.com/docs/zh-CN/best-practices)  
- [故障排除](https://code.claude.com/docs/zh-CN/troubleshooting)  
