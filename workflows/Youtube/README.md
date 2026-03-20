# Youtube

English | [简体中文](./README.zh-CN.md)

This folder contains standalone n8n workflows for YouTube.

## Contents

- `Create/youtube-create.redacted.json`
- `Update/youtube-update.redacted.json`

## When to use each workflow

### Create
Create a new YouTube tracking table and import collected data from channels or videos.

### Update
Refresh video performance data from existing records and write it back to the original table.

## Dependencies

- n8n
- Feishu / Lark
- Bitable
- Apify
- The Create flow also depends on DeepSeek

## Usage notes

- Decide whether you want to collect channel, video, or Shorts data before import.
- If your table fields differ from the default mapping, adjust the field detection and mapping logic first.
- These workflows depend on Apify actors, so confirm that your Apify account has the required subscription, quota, or actor access before production use.
