# Lab 1: Practical Vulnerability Assessment (Metasploitable 2)

**Author:** Esther  
**Scan date:** 23 October 2026  
**Target:** Metasploitable 2 (`192.168.56.101`) in an isolated VirtualBox lab network  
**Assessor machine:** Kali Linux

I scanned a deliberately vulnerable server with Nmap, Nikto and Nuclei, then turned the results into a risk assessment and an executive summary.

## What is in this folder

| Item | What it is |
|---|---|
| [Report.md](Report.md) | Full report: commands, Risk Assessment Table, Executive Summary |
| [scans/](scans/) | Raw scan outputs (Nmap, Nikto, Nuclei) |
| [screenshots/](screenshots/) | Evidence screenshots, labelled Figure 1.0 to 6.1 |

## Quick results

- **Nmap:** 30 open ports, Linux kernel from 2008
- **Nikto:** 31 web findings
- **Nuclei:** 71 matches, 5 rated critical
