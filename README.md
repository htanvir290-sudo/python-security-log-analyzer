# 🛡️ Automated Security Log Analyzer & Threat Detector

A lightweight Security Operations Center (SOC) utility written in Python. This tool parses raw HTTP access logs, identifies suspicious authentication anomalies (such as brute-force password attacks), and outputs an automated incident response report in JSON format.

---

## 📌 Project Overview

Monitoring system and application logs is a critical responsibility in network security and system administration. Unmonitored log data can allow persistent brute-force attempts or unauthorized intrusion vectors to go unnoticed.

This tool automates log inspection by scanning access logs for elevated rates of HTTP `401 Unauthorized` responses on critical endpoints (e.g., `/login`). When an IP address exceeds a configurable threshold within a single session, the script flags it as a high-risk security threat and generates a structured incident summary.

---

## 🛠️ Tech Stack & Key Concepts

* **Language:** Python 3.x
* **Parsing Techniques:** Regular Expressions (`re`) & Pattern Matching
* **Data Structures:** `collections.Counter` for efficient frequency aggregation
* **Output Format:** JSON (Machine-readable for SIEM integration)
* **Core Cybersecurity Concepts:** 
  * Log Analysis & Intrusion Detection
  * Brute-Force Attack Mitigation
  * Incident Reporting & Threat Assessment

---

## 📂 Repository Structure

```text
python-security-log-analyzer/
│
├── log_analyzer.py      # Core Python detection engine
├── sample_access.log    # Raw server access log dataset
├── security_report.json # Automated output report generated upon detection
└── README.md            # Documentation & project architecture

🚀 How to Run the Project
Prerequisites
Python 3.x installed on your computer.

Step-by-Step Execution

1. Clone or Download the Repository:
   git clone [https://github.com/htanvir290-sudo/python-security-log-analyzer.git](https://github.com/htanvir290-sudo/python-security-log-analyzer.git)cd python-security-log-analyzer

2. Verify File Location:
   Ensure sample_access.log and log_analyzer.py are in the same folder.

3. Run the Script:
   python log_analyzer.py

4.Terminal Output:
  [*] Scanning log file for suspicious activity...
  [!] THREAT DETECTED: IP 192.168.1.100 failed login 5 times!
  [*] Analysis complete. Report saved to 'security_report.json'.

📊 Automated Incident Report Output
   When a threat is detected, the script outputs security_report.json:

{
    "status": "ALERT",
    "threshold_limit": 3,
    "flagged_threats": [
        {
            "ip_address": "192.168.1.100",
            "failed_attempts": 5,
            "risk_level": "HIGH - Potential Brute Force Attack"
        }
    ]
}



🎯 Future Upgrades
Implement time-window analysis (e.g., tracking failed attempts within a 60-second window).

Add automatic IP blocking configuration export (e.g., iptables rules).

Integrate email or Webhook alerts upon detection of critical events.


Author: Kizzard
