# Facebook / Update

English | [简体中文](./README.zh-CN.md)

This workflow is the standalone Facebook version extracted from the SocialMediaTracker Update flow.

Corresponding file: `facebook-update.redacted.json`

## Purpose

- Read existing Bitable records
- Filter Facebook records only
- Re-fetch post engagement data
- Update the original table

## Configuration to replace after import

- `{{BITABLE_APP_TOKEN}}`
- `{{BITABLE_TABLE_ID}}`
- `{{FEISHU_APP_ID}}`
- `{{FEISHU_APP_SECRET}}`
- Apify credential binding

## Notes

Facebook page and post URL formats change often, so validate the workflow with a small sample after import.
