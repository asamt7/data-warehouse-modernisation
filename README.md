# Data Warehouse Modernisation — BA Case Study

> **Portfolio case study** | Sanitised for public sharing. Client and company names have been anonymised.

---

## Project Summary

| | |
|---|---|
| **Role** | Lead Business Analyst & Scrum Master |
| **Duration** | 7 months (Discovery → Deployment) |
| **Domain** | Retail Trade Association / Data & Insight |
| **Tech Stack** | Azure Data Factory, Azure Data Lake, Power BI, Azure Logic Apps |
| **Methodology** | Agile (Scrum) - 14 Sprints |
| **Status** | Live in Production |

---

## Problem Statement

A leading trade association representing 200+ major retailers had built their entire insight and reporting capability on Excel. Their team managed multiple data monitors — covering retail sales, footfall, pricing, and economic data — all through manual spreadsheet workflows stored on a shared cloud drive.

**Core pain points identified during discovery:**

- **Data fragmentation** — each monitor lived in a separate Excel file; cross-monitor analysis was nearly impossible
- **Data integrity risk** — no version control or change tracking; data could be modified or deleted without detection
- **Reporting bottlenecks** — generating reports required hours of manual formatting across multiple files
- **Scalability barrier** — the organisation wanted to grow its insight offer (custom reports, member-facing data access, proprietary indices) but the Excel infrastructure couldn't support it
- **No dedicated IT function** — the organisation relied on external consultants for any technical changes

The client needed to migrate from a fragmented, Excel-based data estate to a centralised, cloud-based Data Warehouse — without disrupting ongoing monthly reporting cycles.

---

## Objectives

1. Replace manual, Excel-based data processes with an automated, centralised Data Warehouse
2. Enable cross-monitor analysis through a unified data model
3. Automate ETL pipelines for 7+ retail data monitors
4. Deliver self-service Power BI dashboards for the insight team
5. Establish data governance, quality controls, and audit capability
6. Complete delivery without disrupting monthly reporting obligations

---

## My Role & Deliverables

As the Lead Business Analyst and Scrum Master, I was responsible for the full BA lifecycle and Agile delivery governance across 14 sprints:

| Deliverable | Description |
|---|---|
| **Statement of Work (SOW)** | Defined scope, deliverables, team structure, risks, and financials |
| **Business Requirements** | Stakeholder interviews, process mapping, AS-IS / TO-BE documentation |
| **Solution Design Document (SDD)** | Architecture overview, data modelling, ELT design, naming conventions |
| **Data Models** | Conceptual, Logical, and Physical data models per monitor |
| **Source-to-Target Mapping (SMX)** | Column-level mapping from raw source data to curated warehouse layer |
| **Activity Breakdown** | Task-level breakdown with descriptions for every monitor and workstream |
| **Project Plan** | 14-sprint Gantt-style delivery plan across 7 months |
| **Process Flowcharts** | BPMN flowcharts for AS-IS and TO-BE data processes |
| **Power BI Dashboard Specs** | KPI definitions, visualization requirements, Figma-referenced mockups |

---

## Data Monitors Delivered

| # | Monitor | Data Source | Delivery Sprint |
|---|---|---|---|
| 0 | Planning, Infrastructure & Documentation | Internal | Sprint 1–2 |
| 7 | Footfall Monitor | Third-party footfall provider | Sprint 1–2 |
| 3 | Shop Price Index | Third-party pricing provider | Sprint 2–4 |
| 1 | Retail Sales Monitor | External research partner | Sprint 3–6 |
| 2 | Regional Retail Sales Monitor | External research partner | Sprint 4–7 |
| 4 | Economic Monitor | Internal + external | Sprint 5–8 |
| — | Project Handover & Overall Testing | — | Sprint 13–14 |

---

## Solution Architecture (High-Level)

```
azure_data_warehouse_architecture.svg
```

---

## Data Modelling Approach

For each monitor, the following modelling artefacts were produced:

| Artefact | Purpose |
|---|---|
| **Conceptual Data Model** | Entities and relationships - business-level understanding |
| **Logical Data Model** | Entities, attributes, and relationships - technology-agnostic |
| **Physical Data Model** | Column names, data types, referential integrity - implementation-ready |
| **Source-to-Target Mapping (SMX)** | Column-level transformation logic from source to curated layer |
| **Pre-Processor Mapping** | Identifies tables that can be combined; raw-to-fact structure guide |

---

## Activity Breakdown (Sample — Footfall Monitor)

| Area | Task | Description |
|---|---|---|
| Data Modelling | Client Meeting | Address stakeholder questions post-overview |
| Data Modelling | Source System Analysis | Analyse data generation and processing at source |
| Data Modelling | KPI Mapping | Map KPIs to base data and derivation logic |
| Data Modelling | Source File Refining | Optimise source data for DWH storage |
| Data Modelling | Pre-Processor Mapping | Identify combinable tables; raw-to-fact mapping |
| Data Modelling | Conceptual Data Model | Entity identification and relationship modelling |
| Data Modelling | Logical Data Model | Entity and process modelling |
| Data Modelling | Physical Data Model | Column types, referential integrity |
| Data Modelling | SMX Creation | Source-to-target transformation logic |
| ETL Development | Pipeline Build | Azure Data Factory pipeline per monitor |
| Dashboard | Power BI Build | KPI visualisations per spec |
| Testing | SIT | System integration testing |
| Testing | UAT | User acceptance testing with client team |

Full breakdown available in [`/docs/activity-breakdown.md`](docs/activity-breakdown.md)

---

## Key Outcomes

| Metric | Result |
|---|---|
| Report generation time reduction | **40%** |
| Monitors delivered | **7** |
| Sprints completed on time | **13 / 14** |
| Stakeholder engagement score (post-launch) | **+20%** |
| Executive paper approved | Budget secured for full build |
| Manual Excel workflows replaced | All 7 monitors |

---

## Governance & Risk Management

Key risks identified and mitigated:

| Risk | Mitigation |
|---|---|
| Disruption to live monthly reporting | Parallel running during transition; phased monitor migration |
| Data quality issues in source files | Data validation rules built into ELT pipeline |
| Stakeholder availability for sign-off | Weekly checkpoint meetings; async approval process defined |
| Scope creep | Formal change request process defined in SOW |
| No internal IT function at client | All technical work managed by delivery team; knowledge transfer plan |

---

## Repository Structure

```
├── README.md                          ← You are here
├── docs/
│   ├── business-requirements.md       ← Stakeholder needs, AS-IS/TO-BE
│   ├── activity-breakdown.md          ← Task-level breakdown per monitor
│   ├── project-governance.md          ← Risks, team structure, sprint plan
│   └── disclaimer.md                  ← Portfolio / anonymisation notice
├── diagrams/
│   ├── bpmn-as-is-process.png         ← Current state data flow
│   ├── bpmn-to-be-process.png         ← Future state automated pipeline
│   └── solution-architecture.png      ← High-level Azure architecture
```

---

## Tools & Skills Demonstrated

`Business Analysis` · `Data Warehousing` · `Azure (Data Factory, Data Lake, Logic Apps)` · `Power BI` · `BPMN Process Mapping` · `Data Modelling (Conceptual / Logical / Physical)` · `ETL Design` · `SOW & SDD Authoring` · `Stakeholder Workshops` · `Scrum Master` · `Jira` · `Agile Delivery` · `Risk Management` · `UAT Planning`

---

## Disclaimer

See [`/docs/disclaimer.md`](docs/disclaimer.md) for full details. All client and company names have been anonymised. Documents are shared with permission for portfolio purposes only.
