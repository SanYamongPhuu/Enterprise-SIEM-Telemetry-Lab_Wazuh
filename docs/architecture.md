# Lab Architecture & Documentation

## Overview
* **Endpoints:** Windows Server with Sysmon Agent
* **Manager:** Wazuh SIEM Centralized Manager
* **Analytics:** Microsoft Sentinel Workspace (KQL Logging)

# Enterprise SIEM Lab Architecture

```mermaid
graph TD
    A[Windows Server / Sysmon Agent] -->|Security Events & Sysmon Telemetry| B(Wazuh SIEM Manager)
    C[MS SQL Server & IIS Web Logs] -->|ERRORLOG & Access Logs| B
    B -->|Custom Rules & Decoders| D[Wazuh Dashboard Alerts]
    B -->|Log Streaming / Telemetry Integration| E[Microsoft Sentinel Cloud Workspace]
    E -->|KQL Threat Hunting & Forensics| F[Security Analyst Investigation]
