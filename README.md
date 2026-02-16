# CYBERSECURITY-TASK-3
Vulnerability Assessment Report – plabwin10
Target Details
Hostname: plabwin10.practicelabs.com
IP Address: 192.168.0.4
Scan Engine: Greenbone Security Assistant
High Severity Findings
Vulnerability
Severity
Detection Quality
Issue
Impact
Remediation
Outdated / EOL Scan Engine
10.0
97%
The vulnerability scanner environment is end-of-life (EOL).
New threats may go undetected due to outdated signature databases.
Upgrade the Greenbone scan engine and update NVTs (Network Vulnerability Tests).
Medium Severity Findings
Vulnerability
Severity
Port
Issue
Impact
Remediation
MSRPC Service Enumeration
5.0
135/tcp
The system allows remote users to list internal services.
Provides an attacker with a detailed map of the system's architecture.
Restrict access to Port 135 using a host-based firewall.
Deprecated TLS (v1.0/v1.1)
4.3
3389/tcp (RDP)
Remote Desktop is using obsolete encryption protocols.
Vulnerable to decryption and Man-in-the-Middle (MITM) attacks.
Disable TLS 1.0/1.1 via Registry/Group Policy and enforce TLS 1.2 or higher.
Remediation Summary
Update Environment: Refresh the scanner feed to ensure full visibility of vulnerabilities.
Hardening:
Block Port 135 to prevent service enumeration.
Disable legacy TLS (1.0/1.1) on Port 3389 and enforce TLS 1.2 or higher.
Rescan: Perform a follow-up scan to verify all patches and mitigations have been applied.
