# CYBERSECURITY-TASK-3
Security Assessment Report
Critical Priority: High Severity (10.0)
The most urgent issue identified is a Report of an outdated or end-of-life (EOL) Scan Engine. This is a "meta-vulnerability"—it means the very tool you are using to find security holes is itself insecure or no longer receiving updates.
Impact: Because the scan engine is EOL, the 97% Quality of Detection (QoD) suggests that while this alert is accurate, there may be many other "High" or "Critical" vulnerabilities on this machine that the scanner simply missed because its database is out of date.
Recommendation: Prioritize updating the Greenbone Security Assistant environment and its NVTs (Network Vulnerability Tests) before performing a follow-up scan.
Secondary Concerns: Medium Severity
There are two distinct issues relating to how the server communicates over the network:
1. DCE/RPC and MSRPC Services Enumeration (Severity 5.0)
The scanner found that Port 135/tcp is allowing a remote user to list (enumerate) the services currently running on the Windows host.
Impact: While not a direct exploit, this provides an attacker with a roadmap of the system’s internal architecture, making it much easier to plan a targeted attack.
Recommendation: If this machine does not need to be managed remotely via RPC, consider blocking Port 135 at the firewall level or restricting it to specific administrative IP addresses.
2. Deprecated SSL/TLS Protocol Detection (Severity 4.3)
On Port 3389/tcp (Remote Desktop), the system is still accepting connections via TLS 1.0 and TLS 1.1.
Impact: These protocols are technically obsolete and susceptible to decryption attacks (like BEAST or POODLE). Modern security standards require the use of TLS 1.2 or TLS 1.3.
Recommendation: Disable TLS 1.0 and 1.1 in the Windows Registry or via Group Policy (GPO) to force the use of more secure encryption for RDP sessions.
Summary of Exposure
The presence of deprecated protocols and open enumeration services suggests this host is likely running a default or older Windows configuration that hasn't been "hardened" for a production environment. However, the EOL status of the scanner remains the primary blocker for a truly accurate risk assessment.
