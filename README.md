# 5.8 Flight Data Pipeline & Analytics Architecture

<img width="1281" height="522" alt="5 8M Flight Data Pipeline   Analytics Architecture drawio" src="https://github.com/user-attachments/assets/eb1f7a64-5bfb-4419-a615-08653618a5e4" />

## Overview
#### This project delivers an end-to-end data engineering and business intelligence solution designed to process, model, and analyze over 5.8 million transactional flight records from the U.S. Department of Transportation (DOT).

#### The primary goal of this pipeline is to transform disparate, uncleaned historical aviation data into a high-performance Kimball-style Star Schema Data Mart. The resulting platform powers executive-level Tableau dashboards and exploratory ad-hoc analysis, enabling stakeholders to evaluate carrier reliability, pinpoint delay causes, and identify geographic cancellation hotspots.

### Architecture & Key Accomplishments 
- Scalable Multi-Tiered Architecture:Designed and implemented a production-style layered SQL Server database architecture across 3 distinct schemas: Staging (DS), Enterprise Warehouse (W), and Star Schema Data Mart (SS).
- Automated ETL & Data Cleansing: Built robust SQL Server Integration Services (SSIS) packages to ingest raw DOT datasets, resolving complex data anomalies including 5-digit IATA code remapping, midnight time formatting (2400 $\rightarrow$ 00:00), and missing GIS coordinate lookups.
- Dimensional Modeling: Engineered a dimensional star schema centered on SS.Flight_Facts paired with surrogate-keyed dimension tables (SS.Airline, SS.Airports, SS.Time) to optimize analytical query speed and prevent double-aggregation errors in BI tools.
- Data Quality & Auditability: Executed comprehensive aggregate checksum validations comparing raw staging loads against warehouse fact layers to guarantee 100% data fidelity.
- Executive Visualization: Connected Tableau and Excel directly to the data mart, building custom non-double-aggregating calculated metrics to power an interactive Airport "Misery Map" and carrier market share performance trends.

### Tech Stack & Key Tools
| Layer | Technologies Used |
| ----- | ----------------- |
| Database & Engine | Microsoft SQL Server (SSMS) |
| ETL & Automation | SQL Server Integration Services (SSIS) | 
| Data Modeling | Dimensional Modeling (Kimball Star Schema, Surrogate Keys, Facts & Dimensions) |
| Analytics & BI | Tableau Desktop / Public, Microsoft Excel (PivotTables & Data Model) |
|Querying & Scripts | T-SQL (DDL, DML, Action Queries, CTEs, Aggregation Checksums) |   
