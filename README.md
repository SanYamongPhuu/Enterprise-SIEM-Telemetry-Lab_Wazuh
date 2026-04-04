Project: Cybersecurity SIEM & Threat Hunting Lab
Platform: Wazuh & Microsoft Sentinel

Focus: Enterprise Log Analysis & Incident Response

📝 Project Overview
This repository documents a high-fidelity SIEM (Security Information and Event Management) environment engineered to monitor, detect, and analyze security events across distributed infrastructures. The lab specifically focuses on ingesting and decoding telemetry from Windows Sysmon, IIS Web Servers, and SQL Server ERRORLOGs. 

🏗️ Lab Architecture
The environment utilizes a hybrid-cloud model to simulate modern enterprise security operations:

Endpoints: Windows Server instances configured with Sysmon for deep process and network visibility.


Management: Wazuh serves as the central log collector and manager, utilizing specialized agents for real-time telemetry. 


Analysis: Microsoft Sentinel is integrated for advanced threat hunting, long-term data retention, and complex event correlation. 

📂 Repository Structure

/docs: Contains network topology diagrams and screenshots of operational dashboards demonstrating successful log ingestion. 


/rules: Houses custom XML Decoders and Wazuh Rules developed to identify specific patterns in application-level logs. 


/queries: A library of KQL (Kusto Query Language) queries used for proactive threat hunting and forensic investigation. 

🔍 Threat Detection Use Cases
1. SQL Server Brute Force Detection

Logic: A custom Wazuh rule triggers an alert upon detecting more than five failed login attempts within a 60-second window in the SQL Server ERRORLOG. 

Detection: Captured via automated alerting and visualized in the Wazuh dashboard.

2. IIS Unauthorized Access Patterns

Logic: Analyzing IIS Web Server logs for unusual HTTP status codes (e.g., 403, 404) that may indicate directory traversal or automated scanning. 


Investigation: Utilizing KQL in Sentinel to correlate IP addresses with known malicious actors. 

🚀 Technical Skills Demonstrated

Security Orchestration: Configuration of SIEM agents and managers in a multi-platform environment. 


Log Engineering: Authoring custom XML decoders for non-standard log formats. 


Threat Hunting: Writing complex KQL queries to identify lateral movement and persistence. 


Systems Administration: Managing Windows Server security policies and Sysmon configurations.
