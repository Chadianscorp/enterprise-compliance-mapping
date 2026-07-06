# Enterprise GRC Architecture: Cross-Framework Compliance Control Matrix

## 📌 Executive Summary
In modern enterprise information security, organizations must satisfy multiple overlapping regulatory standards simultaneously. Manually mapping discrete assets to disjointed control frameworks—such as international standards (ISO/IEC 27001) and federal mandates (NIST SP 800-53)—frequently results in operational gaps, fragmented auditing, and visibility silos. 

This project establishes a production-ready, engineering-focused Compliance Control Matrix that bridges the gap between high-level policy frameworks and ground-level technical enforcement. Expanded to include HIPAA Security Rule and HITRUST CSF mappings alongside ISO/IEC 27001 and NIST SP 800-53, this matrix delivers healthcare-specific compliance coverage for organizations handling Protected Health Information (PHI) alongside federal and international standards.

---

## 🛠️ Matrix Architecture & Framework Alignment

This control matrix covers 7 foundational pillars of enterprise infrastructure security, including Third-Party/Vendor Risk, establishing a continuous chain of compliance from asset definition to automated verification across NIST SP 800-53, ISO/IEC 27001, HIPAA, and HITRUST frameworks:

| Asset / System Type | Security Threat / Risk | ISO/IEC 27001 Control | NIST SP 800-53 Rev 5 | Verification | HIPAA (§164.312) | HITRUST CSF |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Endpoint Security** | Malware, Unauthorized Local Access | A.12.6.1, A.8.2.3 | CM-7, SI-3 | Qualys PC / GPO | §164.312(a)(2)(i) (Unique user identification); §164.312(c)(1) (Integrity controls) | 07.a (Information Classification); 09.ab (Monitoring System Use) |
| **Identity & Access (IAM)** | Credential Hijacking, Brute-Force | A.9.2.1, A.9.4.2 | IA-2, AC-2 | Qualys PC Audit | §164.312(d) (Person authentication); §164.312(a)(2)(iii) (Automatic logoff) | 01.a (Access Control Policy); 01.b (User Registration) |
| **SIEM & Central Logging** | Intrusion Blindspots, Log Tampering | A.12.4.1, A.12.4.2 | AU-2, AU-6, AU-9 | Qualys PC & FIM | §164.312(b) (Audit controls); §164.312(c)(2) (Integrity mechanism) | 09.aa (Audit Logging); 09.ab (Monitoring System Use) |
| **Network Boundaries** | Lateral Movement, Data Exfiltration | A.13.1.1, A.13.1.3 | SC-7, AC-4 | Qualys Config Audit | §164.312(e)(1) (Transmission security); §164.312(a)(1) (Access control) | 09.m (Network Controls); 01.d (User Password Management) |
| **Configuration Control / Cloud Infrastructure** | Configuration Drift, Unauthorized Changes | A.12.1.2, A.12.1.1 | CM-3, CM-2 | Qualys FIM / CIS | §164.312(c)(1) (Integrity); §164.312(a)(2)(ii) (Emergency access) | 09.i (Configuration Management); 10.m (Control of Technical Vulnerabilities) |
| **Vulnerability & Patching** | Known Vulnerability Exploitation (CVEs) | A.12.6.1 | RA-5, SI-2 | Qualys VMDR | §164.308(a)(8) (Evaluation); §164.312(c)(1) (Integrity) | 10.m (Control of Technical Vulnerabilities); 09.ab (Monitoring System Use) |
| **Third-Party/Vendor Risk** | Supply Chain Compromise, Vendor Data Breach | A.15.1.1, A.15.2.1 | SA-9, SR-6 | Qualys PC | §164.308(b)(1) (Business associate contracts); §164.314(a)(1) (BA contracts) | 09.ab (Monitoring System Use); 05.i (Risks Related to External Parties) |

<sub>📎 Full compliance matrix with detailed technical implementation requirements, audit evidence artifacts, and complete control references available in the <a href="Enterprise_GRC_Control_Matrix.xlsx">accompanying workbook</a>. <em>Note: TalentVanguard is a fictional organization used for demonstration purposes.</em></sub>
---

## 🔍 Core Security Implementation Breakdown

### 1. Endpoint Security & Workstations
* **Technical Enforcement:** Local administrative privileges are completely restricted; Endpoint Detection & Response (EDR) agents are globally deployed; unauthorized external USB storage devices are blocked via Active Directory Group Policy Objects (GPOs).
* **Auditor Paper Trail:** Active GPO configuration reports, Qualys compliance scan exports proving EDR agent health, and official Corporate Endpoint Protection Policies.

### 2. Identity & Access Management (IAM)
* **Technical Enforcement:** Strict 14-character minimum password complexity; global enforcement of Multi-Factor Authentication (MFA) across all identity providers (Active Directory / Okta); automated account deprovisioning following 90 days of continuous user inactivity.
* **Auditor Paper Trail:** Live configuration screenshots of IAM/Active Directory password/MFA panels, Access Control Policy documents, and exported system logs demonstrating automated account expiration.

### 3. SIEM & Central Log Repositories
* **Technical Enforcement:** Centralized aggregation of operating system, firewall, and application event logs to a write-once SIEM platform; strict Access Control Lists (ACLs) to prevent log manipulation; a mandatory 365-day log retention policy.
* **Auditor Paper Trail:** SIEM retention settings configuration files, verified sample log ingestion records, and directory permissions demonstrating that standard administrators do not possess log-deletion capabilities.

### 4. Boundary Protection & Network Segmentation
* **Technical Enforcement:** Network boundary firewalls configured to a default "deny-all, permit-by-exception" posture; complete physical or logical separation of public guest Wi-Fi networks from internal production directories; implementation of segmented VLANs to safeguard sensitive payment/data environments.
* **Auditor Paper Trail:** Up-to-date network topology maps, active firewall ruleset/ACL table exports, and a copy of the Network Security Policy.

### 5. Configuration Control & Cloud Infrastructure Hardening
* **Technical Enforcement:** Production adjustments governed strictly by an audited Change Advisory Board (CAB) workflow; File Integrity Monitoring (FIM) activated to track modifications to system binaries; servers hardened against industry-standard Center for Internet Security (CIS) Benchmarks.
* **Auditor Paper Trail:** Signed CAB tickets cross-referenced with exact timestamped deployment logs, the Configuration Management Policy, and automated daily Qualys compliance reports tracking adherence to the CIS baseline.

### 6. Vulnerability Management & Patching
* **Technical Enforcement:** Automated weekly vulnerability assessments executed across all internal enterprise subnets; critical operating system and application patches deployed within 14 days of commercial release; emergency out-of-band patching tracks established for zero-day exploits.
* **Auditor Paper Trail:** Historical Qualys VMDR scan reports, centralized patch engine management logs detailing successful deployment rates, and a copy of the Vulnerability Management Policy.

### 7. Third-Party/Vendor Risk Management
* **Technical Enforcement:** Mandatory vendor risk assessments conducted prior to onboarding any third-party with access to organizational systems or data; contractual security requirements enforced via Business Associate Agreements (BAAs) and vendor contracts; annual reassessment cycle with SOC 2 Type II or equivalent documentation required for continued vendor approval.
* **Auditor Paper Trail:** Completed vendor risk questionnaires, executed BAAs and vendor contracts containing explicit security clauses, vendor-provided SOC 2 Type II reports, and annual reassessment records demonstrating ongoing third-party compliance monitoring.

---

## 🚀 Key GRC Methodologies Demonstrated
* **Multi-Framework Mapping:** Alignment of technical security controls across four regulatory frameworks (ISO/IEC 27001, NIST SP 800-53 Rev. 5, HIPAA Security Rule, and HITRUST CSF), establishing a unified control library that reduces duplication and consolidates compliance evidence collection.
* **Automated Audit Readiness:** Transitioning traditional "point-in-time" manual auditing into continuous monitoring models using automated vulnerability and compliance tooling (Qualys PC, FIM, and VMDR).
* **Evidentiary Integrity:** Explicitly defining technical verification steps and administrative artifacts to ensure defensible, ironclad compliance packages during third-party or federal assessments.
* **Healthcare Compliance Integration:** Extended framework alignment to include HIPAA Security Rule (§164.312) and HITRUST CSF control references, enabling direct application to healthcare and regulated commercial environments requiring PHI protection and vendor risk governance.


