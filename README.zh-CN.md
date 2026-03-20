# n8n Workflow Collection

[English](./README.md) | 简体中文

这是一个整理后的 n8n 工作流仓库，主要包含经过脱敏处理的 Feishu / Lark、Bitable，以及社媒数据采集与更新相关 workflow。

## 包含内容

### Lark / 飞书
- [`workflows/Lark/FeishuBotBitable/`](./workflows/Lark/FeishuBotBitable/README.zh-CN.md)
- 将飞书机器人消息转换为结构化 Bitable 记录，并生成 PRD 内容。

### SocialMediaTracker
- [`workflows/SocialMediaTracker/Create/`](./workflows/SocialMediaTracker/Create/README.zh-CN.md)
- 创建当月数据表，并批量导入社媒帖子数据。

- [`workflows/SocialMediaTracker/Update/`](./workflows/SocialMediaTracker/Update/README.zh-CN.md)
- 更新 Instagram、X、YouTube、Facebook 的已有记录。

### 平台独立工作流
- [`workflows/Instagram/`](./workflows/Instagram/README.zh-CN.md)
- [`workflows/X/`](./workflows/X/README.zh-CN.md)
- [`workflows/Youtube/`](./workflows/Youtube/README.zh-CN.md)
- [`workflows/Facebook/`](./workflows/Facebook/README.zh-CN.md)

这些目录提供拆分后的单平台 workflow，便于单独复用和维护。

## 依赖服务

大部分 workflow 需要以下服务或账号：
- n8n
- Feishu / Lark 开放平台
- Feishu Bitable
- DeepSeek API
- Apify

> 社媒相关 workflow 依赖 Apify Actor。仅导入 workflow 并不代表一定可用，Apify 账号仍需具备对应权限、额度或订阅能力。

## 快速开始

1. 将目标 `.redacted.json` 文件导入 n8n。
2. 按文档把占位符替换成自己的凭证、ID 和链接。
3. 在 n8n 中重新绑定凭证、Webhook、表格 ID 和平台参数。
4. 先在测试环境验证。
5. 确认无误后再启用或配置定时执行。

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

## 安全说明

仓库中的 workflow 导出均已做脱敏处理，移除或替换的内容包括：
- Feishu / Lark 应用凭证
- DeepSeek API Key
- Webhook path 和 ID
- Bitable app、table、record 相关标识
- Apify credential 引用
- 内部 profile URL 和业务地址

如果后续继续新增 workflow，建议保持同样的脱敏标准后再提交。

## 文档入口

- [Lark / 飞书工作流](./workflows/Lark/FeishuBotBitable/README.zh-CN.md)
- [SocialMediaTracker 总览](./workflows/SocialMediaTracker/README.zh-CN.md)
- [SocialMediaTracker / Create](./workflows/SocialMediaTracker/Create/README.zh-CN.md)
- [SocialMediaTracker / Update](./workflows/SocialMediaTracker/Update/README.zh-CN.md)
- [Instagram 总览](./workflows/Instagram/README.zh-CN.md)
- [Instagram / Create](./workflows/Instagram/Create/README.zh-CN.md)
- [Instagram / Update](./workflows/Instagram/Update/README.zh-CN.md)
- [X 总览](./workflows/X/README.zh-CN.md)
- [X / Create](./workflows/X/Create/README.zh-CN.md)
- [X / Update](./workflows/X/Update/README.zh-CN.md)
- [Youtube 总览](./workflows/Youtube/README.zh-CN.md)
- [Youtube / Create](./workflows/Youtube/Create/README.zh-CN.md)
- [Youtube / Update](./workflows/Youtube/Update/README.zh-CN.md)
- [Facebook 总览](./workflows/Facebook/README.zh-CN.md)
- [Facebook / Create](./workflows/Facebook/Create/README.zh-CN.md)
- [Facebook / Update](./workflows/Facebook/Update/README.zh-CN.md)

## 说明

这个仓库更适合作为可复用 workflow 样例和公开导出集合。导入后通常仍需要根据自己的字段设计、表结构、凭证和业务规则做调整。
