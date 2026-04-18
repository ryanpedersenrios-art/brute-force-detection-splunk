# 🚀 Brute Force Attack Detection & Analysis using Splunk SIEM

## 📌 Overview
This project simulates a brute force attack in a controlled lab environment and demonstrates how a SOC Analyst detects suspicious authentication activity using Splunk.

### 🛠️ Tools Used
Splunk Enterprise (SIEM)
Windows Server 2016
Windows Event Viewer
SPL (Search Processing Language)

### ⚙️ Lab Setup
Windows Server used as target system
Failed login attempts generated manually
Security logs exported and ingested into Splunk

### 🔍 Detection Process
1. Identify Failed Login Events
index=* EventCode=4625
2. Aggregate by Account
index=* EventCode=4625 | stats count by Account_Name
3. Detect Suspicious Activity
index=* EventCode=4625 | stats count by Account_Name | where count > 5

## 🧠 Detection Logic Explained
- EventCode 4625 represents failed login attempts in Windows Security logs
- Multiple failed attempts across the same account may indicate brute-force activity
- Aggregating events by account helps identify patterns of repeated failures
- Applying a threshold (e.g., >5 attempts) helps filter out normal user error and highlight suspicious behavior

## 📊 Key Findings
- Identified repeated failed login attempts (EventCode 4625) across multiple accounts
- Detected high-frequency authentication failures exceeding normal user behavior
- Patterns observed are consistent with brute-force attack techniques
- SIEM correlation and aggregation enabled clear identification of suspicious activity

### 📸 Screenshots
🔹 Network Configuration

🔹 Windows Security Logs (EventCode 4625)

🔹 Exporting Logs

🔹 Uploading to Splunk

🔹 Log Ingestion Confirmation

🔹 Query Results

🔹 Detection Threshold

🔹 Visualization

### 🧠 Challenges & Troubleshooting
Resolved Splunk disk space limitations
Restarted Splunk services to restore functionality
Validated successful data ingestion after errors

## 🎯 Skills Demonstrated
SIEM (Splunk)
Log Analysis
Threat Detection
Event Correlation
Troubleshooting (EventCode 4625)

## 🔑 Key Takeaways
- Brute force attacks can be identified through repeated failed authentication events (EventCode 4625)
- Aggregating log data helps reveal patterns not visible in individual events
- Setting thresholds is critical for distinguishing normal behavior from potential threats
- SIEM tools like Splunk enable efficient detection, correlation, and visualization of security events
- Proper log ingestion and validation are essential for accurate threat detection

## 🚧 Next Steps / Response Actions
- Investigate source IP addresses associated with failed login attempts
- Implement account lockout policies to prevent further brute-force attempts
- Monitor for successful logins following failed attempts (possible compromise)
- Create automated alerts in Splunk for repeated failed login thresholds
