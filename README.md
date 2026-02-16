# CYBERSECURITY-TASK-3
Vulnerability Scan Report:
Target Information
Host IP: 192.168.0.4
Hostname: kali
Scan Tool: Greenbone Security Assistant (GSA)
Date: Aug 2, 2023
Critical Findings (High Severity)
🚨 Report Outdated / EOL Scan Engine
Severity: 10.0 (High)
Location: general/tcp
QoD: 97%
Summary: The Greenbone vulnerability feed or engine is end-of-life.
Impact: Results may be inaccurate or missing critical new vulnerabilities.
Remediation: Update the GVM/OpenVAS feed and upgrade the scanner to a supported version.
Medium Severity Findings
⚠️ DCE/RPC and MSRPC Services Enumeration
Severity: 5.0 (Medium)
Location: Port 135/tcp
QoD: 80%
Summary: Allows remote attackers to enumerate system services.
Impact: Information leakage that assists in reconnaissance for further attacks.
Remediation: Filter Port 135 at the firewall level to allow only trusted administrative traffic.
⚠️ SSL/TLS: Deprecated TLSv1.0 and TLSv1.1 Detection
Severity: 4.3 (Medium)
Location: Port 3389/tcp (RDP)
QoD: 98%
Summary: Weak encryption protocols are enabled for Remote Desktop.
Impact: Susceptible to man-in-the-middle (MITM) attacks and credential theft.
Remediation: Disable TLS 1.0/1.1 in Windows Registry/Group Policy and enforce TLS 1.2+.
Summary Table of Actions
Update Scanner Environment (Mandatory for accurate data).
Restrict RPC (Port 135) via Network Security Groups or Firewalls.
Hardening RDP (Port 3389) by disabling legacy TLS versions.
