# CYBERSECURITY-TASK-3

🔐 Vulnerability Assessment Report – plabwin10
📌 Target Details
Field	Value
Hostname	plabwin10.practicelabs.com
IP Address	192.168.0.4
Scan Engine	Greenbone Security Assistant
🚨 High Severity Findings
1️⃣ Outdated / EOL Scan Engine
Severity: 10.0 (Critical)

Detection Quality: 97%

Issue: The vulnerability scanner environment is End-of-Life (EOL).

Impact:

New and emerging threats may go undetected.

Outdated signature databases reduce scan reliability.

Recommended Fix:

Upgrade the Greenbone Scan Engine.

Update all Network Vulnerability Tests (NVTs).

Verify scan engine version after update.

⚠️ Medium Severity Findings
2️⃣ MSRPC Service Enumeration (Port 135/tcp)
Severity: 5.0

Port: 135/tcp

Issue: The system allows remote users to enumerate internal services via MSRPC.

Impact:

Attackers can gather detailed system architecture information.

Increases risk of targeted exploitation.

Recommended Fix:

Restrict access to port 135 using a host-based firewall (Windows Firewall).

Allow only trusted internal network ranges if required.

3️⃣ Deprecated TLS Versions (v1.0 / v1.1) – Port 3389/tcp (RDP)
Severity: 4.3

Port: 3389/tcp

Service: Remote Desktop Protocol (RDP)

Issue: Obsolete TLS versions (1.0 and 1.1) are enabled.

Impact:

Susceptible to decryption attacks.

Vulnerable to Man-in-the-Middle (MITM) attacks.

Recommended Fix:

Disable TLS 1.0 and TLS 1.1 via:

Windows Registry

Group Policy Editor

Enforce TLS 1.2 or higher.

Restart system and verify configuration.

🛠️ Remediation Summary
✅ Immediate Actions Required
Upgrade and update the vulnerability scan engine.

Harden system network exposure.

Disable legacy encryption protocols.

Validate fixes through a follow-up security scan.

🔁 Post-Remediation Validation
After applying all fixes:

Perform a full vulnerability re-scan.

Confirm:

No EOL scanner warnings.

Port 135 properly restricted.

TLS 1.0/1.1 fully disabled.

Document remediation evidence.

Update repository with revised scan results.

📊 Overall Risk Posture
Severity Level	Count
High	1
Medium	2
Low	0
📌 Conclusion
The system requires immediate scanner updates and network hardening measures.
Once remediation steps are implemented and verified, overall exposure will be significantly reduced.

