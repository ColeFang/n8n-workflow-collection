# X

English | [简体中文](./README.zh-CN.md)

This folder contains standalone n8n workflows for X / Twitter.

## Contents

- `Create/x-create.redacted.json`
- `Update/x-update.redacted.json`

## When to use each workflow

### Create
Create a monthly X tracking table and collect posts from selected accounts within a time range.

### Update
Read existing records, refresh X post engagement data, and write it back to the table.

## Dependencies

- n8n
- Feishu / Lark
- Bitable
- Apify
- The Create flow also depends on DeepSeek

## Usage notes

- If the link format is not a standard account page, check the account extraction logic first.
- The Create flow builds X search conditions from year/month settings, so review the collection range when you change the month.
- These workflows depend on Apify actors, so confirm that your Apify account has the required subscription, quota, or actor access before production use.
