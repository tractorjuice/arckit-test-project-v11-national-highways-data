# Wardley Map: National Highways Data Architecture - Current State & Procurement Strategy

> **Template Status**: Experimental | **Version**: 0.11.2 | **Command**: `/arckit.wardley`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-WARD-v1.1 |
| **Document Type** | Wardley Map |
| **Project** | National Highways Data Architecture Modernization (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.1 |
| **Created Date** | 2025-11-13 |
| **Last Modified** | 2026-01-26 |
| **Review Cycle** | Quarterly |
| **Next Review Date** | 2026-04-26 |
| **Owner** | Chief Data & Technology Officer, National Highways |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | Programme Team, Architecture Review Board, Procurement Team |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2025-11-13 | ArcKit AI | Initial creation from `/arckit.wardley` command | PENDING | PENDING |
| 1.1 | 2026-01-26 | ArcKit AI | Updated to v0.11.2 template format | PENDING | PENDING |

---

## Executive Summary

This Wardley Map visualizes the National Highways Data Architecture Modernization initiative, mapping 35 components across the value chain from user needs (driver journey planning) down to infrastructure (cloud hosting, databases). The map reveals critical build vs buy decisions and procurement strategy for the £45M investment.

**Key Strategic Insights**:

1. **Build Custom** (8 components): Data mesh implementation, real-time incident management, ANPR journey time calculation provide competitive advantage
2. **Buy Product** (12 components): Navigation API integration, monitoring tools, authentication services from mature markets
3. **Use Commodity** (15 components): Cloud hosting (Azure UK), managed databases, event streaming leverage utility services

**Procurement Route**:
- **G-Cloud Framework**: £28M (62%) - Cloud services (Azure), managed databases, monitoring platforms
- **Build In-House**: £12M (27%) - Custom data mesh, incident management, GDPR-compliant ANPR processing
- **DOS Outcomes**: £5M (11%) - Discovery and implementation support for data mesh transformation

**High-Risk Areas**:
- **Legacy Oracle Migration** (Custom, 0.42) - 7 systems, 500TB data, 6-month parallel running risk
- **ANPR Privacy Controls** (Custom, 0.38) - 24-hour anonymization critical for UK GDPR compliance
- **Real-Time Event Processing** (Custom, 0.45) - 5TB/day throughput, <2 sec latency requirement

**Rapid Evolution Predictions**:
- **Event Streaming** moving Product → Commodity (0.72 → 0.88 in 18 months) - consolidation around Kafka
- **API Management** moving Custom → Product (0.48 → 0.68 in 12 months) - cloud-native API gateways maturing
- **Geospatial Databases** stable Product (0.78) - PostGIS industry standard, minimal movement expected

---

## Map Visualization

**View this map**: Paste the map code below into [https://create.wardleymaps.ai](https://create.wardleymaps.ai)

```wardley
title National Highways Data Architecture - Current State & Procurement Strategy

anchor Driver Journey Planning [0.95, 0.22]

annotation 1 [0.40, 0.35] BUILD CUSTOM - Competitive Advantage
annotation 2 [0.72, 0.68] BUY PRODUCT - Mature Market
annotation 3 [0.90, 0.25] USE COMMODITY - Cloud/Utility
note G-Cloud procurement for cloud services (62% of budget) [0.88, 0.15]
note Build in-house for data mesh and incident management (27% budget) [0.42, 0.55]

component Driver Journey Planning [0.95, 0.22]
component Third-Party Navigation Apps [0.92, 0.68]
component Regional Control Room Operations [0.90, 0.35]
component Emergency Services Response [0.88, 0.48]
component Public Open Data Access [0.86, 0.75]

component Real-Time Journey Time API [0.82, 0.38]
component Incident Management Workflow [0.78, 0.42]
component Traffic Flow Visualization [0.75, 0.52]
component Roadworks Scheduling [0.72, 0.58]
component CCTV Monitoring [0.70, 0.45]

component Data Mesh Implementation [0.65, 0.38]
component Real-Time Event Processing [0.62, 0.45]
component API Management Gateway [0.60, 0.68]
component ANPR Journey Time Calculation [0.58, 0.35]
component Incident Detection AI [0.55, 0.28]

component Traffic Domain Data Product [0.52, 0.42]
component Incidents Domain Data Product [0.50, 0.45]
component Roadworks Domain Data Product [0.48, 0.52]
component Assets Domain Data Product [0.46, 0.55]
component Weather Domain Data Product [0.44, 0.58]

component Event Streaming Platform [0.58, 0.72]
component Geospatial Database PostGIS [0.55, 0.78]
component Time-Series Database [0.52, 0.75]
component API Authentication OAuth2 [0.50, 0.68]
component Monitoring Observability Platform [0.48, 0.72]

component Legacy Oracle Migration [0.45, 0.42]
component GDPR Anonymization Engine [0.42, 0.38]
component Data Quality Framework [0.40, 0.45]
component Schema Registry [0.38, 0.65]

component Cloud Hosting Azure UK [0.30, 0.95]
component Managed Database Services [0.28, 0.92]
component Object Storage Azure Blob [0.26, 0.95]
component Container Orchestration Kubernetes [0.24, 0.88]
component Secret Management Azure KeyVault [0.22, 0.90]
component CDN Edge Caching [0.20, 0.92]

Driver Journey Planning -> Real-Time Journey Time API
Driver Journey Planning -> Third-Party Navigation Apps
Third-Party Navigation Apps -> API Management Gateway
Regional Control Room Operations -> Incident Management Workflow
Regional Control Room Operations -> CCTV Monitoring
Regional Control Room Operations -> Traffic Flow Visualization
Emergency Services Response -> Incident Management Workflow
Public Open Data Access -> API Management Gateway

Real-Time Journey Time API -> ANPR Journey Time Calculation
Real-Time Journey Time API -> Traffic Domain Data Product
Incident Management Workflow -> Incidents Domain Data Product
Incident Management Workflow -> Incident Detection AI
Traffic Flow Visualization -> Traffic Domain Data Product
Roadworks Scheduling -> Roadworks Domain Data Product
CCTV Monitoring -> Object Storage Azure Blob

Data Mesh Implementation -> Traffic Domain Data Product
Data Mesh Implementation -> Incidents Domain Data Product
Data Mesh Implementation -> Roadworks Domain Data Product
Data Mesh Implementation -> Assets Domain Data Product
Data Mesh Implementation -> Weather Domain Data Product

Real-Time Event Processing -> Event Streaming Platform
ANPR Journey Time Calculation -> GDPR Anonymization Engine
ANPR Journey Time Calculation -> Geospatial Database PostGIS
Incident Detection AI -> Time-Series Database

Traffic Domain Data Product -> Real-Time Event Processing
Incidents Domain Data Product -> Real-Time Event Processing
Roadworks Domain Data Product -> Schema Registry
Assets Domain Data Product -> Geospatial Database PostGIS
Weather Domain Data Product -> Time-Series Database

API Management Gateway -> API Authentication OAuth2
API Management Gateway -> CDN Edge Caching
Event Streaming Platform -> Cloud Hosting Azure UK
Geospatial Database PostGIS -> Managed Database Services
Time-Series Database -> Managed Database Services
Monitoring Observability Platform -> Cloud Hosting Azure UK

Legacy Oracle Migration -> Managed Database Services
GDPR Anonymization Engine -> Secret Management Azure KeyVault
Data Quality Framework -> Monitoring Observability Platform
Schema Registry -> Container Orchestration Kubernetes

Managed Database Services -> Cloud Hosting Azure UK
Object Storage Azure Blob -> Cloud Hosting Azure UK
Container Orchestration Kubernetes -> Cloud Hosting Azure UK
Secret Management Azure KeyVault -> Cloud Hosting Azure UK

evolve Event Streaming Platform 0.88 label Commoditizing 18m
evolve API Management Gateway 0.78 label Cloud-native gateways mature
evolve Incident Detection AI 0.48 label AI ops maturing

style wardley
```

---

## Evolution Stages Reference

| Stage | Maturity | Characteristics | Strategic Actions |
|-------|----------|-----------------|-------------------|
| **Genesis** (0.00 - 0.25) | Novel, uncertain, rapidly changing | - Unique and rare<br>- Poorly understood<br>- Rapid change<br>- High uncertainty<br>- Future value uncertain | - R&D focus<br>- Accept failure<br>- Explore and experiment<br>- Build in-house if strategic |
| **Custom** (0.25 - 0.50) | Emerging, growing understanding | - Bespoke solutions<br>- Artisanal development<br>- Competitive advantage<br>- Requires significant skill<br>- Still evolving rapidly | - Invest in differentiation<br>- Build custom if competitive advantage<br>- Patent/protect IP<br>- Hire specialists |
| **Product** (0.50 - 0.75) | Maturing, good/rental services | - Products with feature differentiation<br>- Rental models<br>- Slower evolution<br>- Defined practices<br>- Training available | - Buy products<br>- Compare features<br>- Use market leaders<br>- Standardize where possible |
| **Commodity** (0.75 - 1.00) | Industrialized, utility | - Standardized<br>- Volume operations<br>- Cost of deviation high<br>- Utility services<br>- Highly evolved | - Use commodity/utility<br>- Cloud services<br>- Outsource/procure<br>- Focus on cost efficiency |

---

## Component Inventory

### User Needs (Top of Map - High Visibility)

| Component | Visibility | Evolution | Stage | Description | Strategic Notes |
|-----------|-----------|-----------|-------|-------------|-----------------|
| Driver Journey Planning | 0.95 | 0.22 | Genesis | Drivers need accurate, real-time journey planning with alternative routes | Novel user need - competitive differentiator for National Highways |
| Third-Party Navigation Apps | 0.92 | 0.68 | Product | Google Maps, Waze, TomTom integration consuming NH data | Mature product market, integrate via open API |
| Regional Control Room Operations | 0.90 | 0.35 | Custom | Traffic officers managing incidents across 7 regional control rooms | Custom operational workflow, domain-specific |
| Emergency Services Response | 0.88 | 0.48 | Custom | Police, ambulance, fire services responding to incidents | Bespoke integration with CAD systems |
| Public Open Data Access | 0.86 | 0.75 | Product | Open Government License data publication for developers | Standard practice, OpenAPI 3.x specification |

### Supporting Capabilities (Mid-Level Visibility)

| Component | Visibility | Evolution | Stage | Description | Strategic Notes |
|-----------|-----------|-----------|-------|-------------|-----------------|
| Real-Time Journey Time API | 0.82 | 0.38 | Custom | Sub-500ms API providing current journey times with ANPR data | Custom competitive advantage - real-time processing |
| Incident Management Workflow | 0.78 | 0.42 | Custom | Automated incident lifecycle from detection to clearance | Domain-specific workflow, competitive ops efficiency |
| Traffic Flow Visualization | 0.75 | 0.52 | Product | Live traffic map for control rooms with congestion heatmaps | Product market emerging (Esri, Mapbox) |
| Roadworks Scheduling | 0.72 | 0.58 | Product | Roadworks calendar with conflict detection | Commercial products available (Confirm, Symology) |
| CCTV Monitoring | 0.70 | 0.45 | Custom | 3,500 CCTV cameras with AI incident detection | Custom integration, privacy controls |
| Data Mesh Implementation | 0.65 | 0.38 | Custom | 5-domain federated data architecture | Custom architecture pattern, competitive advantage |
| Real-Time Event Processing | 0.62 | 0.45 | Custom | 5TB/day sensor data ingestion with <2 sec latency | Custom performance requirements |
| API Management Gateway | 0.60 | 0.68 | Product | API gateway for public/partner APIs with rate limiting | Product market (Azure API Management, Kong, Apigee) |
| ANPR Journey Time Calculation | 0.58 | 0.35 | Custom | Vehicle plate matching with 24h GDPR anonymization | Custom privacy-preserving algorithm |
| Incident Detection AI | 0.55 | 0.28 | Genesis | AI/ML detecting incidents from CCTV and sensor anomalies | Novel AI application, R&D phase |

### Data Products (Data Mesh Domains)

| Component | Visibility | Evolution | Stage | Description | Strategic Notes |
|-----------|-----------|-----------|-------|-------------|-----------------|
| Traffic Domain Data Product | 0.52 | 0.42 | Custom | Real-time traffic flow with SLA (99.9% avail, <2 min freshness) | Custom data mesh product, competitive advantage |
| Incidents Domain Data Product | 0.50 | 0.45 | Custom | Incident records with lifecycle tracking, published API | Custom workflow integration |
| Roadworks Domain Data Product | 0.48 | 0.52 | Product | Roadworks schedule with DATEX II compliance | Emerging product patterns, European standard |
| Assets Domain Data Product | 0.46 | 0.55 | Product | Road network topology (GeoJSON), bridge/tunnel inventory | Product patterns (Ordnance Survey integration) |
| Weather Domain Data Product | 0.44 | 0.58 | Product | Met Office Datapoint integration, roadside weather stations | Established product (Met Office API) |

### Technical Components (Lower Visibility)

| Component | Visibility | Evolution | Stage | Description | Strategic Notes |
|-----------|-----------|-----------|-------|-------------|-----------------|
| Event Streaming Platform | 0.58 | 0.72 | Product | Kafka/Azure Event Hubs for real-time data pipelines | Product market consolidating around Kafka |
| Geospatial Database PostGIS | 0.55 | 0.78 | Product/Commodity | PostgreSQL with PostGIS for road network geospatial queries | Industry standard, commodity-like stability |
| Time-Series Database | 0.52 | 0.75 | Product | Azure Data Explorer for 500M sensor readings/day | Product market (ADX, InfluxDB, TimescaleDB) |
| API Authentication OAuth2 | 0.50 | 0.68 | Product | OAuth 2.0 / OpenID Connect for API security | Standard protocol, product implementations |
| Monitoring Observability Platform | 0.48 | 0.72 | Product | Azure Monitor, Prometheus, Grafana for telemetry | Mature product market |
| Legacy Oracle Migration | 0.45 | 0.42 | Custom | 7 Oracle databases (500TB) migration to cloud | Custom ETL, one-time project |
| GDPR Anonymization Engine | 0.42 | 0.38 | Custom | SHA-256 hashing with 24h automated deletion for ANPR | Custom privacy engineering |
| Data Quality Framework | 0.40 | 0.45 | Custom | Automated validation (99% completeness, <2 min freshness) | Custom quality rules per domain |
| Schema Registry | 0.38 | 0.65 | Product | Confluent Schema Registry for event schema versioning | Product market (Confluent, AWS Glue) |

### Infrastructure Components (Low Visibility)

| Component | Visibility | Evolution | Stage | Description | Strategic Notes |
|-----------|-----------|-----------|-------|-------------|-----------------|
| Cloud Hosting Azure UK | 0.30 | 0.95 | Commodity | Azure UK South + UK West (data residency) | Commodity utility, G-Cloud procurement |
| Managed Database Services | 0.28 | 0.92 | Commodity | Azure SQL, PostgreSQL managed services | Commodity cloud services |
| Object Storage Azure Blob | 0.26 | 0.95 | Commodity | CCTV footage storage (35TB/day) | Commodity object storage |
| Container Orchestration Kubernetes | 0.24 | 0.88 | Commodity | Azure Kubernetes Service (AKS) for microservices | Commodity orchestration |
| Secret Management Azure KeyVault | 0.22 | 0.90 | Commodity | Azure Key Vault for secrets, certificates | Commodity secrets management |
| CDN Edge Caching | 0.20 | 0.92 | Commodity | Azure CDN for API response caching | Commodity CDN |

---

## Evolution Analysis

### Components in Genesis (0.00 - 0.25)

**Novel, unproven, high uncertainty**

| Component | Current Position | Risk | Opportunity | Action |
|-----------|------------------|------|-------------|--------|
| Driver Journey Planning | 0.22 | **HIGH** - User need not yet solved well by current systems | **HIGH** - Differentiate NH from navigation apps with authoritative data | Build custom real-time journey planning capability with ANPR data |
| Incident Detection AI | 0.28 | **HIGH** - AI/ML accuracy unproven, 85% detection rate target | **MEDIUM** - Reduce incident response time 30% through early detection | Pilot AI incident detection with CCTV analytics, accept 15% false positives initially |

**Strategic Recommendations**:
- [x] Accept high failure rate for Incident Detection AI (pilot with low-risk routes first)
- [x] Invest in R&D for journey planning algorithms
- [x] Build in-house Driver Journey Planning (strategic differentiator)
- [ ] Avoid outsourcing AI incident detection core innovation (retain IP)
- [x] Plan for rapid iteration and algorithm refinement

### Components in Custom (0.25 - 0.50)

**Emerging practices, competitive advantage**

| Component | Current Position | Competitive Advantage? | Action |
|-----------|------------------|------------------------|--------|
| Regional Control Room Operations | 0.35 | **YES** - Unified dashboard replaces 7 legacy systems, 30% efficiency gain | **BUILD** - Custom workflow matching NH operational processes |
| ANPR Journey Time Calculation | 0.35 | **YES** - Privacy-preserving 24h anonymization competitive advantage vs Google | **BUILD** - Custom GDPR-compliant journey time algorithm |
| Data Mesh Implementation | 0.38 | **YES** - Federated governance enables domain autonomy vs centralized data warehouse | **BUILD** - Custom data mesh architecture tailored to NH domains |
| Real-Time Journey Time API | 0.38 | **YES** - <500ms p95 latency competitive vs navigation apps | **BUILD** - Custom API optimized for real-time queries |
| GDPR Anonymization Engine | 0.38 | **YES** - Automated 24h deletion ensures UK GDPR compliance | **BUILD** - Custom privacy engineering for ANPR |
| Incident Management Workflow | 0.42 | **YES** - Automated notifications <10 sec to emergency services | **BUILD** - Custom incident lifecycle automation |
| Traffic Domain Data Product | 0.42 | **YES** - 99.9% SLA with <2 min freshness differentiates from competitors | **BUILD** - Custom data product with domain ownership |
| Legacy Oracle Migration | 0.42 | **NO** - Technical debt cleanup, not competitive advantage | **BUILD** (one-time project) - Custom ETL for 500TB migration, then decommission |
| Data Quality Framework | 0.45 | **PARTIAL** - 99% completeness enables trust, but not unique capability | **BUILD** - Custom quality rules per domain, leverage open source frameworks |
| Real-Time Event Processing | 0.45 | **YES** - 5TB/day with <2 sec latency enables real-time services | **BUILD** - Custom streaming architecture for scale |
| Incidents Domain Data Product | 0.45 | **YES** - Incident lifecycle tracking with audit trail | **BUILD** - Custom data product for operational domain |
| CCTV Monitoring | 0.45 | **PARTIAL** - 3,500 cameras with AI detection differentiates from manual review | **BUILD** integration - Custom privacy controls, buy AI detection product |

**Strategic Recommendations**:
- [x] Build custom for all data mesh components (competitive advantage)
- [x] Build ANPR journey time calculation (privacy-preserving differentiator)
- [x] Build real-time event processing (performance requirement unmet by products)
- [x] Invest in specialist skills: Data mesh architects, privacy engineers, real-time engineers
- [x] Monitor evolution velocity - Event Processing may move to Product in 18 months
- [x] Critical Build vs Buy decision point - commit to build for competitive advantage components

### Components in Product (0.50 - 0.75)

**Maturing market, feature differentiation**

| Component | Current Position | Market Options | Action |
|-----------|------------------|----------------|--------|
| Traffic Flow Visualization | 0.52 | Esri ArcGIS, Mapbox, HERE Maps | **BUY** - Esri ArcGIS for geospatial visualization (existing NH license) |
| Roadworks Domain Data Product | 0.52 | Roadworks management products (Confirm, Symology) | **BUILD** data product API - Buy roadworks planning tool integration |
| Assets Domain Data Product | 0.55 | Ordnance Survey data, asset management products | **BUILD** data product - Integrate Ordnance Survey (authoritative UK maps) |
| Roadworks Scheduling | 0.58 | Confirm, Symology, Elgin roadworks management | **BUY** - RFP for roadworks scheduling tool with API integration |
| Weather Domain Data Product | 0.58 | Met Office Datapoint API (authoritative UK weather) | **BUY** - Met Office Datapoint subscription (£20k/year) |
| Schema Registry | 0.65 | Confluent Schema Registry, AWS Glue Schema Registry | **BUY** - Confluent Schema Registry (£50k/year) or open source |
| API Authentication OAuth2 | 0.68 | Auth0, Okta, Azure AD B2C | **BUY** - Azure AD B2C (£40k/year, integrated with Azure) |
| API Management Gateway | 0.68 | Azure API Management, Kong, Apigee, AWS API Gateway | **BUY** - Azure API Management (£60k/year, G-Cloud) |
| Third-Party Navigation Apps | 0.68 | Google Maps, Waze, TomTom, HERE | **INTEGRATE** - Open API for third-party consumption (no direct cost) |
| Event Streaming Platform | 0.72 | Apache Kafka, Azure Event Hubs, AWS Kinesis, Confluent Cloud | **BUY** - Azure Event Hubs (£120k/year, G-Cloud) or Confluent Cloud |
| Monitoring Observability Platform | 0.72 | Azure Monitor, Datadog, New Relic, Prometheus/Grafana | **BUY** - Azure Monitor (£80k/year) + Grafana open source |
| Public Open Data Access | 0.75 | OpenAPI 3.x standard, developer portals (SwaggerHub, ReadMe) | **BUY** - Azure API Management developer portal (included) |
| Time-Series Database | 0.75 | Azure Data Explorer, InfluxDB Cloud, TimescaleDB Cloud | **BUY** - Azure Data Explorer (£180k/year, G-Cloud) |
| Geospatial Database PostGIS | 0.78 | PostgreSQL + PostGIS (open source), Azure Database for PostgreSQL | **BUY** - Azure Database for PostgreSQL with PostGIS (£140k/year) |

**Strategic Recommendations**:
- [x] Procure from market leaders via G-Cloud framework
- [x] Compare feature sets: Azure-native vs best-of-breed (e.g., Confluent vs Azure Event Hubs)
- [x] Standardize on Azure services where performance acceptable (cost efficiency, integration)
- [x] Avoid custom development for product-stage components (high cost, low value)
- [x] Use RFP process for roadworks scheduling tool (£200k procurement)
- [x] Met Office Datapoint subscription (authoritative weather data, no alternative)

### Components in Commodity (0.75 - 1.00)

**Industrialized, utility services**

| Component | Current Position | Commodity Provider | Action |
|-----------|------------------|-------------------|--------|
| Container Orchestration Kubernetes | 0.88 | Azure Kubernetes Service (AKS), AWS EKS, Google GKE | **USE COMMODITY** - Azure AKS (£100k/year, G-Cloud) |
| Secret Management Azure KeyVault | 0.90 | Azure Key Vault, AWS Secrets Manager, HashiCorp Vault Cloud | **USE COMMODITY** - Azure Key Vault (£10k/year, G-Cloud) |
| CDN Edge Caching | 0.92 | Azure CDN, Cloudflare, AWS CloudFront, Fastly | **USE COMMODITY** - Azure CDN (£40k/year, G-Cloud) |
| Managed Database Services | 0.92 | Azure SQL Database, Azure Database for PostgreSQL, AWS RDS | **USE COMMODITY** - Azure managed databases (£300k/year, G-Cloud) |
| Cloud Hosting Azure UK | 0.95 | Azure UK South + UK West, AWS London, Google Cloud UK | **USE COMMODITY** - Azure UK regions (£800k/year, G-Cloud) |
| Object Storage Azure Blob | 0.95 | Azure Blob Storage, AWS S3, Google Cloud Storage | **USE COMMODITY** - Azure Blob Storage (£200k/year, G-Cloud) |

**Strategic Recommendations**:
- [x] Use commodity/utility services exclusively (never build custom infrastructure)
- [x] Focus on cost efficiency via Azure reserved instances (60% discount vs pay-as-you-go)
- [x] Avoid custom infrastructure development (highest cost-to-value ratio)
- [x] Use G-Cloud Digital Marketplace for all cloud services procurement
- [x] Automate provisioning via Infrastructure as Code (Terraform/Bicep)
- [x] UK data residency: Azure UK South (primary) + UK West (DR) only

---

## Build vs Buy Analysis

### Build (In-House Development)

**Candidates for Building** (8 components, £12M investment):

| Component | Evolution Stage | Rationale | Risk | Investment |
|-----------|----------------|-----------|------|------------|
| Driver Journey Planning | Genesis (0.22) | Strategic differentiator - real-time journey planning with authoritative NH data | **HIGH** - Novel capability, user adoption uncertain | £1.5M (R&D, algorithm development) |
| Incident Detection AI | Genesis (0.28) | Early incident detection reduces response time 30%, competitive advantage | **HIGH** - AI accuracy unproven (85% target), false positives | £2.0M (AI/ML specialists, training data) |
| ANPR Journey Time Calculation | Custom (0.35) | Privacy-preserving 24h anonymization differentiates from Google/Waze | **MEDIUM** - GDPR compliance critical, ICO approval required | £1.2M (Privacy engineers, DPIA process) |
| Regional Control Room Operations | Custom (0.35) | Unified dashboard replaces 7 legacy systems, 30% efficiency gain | **MEDIUM** - Change management, user training required | £1.8M (Custom UI/UX, workflow automation) |
| Data Mesh Implementation | Custom (0.38) | Federated governance enables domain autonomy, competitive ops model | **MEDIUM** - Organizational change, new governance model | £1.5M (Data mesh architects, platform team) |
| Real-Time Journey Time API | Custom (0.38) | <500ms p95 latency competitive vs navigation apps, real-time differentiator | **MEDIUM** - Performance optimization, scale testing | £1.0M (API engineers, load testing) |
| GDPR Anonymization Engine | Custom (0.38) | Automated 24h deletion ensures UK GDPR compliance for ANPR | **LOW** - Well-understood hashing, automated deletion | £0.5M (Privacy engineering, automation) |
| Incident Management Workflow | Custom (0.42) | Automated notifications <10 sec to emergency services, ops efficiency | **LOW** - Event-driven patterns established | £0.8M (Workflow automation, CAD integration) |
| **TOTAL BUILD INVESTMENT** | | **Competitive advantage, domain-specific** | | **£10.3M (23% of £45M)** |

**Build Criteria Met**:
- ✅ Genesis/Custom stage (< 0.50 evolution) - No mature market solutions
- ✅ Provides competitive advantage - Real-time journey planning, privacy-preserving ANPR, operational efficiency
- ✅ Core to business differentiator - Authoritative road network data, 99.95% CNI availability
- ✅ No suitable market alternatives - Privacy-preserving ANPR, data mesh for 5 domains
- ✅ Skills available or acquirable - Data mesh architects, privacy engineers, AI/ML specialists
- ✅ Strategic IP ownership important - Journey planning algorithms, ANPR anonymization

**Build Risks**:
- **Skills Gap**: Data mesh architects (3 FTE needed), privacy engineers (2 FTE), AI/ML specialists (5 FTE)
- **Delivery Risk**: Custom development delays could push 12-month API launch to 18 months
- **Quality Risk**: 99% data quality SLA requires sophisticated validation framework
- **Mitigation**: Hire specialists (£2M recruitment), agile delivery with MVPs, automated testing (80% coverage)

### Buy (Procurement from Market)

**Candidates for Buying** (12 components, £28M investment over 3 years):

| Component | Evolution Stage | Market Options | Rationale | Procurement Route |
|-----------|----------------|----------------|-----------|-------------------|
| Traffic Flow Visualization | Product (0.52) | Esri ArcGIS £120k/yr, Mapbox £60k/yr | Mature geospatial visualization, existing NH Esri license | Direct award (existing supplier) |
| Roadworks Scheduling | Product (0.58) | Confirm £150k, Symology £180k, Elgin £200k | Commercial roadworks management products available | RFP via G-Cloud (£200k one-time + £40k/yr) |
| Weather Domain Integration | Product (0.58) | Met Office Datapoint API £20k/yr | Authoritative UK weather data, no alternative | Direct subscription |
| Schema Registry | Product (0.65) | Confluent £50k/yr, AWS Glue £30k/yr, OSS free | Event schema versioning, mature products | G-Cloud (Confluent Cloud) or open source |
| API Authentication OAuth2 | Product (0.68) | Auth0 £60k/yr, Azure AD B2C £40k/yr, Okta £80k/yr | Standard OAuth 2.0, integrated solutions | G-Cloud (Azure AD B2C - integrated) |
| API Management Gateway | Product (0.68) | Azure API Management £60k/yr, Kong £50k/yr, Apigee £100k/yr | API gateway for public API, rate limiting | G-Cloud (Azure API Management) |
| Event Streaming Platform | Product (0.72) | Azure Event Hubs £120k/yr, Confluent Cloud £180k/yr, AWS Kinesis £100k/yr | 5TB/day throughput, mature market consolidating around Kafka | G-Cloud (Azure Event Hubs - managed) |
| Monitoring Observability | Product (0.72) | Azure Monitor £80k/yr, Datadog £120k/yr, New Relic £100k/yr | Metrics, logs, traces, mature tooling | G-Cloud (Azure Monitor + Grafana OSS) |
| Time-Series Database | Product (0.75) | Azure Data Explorer £180k/yr, InfluxDB Cloud £100k/yr, TimescaleDB £80k/yr | 500M sensor readings/day, time-series optimized | G-Cloud (Azure Data Explorer) |
| Geospatial Database PostGIS | Product (0.78) | Azure PostgreSQL + PostGIS £140k/yr, AWS RDS £120k/yr | Industry standard for geospatial, PostGIS mature | G-Cloud (Azure Database for PostgreSQL) |
| Container Orchestration K8s | Commodity (0.88) | Azure AKS £100k/yr, AWS EKS £90k/yr, GKE £95k/yr | Kubernetes commodity, managed service | G-Cloud (Azure AKS) |
| Cloud Hosting Azure UK | Commodity (0.95) | Azure UK £800k/yr, AWS London £750k/yr, Google Cloud UK £780k/yr | Commodity cloud, UK data residency required | G-Cloud (Azure UK South + UK West) |
| **TOTAL BUY INVESTMENT** | | | **Mature market, commodity services** | **£27.5M over 3 years (61% of budget)** |

**Buy Criteria Met**:
- ✅ Product/Commodity stage (> 0.50 evolution) - Mature markets with multiple vendors
- ✅ Mature market with multiple vendors - Cloud services, API management, monitoring
- ✅ Not a competitive differentiator - Infrastructure, authentication, monitoring are table stakes
- ✅ Cost of building > cost of buying - £2M to build API gateway vs £60k/year to rent
- ✅ Time to market critical - 12-month API launch requires rapid procurement
- ✅ Skills not available in-house - Kubernetes operations, time-series database optimization

**Procurement Strategy**:
- **G-Cloud Framework** (primary): £25M (91% of buy budget) - Cloud services, SaaS, managed databases
- **Direct Award** (existing suppliers): £1.5M - Esri ArcGIS (existing license), Met Office Datapoint
- **RFP via G-Cloud**: £1M - Roadworks scheduling tool (competitive tender)

**Buy Risks**:
- **Vendor Lock-In**: Azure-native services create switching costs (mitigation: multi-cloud abstraction where practical)
- **Cost Overruns**: Cloud consumption exceeds forecast (mitigation: FinOps cost monitoring, reserved instances)
- **Integration Complexity**: 12 product integrations create complexity (mitigation: API gateway, schema registry)

### Rent/SaaS (Utility Services)

**Candidates for SaaS/Cloud** (7 commodity components, £1.7M/year):

| Component | Evolution Stage | Provider | Rationale | Procurement Route |
|-----------|----------------|----------|-----------|-------------------|
| Cloud Hosting Azure UK | Commodity (0.95) | Microsoft Azure UK South + UK West | UK data residency for OFFICIAL-SENSITIVE, commodity utility | G-Cloud (£800k/year reserved instances) |
| Object Storage Azure Blob | Commodity (0.95) | Microsoft Azure Blob Storage | 35TB/day CCTV footage, commodity object storage | G-Cloud (£200k/year hot+archive tiers) |
| Managed Database Services | Commodity (0.92) | Azure SQL, Azure PostgreSQL | Managed databases reduce operational burden | G-Cloud (£300k/year managed services) |
| CDN Edge Caching | Commodity (0.92) | Azure CDN | API response caching, global edge network | G-Cloud (£40k/year pay-as-you-go) |
| Secret Management | Commodity (0.90) | Azure Key Vault | Secrets, certificates, keys management | G-Cloud (£10k/year) |
| Container Orchestration | Commodity (0.88) | Azure Kubernetes Service (AKS) | Managed Kubernetes, auto-scaling, patching | G-Cloud (£100k/year cluster costs) |
| **TOTAL SAAS/CLOUD** | | Microsoft Azure (G-Cloud) | **Pay-as-you-go utility model** | **£1.45M/year (£4.35M over 3 years)** |

**Rent Criteria Met**:
- ✅ Commodity stage (> 0.75 evolution) - Utility services, standardized functionality
- ✅ Utility services available - Azure, AWS, GCP all offer commodity infrastructure
- ✅ Pay-as-you-go model preferred - Align costs with usage, scale down off-peak
- ✅ Low switching costs - Multi-cloud abstraction (Terraform) enables portability
- ✅ Standardized functionality sufficient - Commodity storage, compute, networking
- ✅ Operational burden not desired - Managed services reduce 2AM patching overhead

**SaaS Optimization**:
- **Reserved Instances**: 60% discount for 3-year Azure reservations (£800k → £320k/year cloud hosting)
- **Tiered Storage**: Hot (31 days) → Archive (legal hold) for CCTV (£200k → £60k/year)
- **Auto-Scaling**: Scale down 50% overnight/weekends (£100k/year savings)
- **FinOps Monitoring**: Monthly cost review, budget alerts at 80% threshold

---

## Inertia and Barriers to Change

**Inertia** = resistance to evolution due to existing practices, skills, or investments

| Component | Current Evolution | Desired Evolution | Inertia Factor | Barrier Description | Mitigation Strategy |
|-----------|-------------------|-------------------|----------------|---------------------|---------------------|
| Legacy Oracle Migration | 0.42 | 0.92 (Managed DB) | **VERY HIGH** | 7 Oracle databases (500TB data), 15-year operational history, 45 FTE Oracle DBA skills | **Phased Migration**: 6-month parallel running, automated data validation, Oracle → PostgreSQL training (£500k), retain 5 Oracle DBAs as PostgreSQL specialists |
| Regional Control Room Operations | 0.35 | 0.55 | **HIGH** | 7 legacy systems, 40 hours operator training (vs 8 hours new system), resistance to change "we've always done it this way" | **Change Management**: Pilot with 1 control room (Greater Manchester), 120 operators upskilled (£200k training), monthly user feedback sessions, phased rollout over 12 months |
| Incident Detection AI | 0.28 | 0.48 | **MEDIUM** | Manual incident reporting trusted (20-year practice), AI 85% accuracy concerns ("will I lose my job?"), operators skeptical | **Pilot Programme**: Low-risk routes first (M25 J15-J16), operators review AI detections (human-in-loop), transparency about 15% false positives, 6-month trust-building |
| Event Streaming Platform | 0.72 | 0.88 | **LOW** | Existing batch ETL processes (nightly), team familiar with SQL (not streaming), learning curve for event-driven architecture | **Upskilling**: Confluent Kafka certification for 10 data engineers (£50k), streaming architecture training, dual-mode (batch + streaming) during transition |
| Data Mesh Implementation | 0.38 | 0.58 | **MEDIUM** | Centralized data warehouse culture (10 years), data ownership unclear ("IT owns data"), domain teams lack data product skills | **Federated Governance**: Data mesh council (monthly), domain data owners appointed (5 FTE), platform team provides paved road (shared infra), 18-month transformation timeline |

**Common Inertia Sources Identified**:
- **Skills inertia**: 45 Oracle DBAs need PostgreSQL retraining (£500k investment)
- **Process inertia**: Manual incident reporting (20-year workflow), operators skeptical of AI automation
- **Vendor lock-in**: Oracle licensing (£8M annual cost), technical dependencies on Oracle-specific features (PL/SQL)
- **Cultural inertia**: Centralized data warehouse mindset vs data mesh federated ownership
- **Capital investment**: £25M sunk cost in 7 legacy systems over 15 years

**De-risking Strategies**:
- [x] Upskilling programs: 120 control room operators (£200k), 45 Oracle DBAs (£500k), 10 Kafka engineers (£50k)
- [x] Pilot projects: Incident Detection AI on low-risk routes, Data Mesh with Traffic Domain first
- [x] Phased migration: 6-month parallel running for Oracle → PostgreSQL (zero data loss validation)
- [x] Vendor negotiations: Oracle license termination after successful PostgreSQL migration (£8M/year savings)
- [x] Change management: Monthly steering committee, quarterly all-hands updates, user feedback loops

---

## Movement and Evolution Predictions

**Evolution Velocity** = how fast components are expected to move along evolution axis

### Next 12 Months

| Component | Current | Predicted (12m) | Velocity | Impact | Action Required |
|-----------|---------|----------------|----------|--------|-----------------|
| API Management Gateway | 0.68 | 0.78 | **FAST** | Cloud-native API gateways (Azure, AWS, Kong) maturing rapidly, feature parity | Monitor market consolidation, Azure API Management likely choice (integrated) |
| Incident Detection AI | 0.28 | 0.38 | **MEDIUM** | AI/ML ops tooling maturing (MLOps), but custom models still artisanal | Continue in-house development, leverage Azure ML for infrastructure |
| Data Mesh Implementation | 0.38 | 0.42 | **SLOW** | Organizational change slower than tech, governance model evolving | Federated governance council quarterly reviews, platform team support |
| Event Streaming Platform | 0.72 | 0.80 | **FAST** | Kafka consolidating market, Azure Event Hubs and Confluent Cloud maturing | Procure now before further commoditization increases lock-in risk |
| Legacy Oracle Migration | 0.42 | 0.92 | **VERY FAST** (one-time jump) | Migration project completes Month 18, Oracle decommissioned | Execute migration (£2M project), achieve £8M/year savings |
| GDPR Anonymization Engine | 0.38 | 0.42 | **SLOW** | Privacy engineering practices maturing slowly, regulations stable | Build custom (competitive advantage), monitor GDPR case law |

### Next 24 Months

| Component | Current | Predicted (24m) | Velocity | Impact | Action Required |
|-----------|---------|----------------|----------|--------|-----------------|
| Event Streaming Platform | 0.72 | 0.88 | **VERY FAST** | Kafka commoditizing, managed services (Azure Event Hubs, Confluent Cloud) becoming utility | Plan cloud migration for self-hosted Kafka (if applicable), use managed services |
| Incident Detection AI | 0.28 | 0.48 | **FAST** | AI ops market maturing, pre-trained models for incident detection emerging | Evaluate build vs buy again at Month 18, market products may catch up |
| Data Mesh Implementation | 0.38 | 0.48 | **MEDIUM** | Data mesh patterns emerging (Thoughtworks, Databricks), products appearing | Continue custom implementation, leverage emerging data mesh platforms (Databricks Unity Catalog) |
| API Management Gateway | 0.68 | 0.82 | **FAST** | API gateways consolidating (Azure, AWS, Kong), commodity features | Lock-in Azure API Management now (integrated), feature set sufficient |
| Traffic Flow Visualization | 0.52 | 0.65 | **MEDIUM** | Geospatial visualization products maturing (Esri, Mapbox), but custom needs remain | Continue Esri ArcGIS (existing license), monitor Mapbox for cost efficiency |
| Geospatial Database PostGIS | 0.78 | 0.82 | **SLOW** | PostGIS stable product, minimal evolution (mature standard) | No action required, PostGIS industry standard for 10+ years |

**Strategic Implications**:
- [x] Event Streaming moving to Commodity (0.72 → 0.88) - Procure managed service NOW before self-hosted becomes legacy
- [x] API Management moving to Commodity (0.68 → 0.82) - Lock-in Azure API Management (integrated, cost-effective)
- [x] Incident Detection AI moving Custom → Product (0.28 → 0.48) - Build now, re-evaluate buy at Month 18
- [x] Data Mesh slow evolution (0.38 → 0.48) - Custom implementation justified, organizational change gating factor
- [x] Legacy Oracle migration velocity (0.42 → 0.92 in 18 months) - Aggressive timeline required for £8M/year savings

**Market Monitoring**:
- **Event Streaming**: Confluent IPO (2021), Azure Event Hubs feature parity, AWS Kinesis competition
- **AI/ML Ops**: Databricks MLOps, Azure ML, AWS SageMaker maturing rapidly
- **Data Mesh**: Thoughtworks advocacy, Databricks Unity Catalog, Starburst emerging
- **API Management**: Kong raised $100M Series D (2022), Azure API Management adding features

---

## UK Government Context

### GOV.UK Services and Platforms

**Mapped GOV.UK Components**:

| GOV.UK Service | Evolution Stage | Current Usage | Rationale for Evolution Position |
|----------------|----------------|---------------|----------------------------------|
| GOV.UK Pay | Commodity (0.90) | **NOT USED** (no payment processing required) | Payment gateway utility, standardized across government |
| GOV.UK Notify | Commodity (0.92) | **SHOULD USE** for incident notifications (SMS/email to drivers) | Notification service utility, free for government, 500M messages/year capacity |
| GOV.UK Design System | Product (0.75) | **SHOULD USE** for public API developer portal | Accessibility (WCAG 2.2 AA) built-in, 100+ government services use it |
| GOV.UK PaaS | Commodity (0.85) | **NOT RECOMMENDED** (Azure UK required for CNI security controls) | Cloud Foundry PaaS, but Azure Kubernetes preferred for NH scale |
| GOV.UK Verify | Product (0.68) | **NOT APPLICABLE** (public API uses API keys, not citizen authentication) | Identity verification for citizen logins, NH doesn't authenticate citizens |

**Reuse Opportunities**:
- [x] GOV.UK Notify for incident SMS alerts to registered drivers (£0 cost, avoid building custom notification service)
- [x] GOV.UK Design System for API developer portal (accessibility compliance, consistent UX with other government services)
- [ ] GOV.UK Pay - Not applicable (no payment processing)
- [ ] GOV.UK PaaS - Not recommended (Azure AKS preferred for CNI security, scale requirements)
- [ ] GOV.UK Verify - Not applicable (API key authentication sufficient)

**Cross-Government Reuse**:
- **Transport for London (TfL)**: Potential data exchange for London traffic data (M25 London Orbital integration)
- **Local Highway Authorities**: 152 councils could reuse NH open data API (avoid duplicate data collection)
- **Department for Transport (DfT)**: Reporting API for ministerial dashboards

### Digital Marketplace Procurement Strategy

**Components to Procure via Digital Marketplace** (£25M via G-Cloud):

| Component | Evolution Stage | Framework | Rationale |
|-----------|----------------|-----------|-----------|
| Cloud Hosting Azure UK | Commodity (0.95) | **G-Cloud** | Azure UK South + UK West regions, OFFICIAL-SENSITIVE approval, £800k/year |
| Managed Database Services | Commodity (0.92) | **G-Cloud** | Azure SQL, PostgreSQL managed services, £300k/year |
| Object Storage Azure Blob | Commodity (0.95) | **G-Cloud** | Azure Blob Storage for CCTV (35TB/day), £200k/year |
| Container Orchestration K8s | Commodity (0.88) | **G-Cloud** | Azure Kubernetes Service (AKS), £100k/year |
| Event Streaming Platform | Product (0.72) | **G-Cloud** | Azure Event Hubs or Confluent Cloud, £120k/year |
| API Management Gateway | Product (0.68) | **G-Cloud** | Azure API Management Premium tier, £60k/year |
| Monitoring Observability | Product (0.72) | **G-Cloud** | Azure Monitor + Datadog (if needed), £80k/year |
| Time-Series Database | Product (0.75) | **G-Cloud** | Azure Data Explorer for sensor data, £180k/year |
| Geospatial Database PostGIS | Product (0.78) | **G-Cloud** | Azure Database for PostgreSQL with PostGIS, £140k/year |
| Roadworks Scheduling Tool | Product (0.58) | **G-Cloud + RFP** | Competitive tender (Confirm, Symology, Elgin), £200k one-time + £40k/year |
| **TOTAL G-CLOUD PROCUREMENT** | | | **£25M over 3 years (56% of £45M budget)** |

**Procurement Recommendations by Evolution Stage**:
- **Genesis/Custom** (< 0.50): **Build in-house** or consider **DOS Outcomes** for discovery + build (£5M for data mesh transformation consulting)
- **Product** (0.50-0.75): **G-Cloud** for commercial off-the-shelf products (API management, monitoring, databases)
- **Commodity** (> 0.75): **G-Cloud** for cloud services (Azure, AWS, GCP commodity infrastructure)

**DOS Outcomes Opportunity** (£5M):
- **Data Mesh Transformation**: DOS Outcomes for discovery phase (£500k) + implementation support (£4.5M over 18 months)
- **Specialists**: Data mesh architects (3 FTE), privacy engineers (2 FTE), AI/ML specialists (5 FTE)
- **Rationale**: Data mesh is Custom (0.38) - no off-the-shelf products, requires strategic consulting and build

### Technology Code of Practice Mapping

| TCoP Point | Related Components | Compliance Status | Gap Analysis |
|------------|-------------------|-------------------|--------------|
| **1. User Needs** | Driver Journey Planning, Third-Party Navigation Apps, Regional Control Room Operations | ✅ **COMPLIANT** | User research conducted with 30+ drivers, control room operators, emergency services |
| **2. Accessibility** | GOV.UK Design System for API developer portal | ✅ **COMPLIANT** | WCAG 2.2 Level AA compliance via GOV.UK Design System |
| **3. Open Source** | Schema Registry (Confluent open source), PostgreSQL + PostGIS | ⚠️ **PARTIAL** | Using open source where appropriate (PostGIS, Kubernetes), but Azure-native services preferred for support |
| **5. Cloud First** | Cloud Hosting Azure UK, Managed Databases, Object Storage | ✅ **COMPLIANT** | 100% cloud-hosted (Azure UK South + UK West), no on-premises for new workloads |
| **6. Security** | GDPR Anonymization Engine, Secret Management, API Authentication OAuth2 | ✅ **COMPLIANT** | NCSC Cloud Security Principles compliance, zero-trust architecture, DPIA for ANPR/CCTV |
| **7. Privacy** | GDPR Anonymization Engine (24h ANPR deletion), CCTV retention (31 days) | ✅ **COMPLIANT** | UK GDPR compliance, automated deletion, DPIA approved by DPO |
| **8. Share/Reuse** | Public Open Data Access (Open Government License), GOV.UK Notify | ✅ **COMPLIANT** | Open Data API for 152 local authorities, reusing GOV.UK Notify |
| **11. Purchasing** | G-Cloud procurement (£25M), DOS Outcomes (£5M) | ✅ **COMPLIANT** | Digital Marketplace procurement strategy, competitive tenders where required |

**TCoP Compliance Summary**: **7/8 points compliant, 1 partial** (Open Source)

**Gap Remediation**:
- **Point 3 (Open Source)**: Document rationale for Azure-native services over open source alternatives (support, integration, managed services reduce operational burden)

---

## Dependencies and Value Chain

**Component Dependencies** (Top-to-Bottom Value Chain):

```
Driver Journey Planning (User Need)
  └─> Real-Time Journey Time API (Capability)
      ├─> ANPR Journey Time Calculation (Custom - BUILD)
      │   ├─> GDPR Anonymization Engine (Custom - BUILD)
      │   │   └─> Secret Management Azure KeyVault (Commodity - G-Cloud)
      │   └─> Geospatial Database PostGIS (Product - G-Cloud)
      │       └─> Managed Database Services (Commodity - G-Cloud)
      │           └─> Cloud Hosting Azure UK (Commodity - G-Cloud)
      └─> Traffic Domain Data Product (Custom - BUILD)
          └─> Real-Time Event Processing (Custom - BUILD)
              └─> Event Streaming Platform (Product - G-Cloud)
                  └─> Cloud Hosting Azure UK (Commodity - G-Cloud)

Regional Control Room Operations (User Need)
  └─> Incident Management Workflow (Capability)
      ├─> Incidents Domain Data Product (Custom - BUILD)
      │   └─> Real-Time Event Processing (Custom - BUILD)
      ├─> Incident Detection AI (Genesis - BUILD)
      │   └─> Time-Series Database (Product - G-Cloud)
      └─> CCTV Monitoring (Custom - BUILD Integration)
          └─> Object Storage Azure Blob (Commodity - G-Cloud)

Third-Party Navigation Apps (User Need)
  └─> API Management Gateway (Product - G-Cloud)
      ├─> API Authentication OAuth2 (Product - G-Cloud)
      ├─> CDN Edge Caching (Commodity - G-Cloud)
      └─> Traffic Domain Data Product (Custom - BUILD)

Data Mesh Implementation (Architecture Pattern)
  ├─> Traffic Domain Data Product (Custom - BUILD)
  ├─> Incidents Domain Data Product (Custom - BUILD)
  ├─> Roadworks Domain Data Product (Product - BUY integration)
  ├─> Assets Domain Data Product (Product - BUY integration)
  └─> Weather Domain Data Product (Product - BUY Met Office API)
```

**Critical Path Analysis**:

**Path to Driver Journey Planning** (12-month delivery commitment):
1. Cloud Hosting Azure UK (Month 1) ✅ G-Cloud procurement
2. Event Streaming Platform (Month 2) ✅ Azure Event Hubs via G-Cloud
3. Real-Time Event Processing (Months 3-6) ⚠️ Custom build - HIGH RISK if delayed
4. ANPR Journey Time Calculation (Months 4-8) ⚠️ Custom privacy engineering - MEDIUM RISK (GDPR compliance)
5. Traffic Domain Data Product (Months 5-9) ⚠️ Custom data mesh - MEDIUM RISK (data quality)
6. Real-Time Journey Time API (Months 7-11) ⚠️ Custom API optimization - MEDIUM RISK (latency targets)
7. **API Launch** (Month 12) 🎯 **CRITICAL MILESTONE** - Minister commitment

**High-Risk Dependencies**:
- **Real-Time Event Processing** (Custom, 0.45) - 5TB/day throughput, <2 sec latency is critical path blocker
- **ANPR Journey Time Calculation** (Custom, 0.35) - GDPR DPIA approval from ICO required before production
- **Legacy Oracle Migration** (Custom, 0.42) - Delays in 500TB migration could block data mesh implementation

**Single Vendor Dependencies**:
- **Microsoft Azure** (Commodity, 0.95) - 100% Azure for cloud hosting, managed services creates lock-in (Mitigation: Terraform multi-cloud abstraction, but pragmatic Azure-native choice for integration)
- **Met Office Datapoint** (Product, 0.58) - Only authoritative UK weather data source, no alternative (Acceptable: Public sector monopoly)
- **Esri ArcGIS** (Product, 0.52) - Existing license for geospatial visualization (Mitigation: Monitor Mapbox as alternative)

**Map to Requirements Traceability**:
- **BR-001 (Real-Time Journey Planning)** → Driver Journey Planning → Real-Time Journey Time API → ANPR Journey Time Calculation
- **FR-001 (Real-Time Data Ingestion)** → Real-Time Event Processing → Event Streaming Platform → Cloud Hosting
- **NFR-SEC-001 (Zero-Trust)** → API Authentication OAuth2 → Secret Management Azure KeyVault
- **DR-003 (ANPR Anonymization)** → GDPR Anonymization Engine → ANPR Journey Time Calculation

---

## Strategic Gameplay

### Gameplay Patterns Identified

**Accelerators** (speed up evolution to commoditize competitors):
- [x] **Event Streaming Platform** (0.72 → 0.88): Contribute to Apache Kafka ecosystem (open source), accelerate commoditization to reduce vendor power (Confluent pricing pressure)
- [x] **API Management Gateway** (0.68 → 0.82): Adopt cloud-native API gateways (Azure, AWS, Kong) to accelerate commodity transition, reduce custom gateway lock-in
- [x] **Open Data API** (0.75): Publish traffic data under Open Government License to commoditize basic traffic data, force competitors (Google, Waze) to differentiate on value-added services

**Tower and Moat** (protect competitive advantage):
- [x] **ANPR Journey Time Calculation** (0.35): Build custom privacy-preserving algorithm, create patent/IP protection to prevent Google/Waze replication (24h anonymization moat)
- [x] **Data Mesh Implementation** (0.38): Build federated data architecture, create organizational switching costs (5 domain data products, governance council)
- [x] **Incident Detection AI** (0.28): Build in-house AI models, retain training data IP, create accuracy moat (85% detection rate competitive advantage)

**Exploiting Inertia** (leverage competitors' resistance to change):
- [x] **Legacy Oracle Competitors** have inertia in Oracle databases (expensive, on-premises) - NH moves faster to PostgreSQL managed services (£8M/year cost advantage, cloud-native agility)
- [x] **Navigation App Providers** (Google, Waze) have inertia in stale crowdsourced data - NH real-time authoritative sensor data (10,000 sensors) provides fresher journey times
- [x] **Local Highway Authorities** (152 councils) have fragmented systems - NH data mesh enables federation without centralized mandate (political advantage, no top-down control)

**Sensing Engines** (early warning systems):
- [x] Monitor **AI/ML ops market** for pre-trained incident detection models (Databricks, Azure ML, AWS SageMaker) - re-evaluate build vs buy at Month 18 if market catches up
- [x] Track **Apache Kafka** evolution velocity - if commoditization accelerates (0.72 → 0.88 in 18 months), migrate from self-hosted to managed service (Azure Event Hubs)
- [x] Watch **Data Mesh market** for emerging products (Databricks Unity Catalog, Starburst) - could reduce custom build investment if mature products appear

**Doctrine Gameplay**:
- **Small Teams**: Data mesh domain teams (5-10 people per domain) vs centralized data warehouse (50-person team) - agility advantage
- **Use Appropriate Tools**: Azure-native where commodity (AKS, Event Hubs), open source where strategic (PostGIS), build custom where competitive advantage (ANPR anonymization)
- **Manage Inertia**: Phased Oracle migration (6-month parallel running) reduces change resistance, upskilling (£750k) converts inertia into momentum

---

## Risk Analysis

### High-Risk Areas

| Risk | Component(s) Affected | Likelihood | Impact | Mitigation |
|------|----------------------|------------|--------|------------|
| **Single vendor dependency (Azure lock-in)** | Cloud Hosting Azure UK, all managed services (15 components) | **HIGH** | **MEDIUM** (£1.5M/year cloud spend, 3-year commitment) | Multi-cloud abstraction via Terraform, but pragmatic Azure-native choice for integration; Reserved instances lock-in £800k/year for 60% discount |
| **Genesis component failure (AI accuracy <85%)** | Incident Detection AI | **MEDIUM** | **HIGH** (30% efficiency gain target missed, £2M investment wasted) | Pilot on low-risk routes (M25 J15-J16), human-in-loop validation, accept 15% false positives initially, re-evaluate buy vs build at Month 18 |
| **Rapid commoditization (Event Streaming)** | Event Streaming Platform (0.72 → 0.88 predicted) | **HIGH** | **LOW** (early procurement locks in Azure Event Hubs at £120k/year, but managed service reduces operational burden) | Procure managed service NOW (Azure Event Hubs via G-Cloud), avoid self-hosted Kafka operational complexity |
| **Skills gap (Data Mesh architects)** | Data Mesh Implementation, all 5 domain data products | **HIGH** | **HIGH** (18-month transformation delay, £1.5M investment risk) | Hire 3 FTE Data Mesh architects (£300k/year), DOS Outcomes consulting (£4.5M), federated governance training for domain owners (£200k) |
| **Regulatory change (UK GDPR tightening)** | GDPR Anonymization Engine, ANPR Journey Time Calculation | **LOW** | **VERY HIGH** (£17.5M ICO fine, project shutdown risk) | DPIA approval from ICO before production, legal counsel review (£50k), automated deletion monitoring with 7-year audit logs, DPO oversight |
| **Legacy migration failure (Oracle 500TB)** | Legacy Oracle Migration, all data products depend on migrated data | **MEDIUM** | **VERY HIGH** (6-month delay blocks API launch, £8M/year savings missed) | 6-month parallel running (dual-write), automated data validation (checksums), rollback capability, 5 Oracle DBAs retained as PostgreSQL specialists |
| **Real-time performance miss (<2 sec latency)** | Real-Time Event Processing, Real-Time Journey Time API | **MEDIUM** | **HIGH** (API SLA breach, user abandonment) | Load testing at 10x capacity (50,000 req/sec), CDN edge caching, query optimization, time-series database (Azure Data Explorer) for sensor data |

### Opportunities

| Opportunity | Component(s) | Potential Value | Investment Required | Action Plan |
|-------------|--------------|-----------------|---------------------|-------------|
| **Open Data Ecosystem** | Public Open Data Access, Third-Party Navigation Apps | £50M economic value (20% journey time variability reduction × £1.8B congestion cost) | £500k (API development, developer portal) | Launch open API Month 12, integrate Google Maps/Waze/TomTom, 50M API requests/month target |
| **Local Authority Data Exchange** | 152 councils reuse NH traffic data, avoid duplicate sensor deployment | £10M cost avoidance (152 councils × £65k sensor deployment savings) | £200k (integration support, DATEX II compliance) | Pilot with 5 progressive councils Month 9, offer free API access, federated governance model |
| **Emergency Services Integration** | Emergency Services Response, Incident Management Workflow | 30% incident response time improvement (18 min → 12.6 min), lives saved | £800k (CAD system integration, PSN connectivity) | Integrate ≥3 emergency services (Police, Ambulance, Fire), <10 sec incident alert delivery, 99.99% SLA |
| **ANPR Privacy Differentiation** | ANPR Journey Time Calculation, GDPR Anonymization Engine | Competitive advantage vs Google/Waze (privacy-preserving journey times), public trust | £1.2M (privacy engineering, DPIA process) | 24-hour automated anonymization, transparent privacy notice, ICO DPIA approval, differentiate from surveillance-based tracking |
| **Data Mesh Replication** | Data Mesh Implementation pattern reusable across government | £5M consulting revenue (share data mesh learnings with other departments via GDS) | £500k (documentation, case study, GDS engagement) | Publish data mesh architecture decision records (ADRs), present at GDS cross-government events, offer consulting to DfT/TfL |

---

## Traceability

### Requirements Mapping

| Requirement ID | Related Components | Evolution Stage | Build/Buy Decision |
|----------------|-------------------|-----------------|-------------------|
| **BR-001: Real-Time Journey Planning** | Driver Journey Planning (0.22), Real-Time Journey Time API (0.38), ANPR Journey Time Calculation (0.35) | Genesis/Custom | **BUILD** - Competitive differentiator, privacy-preserving ANPR |
| **BR-002: £15M Cost Savings** | Legacy Oracle Migration (0.42 → 0.92), Cloud Hosting Azure UK (0.95), Managed Database Services (0.92) | Custom → Commodity | **BUILD** migration + **BUY** Azure managed services - £8M Oracle license savings |
| **BR-003: Open Data API** | Public Open Data Access (0.75), API Management Gateway (0.68), Third-Party Navigation Apps (0.68) | Product | **BUY** - Azure API Management (£60k/year, G-Cloud) |
| **BR-004: Operational Continuity** | Regional Control Room Operations (0.35), Incident Management Workflow (0.42), CCTV Monitoring (0.45) | Custom | **BUILD** - Custom unified dashboard, 30% efficiency gain |
| **BR-005: UK GDPR Compliance** | GDPR Anonymization Engine (0.38), ANPR Journey Time Calculation (0.35), Secret Management Azure KeyVault (0.90) | Custom + Commodity | **BUILD** anonymization + **BUY** Key Vault - 24h deletion, DPIA approval |
| **FR-001: Real-Time Data Ingestion** | Real-Time Event Processing (0.45), Event Streaming Platform (0.72), Cloud Hosting Azure UK (0.95) | Custom + Product + Commodity | **BUILD** processing + **BUY** Azure Event Hubs (£120k/year) |
| **FR-002: Public Journey API** | Real-Time Journey Time API (0.38), API Management Gateway (0.68), CDN Edge Caching (0.92) | Custom + Product + Commodity | **BUILD** API + **BUY** Azure API Management + CDN |
| **FR-006: Data Mesh Products** | Data Mesh Implementation (0.38), Traffic/Incidents/Roadworks/Assets/Weather Domain Data Products (0.42-0.58) | Custom + Product | **BUILD** data mesh architecture + **BUY** Met Office API (£20k/year) |
| **NFR-P-001: <500ms p95 Latency** | Real-Time Journey Time API (0.38), CDN Edge Caching (0.92), Time-Series Database (0.75) | Custom + Product + Commodity | **BUILD** API optimization + **BUY** Azure Data Explorer (£180k/year) |
| **NFR-SEC-001: Zero-Trust** | API Authentication OAuth2 (0.68), Secret Management Azure KeyVault (0.90), GDPR Anonymization Engine (0.38) | Product + Commodity + Custom | **BUY** Azure AD B2C (£40k/year) + Key Vault + **BUILD** anonymization |
| **NFR-A-001: 99.95% Availability** | Cloud Hosting Azure UK (0.95), Managed Database Services (0.92), Monitoring Observability Platform (0.72) | Commodity + Product | **BUY** - Azure multi-region (UK South + UK West), managed services, Azure Monitor |
| **INT-004: Met Office Weather** | Weather Domain Data Product (0.58) | Product | **BUY** - Met Office Datapoint API (£20k/year, authoritative UK weather) |
| **DR-003: ANPR Anonymization** | ANPR Journey Time Calculation (0.35), GDPR Anonymization Engine (0.38) | Custom | **BUILD** - Privacy-preserving algorithm, 24h automated deletion, competitive advantage |

**Requirements Coverage**: **100%** - All 12 key requirements mapped to components with build/buy decisions

### Architecture Principles Alignment

| Principle | Related Components | Compliance | Gap Analysis |
|-----------|-------------------|------------|--------------|
| **#1 Real-Time First** | Real-Time Event Processing (0.45), Real-Time Journey Time API (0.38), Event Streaming Platform (0.72) | ✅ **COMPLIANT** | <2 sec sensor-to-API latency, <500ms p95 API response, streaming architecture |
| **#2 Scalability** | Cloud Hosting Azure UK (0.95), Event Streaming Platform (0.72), Auto-scaling (10x capacity) | ✅ **COMPLIANT** | 5,000 → 50,000 req/sec auto-scaling, 5TB/day → 20TB/day capacity, horizontal scaling |
| **#3 Resilience** | Cloud Hosting Azure UK (0.95 multi-region), Managed Database Services (0.92), RTO <15 min | ✅ **COMPLIANT** | 99.95% availability SLA, UK South + UK West multi-region, automated failover |
| **#4 Security by Design** | GDPR Anonymization Engine (0.38), Secret Management Azure KeyVault (0.90), API Authentication OAuth2 (0.68) | ✅ **COMPLIANT** | Zero-trust architecture, encryption at rest/transit, MFA, secrets in Key Vault, DPIA approved |
| **#5 Open by Default** | Public Open Data Access (0.75), API Management Gateway (0.68), Open Government License | ✅ **COMPLIANT** | Open Data API with OpenAPI 3.x spec, traffic data under OGL, developer portal |
| **#6 Interoperability** | API Management Gateway (0.68), Schema Registry (0.65), DATEX II compliance (Roadworks) | ✅ **COMPLIANT** | RESTful APIs (OpenAPI 3.x), DATEX II for European interoperability, OAuth 2.0 standard |
| **#7 Observability** | Monitoring Observability Platform (0.72), Structured logging, SLO-based alerting | ✅ **COMPLIANT** | Azure Monitor + Grafana, golden signals (latency, traffic, errors, saturation), 7-year security logs |
| **#8 Data Mesh** | Data Mesh Implementation (0.38), 5 domain data products, Federated governance | ✅ **COMPLIANT** | Traffic/Incidents/Roadworks/Assets/Weather domains, published SLAs, data catalog |
| **#11 Data Sovereignty** | Cloud Hosting Azure UK (0.95), Managed Database Services (0.92), UK South + UK West only | ✅ **COMPLIANT** | OFFICIAL-SENSITIVE data in UK regions only, no cross-border transfers |
| **#12 Data Minimization** | GDPR Anonymization Engine (0.38), 24h ANPR deletion, 31-day CCTV retention | ✅ **COMPLIANT** | Automated deletion (ANPR 24h, CCTV 31 days), retention policy per data classification |

**Principles Compliance**: **10/10 compliant** - All architecture principles mapped and validated

---

## Recommendations

### Immediate Actions (0-3 months)

1. **Procure Azure Cloud Hosting via G-Cloud**
   - **Component**: Cloud Hosting Azure UK (0.95), Managed Database Services (0.92), Object Storage (0.95)
   - **Rationale**: Critical path dependency for all custom builds, 3-year reserved instances provide 60% discount
   - **Investment**: £800k/year (£2.4M 3-year reservation upfront)
   - **Owner**: CDTO, Infrastructure Team
   - **Success Criteria**: Azure UK South (primary) + UK West (DR) provisioned Month 1, Terraform IaC configured

2. **Start Legacy Oracle Migration Planning**
   - **Component**: Legacy Oracle Migration (0.42 → 0.92)
   - **Rationale**: 500TB data migration critical path, 6-month parallel running required for zero data loss
   - **Investment**: £2M migration project (consulting, ETL development, validation)
   - **Owner**: Data Engineering Team, Oracle DBAs
   - **Success Criteria**: Migration plan approved Month 2, pilot database (50GB) migrated Month 3, automated validation framework tested

3. **Hire Data Mesh Architects and Privacy Engineers**
   - **Component**: Data Mesh Implementation (0.38), GDPR Anonymization Engine (0.38)
   - **Rationale**: Skills gap blocks custom builds, 3 FTE Data Mesh architects and 2 FTE Privacy Engineers required
   - **Investment**: £500k recruitment + £300k/year salaries (5 FTE)
   - **Owner**: CDTO, HR
   - **Success Criteria**: 3 Data Mesh architects hired Month 2, 2 Privacy Engineers hired Month 3, DOS Outcomes consulting engaged (£500k discovery phase)

### Short-Term Actions (3-12 months)

1. **Build Real-Time Event Processing Platform**
   - **Component**: Real-Time Event Processing (0.45), Event Streaming Platform (0.72)
   - **Rationale**: Critical path for API launch Month 12, 5TB/day throughput, <2 sec latency requirement
   - **Investment**: £2M custom build (data engineers, streaming infrastructure) + £120k/year Azure Event Hubs
   - **Owner**: Data Engineering Team
   - **Success Criteria**: 5TB/day throughput validated Month 6, <2 sec p95 latency achieved Month 8, 10x load testing passed Month 10

2. **Build ANPR Journey Time Calculation with GDPR Anonymization**
   - **Component**: ANPR Journey Time Calculation (0.35), GDPR Anonymization Engine (0.38)
   - **Rationale**: Privacy-preserving journey times competitive advantage, 24h deletion UK GDPR compliance
   - **Investment**: £1.7M (privacy engineering, DPIA process, automated deletion)
   - **Owner**: Privacy Engineers, Data Engineering Team, DPO
   - **Success Criteria**: DPIA approved by ICO Month 6, 24h automated deletion tested Month 8, journey time accuracy >95% Month 10

3. **Launch Public Open Data API (Month 12 Commitment)**
   - **Component**: Public Open Data Access (0.75), API Management Gateway (0.68), Third-Party Navigation Apps (0.68)
   - **Rationale**: Minister's 12-month delivery commitment, open data ecosystem enabler
   - **Investment**: £500k API development + £60k/year Azure API Management
   - **Owner**: CDTO, API Development Team
   - **Success Criteria**: OpenAPI 3.x spec published Month 10, developer portal live Month 11, Google Maps/Waze/TomTom integrated Month 12, 50M API requests/month target by Month 18

4. **Build Regional Control Room Unified Dashboard**
   - **Component**: Regional Control Room Operations (0.35), Incident Management Workflow (0.42)
   - **Rationale**: Replace 7 legacy systems, 30% operational efficiency gain, 8-hour training (vs 40 hours legacy)
   - **Investment**: £1.8M custom dashboard + £200k operator training
   - **Owner**: COO, Regional Control Room Managers
   - **Success Criteria**: Pilot with Greater Manchester control room Month 9, 120 operators trained Month 11, 7 control rooms migrated Month 18

### Long-Term Strategic Actions (12-24 months)

1. **Complete Legacy Oracle Migration and Decommission**
   - **Component**: Legacy Oracle Migration (0.42 → 0.92)
   - **Rationale**: £8M/year Oracle license savings, cloud-native PostgreSQL managed services
   - **Investment**: £2M migration project (already allocated)
   - **Owner**: Data Engineering Team, Oracle DBAs
   - **Success Criteria**: 7 Oracle databases migrated Month 18, 6-month parallel running Month 12-18, Oracle licenses terminated Month 19, £8M/year savings verified by CFO

2. **Pilot Incident Detection AI on Low-Risk Routes**
   - **Component**: Incident Detection AI (0.28 → 0.38)
   - **Rationale**: 30% incident response time improvement (18 min → 12.6 min), novel AI capability
   - **Investment**: £2M AI/ML development (5 FTE specialists)
   - **Owner**: Data Science Team, Regional Control Rooms
   - **Success Criteria**: 85% detection accuracy on M25 J15-J16 pilot Month 18, human-in-loop validation, 15% false positive rate acceptable, re-evaluate build vs buy Month 18 if market products emerge

3. **Expand Data Mesh to All 5 Domains**
   - **Component**: Data Mesh Implementation (0.38 → 0.48), Traffic/Incidents/Roadworks/Assets/Weather Domain Data Products
   - **Rationale**: Federated governance enables domain autonomy, 99.9% SLA per data product
   - **Investment**: £1.5M data mesh transformation (already allocated) + £4.5M DOS Outcomes consulting
   - **Owner**: CDTO, Data Domain Owners (5 FTE)
   - **Success Criteria**: Traffic Domain data product live Month 9 (pilot), Incidents Domain Month 12, all 5 domains live Month 18, federated governance council operational, 99.9% availability SLA achieved

4. **Monitor Event Streaming Evolution and Plan Managed Service Migration**
   - **Component**: Event Streaming Platform (0.72 → 0.88)
   - **Rationale**: Kafka commoditizing rapidly, managed services (Azure Event Hubs, Confluent Cloud) reduce operational burden
   - **Investment**: £120k/year Azure Event Hubs (already allocated)
   - **Owner**: Data Engineering Team
   - **Success Criteria**: Azure Event Hubs adopted Month 24 (if not already), self-hosted Kafka migrated to managed service (if applicable), operational overhead reduced 50%

---

## Map Versioning

**Version History**:

| Version | Date | Author | Changes | Rationale |
|---------|------|--------|---------|-----------|
| v1.0 | 2025-11-13 | ArcKit AI (Claude Sonnet 4.5) | Initial map - Current state & procurement strategy | Strategic planning for £45M investment, build vs buy decisions, G-Cloud procurement (£25M) |

**Next Review Date**: 2025-Q2 (April-June 2025)

**Review Frequency**: Quarterly (align with steering committee meetings, budget reviews)

**Review Triggers**:
- Major requirement changes (e.g., new user needs, regulatory changes)
- Component evolution velocity changes (e.g., Event Streaming commoditizes faster than predicted)
- Procurement decisions (e.g., vendor selection, build vs buy re-evaluation)
- Risk materialization (e.g., Oracle migration delays, DPIA rejection)

---

## Appendix: Wardley Mapping Primer

### What is a Wardley Map?

A Wardley Map is a visual representation of:
1. **Value Chain** (Visibility axis, top to bottom): User needs → capabilities → components
2. **Evolution** (Evolution axis, left to right): Genesis → Custom → Product → Commodity
3. **Movement**: How components evolve over time (velocity)
4. **Dependencies**: What depends on what (arrows show dependency direction)

### How to Read This Map

- **Y-axis (Visibility)**: How visible the component is to the user
  - Top (0.95-1.0): Direct user needs (Driver Journey Planning)
  - Middle (0.4-0.7): Supporting capabilities (Incident Management, API Gateway)
  - Bottom (0.0-0.3): Infrastructure components (Cloud Hosting, Databases)

- **X-axis (Evolution)**: How industrialized/commoditized the component is
  - Left (0.0-0.25): Genesis - novel, unproven, uncertain (Driver Journey Planning, Incident Detection AI)
  - Custom (0.25-0.50): Bespoke, emerging practices (Data Mesh, ANPR Anonymization)
  - Product (0.50-0.75): Products with feature differentiation (API Management, Event Streaming)
  - Right (0.75-1.0): Commodity - utility, standardized (Cloud Hosting, Managed Databases)

### Strategic Decision Rules

1. **Genesis** (0.0-0.25): **Build only if strategic differentiator** - Accept high failure rate, invest in R&D
2. **Custom** (0.25-0.50): **Build vs Buy decision critical** - Evaluate competitive advantage, IP ownership
3. **Product** (0.50-0.75): **Buy from market unless very specific needs** - Compare vendors, feature sets
4. **Commodity** (0.75-1.0): **Always use commodity/utility - never build** - Cloud services, managed databases

### Common Mistakes to Avoid

❌ **Building custom solutions for commodity components** (e.g., building custom object storage instead of using Azure Blob - high cost, low value)

❌ **Buying products for Genesis stage needs** (e.g., buying off-the-shelf AI incident detection when no market solutions exist - premature)

❌ **Ignoring inertia** (e.g., not accounting for Oracle DBA retraining costs, change management for 120 control room operators)

❌ **Not mapping dependencies** (e.g., missing that Real-Time Event Processing is critical path for API launch - schedule risk)

❌ **Static maps** (e.g., not updating map when Event Streaming evolves from Product to Commodity - procurement strategy outdated)

---

## Additional Resources

- **Wardley Mapping**: https://learnwardleymapping.com/ - Free online book by Simon Wardley
- **Create Maps**: https://create.wardleymaps.ai - Paste map code to visualize
- **UK Government Digital Marketplace**: https://www.digitalmarketplace.service.gov.uk/ - G-Cloud and DOS frameworks
- **Technology Code of Practice**: https://www.gov.uk/guidance/the-technology-code-of-practice - 13 TCoP points
- **GDS Service Standard**: https://www.gov.uk/service-manual/service-standard - 14 service standard points
- **NCSC Cloud Security Principles**: https://www.ncsc.gov.uk/collection/cloud/the-cloud-security-principles - 14 cloud security principles

---

**Generated by**: ArcKit `/arckit.wardley` command
**Generated on**: 2026-01-26
**ArcKit Version**: 0.11.2
**Project**: National Highways Data Architecture Modernization (Project 001)
**Model**: Claude Opus 4.5 (claude-opus-4-5-20251101)
**Generation Context**: Strategic Wardley Map created from requirements (ARC-001-REQ-v1.1), stakeholder drivers (ARC-001-STKE-v1.1), data model (ARC-001-DATA-v1.1), and architecture principles (ARC-NH-PRIN-v1.1) - mapping 35 components across value chain with build vs buy analysis and UK Government G-Cloud procurement strategy for £45M investment
