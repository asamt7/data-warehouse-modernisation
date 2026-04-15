# Activity Breakdown & Project Governance

> This document details the task-level breakdown used across the 14-sprint delivery plan,  
> along with team structure, sprint schedule, and risk register.

---

## 1. Sprint Delivery Plan

The project was delivered across **14 two-week sprints** over **7 months** (August 2024 — February 2025).

| Sprint | Period | Key Focus |
|---|---|---|
| Sprint 1 | Aug 5 – Aug 16 | Planning, Infrastructure Setup, Footfall Monitor Modelling |
| Sprint 2 | Aug 19 – Aug 30 | Documentation, Footfall ETL Dev, Shop Price Index Modelling |
| Sprint 3 | Sep 2 – Sep 13 | Footfall Dashboard, Shop Price ETL, Retail Sales Modelling |
| Sprint 4 | Sep 16 – Sep 27 | Footfall SIT/UAT, Shop Price Dashboard, Scottish Retail Modelling |
| Sprint 5 | Sep 30 – Oct 11 | Shop Price SIT/UAT, Retail Sales ETL, Economic Monitor Modelling |
| Sprint 6 | Oct 14 – Oct 25 | Retail Sales Dashboard, Scottish Retail ETL, Economic ETL |
| Sprint 7 | Oct 28 – Nov 8 | Retail Sales SIT/UAT, Scottish Retail Dashboard |
| Sprint 8 | Nov 11 – Nov 22 | Scottish Retail SIT/UAT, Economic Dashboard |
| Sprint 9 | Nov 25 – Dec 6 | Economic SIT/UAT |
| Sprints 10–12 | Dec – Jan | Buffer / additional monitors / regression testing |
| Sprint 13 | Jan 20 – Jan 31 | Project Handover preparation |
| Sprint 14 | Feb 3 – Feb 14 | Overall testing, final sign-off, knowledge transfer |

---

## 2. Activity Breakdown by Area

### 2.1 Data Modelling Tasks (Per Monitor)

| Task | Description |
|---|---|
| **Client Meeting** | Address questions raised following initial dashboard/benchmark overview |
| **Source System Analysis** | Analyse how data is generated and processed at source; identify all data sources |
| **KPI Mapping** | Map KPIs to base data; analyse how they are derived from underlying data sources |
| **Source File Refining** | Refine source data for optimal storage and efficiency within the DWH |
| **Pre-Processor Mapping** | Identify combinable tables; generate report showing raw structure vs. fact table structure |
| **Conceptual Data Model** | Identify entities; create model representing entity relationships |
| **Logical Data Model** | Create model highlighting entities and processes within the monitor |
| **Physical Data Model** | Specify column data types and referential integrity |
| **SMX Creation** | Source matrix guide: document logic for each column including source tables, transformations, and data types |

### 2.2 ETL Development Tasks (Per Monitor)

| Task | Description |
|---|---|
| **Pipeline Design** | Design Azure Data Factory pipeline per monitor; document data flow |
| **Raw Layer Build** | Implement ingestion pipeline to raw layer |
| **Transformation Build** | Implement curation logic per SMX specification |
| **CDC Implementation** | Implement Change Data Capture on applicable source tables |
| **Job Orchestration** | Configure scheduling and dependency management |
| **Data Quality Rules** | Implement table-level validation tests |

### 2.3 Dashboard Tasks (Per Monitor)

| Task | Description |
|---|---|
| **KPI Definition Review** | Validate KPI calculations with insight team |
| **Mockup Review** | Review Figma mockups with stakeholders before build |
| **Power BI Development** | Build dashboard per approved mockup and KPI spec |
| **Stakeholder Review** | Demonstrate dashboard; capture and implement feedback |

### 2.4 Testing Tasks (Per Monitor)

| Task | Description |
|---|---|
| **SIT (System Integration Testing)** | Test end-to-end pipeline from ingestion to Power BI |
| **UAT (User Acceptance Testing)** | Client insight team validates dashboard and data accuracy |
| **Defect Management** | Log, prioritise, and resolve defects in Jira |

---

## 3. Team Structure

| Role | Responsibility |
|---|---|
| **Lead Business Analyst / Scrum Master** | Requirements, process mapping, delivery governance, sprint ceremonies |
| **Data Architect** | Solution design, data modelling, architecture oversight |
| **Data Engineer (x2)** | ETL pipeline development, Azure Data Factory, Data Lake |
| **Power BI Developer** | Dashboard development, KPI implementation |
| **QA Analyst** | Test planning, SIT execution, defect management |
| **Client — Director of Insight** | Executive sponsor, acceptance sign-off |
| **Client — Insight Team (x2)** | UAT, KPI validation, feedback |

---

## 4. Risk Register

| # | Risk | Probability | Impact | Mitigation |
|---|---|---|---|---|
| 1 | Disruption to live monthly reporting cycle | Medium | High | Parallel running during transition; phased monitor migration by sprint |
| 2 | Data quality issues in source Excel files | High | Medium | Data profiling in Sprint 1; validation rules built into ETL before curated layer |
| 3 | Stakeholder unavailability for UAT | Medium | High | Async approval process; UAT windows scheduled 2 weeks in advance |
| 4 | Scope creep from new monitor requests | Medium | Medium | Formal change request process defined in SOW; Sprint 0 backlog freeze |
| 5 | No internal IT support at client | High | Low | Full technical documentation; knowledge transfer plan in Sprint 13–14 |
| 6 | Third-party data format changes | Low | High | Source file validation at ingestion; alert on schema deviation |

---

## 5. Definition of Done

A monitor is considered **Done** when:

- [ ] Conceptual, Logical, and Physical data models reviewed and approved
- [ ] SMX documented and signed off by data architect
- [ ] ETL pipeline deployed to production environment
- [ ] Data quality validation rules active and passing
- [ ] Power BI dashboard signed off by client insight team
- [ ] SIT completed with zero critical defects
- [ ] UAT completed and signed off by client
- [ ] Documentation updated in Confluence / repository
