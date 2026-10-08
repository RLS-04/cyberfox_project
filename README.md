# CyberFox Internship Project: Detection Engineering & Log Analysis Lab

## 1. Problem Identification
Modern enterprise networks face continuous, automated security threats ranging from brute-force access attempts to unauthorized privilege escalation. Security Operations Centers (SOCs) cannot effectively mitigate these threats without granular visibility into endpoint telemetry. 

The core problems this project addresses are:
* **Lack of Visibility:** Recognizing systemic blind spots where critical operating system events (such as failed authentications or log tampering) go unmonitored.
* **Alert Fatigue:** Filtering out standard background system noise to highlight true indicators of compromise (IoCs).
* **Delayed Incident Response:** The absence of centralized log aggregation and behavioral visualization dashboards, which slows down triage and investigation times for SOC analysts.

---

## 2. Research & Theoretical Framework
To address these problems, this project implements a centralized, open-source Security Information and Event Management (SIEM) architecture utilizing the **Wazuh** platform. 

The research framework is built upon three industry-standard methodologies:
1. **Telemetry Collection:** Monitoring system logs (`/var/log/auth.log`, `syslog`) to track authentication behaviors and administrative actions.
2. **Threat Mapping (MITRE ATT&CK):** Aligning detected anomalies with globally recognized adversary tactics, specifically targeting **Brute Force (T1110)** and **Indicator Removal on Host (T1070)**.
3. **Detection Engineering:** Researching rule structures (XML/YAML configurations) to translate raw log structures into high-fidelity alerting mechanisms.

---

## 3. Lab Environment & Technical Architecture
The testing laboratory is hosted locally using Oracle VirtualBox. It utilizes an isolated internal host-only network layout to safely simulate attacks without impacting production environments.

| Component | Hostname / OS | Lab Role | Telemetry Status |
| :--- | :--- | :--- | :--- |
| **Attacker Node** | Kali Linux | Adversary Simulation | None (External Vector) |
| **Target Node** | Ubuntu / Metasploitable | Victim Endpoint | Wazuh Agent Installed |
| **SIEM Engine** | Ubuntu Server | Log Ingestion & Indexing | Wazuh Manager Active |

### Architectural Data Flow
[ Kali Linux (Attacker) ] --(Simulates Exploits)--> [ Ubuntu / Metasploitable (Target) ]
|
(Forwards System & Auth Logs)
v
[ Web Interface / Browser ] <--(Visualizes Data)-- [ Ubuntu Server (Wazuh SIEM) ]


---

## 4. Week 1 Verification & Telemetry Proof
The centralized logging pipeline has been successfully researched, planned, and deployed. The target endpoint has been integrated into the SIEM environment. System logs, authentication attempts, and process events are now actively streaming into the SIEM manager console.

### Target Endpoint Verification
*(Replace this placeholder text with your screenshot showing the active agent listing inside your Wazuh/SIEM dashboard web interface)*
