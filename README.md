# Raspberry Pi Cybersecurity Lab

**Author**: Andrew Boschini  
**Role**: Network Administrator | Cybersecurity Enthusiast  
**Lab Focus**: Home-brewed offensive & defensive simulation environment using Raspberry Pi clusters

---

##  Lab Overview

This personal lab environment was designed to simulate enterprise-style networking and security scenarios using Raspberry Pi hardware. It includes isolated offensive and defensive subnets, a pivotable network, and multiple security tools such as Splunk, Kali Linux, and Pi-hole.

---

##  Hardware Setup

- Raspberry Pi 3 – Infra Node (SSD Attached)
- Raspberry Pi 4 x2 – Defender and SIEM Nodes
- Raspberry Pi 5 – Offensive Node (Kali ARM)
- Simulated Victim Systems – 3 total (Linux/Windows VMs on host or Pi network)
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
     │ Dock   │───> [Switch] ─> [RPi3] ─ Infra + SSD
     └────────┘             └> [RPi4] ─ Defender
                             └> [RPi4] ─ SIEM
                             └> [RPi5] ─ Kali Offensive ─> Victim 1
                                                         └> Victim 2
                                                         └> Victim 3
```

---

##  Services & Tools

| Node       | Purpose         | Key Tools/Services                         |
|------------|------------------|-------------------------------------------|
| `infra`    | DHCP, DNS, storage | Pi-hole, SSH, syslog, mounted SSD         |
| `defender` | Blue Teaming      | Snort, UFW, auditd, Suricata               |
| `siem`     | Central logging   | Splunk Free, syslog-ng                    |
| `attack`   | Red Teaming       | Kali Linux ARM, Metasploit, Nmap, Nikto   |
| `victims`  | Exploit Targets   | Open ports, misconfigurations, OS variety |

---

##  Functionality

- **Offensive Ops**: Penetration testing, pivoting, privilege escalation
- **Defensive Ops**: IDS/IPS tuning, firewall logging, alerting
- **Log Aggregation**: Real-time analysis using Splunk dashboards
- **Network Segmentation**: Lab VLAN isolation using router config
- **Storage**: SSD mounted on `infra` for syslog and config persistence

---

##  Skills Demonstrated

- Network architecture design
- VLAN and subnet segmentation
- Red/Blue team scenarios across mixed devices
- Log management, detection, and response
- OS hardening, scripting, and automation
- Penetration testing on real and emulated systems

---

##  Future Enhancements

- Terraform or Ansible for automated configuration
- Grafana dashboards for real-time metrics
- Docker swarm or Kubernetes Pi orchestration
- Windows AD emulation for advanced escalation testing

---

##  Why This Matters

This lab mirrors many of the challenges in real-world enterprise security—limited resources, mixed environments, and the need for visibility and control. I built it to reinforce my skills in network segmentation, threat detection, and Red vs Blue team thinking.
