<div align="center">

```
██╗    ██╗██╗██████╗ ███████╗███████╗██╗  ██╗ █████╗ ██████╗ ██╗  ██╗
██║    ██║██║██╔══██╗██╔════╝██╔════╝██║  ██║██╔══██╗██╔══██╗██║ ██╔╝
██║ █╗ ██║██║██████╔╝█████╗  ███████╗███████║███████║██████╔╝█████╔╝ 
██║███╗██║██║██╔══██╗██╔══╝  ╚════██║██╔══██║██╔══██║██╔══██╗██╔═██╗ 
╚███╔███╔╝██║██║  ██║███████╗███████║██║  ██║██║  ██║██║  ██║██║  ██╗
 ╚══╝╚══╝ ╚═╝╚═╝  ╚═╝╚══════╝╚══════╝╚═╝  ╚═╝╚═╝  ╚═╝╚═╝  ╚═╝╚═╝  ╚═╝
```

**God-Level Interactive Reference for SOC Analysts, DFIR Investigators & Blue Teamers**

[![Live Demo](https://img.shields.io/badge/🚀_LIVE_DEMO-View_Cheatsheet-14e8c8?style=for-the-badge&labelColor=03080f)](https://oracleo.github.io/Wireshark-GOD-Level-Cheatsheet/Wireshark-GOD-Level-Cheatsheet.html)
[![License](https://img.shields.io/badge/LICENSE-MIT-0ea5e9?style=for-the-badge&labelColor=03080f)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-WELCOME-f59e0b?style=for-the-badge&labelColor=03080f)](CONTRIBUTING.md)

![Wireshark](https://img.shields.io/badge/WIRESHARK-4.x-14e8c8?style=flat-square&labelColor=03080f)
![SOC](https://img.shields.io/badge/ROLE-SOC_ANALYST-0ea5e9?style=flat-square&labelColor=03080f)
![DFIR](https://img.shields.io/badge/ROLE-DFIR_INVESTIGATOR-8b5cf6?style=flat-square&labelColor=03080f)
![tshark](https://img.shields.io/badge/INCLUDES-TSHARK_CLI-f59e0b?style=flat-square&labelColor=03080f)
![HTML](https://img.shields.io/badge/BUILT_WITH-HTML_·_CSS_·_JS-f59e0b?style=flat-square&labelColor=03080f)

</div>

---

## What Is This?

A **single-file, fully interactive Wireshark cheatsheet** for cybersecurity professionals preparing for SOC analyst, DFIR, blue team, and penetration tester interviews. Covers everything from beginner display filters to advanced forensic techniques and tshark CLI mastery.

> *"Most candidates know how to open a PCAP. You know how to reconstruct an attack, extract credentials, detect C2 beaconing, and identify DNS tunneling — all within 60 seconds of opening a file. That's what gets you hired."*

---

## Preview

<div align="center">

| Display Filters | Attack Detection | Interview Scenarios |
|:---:|:---:|:---:|
| Protocol-aware field syntax | Real-world attack signatures | 10 investigative walkthroughs |
<img width="1350" height="611" alt="image" src="https://github.com/user-attachments/assets/83af82b9-6dc7-46f8-9394-d44b00a4e5b7" />

</div>

---

## What's Inside

| Tab | Contents |
|-----|----------|
| **📡 Overview** | Master quick-reference — display filters, BPF syntax, TCP flags, operators, color codes |
| **🎣 Capture Filters** | BPF syntax: host, net, port, src/dst, compound filters — what gets recorded |
| **🔍 Display Filters** | Wireshark field syntax: ip.addr, http, dns, tcp flags, frame contains, regex matching |
| **🔬 Protocols** | DNS, HTTP, TLS, SMB, FTP, ICMP, ARP, SSH, DHCP, SMTP — deep protocol filters |
| **💻 TShark CLI** | Headless capture, -r/-w/-Y/-T/-e, field extraction, ring buffers, statistics |
| **💀 Attack Detection** | Port scan, ARP poisoning, DNS tunneling, brute force, C2 beaconing, SQLi, ICMP tunnel |
| **🔎 Forensics** | Follow TCP Stream, Export Objects, Protocol Hierarchy, Conversations, IO Graph |
| **⌨️ Shortcuts** | Complete keyboard reference + power-user tshark one-liners |
| **🎯 Interview Scenarios** | 10 real interview questions with full investigative methodology answers |

---

## Quick Start

**Option 1 — Just open it:**
```bash
git clone https://github.com/Oracleo/Wireshark-GOD-Level-Cheatsheet.git
cd Wireshark-GOD-Level-Cheatsheet
open Wireshark-GOD-Level-Cheatsheet.html   # macOS
xdg-open Wireshark-GOD-Level-Cheatsheet.html  # Linux
```

**Option 2 — Live on GitHub Pages:**

Visit → **[oracleo.github.io/Wireshark-GOD-Level-Cheatsheet](https://oracleo.github.io/Wireshark-GOD-Level-Cheatsheet/Wireshark-GOD-Level-Cheatsheet.html)**

---

## Filters & Techniques Covered



```
CAPTURE FILTERS (BPF)    │  DISPLAY FILTERS          │  PROTOCOL FILTERS
─────────────────────────┼───────────────────────────┼─────────────────────────
host 192.168.1.1         │  ip.addr == 192.168.1.1   │  dns.qry.name
src host / dst host      │  ip.src == / ip.dst ==    │  http.request.method
net 10.0.0.0/8           │  tcp.port == 4444         │  smb2.filename
port 443                 │  http.request.uri         │  ftp.request.command
not port 22              │  dns.qry.name contains    │  tls.handshake.type
host X and port Y        │  frame contains           │  arp.duplicate-address
ether host [MAC]         │  tcp.flags.syn==1&&ack==0 │  icmp && data.len > 64

ATTACK DETECTION         │  FORENSICS                │  TSHARK CLI
─────────────────────────┼───────────────────────────┼─────────────────────────
tcp.flags == 0x000       │  Follow TCP Stream        │  tshark -i eth0 -w file
tcp.flags == 0x029       │  Export Objects (HTTP/SMB)│  tshark -r file.pcap
arp.duplicate-address    │  Statistics → Hierarchy   │  tshark -Y "dns" -T fields
dns.qry.name matches     │  Statistics → Conversations│  tshark -e dns.qry.name
http.response.code==401  │  Analyze → Expert Info    │  tshark -z conv,tcp
```


---

## 🎯 Interview Scenarios Covered

Real questions you'll be asked, with full methodology answers:

```
1. "Detect a port scan in a PCAP"
   → tcp.flags.syn==1 && tcp.flags.ack==0 + Statistics → Conversations

2. "Difference between capture and display filters"  
   → BPF (kernel-level, pre-capture) vs Wireshark syntax (post-capture, protocol-aware)

3. "Extract credentials from a PCAP"
   → http.authbasic + ftp PASS + frame contains + Follow TCP Stream

4. "Investigate suspected malware on a host"
   → ip.addr → Protocol Hierarchy → Conversations → IO Graph → beaconing analysis

5. "Detect data exfiltration"
   → Conversations sorted by bytes + Export Objects + large payload filters

6. "Detect ARP poisoning / MITM"
   → arp.duplicate-address-detected (Wireshark auto-flags this)

7. "Investigate a web attack"
   → http.request + response codes + URI injection signatures

8. "Capture on a remote server (no GUI)"
   → tshark -i eth0 -w /tmp/cap.pcap + SCP + analyze locally

9. "What is DNS tunneling and how do you detect it?"
   → Long subdomains, high query frequency, large TXT responses, regex filters

10. "First 3 things you check in an unknown PCAP"
    → Expert Information → Protocol Hierarchy → Conversations sorted by bytes
```

---

## Features

- **🔎 Live Search** — Instantly filter across ALL 9 tabs simultaneously
- **📑 9 Organized Tabs** — From capture basics to advanced forensics
- **🎨 Packet Capture Aesthetic** — Deep blue terminal UI with animated packet flow
- **🏷️ Technique Badges** — CRITICAL / SOC / FORENSIC / ATTACK / PRO labels
- **💡 Guru Tips & Interview Boxes** — Contextual insights throughout
- **📱 Responsive** — Works on desktop and mobile
- **⚡ Zero Dependencies** — Single HTML file, works fully offline

---

## Who Is This For?

```
✅ SOC Analyst candidates (L1/L2/L3 interviews)
✅ DFIR investigators learning packet analysis
✅ Blue teamers building threat hunting skills
✅ CTF players (HackTheBox, TryHackMe — network challenges)
✅ Penetration testers learning to analyze their own traffic
✅ Security students (CompTIA Security+, CySA+, GCIH prep)
✅ Anyone learning Wireshark beyond the basics
```

---

## Tech Stack

| Layer | Choice | Why |
|-------|--------|-----|
| Structure | Pure HTML5 | Zero build step, instant open |
| Styling | CSS3 + Custom Properties | No framework bloat |
| Logic | Vanilla JavaScript | Live cross-tab search |
| Fonts | IBM Plex Mono + Syncopate + Barlow | Packet capture terminal aesthetic |
| Hosting | GitHub Pages | Free, fast, permanent URL |

---

## Repository Structure

```
Wireshark-GOD-Level-Cheatsheet/
│
├── Wireshark-GOD-Level-Cheatsheet.html   # ← The entire app. One file.
├── README.md                              # ← You are here
└── LICENSE                               # MIT
```

---

## 🔗 Related Projects

> Building a complete security tools reference series:

- 🟢 **[NMAP GOD Level Cheatsheet](https://github.com/Oracleo/Nmap-GOD-Level-Cheatsheet)** — Port scanning, recon, NSE scripts, firewall evasion
- 🔵 **Wireshark GOD Level Cheatsheet** ← You are here

*More tools coming: Metasploit, Burp Suite, Splunk, Volatility...*

---

## 🤝 Contributing

Found a missing filter? Know a better interview answer? PRs welcome.

```bash
git clone https://github.com/Oracleo/Wireshark-GOD-Level-Cheatsheet.git
```

Open an issue to suggest new sections — Zeek/Bro filters, Suricata rule comparison, JA3 fingerprinting, NetworkMiner comparison.

---

## 📜 License

MIT — use it, share it, build on it.

---

## 🌐 Connect

If this helped you land a role or ace an interview, I'd love to know.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077b5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/dr-niladri-biswas/)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Oracleo)

---

<div align="center">

**Built for the security community. Analyze every packet. Miss nothing.**

`wireshark` · `tshark` · `packet-analysis` · `soc` · `dfir` · `blue-team` · `network-forensics` · `cybersecurity` · `interview-prep` · `pcap`

</div>
