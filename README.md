# Integrated SIEM & IDS Detection Lab (Wazuh + Suricata)

## Overview
This project implements a **SOC-style detection and monitoring lab** using an
integrated **SIEM and IDS architecture** deployed across a **three–virtual machine
environment**.

The objective was to understand how **network-based intrusion detection**, **host
telemetry**, and **centralized SIEM correlation** work together to detect, analyze,
and investigate security events in a controlled lab setting.

All systems were deployed in an **isolated host-only network** and used solely for
educational and defensive security research.

---

## Objectives
- Design a multi-VM SOC-style detection environment
- Deploy and integrate Suricata IDS with Wazuh SIEM
- Centralize network and host security telemetry
- Build and tune detection and correlation rules
- Simulate attack activity to validate detections
- Analyze alert quality and reduce false positives

---

## Lab Architecture (3-VM Design)

### Virtual Machines
- **Victim VM (Ubuntu Desktop)**
  - Suricata IDS
  - Wazuh Agent
  - Host-based firewall and system logs

- **SIEM VM (Ubuntu Server)**
  - Wazuh Manager
  - Wazuh Indexer
  - Wazuh Dashboard

- **Attacker VM (Kali Linux)**
  - Used to simulate reconnaissance and attack activity
  - Generated traffic for detection testing

### Network Configuration
- Host-only virtual network
- No external internet exposure
- All traffic confined to the lab environment

---

## Architecture Overview
```text
Kali Linux VM (Attack Simulation)
              ↓
     Victim Ubuntu VM
     (Suricata IDS + Wazuh Agent)
              ↓
      Ubuntu Server SIEM VM
 (Wazuh Manager / Indexer / Dashboard)
              ↓
        Alerting & Analysis


