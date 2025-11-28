# 📊 Marketing KPI Automation Suite (n8n + Google Sheets + Looker Studio)

This repository contains a full no-code/low-code automation suite to consolidate, analyze, and alert on marketing KPIs using **n8n**, **Google Sheets**, **OpenAI**, and **Looker Studio**.

## 🔧 Modules

1. **KPI Consolidation Workflow** (`marketing_kpi_workflow.json`)
   - Fetches data from Meta Ads, Google Ads, GA4, CRM
   - Calculates KPIs (CAC, ROAS, CTR, CPC, CPM)
   - Stores in a Google Sheet (SSOT)

2. **Weekly Summary with OpenAI** (`weekly_kpi_summary_openai.json`)
   - Calculates weekly trends
   - Sends summary to OpenAI
   - Returns a 3-line executive report
   - Email/Slack integration optional

3. **Anomaly Alerts**
   - `kpi_alerts_workflow.json`: Alerts via Telegram
   - `kpi_alerts_slack_workflow.json`: Alerts via Slack with link to Looker dashboard

## 📁 Templates

- `marketing_kpi_template.csv`: Base SSOT structure (daily campaign data)
- `marketing_kpi_summary_template.csv`: Summary table structure (weekly data)

## 🚀 Getting Started

### 1. Import Workflows into n8n
- Go to **n8n → Workflows → Import from file**
- Choose any `.json` file in this repo

### 2. Setup Credentials in n8n
- Google Sheets OAuth
- OpenAI API Key
- Slack/Telegram credentials

### 3. Setup Google Sheets
- Use the included `.csv` files to create your Google Sheet structure
- Ensure the Sheet name is `SSOT` (for KPI data) and `Summary` (for summaries)

### 4. Connect Looker Studio
- Use Google Sheets connector
- Enable date filters, and optionally `campaign` URL parameters for deep links

## 📅 Scheduling
- Daily KPIs: runs at 06:00 AM
- Summary: runs every Monday at 08:00 AM
- Alerts: run every 3 hours

## 📄 License

MIT License. See LICENSE file.

---


