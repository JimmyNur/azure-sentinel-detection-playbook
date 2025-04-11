azure-sentinel-detection-playbook/
│
├── sentinel/
│   └── analytics-rule-blob-access.json
│
├── docs/
│   ├── rule-overview.png
│   └── run-result.png
│
├── README.md
# 🛡️ Azure Sentinel Detection Playbook

This playbook demonstrates a production-grade analytic rule in Microsoft Sentinel that detects public access events on Azure Blob Storage and automatically triggers an incident response via Logic Apps.

---

## 📌 Detection Rule: Public Blob Access

- **Log Source**: AzureDiagnostics (BlobStorage category)
- **Operation Monitored**: PutBlob
- **Trigger**: Any blob upload with public access
- **Frequency**: Every 5 minutes
- **Severity**: High
- **MITRE Tactic**: Initial Access
- **Response**: Runs Logic App for alert and action

---

## 📂 Files

- [`sentinel/analytics-rule-blob-access.json`](sentinel/analytics-rule-blob-access.json): Sentinel detection rule template
- `docs/rule-overview.png`: Screenshot of rule setup https://docs.google.com/document/d/1fxXPrNG5Ix5xVj0O1Bdh12vsZ90O-9SOZi9FIqMJEDw/edit?usp=sharing
- `docs/run-result.png`: Screenshot of successful detection/trigger

---

## 🚀 How to Deploy

1. Upload JSON to your Sentinel Workspace (Analytics → Create → Import rule)
2. Confirm linked Log Analytics workspace is ingesting Blob Storage logs
3. Attach Logic App under "Automated response"
4. Test by uploading public blob and monitor trigger
