# 🛡 Network Scanning & Enumeration Using Nmap

## 🎯 Project Overview

This project demonstrates the application of *Nmap*, a powerful open-source tool for network discovery and security auditing, in a simulated penetration testing environment. The objective is to emulate the initial reconnaissance phase by identifying live hosts, open ports, and exposed services within an isolated lab network.

---

## 🧰 Tools & Lab Environment

| Component            | Specification                                |
| -------------------- | -------------------------------------------- |
| *Operating System* | Kali Linux 2024.1                            |
| *Tools Utilized*   | Nmap (CLI), Zenmap (GUI)                     |
| *Virtualization*   | VirtualBox (Host-Only Networking)            |
| *Target Machine*   | Metasploitable2 (Deliberately Vulnerable VM) |

---

## ⚙ Lab Setup Instructions

1. Install *VirtualBox* or *VMware Workstation* on your host machine.
2. Download the required virtual machines:

   * [Kali Linux](https://www.kali.org/get-kali/)
   * [Metasploitable2](https://sourceforge.net/projects/metasploitable/)
3. Configure a *Host-Only Network Adapter* and assign it to both VMs.
4. Ensure both machines are on the same subnet (e.g., 192.168.56.0/24).
5. Confirm network connectivity using:

   bash
   ping 192.168.56.101
   

---

## 🔍 Scanning Workflow

### ✅ Step 1: Host Discovery (Ping Sweep)

bash
nmap -sn 192.168.56.0/24


> Identifies live hosts on the subnet using ICMP Echo and ARP requests.

---

### ✅ Step 2: Service Enumeration & OS Fingerprinting

bash
nmap -A -T4 192.168.56.101


> Executes an aggressive scan to extract detailed information:

* OS Detection
* Service Version Detection
* Default NSE Script Execution
* Traceroute Mapping

---

## 📸 Sample Output

![Nmap Scan Result](screenshots/nmap_service_scan.png)

---

## 📊 Scan Results Summary

| Attribute             | Value                                 |
| --------------------- | ------------------------------------- |
| *Open Ports*        | 21, 22, 23, 25, 80, 3306              |
| *Detected Services* | FTP, SSH, Telnet, SMTP, HTTP, MySQL   |
| *OS Fingerprint*    | Linux 2.6.X (likely Ubuntu 8.04–9.04) |
| *Target Identity*   | Metasploitable2 (Vulnerable Test VM)  |

> Noteworthy: The presence of insecure protocols (e.g., Telnet, FTP) opens up vectors for further exploitation, suitable for CTF scenarios or red team simulations.

---

## 🚧 Challenges & Resolutions

| Challenge                       | Mitigation Strategy                         |
| ------------------------------- | ------------------------------------------- |
| VM network misconfiguration     | Reconfigured the host-only adapter settings |
| Zenmap instability during scans | Switched to CLI-based Nmap for reliability  |
| Inefficient timing (-T1)      | Optimized with faster execution using -T4 |

---

## 📘 Key Takeaways

* Acquired hands-on experience in host discovery via ICMP, ARP, and TCP-based techniques.
* Gained deeper insights into TCP/IP behavior during enumeration phases.
* Learned to interpret service banners and perform OS fingerprinting effectively.
* Reaffirmed the importance of isolated lab environments for safe recon and testing.

---

## 🚀 Future Enhancements

* [ ] Automate scanning workflows using Bash scripting.

* [ ] Export scan results in XML/HTML and integrate with reporting tools:

  * [Dradis](https://dradisframework.com/)
  * [MagicTree](https://github.com/govolution/magictree)

* [ ] Benchmark results using high-speed alternatives:

  * [Masscan](https://github.com/robertdavidgraham/masscan)
  * [RustScan](https://github.com/RustScan/RustScan)

---
Contribution:
---

| Name                 | GitHub Username       | Responsibilities                                                                                          |
|----------------------|-----------------------|-----------------------------------------------------------------------------------------------------------|
| *Arijit Nandy* | @Arijit-Nandy           | - , malware dev                                    |
| *Akashneel Ghosh*          | @official-akashneel             | -  malware dev                                                        |
| *Abhra Bhattacharya*          | @ABHRA-BHATTACHARYA             | -CI-CD                                                              |
| *Dipraj Samui*          | @diprajsamui60-gif             | - CI-CD                                                              |
| *Swarnava Paul*          | @swarnavapaul-2004             | -  code optimization                                                              |


---


## 🙏 Acknowledgment

Special thanks to [Biswadeb Mukherjee](https://github.com/official-biswadeb941) for technical guidance and strategic input throughout this lab simulation. His expertise in offensive security, enumeration tactics, and adversarial tooling played a vital role in this project’s successful execution.

---

## 🗂 Project Snapshot

| Field                  | Description                                                      |
| ---------------------- | ---------------------------------------------------------------- |
| *Status*             | ✅ Completed                                                      |
| *Version*            | 1.0                                                              |
| *Completion Date*    | 17 July 2025                                                     |
| *Domain*             | Network Reconnaissance & Enumeration                             |
| *Primary Tools*      | Nmap, Zenmap, Kali Linux                                         |
| *Objective Achieved* | Successfully identified network services and OS on target system |
| *Next Phase*         | Workflow automation and toolchain expansion                      |

---

## 📎 References & Resources

* 📘 [Nmap Official Documentation](https://nmap.org/book/man.html)
* 📓 [Comprehensive Nmap Command Guide (PDF)](https://archive.org/details/comprehensive-nmap-command-guide)
* 💡 [TryHackMe: Nmap Room](https://tryhackme.com/room/nmap)

---

## 📁 Directory Structure


nmap-network-scan/
├── README.md
├── screenshots/
│   └── nmap_service_scan.png
├── reports/
│   └── scan_log.txt
└── scripts/
    └── auto_scan.sh


---

## 👤 Author

**Mr. Biswadeb Mukherjee
| Name                 | GitHub Username       | Responsibilities                                                                                          |
|----------------------|-----------------------|-----------------------------------------------------------------------------------------------------------|
| *Biswadeb Mukherjee* | @biswadebm           | - System architecture, malware dev, recon tools, adversary simulation                                     |

**
Ethical Hacker | Penetration Tester | Malware Developer

[LinkedIn](https://www.linkedin.com/in/biswadeb-mukherjee) • [GitHub](https://github.com/YOUR_GITHUB) • [Portfolio](https://cutt.ly/my_website)

> “I break things to understand them. I write code with a battle plan.”
> Passionate about adversarial simulation, offensive tooling, and cyber forensics.