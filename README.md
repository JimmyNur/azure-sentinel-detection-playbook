# 🛡️ Azure Sentinel 

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
- https://docs.google.com/document/d/1A_9z3uIUT39mVTFOZJEyBqWU7MDYmrlQ9WYZB9bnews/edit?usp=sharing: Visual representation of the rule setup
- https://docs.google.com/document/d/1g6zK0Y-0l8TUybMI_fLvs9q6g2M-guecaYJPRmHr3v0/edit?usp=sharing: Screenshot showcasing a successful detection and response


---

## 🛠️ How to Deploy

Follow these steps to deploy the Azure Sentinel Detection Playbook:

1. **Import the Analytics Rule:**
   - Navigate to Microsoft Sentinel > Analytics > Create > Import from JSON
   - Upload the `analytics-rule-blob-access.json` file found in the `sentinel/` directory.

2. **Configure Logic App Automation:**
   - Ensure that the Logic App linked to the detection rule is properly configured and has the necessary permissions.
   - Test the Logic App by triggering an alert manually.

3. **Testing the Detection:**
   - Simulate a blob upload with public access using PowerShell or Azure CLI.
   - Verify that the detection rule triggers an alert and the Logic App fires correctly.

## 🚀 Deployment Guide

1. **Import the Analytic Rule:**
   - Navigate to Microsoft Sentinel > Analytics > Create > Import from JSON
   - Upload `sentinel/analytics-rule-blob-access.json`

2. **Set Up the Logic App:**
   - Deploy the Logic App using `logic-app/blob-access-response.json`
   - Ensure it has the necessary permissions and is connected to the Sentinel workspace

3. **Testing:**
   - Simulate a public blob access to trigger the rule
   - Verify that the Logic App executes as expected


 ## 🔍 Features

- **Log Source:** AzureDiagnostics (BlobStorage category)
- **Monitored Operation:** PutBlob
- **Trigger Condition:** Public blob uploads
- **Detection Frequency:** Every 5 minutes
- **Severity Level:** High
- **MITRE ATT&CK Tactic:** Initial Access
- **Automated Response:** Integration with Azure Logic App for immediate action

## Reference 
- [`sentinel/analytics-rule-blob-access.json`](sentinel/analytics-rule-blob-access.json)
- [`docs/rule-overview.png`](docs/rule-overview.png)


## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## 🤝 Contribution

Contributions are welcome! Please open an issue or submit a pull request for any enhancements or bug fixes.

