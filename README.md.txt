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