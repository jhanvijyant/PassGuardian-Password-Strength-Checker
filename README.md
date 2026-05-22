# PassGuardian — Password Strength Analyzer

> A real-time password auditing tool built with Python, aligned with NIST SP 800-63B guidelines and integrated with the HaveIBeenPwned API to detect breached credentials.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Tkinter](https://img.shields.io/badge/GUI-Tkinter-blue?style=flat-square)
![NIST](https://img.shields.io/badge/Standard-NIST_SP_800--63B-green?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)

---

## What It Does

PassGuardian evaluates password strength in real time using a multi-factor scoring engine and checks whether your password has appeared in known data breaches — without ever sending your actual password over the network.

**Core features:**
- Multi-factor scoring: entropy (bits), length compliance, character diversity, keyboard-walk detection, dictionary-word flagging
- HaveIBeenPwned API integration via **k-anonymity model** (SHA-1 prefix lookup) — credentials checked against 800M+ breached hashes privately
- Tiered remediation feedback with estimated brute-force crack times
- Promotes passphrase adoption and MFA awareness
- Clean desktop GUI built with Tkinter

---

## Tech Stack

| Component | Technology |
|---|---|
| Language | Python 3.x |
| GUI | Tkinter |
| API | HaveIBeenPwned Pwned Passwords v3 |
| Security Standard | NIST SP 800-63B |
| Packaging | PyInstaller (.exe) |

---

## How to Run

```bash
# Clone the repository
git clone https://github.com/jhanvijyant/PassGuardian-Password-Strength-Checker.git
cd PassGuardian-Password-Strength-Checker

# Install dependencies
pip install requests

# Run the app
python code.py
```

---

## How the Breach Check Works (k-anonymity)

PassGuardian never sends your full password to any external server. Instead it:

1. Computes the SHA-1 hash of your password locally
2. Sends only the **first 5 characters** of the hash to the HaveIBeenPwned API
3. Receives a list of matching hash suffixes
4. Checks locally whether your full hash is in the list

This means your plaintext password — and even your full hash — never leaves your machine.

---

## Strength Evaluation Logic

- Password length (minimum 12 characters per NIST)
- Uppercase and lowercase character presence
- Numeric digit inclusion
- Special character inclusion
- Entropy calculation in bits
- Keyboard-walk pattern detection (e.g., `qwerty`, `12345`)
- Dictionary-word flagging
- Crack-time estimation (seconds to centuries)

---

## Topics

`python` `cybersecurity` `password-security` `nist` `tkinter` `haveibeenpwned` `k-anonymity` `digital-forensics` `infosec`

---

## Author

**Jhanvi Jyant** — B.Tech CSE (Cybersecurity & Digital Forensics), VIT Bhopal

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/jhanvi-jyant-26934b291)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/jhanvijyant)
