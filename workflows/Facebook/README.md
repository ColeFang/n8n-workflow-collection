# Facebook

English | [简体中文](./README.zh-CN.md)

This folder contains standalone n8n workflows for Facebook.

## Contents

- `Create/facebook-create.redacted.json`
- `Update/facebook-update.redacted.json`

## When to use each workflow

### Create
Create a new Facebook tracking table and collect content from the provided page links.

### Update
Re-fetch the latest data for existing Facebook records and write it back to the table.

## Dependencies

- n8n
- Feishu / Lark
- Bitable
- Apify
- The Create flow also depends on DeepSeek

## Usage notes

- Facebook link formats vary a lot, so start with a small sample after import.
- If the returned fields do not match your table, adjust the write-back mapping first.
- These workflows depend on Apify actors, so confirm that your Apify account has the required subscription, quota, or actor access before production use.
