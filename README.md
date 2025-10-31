# Case Study — Unauthorized Disclosure of Citizen Data

[![Risk: High](https://img.shields.io/badge/Risk-High-red)](https://example.com) [![Impact: Very High](https://img.shields.io/badge/Impact-Very%20High-critical)](https://example.com) [![Status: Ongoing](https://img.shields.io/badge/Status-Ongoing-yellow)](https://example.com)

---

## Executive summary

In 2016 and again in 2025, large-scale unauthorised disclosures of citizen data were observed in Turkish e‑government systems. The incidents exposed personally identifiable information (PII) — including national ID numbers, financial obligations and other sensitive records — and resulted in data being sold on illicit marketplaces.

This README summarises the incident, the technical root causes, the current control posture, and a concise, prioritised remediation and improvement plan designed to reduce exposure and restore public trust.

---

## Key facts

| Field                         |                                                   Value |
| ----------------------------- | ------------------------------------------------------: |
| Risk level                    |                                                **High** |
| Impact                        |                                           **Very High** |
| Probability                   |                                                  Medium |
| Known incidents               |                                              2016, 2025 |
| Typical exfiltration channels | SQL injection, cloud misconfiguration, credential theft |

---

## Affected assets

* National citizen registries and identity databases
* E‑government authentication platforms
* Financial and legal records systems
* Institutional reputation and public trust

---

## Technical summary

The attackers exploited a combination of application‑layer and operational weaknesses:

* **Injection vectors**: SQL injection vulnerabilities in public web portals permitted unauthorised access to backend databases.
* **Cloud misconfiguration**: Sensitive backups and buckets were exposed due to permissive access controls.
* **Credential compromise**: Stolen or reused credentials belonging to authorised users enabled lateral movement.
* **Insufficient telemetry**: Limited monitoring and logging prevented timely detection of large‑scale exfiltration.

> The evidence indicates a probable long‑term presence of adversaries in certain subsystems.

---

## Vulnerabilities (at a glance)

| Vulnerability                  | Status              | Rationale                                                                    |
| ------------------------------ | ------------------- | ---------------------------------------------------------------------------- |
| Third‑party security controls  | Partially mitigated | Basic assessments exist but not continuous assurance                         |
| Encryption at rest             | Not mitigated       | Sensitive data stored without enforced strong encryption                     |
| Administrative access controls | Partially mitigated | Controls exist for internal staff; vendor and contractor access remains weak |
| Monitoring / DLP               | Not mitigated       | No comprehensive data loss prevention or mass‑exfiltration detection         |
| Patch management               | Mitigated           | Critical patching improved after 2025 incident                               |

---

## Implemented controls

* Contractual security requirements for vendors (baseline assessments)
* Network segmentation isolating core databases
* Web Application Firewall (WAF) on public portals
* Regular vulnerability scanning and security assessments
* Basic security awareness training for staff
* Documented incident response plan

---

## Planned & recommended controls (prioritised)

**Immediate (0–30 days)**

1. Enforce mandatory **multi‑factor authentication (MFA)** for all administrative and vendor accounts — this is non‑negotiable.
2. Apply compensating controls to restrict access to exposed storage (block public access; enforce least privilege).
3. Implement basic Data Loss Prevention (DLP) rules to detect large exports of PII.

**Short term (1–3 months)**

1. Enforce **strong encryption at rest** for all sensitive datasets (full‑disk and field level where needed).
2. Harden vendor onboarding and introduce continuous third‑party risk monitoring.
3. Extend access control to cover contractor and vendor accounts with role‑based access control (RBAC).

**Mid term (3–9 months)**

1. Deploy a Security Operations Centre (SOC) or an external Managed Detection and Response (MDR) service with tailored use cases for mass exfiltration.
2. Conduct regular penetration testing and red team exercises focused on public‑facing portals and supplier integrations.
3. Establish incident‑impact playbooks that include public communications and legal/forensic steps.

**Long term (9–18 months)**

1. Institutionalise accountability: align security KPIs with senior leadership performance objectives and formalise sanctions for negligence.
2. Implement continual maturity assessments (CIS/ISO benchmarking) and privacy‑by‑design for all new projects.

---

## Organisational recommendations

* **Accountability & governance**: Introduce clear lines of accountability and a statutory requirement for breach notification and corrective action.
* **Public transparency**: Publish summary findings and corrective actions to rebuild trust.
* **Training & culture**: Move beyond basic awareness to role‑based training for privileged users and contractors.

> Technical remediations are necessary but not sufficient — organisational change and consequences are essential to deter repeat incidents.

---

## Incident timeline

* **2016** — Initial mass disclosure identified and partially remediated.
* **2025** — Recurrence with similar technique set; evidence of ongoing access in certain systems.

---

## Priority action checklist (compact)

1. MFA for all admin/vendor access — **Critical**
2. Encrypt all sensitive data at rest — **Critical**
3. Implement DLP + SOC/MDR — **High**
4. RBAC and vendor continuous monitoring — **High**
5. Penetration testing and red teaming — **Medium**

---

## Appendix

* **Regulatory context**: KVKK (personal data protection law) applies; regulatory and reputational consequences must be considered.
* **Suggested measurements**: Mean time to detect (MTTD), mean time to respond (MTTR), percentage of sensitive repositories encrypted, number of privileged accounts with MFA.

---

### Contact & ownership

If this document is adopted as the canonical case study in a repository, assign an owner and version it via the repository changelog. For immediate coordination, the recommended temporary owner is the Chief Information Security Officer (CISO).

---

*Prepared for inclusion in an incident repository. If you would like a PDF export, GitHub badge customisation or a condensed executive one‑page brief, tell me which you prefer.*
