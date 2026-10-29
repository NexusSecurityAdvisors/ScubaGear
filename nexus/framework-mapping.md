# Framework Mapping: ScubaGear Baselines

How to map ScubaGear (M365 SCuBA baseline) results to the frameworks Nexus clients care about. This is a **family-level starting point**; validate each mapping against the specific control text before it goes into a client report.

| SCuBA baseline area | NIST CSF 2.0 | NIST SP 800-171 / CMMC L2 | HIPAA Security Rule | SOC 2 (TSC) |
|---|---|---|---|---|
| **Entra ID (aad):** MFA, legacy auth, Conditional Access, privileged roles | PR.AA | 3.1 Access Control, 3.5 Identification & Authentication | §164.312(a) Access control, §164.312(d) Authentication | CC6.1–CC6.3 |
| **Exchange Online (exo):** SPF/DKIM/DMARC, forwarding, mailbox auditing | PR.DS, DE.CM | 3.13 System & Communications Protection, 3.3 Audit & Accountability | §164.312(e) Transmission security, §164.312(b) Audit controls | CC6.7, CC7.2 |
| **Defender:** anti-phishing, Safe Links/Attachments, alerting, DLP | PR.PS, DE.CM, DE.AE | 3.14 System & Information Integrity | §164.308(a)(5)(ii)(B) Protection from malicious software | CC6.8, CC7.2 |
| **SharePoint / OneDrive:** external sharing, link defaults | PR.DS, PR.AA | 3.1 Access Control (3.1.3 control CUI flow), 3.13 SC | §164.312(a) Access control | CC6.1, CC6.7 |
| **Teams:** external access, guest access, meeting controls | PR.AA, PR.DS | 3.1 Access Control | §164.312(a) Access control | CC6.1 |
| **Power Platform:** environment creation, DLP policies | PR.PS, PR.DS | 3.4 Configuration Management | §164.308(a)(1) Security management process | CC8.1 |
| **Audit logging** (across products) | DE.CM | 3.3 Audit & Accountability | §164.312(b) Audit controls | CC7.2–CC7.3 |

## Notes

- CMMC Level 2 practices align with NIST SP 800-171 requirements; cite the 800-171 requirement number in reports. For CUI, confirm whether the client is on a GCC High / government tenant. Commercial M365 alone may not meet their contractual obligations.
- Cyber-insurance questionnaires focus heavily on MFA, email security, and privileged access. The Entra ID and Exchange findings usually answer most of them.
- HIPAA is risk-based. Present findings as inputs to the client's risk analysis, not as pass/fail compliance.
