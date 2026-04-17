🚀 Brute Force Attack Detection using Splunk SIEM

📌 Overview
This project simulates a brute force attack in a controlled lab environment and demonstrates how a SOC Analyst detects suspicious authentication activity using Splunk.

🛠️ Tools Used
Splunk Enterprise (SIEM)
Windows Server 2016
Windows Event Viewer
SPL (Search Processing Language)

⚙️ Lab Setup
Windows Server used as target system
Failed login attempts generated manually
Security logs exported and ingested into Splunk

🔍 Detection Process
1. Identify Failed Login Events
index=* EventCode=4625
2. Aggregate by Account
index=* EventCode=4625 | stats count by Account_Name
3. Detect Suspicious Activity
index=* EventCode=4625 | stats count by Account_Name | where count > 5

📊 Key Findings
Multiple failed login attempts detected across user accounts
High-frequency attempts indicate potential brute force attack
Visualization highlights abnormal behavior patterns

📸 Screenshots
🔹 Network Configuration

🔹 Windows Security Logs (EventCode 4625)

🔹 Exporting Logs

🔹 Uploading to Splunk

🔹 Log Ingestion Confirmation

🔹 Query Results

🔹 Detection Threshold

🔹 Visualization

🧠 Challenges & Troubleshooting
Resolved Splunk disk space limitations
Restarted Splunk services to restore functionality
Validated successful data ingestion after errors

🎯 Skills Demonstrated
SIEM (Splunk)
Log Analysis
Threat Detection
Event Correlation
Troubleshooting (EventCode 4625)
