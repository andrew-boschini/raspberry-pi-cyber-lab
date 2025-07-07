# Raspberry Pi Cybersecurity Lab

**Author**: Andrew Boschini  
**Role**: Network Administrator | Cybersecurity Enthusiast  
**Lab Focus**: Home-brewed offensive & defensive simulation environment using Raspberry Pi clusters

---

##  Lab Overview

This personal lab environment was designed to simulate enterprise-style networking and security scenarios using Raspberry Pi hardware. It includes isolated offensive and defensive subnets, a pivotable network, and multiple security tools such as Splunk, Kali Linux, and Pi-hole.

---

##  Hardware Setup

- Raspberry Pi 3 – Infra Node
- Raspberry Pi 4 x2 – Defender and SIEM Nodes
- Raspberry Pi 5 – Offensive Node (Kali ARM)
- Cradlepoint E3000 Router (Lab VLAN)
- Netgear Switch (8-port)
- Windows Host Laptop running Kali VM

---

##  Network Topology

```
[Internet via Wi-Fi]
         |
      [Laptop]
         |
     ┌────────┐
     │ USB-C  │
     │ Dock   │───> [Switch] ─> [RPi3] ─ Infra
     └────────┘             └> [RPi4] ─ Defender
                             └> [RPi4] ─ SIEM
                             └> [RPi5] ─ Kali Offensive
```

---

##  Services & Tools

| Node       | Purpose         | Key Tools/Services                         |
|------------|------------------|-------------------------------------------|
| `infra`    | DHCP, DNS, updates | Pi-hole, SSH, syslog server               |
| `defender` | Blue Teaming      | Snort, UFW, auditd, Suricata               |
| `siem`     | Central logging   | Splunk Free, syslog-ng                    |
| `attack`   | Red Teaming       | Kali Linux ARM, Metasploit, Nmap, Nikto   |

---

##  Functionality

- **Offensive Ops**: Penetration testing and privilege escalation training
- **Defensive Ops**: IDS/IPS tuning, firewall logging, alerting
- **Log Aggregation**: Real-time analysis using Splunk dashboards
- **Network Segmentation**: Lab VLAN isolation using router config

---

##  Skills Demonstrated

- Network architecture design
- VLAN and subnet segmentation
- Offensive security tactics (pivoting, scanning)
- Defensive logging, detection, and response
- OS-level hardening and monitoring
- Automation of updates and backups

---

##  Future Enhancements

- Terraform or Ansible integration for config-as-code
- Web dashboard using Grafana for live lab stats
- Raspberry Pi Kubernetes or Docker orchestration

---

##  Why This Matters

This lab mirrors many of the challenges in real-world enterprise security—limited resources, mixed environments, and the need for visibility and control. I built it to reinforce my skills in network segmentation, threat detection, and Red vs Blue team thinking.
