# CYBERSECURITY-TASK-3
Vulnerability Assessment Report: plabwin10
Target Details
Hostname: plabwin10.practicelabs.com
IP Address: 192.168.0.4
Scan Engine: Greenbone Security Assistant
High Severity Findings
🔴 Outdated / EOL Scan Engine
Severity: 10.0
Detection Quality: 97%
Issue: The vulnerability scanner environment is end-of-life (EOL).
Impact: New threats may go undetected due to outdated signature databases.
Fix: Upgrade the Greenbone scan engine and update NVTs (Network Vulnerability Tests).
Medium Severity Findings
🟡 MSRPC Service Enumeration
Severity: 5.0
Port: 135/tcp
Issue: The system allows remote users to list internal services.
Impact: Provides an attacker with a detailed map of the system's architecture.
Fix: Restrict access to Port 135 using a host-based firewall.
🟡 Deprecated TLS (v1.0/v1.1)
Severity: 4.3
Port: 3389/tcp (RDP)
Issue: Remote Desktop is using obsolete encryption protocols.
Impact: Vulnerable to decryption and Man-in-the-Middle (MITM) attacks.
Fix: Disable TLS 1.0/1.1 via Registry/Group Policy and enforce TLS 1.2 or higher.
Remediation Summary
Update Environment: Refresh the scanner feed to ensure total visibility.
Hardening: Block Port 135 and disable legacy TLS on Port 3389.
Rescan: Perform a follow-up scan to verify all patches.
