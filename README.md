# n8n Workflow Collection

这个仓库整理了几套日常在 n8n 中使用的自动化流程，主要覆盖飞书 / Lark、多维表格（Bitable）、社媒数据采集与更新。

目前仓库中的 workflow 已按用途拆分目录，并做了脱敏处理，适合继续整理后推送到 GitHub。仓库里保留的是可公开分享的导出版本，不包含可直接使用的生产密钥、Webhook 标识和业务配置。

## 工作流清单

### 1. Lark / 飞书
- `workflows/Lark/FeishuBotBitable/`
- 用途：接收飞书机器人消息，结合 DeepSeek 生成字段内容和 PRD，再写入 Bitable。

### 2. SocialMediaTracker
- `workflows/SocialMediaTracker/Create/`
- 用途：根据社媒主页链接，新建一张当月数据表并批量采集帖子数据。
- `workflows/SocialMediaTracker/Update/`
- 用途：读取已有表格中的记录，按平台分支更新 Instagram / X / YouTube / Facebook 的帖子数据。

### 3. 平台独立版本
- `workflows/Instagram/`
- `workflows/X/`
- `workflows/Youtube/`
- `workflows/Facebook/`
- 用途：把主流程中的平台分支拆成可单独导入的独立 workflow，方便单平台维护和分享。

## 仓库结构

```text
workflows/
  Lark/
    FeishuBotBitable/
  SocialMediaTracker/
    Create/
    Update/
  Instagram/
    Create/
    Update/
  X/
    Create/
    Update/
  Youtube/
    Create/
    Update/
  Facebook/
    Create/
    Update/
```

## 依赖服务

使用这些流程前，通常需要先准备：
- n8n
- Feishu / Lark 开放平台应用
- Feishu Bitable
- DeepSeek API
- Apify

> 说明：Instagram / X / Youtube / Facebook 这几套平台 workflow 都是基于 Apify 的 Actor 能力来跑的。要想真正开通外部调用 API / 数据抓取能力，通常需要你的 Apify 账号已开通对应订阅、额度或付费权限；如果账号没有开通，导入 workflow 也可能无法正常调用。

## 使用方式

1. 选择对应目录下的 `.redacted.json` 文件导入 n8n。
2. 按 README 中的说明，把占位符替换成你自己的配置。
3. 在 n8n 中重新绑定凭证、Webhook、表格 ID、平台链接等参数。
4. 如果是平台类 workflow，先确认 Apify 账号已经具备对应 Actor 的可调用权限。
5. 先在测试环境跑通，再接入正式环境。

## 安全说明

为了方便公开分享，仓库里的 workflow 导出已经做了脱敏处理，重点包括：
- Feishu / Lark `app_id`、`app_secret`
- DeepSeek API Key
- Webhook path / webhookId
- Bitable app / table / record 相关 ID
- Apify credential 引用
- 业务 profile URL 和内部地址

如果你准备继续新增 workflow，建议也保持同样的处理方式，不要直接提交原始导出文件。

## 目录入口

- [Lark / 飞书工作流](./workflows/Lark/FeishuBotBitable/README.md)
- [SocialMediaTracker 总览](./workflows/SocialMediaTracker/README.md)
- [SocialMediaTracker / Create](./workflows/SocialMediaTracker/Create/README.md)
- [SocialMediaTracker / Update](./workflows/SocialMediaTracker/Update/README.md)
- [Instagram 总览](./workflows/Instagram/README.md)
- [Instagram / Create](./workflows/Instagram/Create/README.md)
- [Instagram / Update](./workflows/Instagram/Update/README.md)
- [X 总览](./workflows/X/README.md)
- [X / Create](./workflows/X/Create/README.md)
- [X / Update](./workflows/X/Update/README.md)
- [Youtube 总览](./workflows/Youtube/README.md)
- [Youtube / Create](./workflows/Youtube/Create/README.md)
- [Youtube / Update](./workflows/Youtube/Update/README.md)
- [Facebook 总览](./workflows/Facebook/README.md)
- [Facebook / Create](./workflows/Facebook/Create/README.md)
- [Facebook / Update](./workflows/Facebook/Update/README.md)

## 说明

这个仓库更适合作为 workflow 样例、结构参考和内部复用基础。不同团队的字段设计、表结构和平台策略不一样，导入后基本都需要按自己的业务重新改一遍配置。