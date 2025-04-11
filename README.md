# 🛡️ Azure Sentinel Detection Playbook

This project showcases a production-ready analytic rule in Microsoft Sentinel designed to detect unauthorized public access to Azure Blob Storage. Upon detection, it triggers an automated incident response via Azure Logic Apps, ensuring swift mitigation.


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

- [`sentinel/analytics-rule-blob-access.json`](https://docs.google.com/document/d/1pfmsuFUVjY5S9P2jZDUp1yHWmoj8GnYeqQvO3o-7kiA/edit?usp=sharing): Sentinel detection rule template
- `docs/rule-overview.png`: Screenshot of rule setup https://docs.google.com/document/d/1fxXPrNG5Ix5xVj0O1Bdh12vsZ90O-9SOZi9FIqMJEDw/edit?usp=sharing
- `docs/run-result.png`: Screenshot of successful detection/trigger

  ## 📁 Repository Structure

- `sentinel/analytics-rule-blob-access.json`: Sentinel detection rule template
- `docs/rule-overview.png`: Visual representation of the rule setup
- `docs/run-result.png`: Screenshot showcasing a successful detection and response


---

## 🚀 How to Deploy

1. Upload JSON to your Sentinel Workspace (Analytics → Create → Import rule)
2. Confirm linked Log Analytics workspace is ingesting Blob Storage logs
3. Attach Logic App under "Automated response"
4. Test by uploading public blob and monitor trigger

## 🚀 Deployment Guide

1. **Import the Analytic Rule:**
   - Navigate to Microsoft Sentinel > Analytics > Create > Import from JSON
   - Upload `analytics-rule-blob-access.json`

2. **Configure the Logic App:**
   - Ensure the Logic App is set up to handle the triggered alerts appropriately.

3. **Testing:**
   - Simulate a public blob upload to verify the detection and automated response.


6. ## 🔍 Features

- **Log Source:** AzureDiagnostics (BlobStorage category)
- **Monitored Operation:** PutBlob
- **Trigger Condition:** Public blob uploads
- **Detection Frequency:** Every 5 minutes
- **Severity Level:** High
- **MITRE ATT&CK Tactic:** Initial Access
- **Automated Response:** Integration with Azure Logic App for immediate action


## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## 🤝 Contribution

Contributions are welcome! Please open an issue or submit a pull request for any enhancements or bug fixes.

