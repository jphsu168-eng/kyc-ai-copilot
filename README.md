# KYC Case Bottleneck Resolver

A B2B KYC workflow prototype for enterprise compliance teams that simulates document evidence review, beneficial ownership completeness checks, screening triage, customer risk profiling, case bottleneck diagnosis, reason-code driven follow-up actions, analyst review notes, and audit-ready decision trails.

## Core Product Question

**Why is this KYC case blocked, and what should happen next?**

## Problem Statement

Modern KYC reviews are delayed by missing evidence, incomplete beneficial ownership information, weak evidence quality, screening items requiring review, unclear ownership of follow-up actions, inconsistent analyst notes, and lack of audit-friendly rationale.

This project simulates a 2026-style KYC case workstation that helps identify case blockers, explain risk drivers, recommend the next review path, and create consistent analyst documentation.

The current prototype uses a single-page multi-view interface to simulate how a production KYC platform could separate case overview, evidence review, risk assessment, action tracking, and audit governance.

## Important Disclaimer

This is an educational portfolio project. It does not perform real sanctions screening, OFAC checks, adverse media searches, identity verification, customer verification, transaction monitoring, or bank decisioning.

This tool supports analyst workflow simulation. Final review, escalation, approval, and customer decisioning require human compliance review.

The current implementation is a static single-page workflow prototype, not production software. It simulates case intake, evidence review, risk assessment, action tracking, and governance outputs without storing or transmitting customer data.

## Target Customer

This prototype is designed as a B2B KYC workflow concept for enterprise compliance teams, including banks, fintech companies, payment companies, MSBs, and compliance operations teams that review business customers, legal entities, and higher-risk onboarding cases.

It is not designed for individual consumers. The primary users are KYC analysts, AML analysts, compliance reviewers, relationship managers, QA reviewers, and KYC operations managers.

Individual remains a supported entity type in the demo because enterprise compliance teams may review sole proprietors, control persons, or individual-linked cases as part of broader KYC operations.

## Buyer / User Distinction

### Buyer / Decision Maker

- Head of Compliance
- KYC Operations Manager
- AML Compliance Officer
- Risk Operations Director
- FinTech COO

### Primary Users

- KYC Analyst
- AML Analyst
- Compliance Analyst
- Relationship Manager
- Compliance Reviewer
- QA Analyst

## Product Structure

- **Overview:** product title, core product question, educational disclaimer, Command Center KPIs, sample cases, generate/reset controls, and short case snapshot.
- **Case Input:** guided case setup, compact document evidence review, core beneficial ownership checks with collapsed advanced BO details, SOF/SOW review, screening triage, and risk indicators.
- **Results:** executive summary, diagnostic details, customer risk profile, evidence quality issues, risk breakdown, bottlenecks, reason codes, and queue priority.
- **Actions:** action tracking table with owner, priority, reason code, suggested due date, status, and follow-up communication draft controls.
- **Governance:** analyst review note, reviewer checklist, lightweight maker-checker Review Control, audit trail, triggered rules, full rule library, and human review disclaimer.

## Key Features

- Command Center with polished empty states and dynamic KPI updates
- Case Data Quality Check with required-field validation, strict U.S. date validation, and logical consistency warnings
- Single-page multi-view workflow stepper with Overview, Case Input, Results, Actions, and Governance views
- Guided workflow navigation and next-step buttons that move from Overview to Case Input, Results, Actions, and Governance while preserving form state
- Sample case shortcuts for Low Risk, Blocked BO, and Sanctions Escalation scenarios
- Case Review Inputs for onboarding, periodic review, trigger event review, and ongoing monitoring alert workflows
- Document Evidence Review with required documents by entity type
- Evidence status dropdowns: Not Received, Received - Acceptable, Received - Expired, Received - Incomplete, Received - Inconsistent, and Not Applicable
- Beneficial Ownership Review with visible core BO checks and collapsed advanced details for BO ID, ownership percentage, 25% ownership, and BO certification/attestation
- Source of Funds / Source of Wealth Review
- Screening Triage helper with cautious documentation language that does not clear screening hits
- Customer Risk Profile across customer type, geography, industry, ownership, product/service, expected activity, screening, documentation, and overall risk
- Rule-based 0-100 risk score with Low, Medium, High, and Critical ratings
- Bottleneck diagnosis with reason codes
- Suggested Review Path: Standard Review, Enhanced Review, Compliance Escalation, or Do Not Proceed Until Cleared
- Decision Confidence / Data Quality output
- Case Stage output, such as Evidence Collection, RM Follow-Up, Compliance Escalation, Ready for Final Review, or Do Not Proceed Until Cleared
- Follow-up action tracker with owner, priority, reason code, illustrative business-day due date, status badges, and reason-code pills
- Follow-Up Communication Draft for Relationship Manager, Customer, or Compliance Officer
- Analyst Review Note with scrollable long-form work note
- Reviewer Checklist for human quality review
- Lightweight maker-checker Review Control showing prepared by, required reviewer, Not submitted status, and human review requirement
- Audit Trail with timestamp, inputs reviewed, evidence issues, BO result, screening result, risk score, reason codes, follow-up owners, suggested review path, case readiness, and disclaimer
- Explainability Center showing only triggered rules first

## Case Data Quality Check

Before generating a case review, the tool performs an educational input-quality review:

- **Blocking issues** prevent generation when required case setup fields are missing, dates are invalid, or the target completion date is earlier than the received date.
- **Non-blocking warnings** flag potentially inconsistent BO, SOF/SOW, screening, and SLA inputs while still allowing the analyst to generate the review.
- **Inline field errors** identify required fields that need correction after a generation attempt.
- **Stale result warnings** appear when material case inputs change after a review has been generated. Recipient Type and Tone remain independently reactive and do not require full regeneration.
- **Audit-friendly output** carries non-blocking data-quality warnings into the Analyst Review Note, Audit Trail, and Triggered Rules.

These checks are illustrative workflow controls, not validation against a bank policy, authoritative customer record, screening system, or external data source.

## Workflow

1. Start in **Overview** to load a sample case or generate/reset a review.
2. Use **Case Input** to complete case setup, evidence, ownership, SOF/SOW, screening, and risk fields. The Case Input view separates demo shortcuts, core case details, review setup, optional risk context, document evidence, beneficial ownership, and SOF/SOW review so the workflow is easier to scan.
3. Generate the review to move automatically into **Results**, where executive summary, diagnostic details, bottlenecks, reason codes, and queue priority are displayed.
4. Continue to **Actions** to review the follow-up action tracker and copy a role-specific communication draft.
5. Continue to **Governance** to review analyst notes, reviewer checklist, audit trail, triggered rules, and the collapsed full rule library.

Switching tabs does not clear form data or generated outputs because the project remains a single HTML page with JavaScript-controlled views.

## Document Evidence Review

Required documents are based on entity type:

| Entity Type | Required Documents |
| --- | --- |
| Private Company | Certificate of Incorporation, Business Registration, Ownership Chart, Beneficial Owner ID, W-9 or W-8, Address Proof, Source of Funds Explanation |
| Public Company | Annual Report or 10-K, Stock Exchange Listing Evidence, Authorized Signer Information, W-9 or W-8 |
| Individual | Government ID, Address Proof, Source of Funds Explanation |
| Non-profit | Registration Certificate, Mission Statement or Website, Authorized Signer Information, Source of Funds Explanation |
| Financial Institution | Banking License or Regulatory Registration, AML Policy Summary, Wolfsberg Questionnaire, Authorized Signer Information |

The tool treats these statuses as evidence issues:

- Not Received
- Received - Expired
- Received - Incomplete
- Received - Inconsistent

Evidence issues appear in Diagnostic Details, Bottleneck Diagnosis, Follow-Up Actions, Analyst Review Note, Reviewer Checklist, and Audit Trail.

## Customer Risk Profile

The Customer Risk Profile uses Low, Medium, High, and Critical labels across:

- Customer Type Risk
- Geography Risk
- Industry Risk
- Ownership Risk
- Product / Service Risk
- Expected Activity Risk
- Screening Risk
- Documentation Risk
- Overall Customer Risk Profile

Each profile component includes a short explanation of which input drove the result.

## Risk Scoring Methodology

The score is rule-based, educational, and capped at 100.

| Risk Factor | Points |
| --- | --- |
| PEP involvement | +25 |
| Sanctions or watchlist concern | +40 |
| Adverse media | +20 |
| High-risk country | +20 |
| Complex ownership structure | +15 |
| BO incomplete | +15 |
| Missing key documents | +10 |
| High expected activity | +10 |
| Higher-risk product/service | +10 |
| Moderate product/service risk | +5 |
| Financial institution customer | +10 |
| Case overdue | +5 |
| Evidence quality issue | +10 |
| Missing Source of Funds | +10 |
| Missing Source of Wealth for higher-risk customer | +10 |
| Weak SOF/SOW explanation | +5 |

Risk levels:

| Score | Risk Level |
| --- | --- |
| 0-24 | Low |
| 25-49 | Medium |
| 50-74 | High |
| 75-100 | Critical |

Rule weights are illustrative and are not calibrated to any bank policy.

## Reason Codes

Reason codes make bottlenecks easier to scan, explain, and audit.

| Code | Meaning |
| --- | --- |
| `DOC-001` | Missing required document |
| `DOC-002` | Evidence quality issue |
| `BO-001` | Beneficial ownership incomplete |
| `BO-002` | Complex ownership escalation |
| `SOF-001` | Source of funds issue |
| `SOW-001` | Source of wealth issue |
| `SCR-001` | Screening clearance needed |
| `SCR-002` | Potential true match |
| `ADV-001` | Adverse media review needed |
| `SLA-001` | Case aging risk |
| `RISK-001` | High or critical risk |
| `DEC-001` | Do not proceed until cleared |
| `CONF-001` | Insufficient information |

Reason codes appear in Bottleneck Diagnosis, Follow-Up Actions, Analyst Review Note, Audit Trail, and Triggered Rules.

## Suggested Review Path

The Suggested Review Path is an educational routing recommendation:

- **Standard Review:** Low or Medium risk with no material blockers.
- **Enhanced Review:** High risk, adverse media, complex ownership, or material evidence gaps.
- **Compliance Escalation:** Critical risk, potential true match, or BO escalation.
- **Do Not Proceed Until Cleared:** Sanctions/watchlist concern.

Educational recommendation only. Final decision requires human compliance review.

## Decision Confidence

Decision Confidence / Data Quality indicates whether the simulated case file is strong enough to support a review note:

- **High:** clean low-risk case with acceptable evidence.
- **Medium:** minor gaps or follow-up items remain.
- **Low:** many missing documents, BO gaps, incomplete screening identifiers, or inconsistent evidence.
- **Insufficient Information:** sanctions/watchlist concern or information gaps prevent decisioning.

If information is insufficient, the tool states that the decision cannot be finalized due to insufficient customer information.

## Explainability Center

The Explainability Center first shows **Triggered Rules for This Case**, meaning only the rules activated by the current inputs. The **Full Rule Library** is collapsed by default and organized into:

- Document Rules
- Evidence Quality Rules
- Beneficial Ownership Rules
- SOF/SOW Rules
- Screening Triage Rules
- Trigger Event Rules
- Risk Scoring Rules
- Case Readiness Rules
- Review Path Rules
- Queue Urgency Rules

## Limitations

- No real OFAC screening
- No sanctions database connection
- No adverse media search
- No identity verification
- No transaction monitoring
- No customer verification
- No bank decisioning
- No backend or database
- No login or role-based approval
- No real customer data storage
- No production policy calibration
- Rule weights are illustrative and not calibrated to any bank policy

## Future Roadmap

- Case queue import
- CSV upload
- Configurable policy rule engine
- Reviewer approval workflow
- Role-based access control
- Database persistence
- Append-only audit log
- Export to PDF or Word case memo
- Vendor screening API integration
- Document management integration
- Manager dashboard

## Future Technical Roadmap

### Current State

The current project is a static frontend prototype built with one HTML file, embedded CSS, and browser-based JavaScript. It demonstrates workflow concepts locally without a backend, database, authentication, persistent storage, production integrations, or real customer-data processing.

The components below describe a possible future production architecture. They are roadmap concepts only and are **not** features of the current application.

### Potential Production Architecture

- **React or Next.js frontend:** component-based case workspaces, queue views, reusable controls, routing, and maintainable application state.
- **FastAPI or Node.js backend:** authenticated APIs for case orchestration, assignments, validation, rule execution, review controls, and controlled integrations.
- **PostgreSQL database:** durable storage for cases, legal entities, beneficial owners, evidence metadata, risk assessments, actions, reviews, and workflow status.
- **Role-based access control:** permissions for KYC Analysts, Reviewers, Compliance Officers, QA users, Relationship Managers, and Operations Managers.
- **Case queue and assignment workflow:** prioritized work queues, ownership, reassignment, service-level targets, due dates, and workload tracking.
- **Maker-checker review process:** formal submission, independent review, return-for-information, escalation, disposition, and approval states.
- **Backend validation engine:** server-side required-field, date, evidence-quality, and logical-consistency checks that cannot be bypassed by the frontend.
- **Configurable rule engine:** institution-approved, versioned policy rules for risk scoring, reason codes, routing, escalation, and document requirements.
- **Append-only audit event log:** immutable workflow events recording input changes, rule versions, assignments, decisions, reviewer actions, and timestamps.
- **Document metadata and secure document storage:** controlled evidence upload, classification, versioning, retention, encryption, access logging, and document lifecycle management.
- **API integrations:** authorized connections to screening vendors, corporate registries, document systems, and internal case-management platforms, subject to institutional controls and vendor agreements.
- **AI-assisted drafting and summarization only:** human-reviewed assistance for analyst notes, follow-up communication, case summaries, and document-gap narratives. AI should not independently approve customers, clear screening alerts, assign final risk ratings, or make regulatory decisions.

This roadmap does not imply that the current prototype performs real sanctions screening, OFAC checks, adverse media searches, identity verification, transaction monitoring, customer verification, or bank decisioning. Final review, escalation, approval, onboarding, and regulatory decisions require qualified human compliance review and institution-specific policies.

## V2 Full-Stack Migration Plan

This section describes a possible future migration from the current static frontend prototype to a full-stack KYC case management platform. None of the V2 architecture or capabilities below are implemented in the current project.

### Phase 1: Frontend Refactor

- Move from a single `index.html` file to React, Vite, and TypeScript.
- Split the interface into reusable layout, navigation, form, result, action, governance, and disclosure components.
- Preserve the current workflow views: Overview, Case Input, Results, Actions, and Governance.
- Move rule definitions, document requirements, reason-code metadata, and sample cases into separate typed modules.
- Introduce shared application state and typed data models while preserving the current workflow behavior during migration.

### Phase 2: Backend API

- Add a FastAPI backend as the controlled service layer for the application.
- Move required-field validation, logical-consistency checks, risk calculations, routing rules, and review generation from the browser to the backend.
- Create REST endpoints for cases, validation, generated reviews, follow-up actions, analyst notes, review controls, and audit events.
- Keep the frontend responsible for presentation and user interaction while treating backend responses as the authoritative workflow state.

### Phase 3: Database

- Add PostgreSQL for durable, structured storage.
- Store customers, KYC cases, document metadata, beneficial ownership data, screening review records, follow-up actions, analyst notes, review decisions, and audit events.
- Define stable identifiers, relationships, timestamps, status history, and retention fields for each record type.
- Use database migrations and transactional updates to maintain consistent workflow data.

### Phase 4: Review Workflow

- Add role-based mock users for Analyst, Reviewer, Compliance Officer, QA, and Manager scenarios.
- Implement an analyst and reviewer maker-checker workflow.
- Add controlled case statuses such as Draft, Submit for Review, Return for Correction, Approved, and Closed.
- Record assignments, comments, review outcomes, status transitions, and responsible users in the audit history.
- Treat approval as an authorized human workflow action, not an automated result from the rule engine.

### Phase 5: AI-Assisted Drafting

- Add optional AI-assisted drafting for analyst review notes, follow-up messages, case summaries, and document-gap narratives.
- Require users to review, edit, and explicitly accept AI-assisted content before it becomes part of a case record.
- Keep rule execution, escalation controls, review status, and final disposition outside the AI drafting layer.
- AI assistance would not make final compliance decisions, clear screening concerns, approve customers, or replace qualified human review.

### Phase 6: Production Readiness

- Add enterprise authentication and secure session management.
- Add authorization and role-based access controls for cases, documents, reviews, and administrative functions.
- Add encryption for data in transit and at rest, with managed secrets and key rotation.
- Add an immutable or append-only audit log for material workflow, policy, data, and reviewer events.
- Add policy and rule versioning with approval history, effective dates, testing evidence, and rollback controls.
- Add secure document handling with malware scanning, controlled access, retention rules, download logging, and storage lifecycle management.
- Add monitoring, backup, recovery, testing, deployment, and incident-response controls appropriate for production use.

This migration plan is an architectural roadmap only. A production implementation would require institution-specific policies, security review, legal and compliance review, vendor governance, testing, and qualified human decisioning.

## How To Run

Open `index.html` directly in a browser. No setup, server, API key, package install, or build step is required.

## Resume Bullet Points

### KYC Analyst / Compliance Analyst

- Built a rule-based KYC case bottleneck workflow that identifies missing evidence, BO gaps, screening concerns, risk drivers, reason codes, and recommended next steps.
- Created analyst-ready review notes, follow-up actions, reviewer checklist, and audit trail outputs for simulated KYC case documentation.
- Modeled evidence quality, beneficial ownership, SOF/SOW, screening triage, and escalation rules in a transparent educational workflow.

### FinTech Operations Analyst

- Designed a static RegTech operations dashboard with a Command Center, Bottleneck Engine, Action Center, and Governance & Audit outputs.
- Added sample cases, urgency scoring, case stage logic, follow-up ownership, and copyable communication drafts to improve demo usability.
- Demonstrated how workflow automation can reduce manual KYC case friction without using backend systems, external data, or production integrations.

### Entry-Level AI Automation / RegTech Role

- Developed a beginner-friendly rule-based automation prototype using plain HTML, CSS, and JavaScript to simulate KYC triage and audit-friendly outputs.
- Structured decision rules, reason codes, sample data, and UI rendering logic so the static project could be extended into a future policy-rule engine.
- Documented limitations and human-review requirements to show responsible automation design for compliance workflows.

## Author, Disclaimer, and License

### Author

Jiangpeng Hu

KYC / Compliance Operations / RegTech Portfolio Project

This project demonstrates a rule-based KYC workflow prototype for case bottleneck diagnosis, evidence quality review, beneficial ownership checks, follow-up actions, analyst review notes, and audit-friendly documentation.

### Legal and Compliance Disclaimer

This project is an educational and portfolio-based workflow prototype. It is not a production compliance system and does not provide legal, regulatory, financial, or compliance advice.

This tool does not perform real OFAC screening, sanctions screening, adverse media search, identity verification, customer verification, transaction monitoring, customer risk rating, or bank decisioning.

All outputs, including risk scores, suggested review paths, reason codes, analyst notes, follow-up actions, and audit-style summaries, are rule-based simulations for demonstration purposes only.

Final KYC review, escalation, approval, customer onboarding, and regulatory decisions require qualified human compliance review and institution-specific policies.

### Original Work and Copyright

This project was independently designed and developed by Jiangpeng Hu as a portfolio project focused on KYC operations, compliance workflow automation, and RegTech product design.

Unless otherwise stated, the project content, workflow design, UI structure, rule logic, documentation, and source code are original work created for educational and portfolio demonstration purposes.

### License

No open-source license has been granted for this repository.

The source code and project materials are provided publicly for portfolio review and demonstration purposes only. You may view the repository, but you may not copy, modify, distribute, sublicense, or use this project for commercial purposes without written permission from the author.

© 2026 Jiangpeng Hu. All rights reserved.
