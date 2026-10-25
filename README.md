# 🦉 OJA3

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-Security-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0-cyan?style=flat-square"/>
</p>

> **OJA3** — part of the OwlSec Toolkit.

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

OJA3 fingerprints TLS clients and servers so you can spot malware, scanners and unusual software on your network. It reads every ClientHello and ServerHello in a packet capture, decodes raw hello hex, or connects to a live server to fingerprint its ServerHello. The resulting hashes are checked against JA3 blocklists such as abuse.ch SSLBL.

---

## ✨ Features

- Accurate JA3 (GREASE preserved, checked byte-for-byte against Salesforce pyja3) and JA3S server fingerprints
- JA4 and JA4S following the FoxIO spec (sorted ciphers/extensions, ALPN, SNI flag)
- PCAP reader (Ethernet, raw IP, Linux SLL) that extracts every ClientHello and ServerHello
- Live mode: sends a ClientHello to host:port and fingerprints the server reply
- Blocklist matching (abuse.ch SSLBL CSV or a plain hash list) plus heuristics for legacy TLS and scanner-like hellos
- Cipher-suite and extension reference, fingerprint compare mode, and TXT/JSON/MD/CSV/SARIF reports

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OJA3                                       # interactive menu
./OJA3 --pcap capture.pcap --blocklist sslbl_ja3.csv
./OJA3 --live example.com:443
./OJA3 --compare <hashA> <hashB>
```

Run `./OJA3 --help` for the full list of options.

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
