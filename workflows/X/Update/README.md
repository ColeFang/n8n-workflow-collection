# X / Update

English | [简体中文](./README.zh-CN.md)

This workflow is the standalone X version extracted from the SocialMediaTracker Update flow.

Corresponding file: `x-update.redacted.json`

## Purpose

- Read existing Bitable records
- Filter X / Twitter records only
- Re-fetch engagement data
- Update the original table

## Configuration to replace after import

- `{{BITABLE_APP_TOKEN}}`
- `{{BITABLE_TABLE_ID}}`
- `{{FEISHU_APP_ID}}`
- `{{FEISHU_APP_SECRET}}`
- Apify credential binding

## Notes

If your stored record links are not standard X post URLs, review the matching logic after import.
