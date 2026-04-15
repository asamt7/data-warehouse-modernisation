# Business Requirements Document — Data Warehouse Modernisation

> **Status:** Approved  
> **Version:** 1.0  
> **SOW Reference:** Anonymised  
> **Prepared by:** Business Analyst (Portfolio Case Study — Anonymised)

---

## 1. Executive Summary

A leading trade association for major retailers required a fundamental transformation of its data and insight infrastructure. The organisation managed multiple monthly data monitors — covering retail sales, footfall, pricing, and economic indicators — entirely through Excel-based workflows. This document captures the business requirements that drove the Data Warehouse modernisation programme.

---

## 2. Current State (AS-IS)

### 2.1 Data Management

- All monitor data received via email from third-party providers
- Processed, analysed, and stored in separate Excel master files per monitor
- Python and R scripts developed by individual team members to expedite data imports
- Final reports produced by updating PowerPoint and Word templates
- All files stored on a shared cloud drive with no access controls or version history enforcement

### 2.2 Key Limitations

| Pain Point | Impact |
|---|---|
| Fragmented data repositories | Cross-monitor analysis impossible without manual effort |
| Data integrity risk | Data can be modified or deleted with no change control |
| Rigid Excel structures | Any structural change risks breaking existing formulas |
| Inconsistent presentation | Brand colours, fonts, chart styles maintained manually per file |
| No data model | "Flat" reporting only — no ability to explore data relationships |
| Scalability ceiling | Cannot grow the insight offer without proportional headcount growth |
| No dedicated IT function | Dependent on external consultants for any technical changes |

---

## 3. Future State (TO-BE)

### 3.1 Target Architecture

A centralised, cloud-based Azure Data Warehouse with:

- A unified data lake (Raw → Curated → Semantic layers)
- Automated ETL pipelines replacing manual Excel ingestion
- Power BI dashboards for self-service reporting
- Formal data governance, quality controls, and audit logging

### 3.2 Business Capabilities Enabled

| Capability | Description |
|---|---|
| Cross-monitor analysis | Single data model enabling relationship-based insight |
| Custom reporting | Stakeholders can slice data by geography, sector, time period |
| Proprietary indices | Infrastructure supports future development of branded benchmarks |
| Member data access | Structured data can be shared with members via controlled access |
| Audit trail | Full change history and data lineage captured automatically |

---

## 4. Stakeholder Requirements

### 4.1 Stakeholder Map

| Stakeholder | Role | Key Requirement |
|---|---|---|
| Director of Insight | Executive sponsor | Richer, relationship-based insight; reduced manual effort |
| Insight Team | Primary users | Self-service reporting; no disruption to monthly cycle |
| IT / Delivery Team | Technical delivery | Clear data models; well-documented transformation logic |
| Members / Customers | External data consumers | Timely, accurate, customisable insight reports |

### 4.2 Elicitation Methods

- Stakeholder interviews (Director of Insight, Insight Team leads)
- AS-IS process walkthroughs
- Review of existing Excel monitor files and report templates
- Workshop sessions for TO-BE scenario validation

---

## 5. Functional Requirements

### 5.1 Data Ingestion

- The system shall ingest data from all existing third-party monitor providers
- Ingestion shall replace manual email-and-Excel workflows
- The system shall support structured file ingestion (CSV, Excel) and API-based ingestion (Phase 2)

### 5.2 Data Warehouse Layers

| Layer | Purpose |
|---|---|
| **Raw** | Data ingested as-is; no transformation; full history preserved |
| **Curated** | Cleaned, validated, and transformed data; referential integrity enforced |
| **Semantic** | Business-ready layer; KPIs calculated; optimised for Power BI consumption |

### 5.3 Data Modelling

For each monitor, the following shall be produced and maintained:
- Conceptual Data Model
- Logical Data Model
- Physical Data Model (with column data types and referential integrity)
- Source-to-Target Mapping (SMX) documenting transformation logic

### 5.4 ETL Pipeline Requirements

- Pipelines shall be automated and schedulable
- Change Data Capture (CDC) shall be implemented to track source data changes
- Naming conventions shall be standardised across all pipelines and tables
- Audit columns shall be included on all curated-layer tables (created_date, modified_date, source_system)
- Job orchestration shall support dependency management across monitors

### 5.5 Reporting & Dashboards

- Power BI dashboards shall be delivered for each monitor
- Dashboards shall match KPI definitions agreed with the insight team
- Visual design shall adhere to the organisation's brand guidelines
- Dashboards shall enable filtering by date range, geography, and monitor type

### 5.6 Data Quality & Validation

- Automated validation rules shall be applied at ingestion
- Table-level tests shall be defined and documented per monitor
- Data quality failures shall trigger alerts to the insight team

---

## 6. Non-Functional Requirements

| Category | Requirement |
|---|---|
| Availability | System operational 24/7; scheduled maintenance windows only |
| Performance | Dashboard load time < 3 seconds for standard queries |
| Data Freshness | Data updated within 4 hours of source file receipt |
| Security | Role-based access control; data encrypted at rest and in transit |
| Auditability | Full data lineage from raw source to Power BI visual |
| Scalability | Architecture supports addition of new monitors without re-architecture |

---

## 7. Out of Scope

- Real-time data streaming (Phase 2)
- Direct API integration with third-party data providers (Phase 2)
- Member-facing self-service data portal (Phase 3)
- Migration of historical data beyond 3 years

---

## 8. Acceptance Criteria

The solution shall be accepted when:

1. All 7 monitors are operational in the Data Warehouse
2. Power BI dashboards are signed off by the insight team for each monitor
3. Monthly reporting cycle can be completed without manual Excel intervention
4. UAT is completed with zero critical defects outstanding
5. Knowledge transfer sessions completed with the client insight team
