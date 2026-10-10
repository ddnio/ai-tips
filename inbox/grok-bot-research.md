# Grok Bot 调研底稿

调研及复核日期：2026-10-10（上海时间）。用途：支撑文章的一、二级要点。结构见 [完整大纲 v4](first-article-outline-v4.md)，口述见 [口述提纲](first-article-speak-outline.md)。

标记约定：“官方事实”来自下列原始文档；“写作解释”是帮助读者理解的组织方式；“作者待补”需要本人经历，调研不能代替。

## 1. 产品定位与工作方式

**官方事实：** Grok Bot 提供持久的 AI 工作伙伴，通过消息承接任务，在带有浏览器、终端和文件的云端电脑上执行多步工作，再交付结果或请求用户介入。关闭本地电脑不会直接停止后台云端任务。默认云端执行，同时支持经授权的本地操作。[产品概述](https://cursor.com/docs/grok-bot)、[FAQ](https://cursor.com/help/grok-bot/faqs)、[安全说明](https://cursor.com/docs/grok-bot/security)

**写作解释：** 先说“给它目标、资料和工具访问，它去处理，你检查交付”，再解释 personal agent。模型负责判断与生成，Bot 承担持续职责，云电脑提供执行环境；这三个层次是本文解释框架。

**重要更正：** 同一账号的多个 Bot 共享一台持久云电脑、文件和网站登录状态，各有屏幕；各自保留角色、对话和工作记忆。不能写成“每个 Bot 独占一台 VM”，也不能用不同角色名称保证权限隔离。[工作说明](https://cursor.com/docs/grok-bot/work)

作者待补：自己的 Bot 分工、电脑配置与实际运行画面。没有查到所有账号统一的“高配”硬件规格承诺；配置截图只代表本人实例。

## 2. 能力怎样组成工作流程

| 能力 | 官方支持与边界 | 写作用途 |
| --- | --- | --- |
| 多 Bot | 创建角色、群聊、交接工作；共享电脑 | 展示分工怎样减少反复交代 |
| 应用接入 | 插件使用授权账号现有权限；安装后还需完成授权 | 围绕案例说明接入工具及实际读写 |
| Skill | 保存可复用方法 | 解释“以后怎么做” |
| Routine | 按时间或支持的事件触发 | 解释“什么时候做”；先完成一次再自动化 |
| 模板分享 | 可分享配置，不等于复制历史、登录或整台电脑 | 区分导入岗位与接管已有工作环境 |
| 手机端 | iOS、Android；同账号跟进工作；电脑恢复操作需桌面端 | 说明跨设备查看、派任务、接手步骤 |

来源：[工作说明](https://cursor.com/docs/grok-bot/work)、[插件授权](https://cursor.com/help/grok-bot/connect-plugins)、[Routine](https://cursor.com/help/grok-bot/routines)、[移动端](https://cursor.com/help/grok-bot/mobile)。

网站可以要求登录、验证码或阻挡云端访问，不能写成“任意网站都能操作”。Routine 的测试会真正执行工作；触发成功和交付成功应分别检查。时区、执行记录、频率与额度都需要观察。[FAQ](https://cursor.com/help/grok-bot/faqs)、[Routine](https://cursor.com/help/grok-bot/routines)

## 3. 账号、订阅与付款

### 3.1 权益路径

官方当前列明：Cursor Pro、Pro+、Ultra 和自助 Teams 可使用；符合条件的个人 SuperGrok、SuperGrok Plus、SuperGrok Heavy 或 X Premium+ 可以关联到 Cursor 账号授予权益。SuperGrok Lite 不含。自助 Grok Business 分配席位通过持有席位的 Grok 账号登录；企业账号按管理员或合同配置处理。[套餐帮助](https://cursor.com/help/grok-bot/plans)

常规正文以作者实际采用的一条路径为主，不说所有用户都必须先买 Cursor Pro。Grok/X 关联不会改变原有 Cursor 套餐；已有 Cursor 权益与关联权益不叠加，两份订阅仍可能分别收费。关联不能随意解除或迁移到另一个 Cursor 账号。[关联说明](https://cursor.com/help/grok-bot/supergrok)

### 3.2 价格与支付

Cursor 个人月付标价：Pro 20 美元、Pro+ 60 美元、Ultra 200 美元。Grok Bot 的包含用量逐档提高，但不能用编辑器的用量倍率推算 Bot 周额度；本次资料未给出适用于所有账号的固定任务次数。[价格帮助](https://cursor.com/help/account-and-billing/pricing)、[Bot 套餐](https://cursor.com/help/grok-bot/plans)

支付宝有官方论坛工作人员回复支持；2026-05-29 的回复说明显示与地区、币种、升级套餐有关。本轮未进入作者结账页，不能保证“选择 CNY 就出现支付宝”或“清缓存就修好”。作者需补付款入口、币种、套餐周期、实付金额和测试日期。[付款说明](https://forum.cursor.com/t/i-wish-cursor-could-support-alipay-payment/100728)

### 3.3 老账号排障

Privacy Mode（Legacy）与旧 request-based 计费是不同状态。上手文档提示旧隐私模式要切换；官方论坛 2026-08-28 回复确认，旧 request-based 用户需选择 usage-based 才能使用。团队文档也列明这两项会阻止启用。[上手文档](https://cursor.com/docs/grok-bot/get-started)、[论坛回复](https://forum.cursor.com/t/cursor-says-grok-bot-is-included-with-pro-now-do-you-actually-have-access-yet/169808/10)、[团队文档](https://cursor.com/docs/grok-bot/teams)

不能把“所有老用户”都归入旧套餐。本人的迁移影响和当前提示以 Dashboard 为准；旧底稿引用的论坛 #17 本次无法读取，其“单向切换、唯一办法”等额外结论不作为已核实操作建议。request-based Teams / Enterprise 不能套用个人 SuperGrok 关联路径。[套餐帮助](https://cursor.com/help/grok-bot/plans)

## 4. 用量、试用与额外费用

- 包含用量按周重置。试用是用量额度，并有 7 天窗口；不是 7 天无限使用。
- 工作消耗按执行步骤和 tokens 计算，不能以聊天消息条数估算。
- 开启 On-demand 后，包含用量耗尽可继续计费，通过 Cursor 账单计入月度按需上限；运行中的任务可能先完成，再停止后续按需用量。
- 没开启按需用量时，包含周额度耗尽后不能继续；提高 Routine 频率会增加消耗。
- Grok Bot 用量在 Cursor 账号计量；手机登录不增加第二份权益，也不能把 Cursor 编辑器月额度直接当作 Bot 周额度。
- Grok Bot 的用量试用不会自动转付费。Apple 的 App Store intro offer 是另一种试用，会按 Apple 订阅规则续订，不能混用这两种说法。

来源：[套餐与试用](https://cursor.com/help/grok-bot/plans)、[Routine](https://cursor.com/help/grok-bot/routines)。

作者待补：套餐、任务范围、运行次数、用量前后变化、是否开启按需、是否影响交付。“额度不够”应写成具体经历。

## 5. 模型与 Bot 邮箱

### 5.1 模型

当前由系统按任务选择 xAI 或第三方模型；用户不能手动指定、切换或屏蔽具体模型，界面也不披露每个请求使用的模型。删除“最近新增模型切换”；不能用模型自报或旁人帖子确认“满血 Opus”。[模型帮助](https://cursor.com/help/grok-bot/models)

### 5.2 邮箱

官方提供 `mail.grokbot.com` 地址，可接收、读取、搜索、发送邮件；可请求 Bot 申请并确认，或使用 Email 插件。新邮件不会自动唤醒 Bot，需设置相应 Routine；团队需管理员启用。Bot 自有邮箱与接入个人 Gmail 是两种入口；不推定每个角色都获得独立隔离邮箱。[邮箱帮助](https://cursor.com/help/grok-bot/agent-email)

作者未实用时，只作能力介绍或附录，不编造收发成功记录。首次上线版本本轮未确认。

## 6. 云电脑、网络与恢复

### 6.1 两种网络方向

| 场景 | 链路 | 当前依据 |
| --- | --- | --- |
| 作者的代理出口案例 | 本人设备 → 本人实际连接方案 → Bot 云电脑 → 目标服务 | 作者确认意图；软件、连接方式、运行结果待补 |
| 官方 Route traffic through this computer | Bot 云电脑 → 本地电脑的网络与 IP → 目标服务 | 官方设置；不是作者方案的配置按钮 |

官方转发设置影响新连接，本地执行权限又是另一项功能。默认云电脑出口是客户共享的 IP 范围，没有专属客户出口 IP。未查到将产品作为通用代理服务的官方保证；作者案例按个人配置写，不把可持续后台任务理解成永久 VPS 服务。[设置](https://cursor.com/docs/grok-bot/settings)、[私有网络](https://cursor.com/docs/grok-bot/private-networks)

### 6.2 维护与持久化

官方区分软件更新和云电脑重建。重建、Recover、Reset 会影响自装软件和包；无法保存时很近的改动可能丢失。持久工作环境不等于所有自装配置永远保留。代理或脚本案例需要交代是否要重装、什么条件下会中断。[电脑恢复](https://cursor.com/help/grok-bot/computer-recovery)

国内可用性按作者网络、日期、开关状态和实际任务记录写；本地客户端能登录不等于云电脑目标网站、插件读写和最终任务都成功。

## 7. 三个案例的证据与讲述顺序

1. **日报作为主案例：** 原本如何做 → 交给 Bot 哪部分 → 指令与来源 → 初稿 → 纠正 → 交付 → 实际运行次数、人工介入和消耗。生成、审核与发布分开记录。
2. **X 运营作为第二案例：** 选题搜集、原帖分析、稿件或复盘中，挑实际做过的环节。官方 X 插件可搜索、读时间线、提及、趋势和书签；支持地区的 `@bot` 是任务转交，确认回复不代表工作完成。[X 文档](https://docs.x.ai/grok-bot/tag-on-x)
3. **代理作为扩展案例：** 保留云电脑广泛用途的个人例子，补软件、连接方式、结果与维护条件，篇幅短于主案例。

官方支持资料处理、用例与 Routine，不证明作者已经自动发日报、发 X 或稳定配置代理。用户未提供这些产物与完整记录。[官方用例](https://cursor.com/docs/grok-bot/use-cases)

## 8. 更新与发表前复核

2026-10-10 查阅的官方 changelog 最新列为 0.68.1（10-07）：幻灯片交付、格式化邮件等；0.68.0（10-05）包括 Gmail 发件身份和 Routine 管理；0.67.0（10-02）将 Marketplace 改为 Connect Apps。邮箱与系统模型路由按当前机制介绍，不擅自归为这些版本新增。[更新日志](https://x.ai/changelog/bot)

发表前复核价格、账号权益、下载界面与版本。补个人支付、网络、云电脑、用量和产物记录。XPass 传闻与早期 X 热度数字不作为当前产品事实或正文结论。
