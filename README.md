# 🕷️ HACKEROFHELL ULTRA v6.0 – 100x Power Auto‑Pentester

<p align="center">
  <img src="https://img.shields.io/badge/Version-6.0--100x-red?style=for-the-badge&logo=hackthebox" />
  <img src="https://img.shields.io/badge/Author-RAJESH%20BAJIYA-blue?style=for-the-badge&logo=github" />
  <img src="https://img.shields.io/badge/Handle-HACKEROFHELL-brightgreen?style=for-the-badge" />
  <img src="https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge" />
</p>

<p align="center">
  <b>The most advanced, fully‑automated bug bounty & penetration testing framework ever built.</b><br>
  <i>“Built by a man from Hell – for bug bounty hunters from Hell.”</i>
</p>

---

## 🔥 What is HACKEROFHELL ULTRA?

ULTRA v6.0 is a **100x power evolution** of the original one‑click installer.  
It turns a single target (domain or IP) into a **complete, professional‑grade security assessment** – fully automated, from OSINT to exploitation.

- **30 phases** covering everything: subdomain enumeration, port scanning, web fingerprinting, content discovery, parameter mining, authentication attacks, injections (SQLi, NoSQLi, SSTI, XXE, SSRF…), client‑side (XSS, CSRF, CORS), server‑side (LFI, RCE, deserialization), cloud (S3, Firebase, K8s), secrets exposure, CVE scanning, subdomain takeover, network attacks, **bug chain analysis**, and **auto‑exploitation**.
- **150+ integrated tools** – all the best open‑source scanners, fuzzers, and exploit frameworks, seamlessly orchestrated.
- **Auto‑repair engine** – if a tool is missing, it installs it on the fly. If a command fails, it retries with fallbacks.
- **Parallel execution** – up to 50 concurrent jobs, making scans lightning fast.
- **Smart chain analysis** – automatically links low‑level bugs into critical escalation paths (e.g., XSS + CORS → ATO, SSRF + Redis → RCE).
- **Professional HTML report** – executive summary, CVSS scoring, PoC commands, remediation advice, and a hacker‑style UI.
- **Your fingerprints everywhere** – `RAJESH BAJIYA` / `HACKEROFHELL` proudly displayed.

> **⚠️ LEGAL DISCLAIMER:** This tool is for **authorized testing only**. Unauthorized use against systems you do not own or have explicit permission to test is illegal. The author assumes no liability for misuse.

---

## 🚀 Features – 100x Power

| Feature | Description |
|--------|-------------|
| **30 Phases** | From OSINT to auto‑exploit, covering every attack vector. |
| **150+ Tools** | Subfinder, Amass, Nuclei, Dalfox, SQLMap, Feroxbuster, FFUF, Nmap, Masscan, WhatWeb, WPScan, Nikto, Gobuster, Gau, Waybackurls, Httpx, Dnsx, Katana, Naabu, Smuggler, Crlfuzz, Kxss, Gxss, Cariddi, Gitrob, TruffleHog, Arjun, ParamSpider, and many more. |
| **Auto‑Repair** | Missing tools are auto‑installed via `go install` or `apt`. Commands retry on failure. |
| **Parallel Execution** | 50+ concurrent jobs – maximum speed. |
| **Bug Chain Analysis** | Finds multi‑stage vulnerabilities (e.g., SSRF + Redis → RCE). |
| **Auto‑Exploit** | Attempts to exploit critical findings (optional). |
| **Cloud Checks** | AWS S3, Azure Blob, GCP, Firebase, Kubernetes, Docker API. |
| **Subdomain Takeover** | Checks 20+ cloud services (AWS, GitHub, Heroku, etc.). |
| **Comprehensive Reporting** | HTML report with executive summary, CVSS, PoC, remediation. |
| **Proxy Support** | Route all traffic through Burp Suite or another proxy. |
| **Webhook Notifications** | Slack / Discord alerts on critical findings. |

---

## 📦 Installation

### One‑liner (recommended)

```bash
sudo bash -c "$(curl -fsSL https://raw.githubusercontent.com/your-repo/hackerofhell_ultra/main/install_ultra.sh)"
```

### Manual

```bash
git clone https://github.com/thehellrider978/HACKEROFHELL-ULTRA-v6.0-Lite.git
cd hackerofhell_ultra
sudo bash install_ultra.sh
```

The installer will:
- Update your system
- Install all APT dependencies (nmap, masscan, go, python3, etc.)
- Install 100+ Go tools
- Install Python tools (arjun, paramspider, truffleHog, etc.)
- Set up `gf` patterns
- Place the main script in `~/autopwn/hackerofhell_ultra.sh`

> **Note:** The installer requires root privileges (for masscan, nmap, etc.). It is safe to run as root.

---

## 🎯 Usage

```bash
sudo bash ~/autopwn/hackerofhell_ultra.sh -t <target> [options]
```

### Required

| Option | Description |
|--------|-------------|
| `-t, --target` | Target domain (e.g., `example.com`) or IP address. |

### Scan Modes

| Option | Description |
|--------|-------------|
| `-m, --mode` | `passive` (only OSINT), `normal` (default), `ultra` (maximum depth). |
| `--deep` | Full 65535‑port scan + all modules. |
| `--ultra` | Same as `-m ultra`. |
| `--skip-heavy` | Skip slow modules (SQLMap, brute‑force). |
| `--chain` | Enable bug chain analysis (default: on). |

### Output

| Option | Description |
|--------|-------------|
| `-o, --output` | Output directory (default: `~/hackerofhell_ultra/<target>/`). |

### Rate / Threads

| Option | Description |
|--------|-------------|
| `-r, --rate` | Requests per second (default: 200). |
| `-T, --threads` | Concurrent threads (default: 100). |

### Integrations

| Option | Description |
|--------|-------------|
| `-p, --proxy` | HTTP proxy (e.g., `http://127.0.0.1:8080`). |
| `-n, --notify` | Slack/Discord webhook URL for notifications. |
| `--shodan KEY` | Shodan API key. |
| `--github TOKEN` | GitHub API token. |
| `--vt KEY` | VirusTotal API key. |
| `--censys ID:SECRET` | Censys API credentials. |

### Wordlist

| Option | Description |
|--------|-------------|
| `-w, --wordlist` | Custom wordlist for directory fuzzing. |

### Auto‑install

| Option | Description |
|--------|-------------|
| `--auto-install` | Auto‑install missing tools (default: true). |

### Help

| Option | Description |
|--------|-------------|
| `-h, --help` | Show help message. |

---

## 📋 Examples

### Basic scan (normal mode)

```bash
sudo bash ~/autopwn/hackerofhell_ultra.sh -t example.com
```

### Ultra‑deep scan with chain analysis

```bash
sudo bash ~/autopwn/hackerofhell_ultra.sh -t example.com --ultra --deep --chain
```

### Use proxy and notify Slack

```bash
sudo bash ~/autopwn/hackerofhell_ultra.sh -t example.com -p http://127.0.0.1:8080 -n https://hooks.slack.com/...
```

### Passive reconnaissance only

```bash
sudo bash ~/autopwn/hackerofhell_ultra.sh -t example.com -m passive
```

### Skip heavy modules (fast)

```bash
sudo bash ~/autopwn/hackerofhell_ultra.sh -t example.com --skip-heavy
```

---

## 📁 Output Structure

After the scan, all results are stored in `~/hackerofhell_ultra/<target>/`:

```
├── 00_preflight/            # Pre‑flight checks
├── 01_osint/                # Subdomains, DNS, emails, OSINT
├── 02_infra/                # Port scans, CDN, cloud detection
├── 03_fingerprint/          # HTTPX, WAF, tech stack
├── 04_content/              # Directory brute‑force, sensitive files
├── 05_params/               # Parameter mining, JS secrets
├── 06_auth/                 # Login endpoints, default creds, JWT
├── 07_injection/            # SQLi, NoSQLi, SSTI, XXE, LDAP, etc.
├── 08_client/               # XSS, CSRF, open redirect, clickjacking
├── 09_server/               # LFI, RFI, RCE, SSRF, HTTP smuggling
├── 10_access/               # IDOR, 403 bypass, privilege escalation
├── 11_logic/                # Business logic flaws, race conditions
├── 12_api/                  # API endpoints, GraphQL, mass assignment
├── 13_cloud/                # S3, Azure, GCP, Firebase, K8s, Docker
├── 14_secrets/              # Git exposure, stack traces, backups
├── 15_cve/                  # Nuclei CVE scan
├── 16_subdomain_attacks/    # Subdomain takeover
├── 17_network/              # CORS, DNS rebinding, TLS, SPF/DMARC
├── 18_chain/                # Bug chain analysis
├── 19_verify/               # Deduplication, false‑positive removal
├── 20_report/               # Final HTML report
├── 21_exploit/              # Auto‑exploitation attempts
├── 22_auto_repair/          # Logs of auto‑install actions
└── findings_ultra.json      # All findings in JSON
```

---

## 📊 Reporting

The final report is an **interactive HTML document** located at:

```
~/hackerofhell_ultra/<target>/20_report/HACKEROFHELL_<target>_<timestamp>.html
```

It includes:
- Executive summary with risk score
- Severity breakdown (Critical, High, Medium, Low)
- Vulnerability chains (escalation paths)
- Detailed findings with:
  - Title, severity, CVSS score
  - Affected URL / parameter
  - Evidence (response snippets)
  - Proof‑of‑concept commands
  - Remediation advice
- Hacker‑style dark theme with copy‑to‑clipboard PoC buttons

Open it in any browser:

```bash
firefox ~/hackerofhell_ultra/example.com/20_report/HACKEROFHELL_example_com_*.html
```

---

## 🧠 How It Works – 100x Power Under the Hood

1. **Preflight** – Checks for all required tools; auto‑installs missing ones.
2. **OSINT** – Harvests subdomains from 20+ sources, DNS records, emails, historical URLs.
3. **Infrastructure** – Full port scan (with Masscan/Nmap), service detection, CDN/origin IP hunting.
4. **Fingerprinting** – Probes all live hosts for tech stack, WAF, headers, CMS.
5. **Content Discovery** – Recursive directory brute‑force, sensitive file checks (env, git, backups).
6. **Parameter Mining** – Extracts parameters from URLs, JS files, uses Arjun, ParamSpider.
7. **Authentication** – Tests default credentials, user enumeration, JWT weaknesses, OAuth misconfigs.
8. **Injection** – Runs SQLMap, NoSQLi payloads, SSTI, XXE, LDAP, command injection (time‑based).
9. **Client‑Side** – Dalfox for XSS, CSRF detection, clickjacking, open redirects.
10. **Server‑Side** – LFI, RFI, SSRF (cloud metadata), HTTP smuggling.
11. **Access Control** – IDOR enumeration, 403 bypass techniques.
12. **Business Logic** – Race conditions, price manipulation.
13. **API Security** – GraphQL introspection, mass assignment, rate limiting.
14. **Cloud** – Checks public S3, Azure, GCP, Firebase, K8s, Docker.
15. **Secrets** – Git dumps, stack traces, source code disclosure.
16. **CVE Scanning** – Nuclei with all templates (cves, misconfigs, exposures).
17. **Subdomain Attacks** – Takeover checks for 20+ services.
18. **Network** – CORS misconfig, DNS rebinding, TLS, SPF/DMARC.
19. **Chain Analysis** – Python logic links findings into attack chains.
20. **Verification** – Deduplicates, recalculates severity, removes false positives.
21. **Auto‑Exploit** – Attempts to gain shells or extract data from critical vulns.
22. **Reporting** – Generates the final HTML report.

All phases run **in parallel** where possible, with smart job control and error handling.

---

## 👨‍💻 Author

**RAJESH BAJIYA** – also known as **HACKEROFHELL**  
- Creator of the HACKEROFHELL ULTRA series  
- Passionate about offensive security, automation, and bug bounty  
- “I build tools that do the impossible – automatically.”

---

## 📜 License

This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.  
You are free to use, modify, and distribute it, but **you are solely responsible for your actions**.

---

## ☕ Support

- **GitHub Issues**: [https://github.com/your-repo/hackerofhell_ultra/issues](https://github.com/your-repo/hackerofhell_ultra/issues)  
- **Email**: (not provided for security reasons)  
- **Follow me on Twitter**: [@HACKEROFHELL](https://twitter.com/HACKEROFHELL) (if exists)

---

<p align="center">
  <b>If this tool helped you find a critical bug, consider buying me a coffee ☕</b><br>
  <i>RAJESH BAJIYA / HACKEROFHELL</i>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/MADE%20IN%20HELL-ff0000?style=for-the-badge" />
</p>
