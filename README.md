# Detection_Engineering_Lab

This repository showcases my end-to-end detection engineering lab project, where I built a full enterprise-like environment to simulate attacks and develop behavioral detections using SIEM and UEBA technologies. It covers infrastructure setup, log pipeline development, attack simulation, and detection engineering—all combining both red and blue team workflows.

---

## 🛠️ Lab Overview

This Detection Engineering Lab replicates a Windows domain-joined enterprise monitored by a self-hosted Gurucul Risk Analytics (GRA) platform. The goal was to simulate realistic adversarial activity and build robust behavioral detections to flag malicious behavior, all within a controlled and observable environment.

---

## 🔧 Lab Setup & Deployment

- Installed **VMware ESXi** on bare-metal servers as the virtualization layer.
- Deployed multiple operating systems:
  - **Windows Server 2019** (Domain Controller)
  - **Three Windows 10 machines** (domain-joined clients)
  - **Kali Linux** (attacker node)
  - **CentOS** (hosting the GRA platform)
- Configured **Active Directory** domain and joined clients.
- Installed **Sysmon** and enabled **GPOs** to enhance telemetry and event logging.

---

## 📦 GRA Platform Migration

- Migrated **Gurucul Risk Analytics** from a cloud-based Linode instance to a CentOS server.
- Restored core components: **MySQL**, **CrateDB**, detection models, and pipelines.
- Configured **SELinux** and firewall rules to secure the environment.

---

## 🔄 Telemetry Pipeline Configuration

- Installed **NxLog** on Windows endpoints to forward event logs to the GRA syslog listener.
- Developed custom **Logstash parsers** to:
  - Parse Windows event logs
  - Map and normalize key attributes
  - Route telemetry into the SIEM pipeline

---

## ⚔️ Red Team Simulation

- Conducted adversary emulation using:
  - **Atomic Red Team**
  - **Caldera**
  - Manual attack scenarios
- Simulated threats included:
  - **Pass-the-Hash**
  - **Kerberoasting**
  - **PrintNightmare**
  - **Log4j (JNDI Injection)**

---

## 🛡️ Blue Team Detection Engineering

- Researched detection strategies using:
  - **Sigma rules**, **YARA signatures**
  - CVE bulletins, threat intel blogs
- Built custom detection content mapped to **MITRE ATT&CK** techniques.
- Tuned **SIEM** and **UEBA** models to detect and alert on malicious behavior.
- Iteratively refined detections by replaying attacks and validating signal quality.

---

## ✅ Key Takeaways

- Full lifecycle experience: infrastructure, telemetry, simulation, detection, tuning.
- Built effective detections for common and high-impact attacks in Windows environments.
- Applied red-blue methodologies to create a realistic and scalable detection engineering lab.

---

## 📁 Repository Structure

- [`Lab Infrastructure Setup`](./Lab%20Infrastructure%20Setup)  
  VMware setup, AD domain config, logging agents, Sysmon.

- [`Screencaps`](./Screencaps)  
  Visual evidence from attack simulations and detection validation.

- [`Simulation Logs`](./Simulation%20Logs)  
  Event logs generated during red team activity.

- [`Threat Research Papers`](./Threat%20Research%20Papers)  
  Detection logic, Sigma/YARA rules, and custom research notes.

