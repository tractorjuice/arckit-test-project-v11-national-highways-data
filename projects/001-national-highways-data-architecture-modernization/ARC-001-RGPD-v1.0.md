# GDPR Compliance Assessment — UK→EU Road Information Sharing

> **Template Origin**: Community | **ArcKit Version**: 4.7.0 | **Command**: `/arckit.eu-rgpd`
>
> ⚠️ **Community-contributed** — not yet validated against current CNIL/EU regulatory text. Verify all citations before relying on output. Review by DPO / legal counsel required before reliance.

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-RGPD-v1.0 |
| **Document Type** | GDPR Compliance Assessment (EU 2016/679) |
| **Project** | National Highways Data Architecture Modernization (Project 001) |
| **Scope** | Proposed sharing of road network information with EU/EEA recipients (DATEX II and discretionary datasets) |
| **Classification** | OFFICIAL-SENSITIVE |
| **Status** | DRAFT |
| **Version** | 1.0 |
| **Created Date** | 2026-04-19 |
| **Last Modified** | 2026-04-19 |
| **Review Cycle** | Annual |
| **Next Review Date** | 2027-04-19 |
| **Owner** | Data Protection Officer (SD-8) |
| **Reviewed By** | PENDING (DPO, CISO, Legal Counsel) |
| **Approved By** | PENDING (DPO, SIRO) |
| **Distribution** | Data Protection Officer, CISO, Legal Counsel, Open Data Lead, EU Liaison |
| **Lead Supervisory Authority (EU)** | Not applicable — National Highways has no EU establishment. Each EU recipient's national DPA has jurisdiction over the processing in its territory. (UK: ICO remains UK-side regulator under UK GDPR) |
| **UK Regulator (outbound transfer side)** | Information Commissioner's Office (ICO) |
| **DPO** | Designated — SD-8 (per stakeholder register), ICO-registered |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-04-19 | ArcKit AI (Opus 4.7) | Initial creation via `/arckit.eu-rgpd` — assesses EU GDPR implications of proposed UK→EU road data sharing | PENDING | PENDING |

---

## Executive Summary

National Highways operates as a **data controller** under UK GDPR for road-network data concerning the Strategic Road Network in England. A proposal has been made to share road information with EU/EEA recipients (Member State road operators, the EU Data for Road Safety ecosystem under Delegated Regulation (EU) 2022/670 and National Access Points under Directive 2010/40/EU as amended, and indirectly downstream commercial navigation providers operating in the EU).

Most shared datasets (aggregated sensor readings, incident headers, roadworks, road-segment metadata) are **non-personal** and fall outside GDPR. However, **two categories carry personal data risk**:

1. **CCTV footage (E-007)** — identifiable persons/vehicles; any EU export of raw footage is a high-risk transfer.
2. **Pre-anonymisation ANPR (E-006, `registration_hash` within 24h window)** — pseudonym that remains personal data under EU GDPR until deletion.

Aggregated ANPR journey times (post-24h) are the design-intended EU export and are **not personal data** once aggregated below re-identification thresholds. This must be verified by the DPO before go-live.

| Area | Status | Key Findings |
|------|--------|-------------|
| Lawful Basis (UK side) | ✅ Established | Public task under UK GDPR Article 6(1)(e) (Highways Act 1980, Traffic Management Act 2004) |
| Lawful Basis (EU recipients) | 🟡 Partial | Each EU recipient must establish their own Article 6 basis in their jurisdiction; not the UK controller's responsibility but should be evidenced in data-sharing agreements |
| Data Subject Rights | 🟡 Partial | SAR, rectification, erasure mechanisms exist in UK. Cross-border SAR handling for EU-initiated requests needs documented workflow |
| International Transfers | ✅ Compliant (subject to caveats) | UK↔EU bilateral adequacy in force: EU Commission adequacy decision for UK (2021) extended June 2025 until 27 June 2031; UK recognises EEA as adequate under Data Protection Act 2018 s.17A. No SCCs required for UK↔EU Member State transfers, but a TIA is recommended for any onward transfer from EU recipients to non-adequate third countries (e.g., US navigation providers) |
| DPIA Requirement | 🔴 Required | 3/9 EDPB criteria met (systematic monitoring, large-scale, innovative tech). Run `/arckit.dpia` to refresh DPIA to cover the EU-sharing extension |
| DPO | ✅ Designated | SD-8 DPO, ICO-registered. EU Article 37 designation obligation depends on whether any EU-facing "core activity" triggers designation; for a UK-only establishment, EU Article 27 (representative) may apply |
| Breach Notification | 🟡 Partial | UK 72-hour process in place (ICO). Parallel EU Article 33 notification to each EU recipient's DPA **required** if the breach affects their data subjects — process not yet documented |
| Records of Processing (RoPA) | ✅ Maintained | UK GDPR Article 30 RoPA held by DPO; must be extended to cover EU-sharing processing activity |

**Overall recommendation**: **Proceed with scoped sharing** — limited to aggregated/non-personal datasets via DATEX II — subject to (a) formal data-sharing agreement with each EU recipient, (b) updated DPIA, (c) extended RoPA entry, (d) confirmation that no pre-anonymisation ANPR or raw CCTV will be transferred, and (e) contractual prohibition on re-identification by EU recipients.

---

## 1. Scope and Role Determination

### 1.1 Role of the Organisation

| Role | Definition | Applicable |
|------|-----------|-----------|
| **Data Controller** | Determines purposes and means of processing | ☑ **YES** — National Highways determines what is collected from SRN sensors, how it is processed, and whom it is shared with |
| **Data Processor** | Processes on behalf of a controller | ☐ No |
| **Joint Controller** | Jointly determines purposes and means with another entity | 🟡 **Possibly** — if National Highways and an EU Member State road operator (e.g., ASFiNAG, Highways Ireland) **jointly** determine purposes for a cross-border traffic management initiative, joint-controller arrangements under **Article 26 GDPR** apply. A written arrangement is required, setting out essence of roles to data subjects. To be determined case-by-case per sharing agreement |
| **Sub-processor** | Engaged by a processor | ☐ No |

**Note**: National Highways has **no establishment in the EU/EEA**. Under **Article 3(2) GDPR**, the EU GDPR applies extraterritorially only where the UK controller is "offering goods or services to" or "monitoring the behaviour of" EU data subjects. Passive receipt of SRN data concerning vehicles that happen to have been registered in the EU does **not** generally trigger Article 3(2). However, **Article 27 GDPR** obligation to designate an EU representative should be assessed if processing of EU data subjects' personal data becomes regular and non-occasional.

### 1.2 Data Categories in the Proposed EU Share

Each dataset considered for EU sharing is classified below. This determines whether GDPR applies at all.

| Dataset (entity) | Content | Personal data under GDPR? | GDPR Reference | Shareable with EU? |
|------------------|---------|---------------------------|----------------|--------------------|
| E-001 Traffic Sensor (metadata) | Sensor ID, location, type | No | N/A | ✅ Yes — non-personal |
| E-002 Sensor Reading (aggregated ≥1 min) | Flow, speed, headway | No (aggregated) | N/A | ✅ Yes — non-personal |
| E-003 Incident (public fields) | Location, type, severity, timing | No (excluding `created_by` operator ID) | N/A | ✅ Yes — redact `created_by` |
| E-006 ANPR **raw** (`registration_hash` pre-24h) | Pseudonymised plate | **YES — personal data (pseudonym)** | Art. 4(5), Recital 26 | 🔴 **DO NOT SHARE** |
| E-006 ANPR **aggregated journey times** (post-24h) | Aggregated corridor journey times | No — aggregated below re-ID threshold | N/A | ✅ Yes — subject to DPO sign-off that aggregation prevents re-identification |
| E-007 CCTV Footage | Video of faces, plates | **YES — personal data** | Art. 4(1) | 🔴 **DO NOT SHARE** as open data. Bilateral sharing with EU law-enforcement only via dedicated legal instrument (e.g., LED 2016/680 / Prüm II) — **out of scope of this assessment** |
| E-008 Road Segment | Topology | No | N/A | ✅ Yes |
| E-009 Roadworks | Schedule, location | No | N/A | ✅ Yes (DATEX II standard) |
| E-015 Weather Observation | Met Office data | No | N/A | ✅ Yes |

**Article 9 (special category) data**: ☐ None — no health, biometric, genetic, racial, political, religious, union, sex-life data processed.
**Article 10 (criminal conviction) data**: ☐ None in the proposed share. CCTV footage used in law-enforcement investigations is handled under a separate legal regime (UK DPA 2018 Part 3 / EU LED) and is out of scope of this assessment.

---

## 2. Lawful Basis Assessment (Articles 6 and 9)

### 2.1 Article 6 Basis Mapping (Standard Personal Data)

For **National Highways' own processing** (UK side, governed by UK GDPR):

| Processing Activity | Data Subjects | UK GDPR Art. 6(1) | Rationale |
|--------------------|--------------|--------------------|-----------|
| ANPR plate capture → hash → 24h retention | Drivers/registered keepers | **(e) Public task** | Highways Act 1980 s.1, Traffic Management Act 2004 — traffic management is statutory function of National Highways |
| CCTV continuous recording (31-day op retention) | Drivers, pedestrians | **(e) Public task** + **(f) Legitimate interests** (for evidential retention beyond op window) | Public-task balancing; Article 6(1)(f) inapplicable to the public-task element (Art 6(1) final paragraph excludes public authorities from LI when performing their tasks) |
| Sharing aggregated journey times with EU recipients | None (non-personal output) | N/A | Output is non-personal — GDPR does not apply |
| Sharing incident/roadworks metadata with EU (DATEX II) | None | N/A | Non-personal |

**⚠️ Flag — Article 6(1)(f) limit for public authorities**: The final paragraph of Article 6(1) excludes "processing carried out by public authorities in the performance of their tasks" from relying on legitimate interests (6(1)(f)). National Highways is a government-owned company exercising public functions; any processing justified by 6(1)(f) (e.g., crime-prevention retention of CCTV) must be narrowly scoped to non-public-task purposes, or re-based on 6(1)(e) with appropriate enabling legislation. Legal sign-off required.

**For EU recipients' onward processing**: Each recipient (e.g., French CEREMA, German BASt, Irish TII) establishes its own lawful basis under the GDPR as applied in their Member State. This is **not the UK controller's liability** but should be evidenced in the data-sharing agreement (DSA).

### 2.2 Article 9 Conditions (Special Category Data)

**Not applicable.** No Article 9 special category data present in the proposed share.

### 2.3 Consent Management (Art. 7)

**Not applicable.** Consent is not a viable lawful basis for passive roadside sensor/camera data collection (drivers cannot practically refuse, so consent would not be "freely given" — Recital 43). Public task is the correct basis.

---

## 3. Privacy by Design and Default (Article 25)

| Principle | Implementation | Status |
|-----------|---------------|--------|
| **Data minimisation** | Only aggregated/non-personal data is in the EU-share scope. Raw ANPR and CCTV excluded by design | ✅ |
| **Purpose limitation** | DSA with each EU recipient must bind them to declared purposes (traffic management, road safety statistics, EU ITS Directive compliance) — **contractual gap until DSAs signed** | 🟡 |
| **Storage limitation** | ANPR 24h / CCTV 31d retention in source system; EU recipients' retention governed by their RoPA — require contractual minimum standard | 🟡 |
| **Pseudonymisation** | ANPR plates SHA-256 hashed with salt; hash deleted at 24h. Re-identification risk if salt compromised — addressed by hardware security module (HSM) per NFR-SEC-004 | ✅ |
| **Privacy-friendly defaults** | Public API default is aggregated/anonymised; personal-data endpoints require authentication + purpose declaration | ✅ |
| **Data protection integrated in design** | Architecture Principle #12 (Data Minimization), #11 (Data Sovereignty); data model enforces PII classification | ✅ |

---

## 4. Data Subject Rights (Articles 15–22)

| Right | Article | Mechanism Implemented | Response Time | Cross-border Implication |
|-------|---------|----------------------|---------------|--------------------------|
| **Right of access (SAR)** | 15 | SAR process via DPO; 1-month response | 1 month | EU data subjects can submit SARs to National Highways for UK-held personal data; workflow must accept EU-language SARs — **gap** |
| **Right to rectification** | 16 | Operator-ID corrections via data steward (E-003); not applicable to hashed ANPR or CCTV faces (identity not held in structured form) | 1 month | ✅ |
| **Right to erasure** | 17 | ANPR hash: automated 24h deletion. CCTV: automated 31d deletion (overrides erasure requests during retention window under public-task basis). Erasure honoured where feasible | Automated | ✅ |
| **Right to restriction** | 18 | Public-task exemption (Art. 18(2)) permits continued processing for public-interest reasons; flag in system required | Notify before lifting | 🟡 System-level "restriction flag" not implemented — **gap** |
| **Right to portability** | 20 | Not applicable — lawful basis is public task, not consent/contract (Art. 20(1) precondition not met) | N/A | ✅ |
| **Right to object** | 21 | Overridden by compelling public-task grounds. Objections must still be assessed and reasoned response given | 1 month | 🟡 Objection-handling SOP not documented — **gap** |
| **Rights re: automated decisions** | 22 | Not applicable — no automated decisions with legal/significant effect. AI-based incident detection triggers operator review (human in loop), not an Art. 22 decision | N/A | ✅ |

**Gap consolidation**: Three workflow gaps — EU-language SAR intake, restriction-flag implementation, documented objection SOP. All LOW-MEDIUM priority but required before EU sharing goes live.

---

## 5. Records of Processing Activities (Article 30)

| Requirement | Status |
|-------------|--------|
| RoPA (Record of Processing Activities) maintained | ☑ (existing UK GDPR Art. 30 RoPA held by DPO) |
| RoPA includes all mandatory fields (Art. 30(1)(a)–(g)) | ☑ |
| RoPA kept up to date | ☑ (Quarterly review cycle) |
| RoPA available to supervisory authority on request | ☑ |
| **RoPA extended to cover EU-sharing processing activity** | ☐ **GAP — action required** |
| RoPA lists EU recipients and transfer safeguards (Art. 30(1)(d) and (e)) | ☐ **GAP — action required** |

**RoPA location**: `projects/000-global/external/ropa-register.xlsx` (DPO-owned)
**Action**: DPO to add processing activity "EU Road Information Sharing" to RoPA with fields: purpose, recipient categories (EU Member State road operators, EU Commission DG MOVE, European Data for Road Safety programme), transfers (UK→EU under EU adequacy decision), retention.

---

## 6. DPIA Assessment (Article 35)

### 6.1 EDPB 9-Criteria Screening

Based on WP248 rev.01 (EDPB guidelines):

| # | Criterion | Present? | Evidence |
|---|-----------|---------|----------|
| 1 | Evaluation/scoring | ☐ No | No profiling or scoring of data subjects |
| 2 | Automated decisions with legal/significant effect | ☐ No | AI incident detection is human-reviewed |
| 3 | **Systematic monitoring** | ☑ **YES** | 3,500 CCTV cameras + 10,000+ sensors continuously monitor public roads (24/7, national scale) |
| 4 | Sensitive/special category data | ☐ No | No Article 9 data |
| 5 | **Large-scale processing** | ☑ **YES** | 5 million ANPR journey records/day, national coverage of England's SRN, millions of data subjects |
| 6 | Matching/combining datasets | ☐ No | Datasets not combined across controllers for new purposes (EU recipients receive only what is in DATEX II scope) |
| 7 | Vulnerable data subjects | ☐ No | No children, patients, employees at scale |
| 8 | **Innovative technology** | ☑ **YES** | ANPR, AI-based incident detection, pseudonymisation-at-scale |
| 9 | Prevents exercising rights | ☐ No | Rights implemented (with caveats in §4) |

**Score: 3/9 → DPIA REQUIRED** under Article 35(3)(c) and the EDPB WP248 "two or more criteria" threshold.

### 6.2 DPIA Status

| DPIA | Conducted | Date | Outcome |
|------|-----------|------|---------|
| ANPR journey-time processing | ☑ Yes (UK GDPR Art. 35) | Per data model §GDPR | ICO consultation pending |
| CCTV surveillance of SRN | ☑ Yes (UK GDPR Art. 35) | Per data model §GDPR | ICO consultation pending |
| **EU sharing of aggregated datasets** | ☐ **No — required** | — | Required before go-live — **Run `/arckit.dpia` to refresh** |

---

## 7. Data Processors and Sub-Processors (Article 28)

| Processor | Service | DPA in Place | Binding Commitments | Notes |
|-----------|---------|--------------|---------------------|-------|
| Microsoft Azure (UK regions) | Cloud hosting (IaaS/PaaS) | ☑ Standard Microsoft DPA + UK Addendum | ☑ | UK data residency (UK South + UK West); no EU replication for OFFICIAL-SENSITIVE |
| Met Office (Datapoint API) | Weather data source | N/A — Met Office is independent controller, not processor | — | Data flow inbound only |
| EU recipient road operators | Data recipient (not processor) | **Data Sharing Agreement (DSA)** required — **not DPA**, because they are independent controllers | ☐ **GAP — DSAs required** | Each DSA must bind recipient to purpose limitation, security standards, and prohibition on onward transfer to non-adequate third countries without National Highways' consent |
| Commercial navigation providers (Google, Waze, TomTom) | Data recipient via public API | N/A — aggregated/non-personal data only | — | Out of scope if non-personal |

DPA / DSA must include:

- [ ] Processing only on controller's instructions (DPA) / purpose limitation (DSA)
- [ ] Confidentiality obligations on authorised persons
- [ ] Appropriate security measures (Article 32) — encryption in transit (TLS 1.3), at rest (AES-256)
- [ ] Sub-processor controls and notification
- [ ] Assistance with data subject rights
- [ ] Deletion/return on contract end
- [ ] Audit cooperation (at least annual)
- [ ] **Prohibition on onward transfer to non-adequate third countries (DSA addition)**
- [ ] **Prohibition on re-identification of pseudonymised/aggregated data (DSA addition)**

---

## 8. International Transfers (Articles 44–49)

### 8.1 Transfer Inventory

| Transfer | Data Type | Destination | Adequacy Decision | Safeguard Required | TIA | Status |
|----------|-----------|-------------|-------------------|---------------------|------|--------|
| T-1 | Aggregated traffic/incident/roadworks (non-personal) | EU/EEA Member States | N/A — non-personal data falls outside GDPR Chapter V | None | N/A | ✅ |
| T-2 | Aggregated ANPR journey times (post-24h, non-personal) | EU/EEA Member States | N/A — non-personal once aggregation verified | None | Internal aggregation verification memo required | 🟡 DPO verification pending |
| T-3 | Operator user IDs embedded in incident records (if not redacted) | EU/EEA Member States | ✅ EU adequacy for UK (Decision (EU) 2021/1772, extended to 27 June 2031 by Implementing Decision (EU) 2025/1033 of June 2025) | None (adequacy applies) | Not required (adequacy) — but TIA recommended for onward transfer visibility | ✅ UK→EU bilateral adequacy |
| T-4 | CCTV footage / raw ANPR hash | EU/EEA | **🔴 OUT OF SCOPE — DO NOT TRANSFER** | — | — | 🔴 Blocked by design |
| T-5 | Onward transfer from EU recipient to US navigation provider | Non-UK, non-EU | US: EU-US Data Privacy Framework (if recipient certified) OR SCCs 2021 Module 1 + TIA | SCC + TIA | **Recipient-side obligation** — DSA to require recipient's compliance | 🟡 Recipient-dependent |

### 8.2 UK↔EU Adequacy Position (Post-Brexit)

**Outbound from UK to EU/EEA**:
- UK Government recognises EEA Member States as providing adequate protection under **Data Protection Act 2018 s.17A** (transitional provision made permanent). No restricted-transfer mechanism required from the UK side.

**Outbound from EU recipient back to UK (reverse flow)**:
- EU Commission adopted **Adequacy Decision (EU) 2021/1772** for the UK on 28 June 2021. This was due to sunset 27 June 2025 but was **extended by Implementing Decision (EU) 2025/1033 until 27 June 2031** (approximately — verify exact text before reliance).
- Effect: no SCCs / BCRs required for EU→UK transfers during the extension period.

**Risk**: If the EU Commission revokes or allows the adequacy decision to lapse (e.g., following a CJEU Schrems-style challenge), EU→UK return flows will immediately require SCCs + TIA. **Contingency**: DSAs should include a fallback clause triggering SCCs 2021 Module 1 if adequacy is withdrawn.

### 8.3 Post-Schrems II Requirements (applicable to T-5 onward transfers only)

| Requirement | Status |
|-------------|--------|
| Transfer Impact Assessment (TIA) documented | ☐ Recipient-side obligation — require via DSA |
| SCCs 2021 (Commission Implementing Decision (EU) 2021/914) | N/A direct; recipient-dependent |
| Supplementary measures (encryption, pseudonymisation, contractual) | Already applied at source (aggregation, pseudonymisation) |
| EU-US Data Privacy Framework status | Monitored — DPF remains subject to ongoing CJEU challenge ("Schrems III") |

---

## 9. Breach Notification (Articles 33–34)

| Requirement | Deadline | Recipient | Status |
|-------------|---------|-----------|--------|
| Notification to ICO (UK GDPR Art. 33) | **72 hours** | ICO | ☑ Established |
| Notification to EU supervisory authorities (EU GDPR Art. 33) | **72 hours** | Each EU recipient's national DPA (if the breach affects their data subjects) | ☐ **GAP — process not defined** |
| Notification to data subjects (if high risk — Art. 34) | Without undue delay | Affected individuals | ☑ UK process only — EU process gap |
| Breach documented in internal register | Ongoing | Internal | ☑ |
| Joint-controller breach protocol (Art. 26) | Per DSA | Joint controller | ☐ Per-DSA gap |

**Breach notification process in place (UK)**: ☑ Yes
**Breach notification process (EU recipients)**: ☐ **Needs extension** — cascaded notification via DSA

**Action**: DPO to amend breach-response runbook to (a) identify whether EU data subjects/recipients are affected, (b) notify each relevant EU DPA in parallel with ICO within 72 hours, (c) use standard template in English plus recipient's national language where feasible.

---

## 10. National Supervisory Authority Context

Because National Highways has no EU establishment, there is **no lead supervisory authority** for EU processing under Article 56 one-stop-shop. Each EU recipient's national DPA has jurisdiction over processing in its territory.

| Member State | Supervisory Authority | National Specificities Relevant to This Share |
|--------------|----------------------|------------------------------------------------|
| France | CNIL | Age of consent 15; cookies (Délibération 2020-091); ITS data shared with CEREMA. **Run `/arckit.fr-rgpd`** if France is a named recipient |
| Germany | BfDI + 16 Länder DPAs | Federal structure — relevant DPA depends on recipient Land (e.g., BASt is federal; road operators are Land-level) |
| Netherlands | Autoriteit Persoonsgegevens (AP) | Strict enforcement on systematic monitoring |
| Spain | AEPD | Specific public-sector requirements |
| Italy | Garante | Additional provisions on profiling and CCTV |
| Belgium | APD | Enforcement on legitimate interests |
| Ireland | DPC | Likely recipient via TII (Transport Infrastructure Ireland) — cross-border interest given common-travel-area road links |
| Sweden | IMY | Strong anonymisation standards — aggregation thresholds stricter than EDPB minimum |
| Austria | DSB | ASFiNAG as likely recipient |
| Denmark | Datatilsynet | — |
| Other EU27/EEA | — | To be populated per DSA scope |

> **Note**: For any French-recipient DSA, run `/arckit.fr-rgpd` to cover CNIL-specific obligations (cookies, HDS if relevant, délibérations on CCTV and ANPR).

### Article 27 EU Representative

Under **Article 27 GDPR**, a controller without EU establishment must designate an EU representative if it processes EU data subjects' personal data on a "regular and non-occasional" basis with risk to data subjects' rights.

**Assessment**: National Highways' EU-sharing scope is **aggregated/non-personal data**. If scope remains non-personal, Article 27 is **not triggered**. If scope expands to include personal data flows (e.g., pseudonymised ANPR shared with EU law enforcement), Article 27 designation would be required. **Recommend: formal decision memo stating Article 27 not required, with trigger criteria for re-assessment.**

---

## 11. Gap Analysis and Action Plan

| # | Gap | Reference | Priority | Owner | Deadline |
|---|-----|-----------|---------|-------|---------|
| G-1 | RoPA not extended to cover EU-sharing processing activity | Art. 30 | 🔴 High | DPO (SD-8) | 2026-05-31 |
| G-2 | DPIA not refreshed for EU-sharing scope | Art. 35 | 🔴 High | DPO + CISO | 2026-06-30 (run `/arckit.dpia`) |
| G-3 | Data Sharing Agreements (DSAs) with each EU recipient not signed | Art. 26 / Ch. V | 🔴 High | Legal Counsel + EU Liaison | Per recipient (before first transfer) |
| G-4 | Breach notification process does not cover parallel notification to EU DPAs | Art. 33 | 🟠 Medium | DPO | 2026-06-30 |
| G-5 | Aggregation verification memo (confirming post-24h ANPR journey times are below re-ID threshold) not produced | Recital 26 | 🟠 Medium | DPO + Data Architect | 2026-05-31 |
| G-6 | Joint-controller analysis per-recipient (Art. 26) not complete | Art. 26 | 🟠 Medium | Legal Counsel | Per recipient |
| G-7 | SAR workflow does not formally handle EU-language requests | Art. 15 | 🟡 Low | DPO + Service Desk | 2026-09-30 |
| G-8 | Restriction-flag (Art. 18) not implemented at data-platform level | Art. 18 | 🟡 Low | Data Architect | 2026-09-30 |
| G-9 | Objection-handling SOP not documented | Art. 21 | 🟡 Low | DPO | 2026-09-30 |
| G-10 | Article 27 EU representative decision not formally recorded | Art. 27 | 🟡 Low | DPO + Legal Counsel | 2026-05-31 |
| G-11 | Adequacy-revocation contingency (SCCs fallback clause) not drafted | Ch. V | 🟡 Low | Legal Counsel | Included in DSA template |
| G-12 | Article 6(1)(f) vs public-authority exclusion — CCTV retention beyond op window requires re-basing review | Art. 6(1) final ¶ | 🟠 Medium | Legal Counsel + DPO | 2026-06-30 |

---

## Assumptions, Caveats & Review Triggers

**Assumptions made in this assessment**:
- EU-sharing scope is limited to DATEX II-standard aggregated/non-personal datasets. If scope expands, this assessment must be re-run.
- UK↔EU mutual adequacy continues to apply. CJEU challenge or political withdrawal would trigger full Chapter V reassessment.
- No sharing of CCTV footage or raw ANPR is in scope. Any such proposal triggers a full DPIA and likely requires a separate legal instrument (LED 2016/680, Prüm II, or bilateral MoU).

**Review triggers** (re-run this assessment if any occur):
- Adequacy decision (EU) 2021/1772 lapsed, revoked, or amended
- New EU recipient added with joint-controller characteristics
- Scope expands to include personal data (CCTV, raw ANPR)
- EU-US Data Privacy Framework struck down by CJEU
- UK Data Protection Act or UK GDPR amended materially
- New EU legislation affecting road-operator data sharing (e.g., Data Act (EU) 2023/2854 Article 5 if vehicle-generated data enters scope)

---

**Generated by**: ArcKit `/arckit.eu-rgpd` command
**Generated on**: 2026-04-19
**ArcKit Version**: 4.7.0
**Project**: National Highways Data Architecture Modernization (001)
**Model**: claude-opus-4-7 (1M context)

---

> ⚠️ **This assessment is a DRAFT requiring qualified DPO, legal counsel, and CISO review before reliance.** Community-contributed commands do not substitute for professional advice. Citations to EU regulations are accurate at time of generation (2026-04-19) — verify against the current published text of EU 2016/679, Implementing Decisions, and EDPB Guidelines before use.
