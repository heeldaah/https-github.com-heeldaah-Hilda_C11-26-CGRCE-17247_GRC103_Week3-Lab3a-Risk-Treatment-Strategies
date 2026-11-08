# INTERNATIONAL CYBERSECURITY AND DIGITAL FORENSICS ACADEMY (ICDFA)

## Governance, Compliance, and Risk (GCR)

### GRC103 Social Engineering & Phishing Campaign Simulation Lab

# Lab 3a: Measuring and Communicating Human Risk Through a Controlled Phishing Simulation

---

| Field | Detail |
|---|---|
| **Course** | GRC103 — Risk Assessment and Management Techniques |
| **Module** | Module 3: Risk Treatment Strategies |
| **Institution** | International Cybersecurity and Digital Forensics Academy (ICDFA) |
| **Assignment** | Practical Laboratories — Lab Submission |
| **Student Name** | Hilda Odein Joshua-Jack |
| **Registration Number** | C11/26/CGRCE/17247 |
| **Submission Date** | 08 Nov 2026 |
| **Due Date** | 08 Nov 2026, 6:18 PM WAT |
| **Maximum Marks** | 100 |
| **Practical Pass Mark** | 50% |
| **Demonstration** | Required |

---

## 1. Assignment Overview

This README documents the controlled social engineering and phishing campaign simulation completed for **Northbridge Services**, a fictional organisation concerned about its resilience to phishing attacks. The lab uses **GoPhish** on a local Kali Linux VM with a local SMTP capture service (Mailtrap) and fictional user details to observe campaign events, calculate risk metrics and prepare management recommendations.

The work follows the full phishing simulation lifecycle:

1. **Setup** — install and configure GoPhish, SMTP sending profile, landing page and email template.
2. **Targeting** — define a small, controlled test group using only fictional identities.
3. **Execution** — launch the campaign against test mailboxes only.
4. **Measurement** — record email delivery, opening, link-clicking and dummy-data submission events.
5. **Analysis** — calculate campaign metrics using clearly stated denominators.
6. **Reporting** — interpret results with acknowledged limitations and prepare a risk assessment and executive summary.

> **Important:** All identities, mailboxes, credentials and organisational details in this lab are fictional. Only test mailboxes controlled by the student were used. Password capture was **disabled**; a dummy form-submission event was sufficient evidence. No real users, real credentials or public cloned institutional login pages were involved. The campaign was stopped after evidence collection.

---

## 2. Lab Environment

| Component | Specification |
|---|---|
| **Attacker/Auditor VM** | Kali Linux — 2 vCPUs, 2–4 GB RAM, 25 GB disk |
| **Network** | Local isolated lab network (no public exposure of cloned pages) |
| **Key software** | GoPhish (v0.12.1), Firefox, Mailtrap (free tier SMTP capture), local SMTP capture service |
| **Phishing framework** | GoPhish admin interface (default `https://127.0.0.1:3333`) |
| **Sending profile** | Mailtrap Test — SMTP host/port/username/password from Mailtrap |
| **Landing page** | Fictional training login page (dummy VPN portal); password capture **disabled** |
| **Target group** | Lab Test Group — student-controlled test mailboxes only |
| **Kali IP (lab)** | *[e.g. 192.168.x.x — replace with actual]* |

A clean VM checkpoint was taken **before** any configuration. All campaign URLs pointed to the actual reachable local landing page; no domain-based masking was assumed to configure DNS or hosting.

---

## 3. Repository / Submission Contents
GRC103-Phishing-Lab-Submission/
├── README.md ← this file
├── GRC103_Phishing_Lab_Report.pdf ← full written report
├── evidence/
│ ├── 01-setup/
│ │ ├── gophish-install.txt
│ │ ├── gophish-admin-login.png
│ │ └── sending-profile-redacted.png
│ ├── 02-campaign-config/
│ │ ├── landing-page-config.png
│ │ ├── email-template-config.png
│ │ ├── target-group-config.png
│ │ └── campaign-launch-config.png
│ ├── 03-results/
│ │ ├── gophish-dashboard.png ← redacted
│ │ ├── campaign-results-timeline.png ← redacted
│ │ └── event-export.csv
│ └── 04-reporting/
│ ├── phishing-risk-assessment-table.xlsx
│ └── executive-summary.md
├── calculations/
│ └── campaign-metrics-workbook.xlsx
└── evidence-index.md


> **Excluded from submission (per brief):** passwords, API keys, SMTP secrets, real credentials, any real user data, and public cloned institutional login pages. All screenshots are redacted where secrets or API keys appear.

---

## 4. Environment Build Summary

| Step | Action | Evidence |
|---|---|---|
| 1 | Downloaded GoPhish v0.12.1, unzipped, made executable, launched admin interface | `evidence/01-setup/gophish-install.txt`, `gophish-admin-login.png` |
| 2 | Configured Sending Profile using Mailtrap free-tier SMTP settings (secrets redacted) | `evidence/01-setup/sending-profile-redacted.png` |
| 3 | Created Landing Page — fictional training login page; password capture **disabled**; redirect to security-training page configured | `evidence/02-campaign-config/landing-page-config.png` |
| 4 | Created Email Template — fictional "VPN Password Reset Required" template using `{{.FirstName}}` and `{{.URL}}` | `evidence/02-campaign-config/email-template-config.png` |
| 5 | Defined Lab Test Group — student-controlled test mailboxes with fictional names | `evidence/02-campaign-config/target-group-config.png` |
| 6 | Launched campaign; set URL to actual reachable local landing page; launched immediately | `evidence/02-campaign-config/campaign-launch-config.png` |
| 7 | Monitored and recorded Email Sent, Opened, Clicked Link, Data Submitted events | `evidence/03-results/gophish-dashboard.png`, `event-export.csv` |
| 8 | Built Phishing Risk Assessment Table with actual counts, rates, denominators, interpretations, limitations and recommended controls | `evidence/04-reporting/phishing-risk-assessment-table.xlsx` |
| 9 | Drafted Executive Summary and Recommendations | `evidence/04-reporting/executive-summary.md` |
| 10 | Stopped the campaign after evidence collection | `evidence/03-results/campaign-stopped.txt` |

---

## 5. Evidence Index (Mapping Evidence → Practical Steps)

### 5.1 Required Evidence Deliverables

| # | Required Evidence (from brief) | Location | Status |
|---|---|---|---|
| 1 | Campaign evidence — GoPhish results dashboard & configuration screenshots (secrets concealed) | `evidence/01-setup/`, `evidence/02-campaign-config/`, `evidence/03-results/` | ✅ |
| 2 | Phishing risk assessment table — actual event counts, rates, denominators, risk interpretations, limitations, recommended controls | `evidence/04-reporting/phishing-risk-assessment-table.xlsx` | ✅ |
| 3 | Executive summary & recommendations — scope, method, key findings, business implications, prioritised improvements | `evidence/04-reporting/executive-summary.md`, `GRC103_Phishing_Lab_Report.pdf` | ✅ |

### 5.2 Step-by-Step Evidence Map

| Step | Description | Evidence File(s) | Test / Validation |
|---|---|---|---|
| 1 | Install & launch GoPhish | `gophish-install.txt`, `gophish-admin-login.png` | Admin interface reachable; default credentials used for lab only |
| 2 | Configure Sending Profile (Mailtrap) | `sending-profile-redacted.png` | Test email delivered to Mailtrap inbox |
| 3 | Create Landing Page (dummy form; password capture disabled) | `landing-page-config.png` | Page reachable; redirect configured |
| 4 | Create Email Template | `email-template-config.png` | Variables render correctly |
| 5 | Define Target Group | `target-group-config.png` | Only student-controlled test mailboxes |
| 6 | Launch Campaign | `campaign-launch-config.png` | Campaign status = Running |
| 7 | Monitor results | `gophish-dashboard.png`, `event-export.csv` | Emails Sent / Opened / Clicked / Data Submitted captured |
| 8 | Risk assessment table | `phishing-risk-assessment-table.xlsx` | Counts, rates, denominators, interpretations documented |
| 9 | Executive summary | `executive-summary.md` | Scope, method, findings, implications, prioritised improvements |
| 10 | Stop campaign | `campaign-stopped.txt` | Campaign stopped after evidence collection |

---

## 6. Key Results Summary

### 6.1 Campaign Metrics (Actual Lab Results)

| Metric | Result | Calculated Rate | Denominator | Risk Interpretation | Control Failure |
|---|---|---|---|---|---|
| Emails Sent | *[e.g. 20/20]* | *[100%]* | Target group size | Delivery working; measurement valid | N/A |
| Emails Opened | *[e.g. 18/20]* | *[90%]* | Emails Sent | High susceptibility to engaging with suspicious emails | Security Awareness Training is ineffective |
| Links Clicked | *[e.g. 15/20]* | *[75%]* | Emails Sent | High risk of users executing malicious actions | Email filtering may be ineffective; users are not verifying links |
| Data Submitted (dummy) | *[e.g. 10/20]* | *[50%]* | Emails Sent | Critical Risk — high probability of credential compromise | MFA is an absolute requirement to mitigate this risk |

> **Replace bracketed figures with your actual measured results.** Denominators are stated explicitly for every rate. The figures in the lab brief are examples, not results to reproduce.

### 6.2 Interpretation and Limitations

| Aspect | Observation |
|---|---|
| **What the simulation measures** | Controlled observations of email engagement, link-clicking and dummy form-submission behaviour in a small, fictional, student-only sample |
| **What the simulation does NOT prove** | That the organisation's training or email controls are ineffective in general — a small laboratory simulation cannot establish this |
| **Sample size limitation** | Small simulated sample; rates are indicative, not statistically generalisable |
| **Fictional content** | Only dummy credentials and fictional identities used; no real users targeted |
| **Password capture** | Disabled; dummy form submission is sufficient evidence of susceptibility behaviour |
| **Control interpretation** | Results suggest control weaknesses worth investigating; they do not by themselves justify a specific budget or policy change without further testing |

### 6.3 Phishing Risk Assessment Table (Condensed)

| Metric | Result | Rate | Denominator | Risk Interpretation | Control Failure | Recommended Controls |
|---|---|---|---|---|---|---|
| Emails Opened | *[18/20]* | *[90%]* | Target group size | High susceptibility to engaging with suspicious emails | Awareness training not effective | Continuous, targeted training; simulated phishing integrated into onboarding |
| Links Clicked | *[15/20]* | *[75%]* | Emails Sent | High risk of users executing malicious actions | Email filtering may be ineffective; users not verifying links | Improve email filtering; link verification training |
| Credentials Submitted (dummy) | *[10/20]* | *[50%]* | Emails Sent | Critical Risk — high probability of credential compromise | MFA absent or not enforced | Accelerate MFA rollout across critical systems |

> Replace bracketed figures with your actual measured results.

---

## 7. Executive Summary and Recommendations (Draft)

### 7.1 Executive Summary

A controlled phishing simulation was conducted on a local Kali Linux / GoPhish environment using fictional identities and student-controlled test mailboxes. The objective was to observe campaign events, calculate risk metrics and prepare management-focused recommendations. All credentials were dummy and password capture was disabled; a dummy form-submission event was used as evidence of susceptibility behaviour. The campaign was stopped after evidence collection.

### 7.2 Key Findings & Metrics

- **Email Open Rate:** *[90%]* — high engagement with themed emails.
- **Link Click-Through Rate:** *[75%]* — failure to identify suspicious links in this small sample.
- **Dummy Credential Submission Rate:** *[50%]* — most critical observed behaviour in the sample.

### 7.3 Risk Analysis

The observations suggest weaknesses in awareness and email control that warrant further investigation. A successful real phishing attack could lead to initial network access, data breaches and financial loss, reputational damage and regulatory consequences. However, this small laboratory simulation does **not** prove that the organisation's training or email controls are ineffective in general; it provides controlled, indicative evidence that should inform further testing and control review.

### 7.4 Recommended Actions

1. **Immediate Technical Control:** Accelerate Multi-Factor Authentication (MFA) rollout across critical systems as the single most effective control against stolen credentials.
2. **Revamp Training Programme:** Move from annual compliance videos to continuous, engaging, targeted training.
3. **Process Integration:** Integrate phishing simulations into onboarding and run them quarterly for all staff.
4. **Policy Update:** Review and update the Acceptable Use Policy (AUP) to explicitly define requirements for identifying and reporting phishing attempts.
5. **Email Filtering Review:** Evaluate and strengthen email filtering and link-verification controls.
6. **Measurement Maturity:** Increase sample sizes and use clear denominators so future campaigns produce more statistically meaningful results.

> All figures above are the student's own measured results. Replace bracketed example figures with actual campaign data before submission.

---

## 8. Monitoring & Operational Handover (Proposed)

| Check | Owner | Frequency | Threshold | Escalation |
|---|---|---|---|---|
| Phishing simulation completion | *[GRC analyst]* | Quarterly | Any incomplete campaign or missing metrics | Security lead |
| MFA coverage | *[IT Ops]* | Monthly | <100% on critical systems | CISO |
| Awareness training completion | *[HR/L&D]* | Quarterly | <90% completion | Head of HR |
| Email filtering effectiveness | *[IT Ops]* | Monthly | Increase in delivered suspicious mail | Security lead |
| Reporting of simulated phishing | *[GRC analyst]* | Per campaign | <50% report rate | Security lead |

> Lab results are **measured**; ongoing monitoring above is **proposed**.

---

## 9. Change & Rollback Records

| Change | Approval | Rollback | Status |
|---|---|---|---|
| Install GoPhish on Kali lab VM | *Simulated — student* | Remove `gophish/` directory | Applied |
| Configure Mailtrap Sending Profile | *Simulated — student* | Delete profile in GoPhish | Applied |
| Create dummy landing page (password capture disabled) | *Simulated — student* | Delete page in GoPhish | Applied |
| Launch simulation campaign | *Simulated — student* | Stop campaign in dashboard | Stopped after evidence collection |
| Test mailboxes only (fictional) | N/A | N/A | No real users affected |

---

## 10. Reproducibility Notes

1. Take a clean VM checkpoint before installing GoPhish.
2. Use only mailboxes you control and fictional identities; never real users.
3. Keep password capture **disabled**; a dummy form-submission event is sufficient evidence.
4. Point the campaign URL to your **actual reachable local landing page** — a domain does not automatically configure DNS or hosting.
5. Redact SMTP secrets, API keys, passwords and any personal data in screenshots.
6. Stop the campaign after collecting the required evidence.
7. State denominators clearly for every calculated rate.
8. Do not claim that a small laboratory simulation proves organisational training or email controls are ineffective.

---

## 11. Security & Integrity Declaration

- Only **fictional/dummy** identities and student-controlled test mailboxes were used.
- No real users, real credentials or real personal data were involved.
- No public cloned institutional login page was published.
- Password capture was **disabled**; a dummy form submission was used as evidence.
- Secrets, SMTP credentials, API keys and passwords are **not** included in this submission.
- All approvals, provider offers and organisational details are **simulated** for the exercise.
- The campaign was stopped after evidence collection.
- Figures presented in the report are the student's actual measured results; the brief's examples are not reproduced as results.

---

## 12. Marking Criteria Alignment

| Criterion | Marks | Where Addressed |
|---|---|---|
| Campaign evidence (dashboard & config screenshots, redacted) | *[refer to rubric]* | §5.1, `evidence/01-setup/`, `evidence/02-campaign-config/`, `evidence/03-results/` |
| Phishing risk assessment table (actual counts, rates, denominators, limitations, controls) | *[refer to rubric]* | §6.3, `evidence/04-reporting/phishing-risk-assessment-table.xlsx` |
| Executive summary & recommendations (scope, method, findings, implications, prioritised improvements) | *[refer to rubric]* | §7, `evidence/04-reporting/executive-summary.md`, `GRC103_Phishing_Lab_Report.pdf` |
| **Total** | **100** | |

> The official rubric split for this lab was not specified in the supplied brief; replace the bracketed marks with the published criterion weights before final submission.

---

## 13. References

- GoPhish open-source phishing framework — https://getgophish.com/
- GoPhish releases (v0.12.1 Linux build) — https://github.com/gophish/gophish/releases
- Mailtrap free-tier SMTP capture — https://mailtrap.io/
- Course basis: ICDFA Social Engineering & Phishing slides, GRC103 Module 3

---

**End of README**
*Student Name: Hilda Odein Joshua-Jack | Registration Number: C11/26/CGRCE/17247*
