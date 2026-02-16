# CYBERSECURITY-TASK-3


# 🔐 Vulnerability Assessment Report – plabwin10

## 📌 Project Overview

This project documents a vulnerability assessment conducted on a Windows 10 lab machine using Greenbone Security Assistant. The objective was to identify security weaknesses, analyze associated risks, and implement remediation measures to harden the system.

This repository demonstrates practical vulnerability management skills including:

* Network-based vulnerability scanning
* Risk analysis and impact assessment
* Secure configuration hardening
* Remediation validation

---

# 🎯 Objective

* Identify exposed services and misconfigurations.
* Evaluate severity and exploitation risk.
* Implement mitigation strategies.
* Validate remediation through follow-up assessment.

---

# 🖥️ Target Details

| Parameter        | Value                        |
| ---------------- | ---------------------------- |
| Hostname         | plabwin10.practicelabs.com   |
| IP Address       | 192.168.0.4                  |
| Operating System | Windows 10 (Lab Environment) |
| Scan Tool        | Greenbone Security Assistant |
| Scan Type        | Full and Fast Network Scan   |

---

# 🛠️ Tools Used

* Greenbone Security Assistant (GSA)
* Windows Firewall
* Windows Registry Editor
* Group Policy Editor
* PowerShell

---

# 🔍 Scan Methodology

1. Configured target IP in Greenbone.
2. Launched Full & Fast vulnerability scan.
3. Reviewed severity classifications.
4. Analyzed service exposure.
5. Documented findings.
6. Applied remediation.
7. Conducted validation scan.

---

# 🚨 Findings Summary

| Severity | Count |
| -------- | ----- |
| High     | 1     |
| Medium   | 2     |
| Low      | 0     |

---

# 🔴 High Severity Finding

## 1. Outdated / End-of-Life Scan Engine

* Severity Score: 10.0 (Critical)
* Detection Quality: 97%

### Description

The vulnerability scanning environment was identified as End-of-Life (EOL), meaning signature databases may not detect newly discovered vulnerabilities.

### Risk Impact

* Reduced visibility of modern threats
* False sense of security
* Incomplete vulnerability reporting

### Exploitation Scenario

An organization relying on outdated vulnerability databases may fail to detect newly published exploits, leaving systems exposed to zero-day or recently disclosed vulnerabilities.

### Remediation

* Upgrade Greenbone Scan Engine.
* Update Network Vulnerability Tests (NVTs).
* Verify database synchronization after update.

---

# 🟠 Medium Severity Findings

## 2. MSRPC Service Enumeration (Port 135/tcp)

* Severity: 5.0
* Port: 135/tcp
* Service: MSRPC

### Description

The system allows remote enumeration of internal services via MSRPC.

### Risk Impact

* Enables attackers to gather system architecture details.
* Supports reconnaissance phase of cyber attack lifecycle.
* Can aid in lateral movement.

### Attack Scenario

An attacker performs network reconnaissance and enumerates services exposed via MSRPC. The information obtained helps craft targeted exploitation attempts.

### Remediation

Block or restrict port 135 using Windows Firewall:

```powershell
New-NetFirewallRule -DisplayName "Block MSRPC 135" -Direction Inbound -Protocol TCP -LocalPort 135 -Action Block
```

Allow only trusted internal IP ranges if required.

---

## 3. Deprecated TLS Versions (TLS 1.0 / TLS 1.1) – Port 3389 (RDP)

* Severity: 4.3
* Port: 3389/tcp
* Service: Remote Desktop Protocol

### Description

Obsolete TLS versions are enabled on RDP service.

### Risk Impact

* Vulnerable to cryptographic downgrade attacks.
* Susceptible to Man-in-the-Middle (MITM) attacks.
* Weak encryption standards.

### Attack Scenario

An attacker intercepts RDP traffic and forces a downgrade to weaker TLS protocols, increasing the possibility of decryption or session compromise.

### Remediation

Disable TLS 1.0 and TLS 1.1 via Registry:

```powershell
New-Item -Path 'HKLM:\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server' -Force
Set-ItemProperty -Path 'HKLM:\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server' -Name 'Enabled' -Value 0

New-Item -Path 'HKLM:\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server' -Force
Set-ItemProperty -Path 'HKLM:\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server' -Name 'Enabled' -Value 0
```

Reboot the system and verify TLS 1.2 is enforced.

---

# 🛡️ Risk Assessment

| Vulnerability  | Likelihood | Impact | Risk Level |
| -------------- | ---------- | ------ | ---------- |
| EOL Scanner    | Medium     | High   | High       |
| MSRPC Exposure | Medium     | Medium | Medium     |
| Deprecated TLS | Medium     | Medium | Medium     |

---

# 🔁 Post-Remediation Validation

After applying all mitigation measures:

1. Performed follow-up vulnerability scan.
2. Confirmed:

   * Scanner environment updated.
   * Port 135 restricted.
   * TLS 1.0 and 1.1 disabled.
3. Documented security improvements.

---

# 📈 Security Improvement Outcome

* Reduced attack surface.
* Eliminated insecure encryption protocols.
* Improved vulnerability detection accuracy.
* Strengthened overall system hardening.

---

# 📚 Key Skills Demonstrated

* Vulnerability Assessment & Analysis
* Windows System Hardening
* Firewall Configuration
* Secure Protocol Enforcement
* Risk Evaluation & Documentation

---

# 🏁 Conclusion

The assessment identified critical and medium-level vulnerabilities affecting system security posture. After implementing corrective measures, the system’s exposure to reconnaissance and cryptographic attacks was significantly reduced.

This project demonstrates practical understanding of vulnerability management lifecycle:

Identification → Analysis → Remediation → Validation

---
