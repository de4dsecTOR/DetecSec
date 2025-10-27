# 🛡️ DetecSec 11  
**A Custom Windows 11 sandbox build for Malware Analysis and Forensics**

![DetecSec Logo](./assets/detecsec_logo.png)

---

## 📘 Overview
**DetecSec 11** is a customized Windows 11 environment designed for **malware analysis, vulnerability assessment, and network defense operations**.  
It provides a pre-configured lab setup with essential tools for both **offensive and defensive security tasks**, all neatly organized and ready to use right after installation.

This project aims to give analysts, researchers, and students a Windows-based sandbox that’s as powerful and practical as Kali Linux or REMnux — but tailored for Windows defenders.

---

## ⚙️ Key Features
- 🧰 **Preinstalled Analysis Tools** – Static, dynamic, and forensic utilities ready out of the box.  
- 🪟 **Windows 11 Core Interface** – Retains the modern Windows UX, with security tweaks and telemetry reduction.  
- 🧩 **Custom Start Menu Layout** – Tools are organized into logical categories (System, Static, Network, Forensics, etc.).  
- 🧱 **Defensive Configuration** – Hardened system policies and visibility tools for malware behavior tracking.  
- 💡 **Portable-Ready Environment** – Most tools can be run directly without installation.  
- 🧑‍💻 **Designed for Virtualization** – Ideal for use inside VirtualBox, VMware, or Hyper-V.

---

## 🧩 Tool Categories

| Category | Purpose | Example Tools |
|-----------|----------|----------------|
| 🧠 **System Analysis** | Process and system inspection | Process Monitor, Autoruns, TCPView |
| 🧬 **Static Analysis** | File and binary examination | CFF Explorer, PEiD, HashMyFiles |
| 🕵️ **Forensics** | Evidence gathering and disk analysis | Autopsy, FTK Imager, Bulk Extractor |
| 🌐 **Network Tools** | Traffic capture and analysis | Wireshark, WinDump, Nmap |
| 🔍 **Vulnerability Scanning** | Detect misconfigurations and weak points | OpenVAS, Nikto, Nessus (optional) |
| 🧰 **Misc Utilities** | Scripting, automation, runtime libraries | PowerShell Tools, Visual C++ Runtimes |

---

## 🧠 Installation Guide

### 1️⃣ Create a New Virtual Machine
- Use **VirtualBox** or **VMware**  
- Minimum Specs:
  - 2 CPU cores
  - 4 GB RAM (8 GB recommended)
  - 40 GB storage
- Load your `DetecSec_11.iso`

### 2️⃣ Initial Setup
Once Windows is installed:
1. Log in as **Administrator**  
2. Run `Setup-DetecSecMenu.ps1` (included in `C:\DetecSec Tools\Setup`)  
3. This script automatically:
   - Creates Start Menu shortcuts  
   - Organizes tools by category  
   - (Optional) Pins selected tools to Start

### 3️⃣ Runtime Dependencies
If any tools fail to start (e.g. missing DLLs), install:
- [Microsoft Visual C++ Redistributable (x64/x86)](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist)
- [.NET Framework 4.8 or later](https://dotnet.microsoft.com/en-us/download/dotnet-framework)
- [Npcap (for WinDump & Wireshark)](https://npcap.com)

---

## 🧪 Example Usage

```powershell
# Run DetecSec Tools setup script
Set-ExecutionPolicy Bypass -Scope Process -Force
C:\DetecSec Tools\Setup\Setup-DetecSecMenu.ps1

# Launch Process Monitor
Start-Process "C:\DetecSec Tools\System Analysis\Procmon.exe"

# Capture network traffic
WinDump -D
