# SME Cybersecurity Risk Assessment & Risk Register
### Enterprise Risk Management (ERM) & Treatment Plan | Purrfect Brew Cat Café

![Project Status](https://img.shields.io/badge/Status-Complete-success?style=flat-square)
![Framework](https://img.shields.io/badge/Framework-CIS%20Controls%20v8%20(IG1)%20%7C%20NIST%20CSF-blue?style=flat-square)
![Scope](https://img.shields.io/badge/Scope-Retail%20%26%20Hospitality%20SME-orange?style=flat-square)

---

## Executive Summary

Small and medium-sized enterprises (SMEs) face increasing exposure to commoditized cyber threats while operating with lean IT resources. This project presents a qualitative cybersecurity risk assessment and operational risk register developed for **Purrfect Brew Cat Café**, a hybrid retail and hospitality business operating in Seattle, WA.

The engagement evaluated **13 distinct cyber and operational risk scenarios** across the organization's cloud platforms, POS infrastructure, customer adoption database, and guest network environments.

### Key Findings
* **Initial Exposure:** **38% of identified risks** initially fell into the **High (Unacceptable)** inherent risk category (Risk Score ≥ 6), driven primarily by business email compromise (phishing), customer adoption PII exposure, cloud booking platform dependencies, and ransomware.
* **Primary Threat Vector:** Phishing targeting administrative credentials (**R4: Inherent Score 9**) represented the single highest operational risk due to shared administrative access across booking, marketing, and adoption records.
* **Post-Treatment Outcome:** Implementing targeted, cost-effective baseline safeguards aligned to **CIS Controls v8 Implementation Group 1 (IG1)** reduced all 13 risks to acceptable or managed levels (**Residual Scores ≤ 3**), satisfying executive risk appetite without exceeding SME capital constraints.

📁 **[Download the Complete Excel Risk Register Workbook (Risk_Register_Cat_Cafe.xlsx)](./Risk_Register_Cat_Cafe.xlsx)**

---

## Business Profile & Scope

| Parameter | Details |
| :--- | :--- |
| **Organization** | Purrfect Brew Cat Café (Hybrid Café, Lounge, and Animal Adoption) |
| **Headquarters** | Seattle, Washington |
| **Workforce** | 12 Employees (Founders, Shift Leads, Baristas, Adoption Coordinators) |
| **Annual Revenue** | $850,000 |
| **Core Systems** | Microsoft 365, Cloud-based Point-of-Sale (POS), Square Terminal, Guest Wi-Fi, Cloud Booking & Adoption Portal |
| **Regulatory Scope** | PCI DSS v4.0 (SAQ A-EP / P2PE Terminal), WA State Data Breach Notification (RCW 19.255.010) |
| **Risk Appetite** | **Low-to-Zero Tolerance** for customer PII leakage, payment card compromise, and unrecoverable downtime. **Moderate Tolerance** for non-critical marketing disruption. |

---

## Risk Assessment Methodology

Risks were identified and evaluated using a qualitative $3 \times 3$ matrix calculating Inherent Risk ($IR$) and Residual Risk ($RR$):

$$\text{Risk Score} = \text{Likelihood (1–3)} \times \text{Impact (1–3)}$$

### Scoring & Appetite Thresholds

| Scale | Likelihood Rating | Impact Rating (Financial / Operational) | Inherent Risk Score | Action Required |
| :---: | :--- | :--- | :---: | :--- |
| **3** | **Likely:** Precedent exists; attack highly probable within 12 mos. | **High:** $25k–$75k+ financial loss; severe brand damage or regulatory penalty. | **6 – 9 (High)** | **Unacceptable:** Immediate remediation plan required. |
| **2** | **Possible:** Attack has occurred in peer industry; moderate probability. | **Medium:** $5k–$25k financial loss; temporary operational disruption. | **3 – 5 (Medium)** | **Manageable:** Mitigate or document risk acceptance. |
| **1** | **Unlikely:** Rare occurrence; significant technical barrier for attacker. | **Low:** < $5k financial loss; minor administrative inconvenience. | **1 – 2 (Low)** | **Acceptable:** Monitor; standard operating procedures suffice. |

---

## Risk Heat Maps: Inherent vs. Residual

### 1. Inherent Risk (Pre-Treatment)
*Identifies threat severity prior to formal control evaluation.*

| Likelihood \ Impact | Low (1) | Medium (2) | High (3) |
| :---: | :---: | :---: | :---: |
| **Likely (3)** | — | — | 🔴 **R4** (Phishing) |
| **Possible (2)** | 🟢 **R2** | 🟠 **R1, R9** | 🔴 **R3, R7, R11, R13** |
| **Unlikely (1)** | — | 🟢 **R8, R10, R12** | 🟠 **R5, R6** |

### 2. Residual Risk (Post-Treatment)
*Reflects remaining exposure following implementation of recommended CIS IG1 baseline controls.*

| Likelihood \ Impact | Low (1) | Medium (2) | High (3) |
| :---: | :---: | :---: | :---: |
| **Likely (3)** | — | — | — |
| **Possible (2)** | 🟢 **R2** | 🟢 **R1, R6, R8, R9, R11, R12, R13** | 🟠 **R3, R4, R5, R7** |
| **Unlikely (1)** | — | 🟢 **R10** | — |

*Note: All high inherent risks (R3, R4, R7, R11, R13) were brought within acceptable operational tolerances through access control, phishing training, MFA, and automated backups.*

---

## Master Risk Register Summary

| ID | Threat Scenario | Inherent (L x I) | Score | Key Safeguards & Controls | CIS v8 Control | Residual Score | Risk Owner |
| :---: | :--- | :---: | :---: | :--- | :---: | :---: | :--- |
| **R1** | Guest Wi-Fi bridging into internal POS / business network | $2 \times 2$ | **4** | 802.1Q VLAN network isolation; WPA3-Personal on private SSID | CIS 12.1, 12.2 | **2** | Devon (Lead Barista) |
| **R2** | Security camera credential compromise | $2 \times 1$ | **2** | Hardware passphrase hardening; disabled default UPnP/P2P routing | CIS 4.1 | **1** | Devon (Lead Barista) |
| **R3** | Customer loyalty PII database breach | $2 \times 3$ | **6** | Least privilege DB access; AES-256 encryption at rest; retention limit | CIS 3.3, 6.1 | **3** | Devon (Lead Barista) |
| **R4** | Spear-phishing compromising Microsoft 365 admin account | $3 \times 3$ | **9** | Enforced FIDO2/MFA; DKIM/DMARC; bi-weekly awareness training | CIS 6.3, 14.1 | **3** | Tina (Chief of Adoptions) |
| **R5** | Physical POS terminal skimming or hardware tampering | $1 \times 3$ | **3** | Daily physical tamper checks; P2PE payment validation; night lockup | CIS 1.1, 4.3 | **3** | Tina (Chief of Adoptions) |
| **R6** | Unauthorized data exfiltration by departing employee | $1 \times 3$ | **3** | Standardized offboarding checklist; automated M365 deprovisioning | CIS 5.3, 6.2 | **2** | Devon (Lead Barista) |
| **R7** | Social media account takeover impacting brand trust | $2 \times 3$ | **6** | App-based MFA; dedicated marketing admin alias; permission review | CIS 6.5 | **3** | Jake (Marketing Lead) |
| **R8** | Malware introduction via untrusted USB devices | $1 \times 2$ | **2** | Group Policy disabling removable media storage on POS terminals | CIS 10.3 | **2** | Devon (Lead Barista) |
| **R9** | DDoS disruption of online cat lounge reservation platform | $2 \times 2$ | **4** | Cloudflare DDoS mitigation; offline walk-in reservation backup plan | CIS 9.5 | **2** | Jake (Marketing Lead) |
| **R10**| Third-party booking vendor cloud breach (TPRM) | $1 \times 2$ | **2** | Vendor security assessment questionnaire; SOC 2 Type II review | CIS 15.1, 15.2 | **2** | Tina (Chief of Adoptions) |
| **R11**| Customer adoption records (Government ID / PII) leakage | $2 \times 3$ | **6** | Role-based folder permissions; redaction of government ID files | CIS 3.1, 3.8 | **2** | Tina (Chief of Adoptions) |
| **R12**| Cloud payroll vendor outage disrupting wage distribution | $1 \times 2$ | **2** | Documented emergency manual payroll disbursement procedures | CIS 11.1 | **2** | Angela (CFO) |
| **R13**| Ransomware infection on store administrative workstation | $2 \times 3$ | **6** | Automated immutable cloud backups; Microsoft Defender for Endpoint | CIS 10.1, 11.2 | **2** | Devon (Lead Barista) |

---

## 90-Day Corrective Action Plan (CAP)

To ensure effective implementation under limited operating budgets, recommendations are prioritized across a 90-day execution roadmap:

### Phase 1: Days 1–30 — Immediate Exposure Mitigation (Low Cost / High Impact)
- **MFA Enforcement:** Enforce mandatory MFA on Microsoft 365, social media, and POS portal accounts (`R4`, `R7`).
- **Network Segmentation:** Isolate Guest Wi-Fi from the administrative subnet using router VLAN segmentation (`R1`).
- **Access Revocation:** Establish a formal offboarding checklist to revoke access immediately upon termination (`R6`).

### Phase 2: Days 31–60 — Data Protection & Governance
- **Sensitive Data Access:** Restrict access to adoption files containing customer government IDs (`R11`).
- **Vendor Due Diligence:** Audit third-party booking vendor SOC 2 compliance / security posture (`R10`).
- **Hardware Tamper Checks:** Standardize daily physical inspection checklists for payment terminals (`R5`).

### Phase 3: Days 61–90 — Resilience & Incident Readiness
- **Backup Verification:** Configure automated daily cloud backups with 30-day versioning and conduct test restore (`R13`).
- **Staff Awareness:** Deliver interactive 15-minute phishing awareness training to all staff (`R4`).
- **Business Continuity:** Document offline business continuity procedures for manual POS and walk-in lounge reservations (`R9`, `R12`).


---

## Key Takeaways & GRC Insights

1. **Governance Bridges Operational Realities:** In an SME, risk mitigation must respect operational velocity. Forcing heavy enterprise toolchains will cause staff to bypass controls; lightweight, built-in controls (like M365 Authenticator and router VLANs) achieve compliance without friction.
2. **Third-Party Dependencies Are Inescapable:** Modern retail relies heavily on SaaS platforms for booking, POS, and payroll. TPRM is not just an enterprise necessity—small businesses must evaluate supplier risk during vendor onboarding.
3. **Qualitative Rigor Drives Executive Decisions:** Clear, defensible likelihood and impact definitions allow non-technical founders to understand where their exposure lies and fund security controls based on business preservation rather than technical jargon.

---
**Author:** [Xavius Johnson](https://github.com/xaviusjohnson44) | Early-Career Cybersecurity GRC & IT Audit Analyst  
**Certifications:** CompTIA Security+ | ISO/IEC 27001 Lead Auditor Trained | CompTIA A+
