# Cybersecurity SIEM & Threat Hunting Lab 🛡️
### Centralized Log Telemetry, Custom Detection & Incident Response

Project: Cybersecurity SIEM & Threat Hunting Lab 
Platform: Wazuh & Microsoft Sentinel

![Wazuh](https://img.shields.io/badge/SIEM-Wazuh-blue)
![Sentinel](https://img.shields.io/badge/Cloud-Microsoft%20Sentinel-azure)
![KQL](https://img.shields.io/badge/Language-KQL%20%2F%20XML-orange)
![Security](https://img.shields.io/badge/Focus-Threat%20Hunting-red)

---

## 📝 Project Overview
This repository documents a high-fidelity SIEM (Security Information and Event Management) environment engineered to monitor, detect, and analyze security events across distributed enterprise infrastructure. The lab specifically focuses on ingesting, decoding, and correlating telemetry from **Windows Sysmon**, **IIS Web Servers**, and **SQL Server ERRORLOGs**.

---

## 🏗️ Lab Architecture
The environment utilizes a hybrid setup to simulate real-world Security Operations Center (SOC) workflows:

* **Endpoints:** Windows Server instances configured with **Sysmon** for process execution and network connection visibility.
* **Log Aggregation:** **Wazuh Manager** serves as the central log collector, deploying lightweight agents for real-time telemetry streaming and File Integrity Monitoring (FIM).
* **Advanced Analytics:** **Microsoft Sentinel** integration enables cloud-native threat hunting, long-term retention, and complex event correlation using Kusto Query Language.

---

## 📂 Repository Structure

* **`docs/`** — Network topology diagrams, architectural notes, and dashboard visualization screenshots.
* **`rules/`** — Custom XML Decoders and Wazuh rules (`local_rules.xml`) developed for application-level threat detection.
* **`queries/`** — Production-ready KQL (Kusto Query Language) and ES|QL queries for forensic investigations and threat hunting.

---

## 🔍 Threat Detection & Hunting Use Cases

### 1. SQL Server Authentication Anomalies & Brute Force
* **Detection Logic:** A custom Wazuh XML rule triggers an alert upon detecting more than **5 failed login attempts within a 60-second window** in the MS SQL Server `ERRORLOG`.
* **Telemetry Source:** Ingested SQL Server log stream mapped to custom alert severity levels.

### 2. IIS Unauthorized Web Access Patterns
* **Detection Logic:** Parsing IIS Web Server access logs for suspicious HTTP response codes (e.g., `401`, `403`, `404`) indicating automated scanning or directory traversal attempts.
* **Forensic Investigation:** Utilizing KQL queries in Sentinel to correlate source IPs, User-Agent strings, and attack patterns.

---

## 🛠️ Tools & Technologies Used
* **SIEM / Telemetry Platforms:** Wazuh SIEM, Microsoft Sentinel, Elastic Stack (ES|QL)
* **Log Sources:** Windows Security Event Logs, Sysmon, IIS Access Logs, SQL Server ERRORLOGs
* **Languages & Parsing:** KQL (Kusto Query Language), XML Decoders, PowerShell, SQL

---

## 🚀 Technical Capabilities Demonstrated
* **Security Orchestration:** Configured multi-platform SIEM agents and telemetry collection pipelines.
* **Detection Engineering:** Authored custom decoders and alert rules for unstructured/non-standard logs.
* **Proactive Threat Hunting:** Executed complex KQL queries to identify lateral movement and persistence mechanisms.
