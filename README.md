# Credit Card Transaction Analysis - SQL Portfolio

## 🎯 Project Overview

This repository demonstrates comprehensive SQL skills through analysis of credit card transaction data. The project showcases database design, complex queries, and business intelligence capabilities using PostgreSQL.

## 📊 Dataset

**Source**: [Comprehensive Credit Card Transactions Dataset](https://www.kaggle.com/datasets/rajatsurana979/comprehensive-credit-card-transactions-dataset) from Kaggle

**Description**: Real-world financial transaction data including customer demographics, merchant information, transaction details, and fraud indicators.

## 🏗️ Database Creation from Scratch

### 📋 Initial Planning & Architecture
**Business Requirements Analysis:** Designed a comprehensive database to support credit card transaction analysis with focus on customer behavior, merchant performance, and fraud detection capabilities.

**Database Architecture Decisions:**
- **Database Engine:** PostgreSQL 15+ selected for enterprise-grade reliability and advanced SQL features
- **Schema Strategy:** Three-tier architecture for logical data separation
- **Normalization Level:** 3NF (Third Normal Form) for optimal performance and data integrity

### 🔨 Database Implementation Process

#### Step 1: Database & Schema Creation

-- Created from scratch using PostgreSQL DDL
CREATE DATABASE credit_card_analysis;

-- Implemented three-tier schema architecture
CREATE SCHEMA raw_data;      -- Source data and staging
CREATE SCHEMA analytics;     -- Processed analytical data  
CREATE SCHEMA reporting;     -- Dashboard-ready summaries

  <div align="center">
    <img src="data/raw/Schema_organization_in_pgAdmin.png" alt="Schema_organization_in_pgAdmin" width="100%" max-width="800px"/>
  </div>

### ⚙️ Technical Challenges Solved

#### Data Import Complexity
> **Challenge:** Single denormalized CSV (100K records) needed transformation into normalized relational structure  
> **Solution:** Implemented staging table strategy with multi-step ETL process

#### PostgreSQL-Specific Issues Resolved
- **Date Format Conversion:** CSV dates (DD-MM-YYYY) → PostgreSQL standard (YYYY-MM-DD)
- **Transaction Isolation:** Database creation commands cannot run in transaction blocks
- **Number Formatting:** Large numbers requiring custom `TO_CHAR` patterns with thousands separators
- **Data Type Casting:** `::numeric` casting for ROUND() function compatibility

#### ETL Pipeline Architecture

### 🎯 Performance & Integrity Implementation

#### Strategic Indexing
Created 7 optimized indexes based on expected query patterns:
- Transaction dates for temporal analysis
- Foreign keys for join optimization
- Amount ranges for statistical queries
- Geographic fields for location-based analysis

#### Data Integrity Enforcement
- **Referential Integrity:** Complete foreign key constraint implementation
- **Business Rules:** Check constraints (positive amounts, valid state codes)
- **Data Quality:** NOT NULL constraints on critical fields
- **Unique Constraints:** Category name uniqueness
## 🛠️ Technology Stack & Implementation

### 💾 Database Infrastructure
- **Database Engine:** PostgreSQL 15+ (Enterprise-grade RDBMS)
- **Database Management:** pgAdmin 4 (Professional GUI interface)
- **Schema Design:** Multi-schema architecture (`raw_data`, `analytics`, `reporting`)
- **Data Types:** Advanced PostgreSQL types (BIGSERIAL, DECIMAL, TIMESTAMP)

### 🔧 Development Environment
- **Code Editor:** Visual Studio Code 2
- **SQL Extensions:** 
  - PostgreSQL Extension (Chris Kolkman)
  - SQLTools with PostgreSQL Driver
- **Connection Strategy:** Configured persistent database connections with proper authentication
- **Terminal Integration:** VS Code integrated terminal for PostgreSQL CLI operations

### 📊 Data Engineering Pipeline

#### Data Acquisition
- **Data Source:** Kaggle - Comprehensive Credit Card Transactions Dataset
- **Format:** CSV files with 100,000 transaction records
- **Time Span:** 10 months (January 1 - October 14, 2023)
- **Volume:** $44.2M total transaction volume across 50K customers

#### ETL Process Implementation

| Phase | Technology | Implementation |
|-------|------------|----------------|
| **Extract** | PostgreSQL COPY | Bulk CSV import with error handling |
| **Transform** | Advanced SQL | Data type conversions, relationship mapping |
| **Load** | Multi-table INSERT | Normalized data distribution with referential integrity |
| **Validate** | SQL Constraints | Data quality checks and relationship verification |

### 📈 Advanced SQL Analytics Implementation

#### Query Complexity Levels Demonstrated
- **Basic Aggregations:** COUNT, SUM, AVG, MIN, MAX with business context
- **Statistical Functions:** PERCENTILE_CONT, STDDEV for distribution analysis
- **Advanced Joins:** Multi-table relationships with complex business logic
- **Window Functions:** ROW_NUMBER, RANK, LAG for analytical rankings
- **Common Table Expressions (CTEs):** Complex multi-step analytical workflows

#### Professional Data Presentation
- **Number Formatting:** `TO_CHAR` with thousands separators (999,999,999)
- **Percentage Calculations:** Precise business ratio computations with proper rounding
- **Date Manipulations:** `DATE_TRUNC`, `EXTRACT` for temporal analysis
- **Text Processing:** `COALESCE`, `CASE` statements for data cleaning

### 🚀 Production-Ready Features

#### Scalability & Performance
- **Future-Proof Keys:** BIGSERIAL for high-volume transaction growth
- **Efficient Indexing:** Strategic indexes for query performance optimization
- **Modular Architecture:** Extensible schema design for additional data sources

#### Enterprise Standards
- **Code Documentation:** Comprehensive inline comments explaining business logic
- **Naming Conventions:** Consistent, descriptive column and table names
- **Error Handling:** Robust CSV import with data type validation
- **Professional Presentation:** Formatted output with business-ready metrics

### 🔄 Version Control & Documentation
- **Repository Management:** Git/GitHub with structured SQL file organization
- **Documentation Strategy:** Comprehensive README with technical and business insights
- **Code Organization:** Logical progression from basic to advanced analytics
- **Professional Standards:** Industry-standard commenting and formatting

> **🎯 Technical Achievement:** This project demonstrates complete database lifecycle management from conceptual design through production implementation, showcasing enterprise-level PostgreSQL database creation, ETL pipeline development, advanced SQL analytics, and professional documentation standards - all built from scratch using industry best practices.

### 📸 Screenshot Placement Guide
**Recommended screenshots to add:**
1. **Database Architecture:** Schema organization in pgAdmin
2. **ERD Diagram:** Table relationships and foreign keys
3. **ETL Process:** Staging table and data transformation steps
4. **Performance Features:** Indexes and constraints in database
5. **SQL Complexity:** Advanced query examples with CTEs and window functions
6. **Repository Structure:** Organized SQL files in GitHub





## 📊 Basic Data Exploration - Key Business Insights

### 🔍 Dataset Overview
Our comprehensive analysis of credit card transaction data reveals a robust dataset spanning **10 months of 2023** (January 1 - October 14) with significant business intelligence opportunities.

**Core Metrics:**
- **Total Transaction Volume:** $44,211,923.94
- **Total Transactions:** 100,000
- **Unique Customers:** 50,000  
- **Active Merchants:** 87,758
- **Product Categories:** 6
- **Average Transaction:** $442.12

*[📸 Screenshot Placeholder: Dataset Overview Results]*

---

### 💰 Transaction Distribution Analysis

**Statistical Profile:**
- **Median Transaction:** $182.20
- **75th Percentile:** $470.52  
- **Transaction Range:** $5.01 - $2,999.88
- **Distribution:** Right-skewed (median significantly below mean)

**Key Insight:** The wide gap between median ($182.20) and mean ($442.12) indicates a mix of routine purchases and high-value transactions, suggesting diverse customer spending behaviors.

*[📸 Screenshot Placeholder: Transaction Amount Distribution]*

---

### 🎯 Category Performance Analysis

**Transaction Count Distribution:**
All 6 categories show remarkably even distribution (~16% each):
- Travel, Electronics, Market, Clothing, Cosmetics, Restaurant

**Revenue Concentration (Disproportionate):**
- **Travel:** 58.36% ($25,800,463.88) - *Dominant revenue driver*
- **Electronics:** 19.88% ($8,788,184.20) - *Secondary contributor*  
- **Other 4 Categories:** Combined ~22% - *Significant underperformance*

**🚨 Strategic Implication:** Travel transactions have much higher average values, representing a premium customer segment.

*[📸 Screenshot Placeholder: Category Performance Table]*

---

### 📅 Temporal Pattern Analysis

#### Weekly Distribution
**Consistent Behavior:** Transaction volume evenly distributed across all days (~14% per day)
- **No weekend/weekday bias** - suggests B2B and B2C mix
- **Operational stability** - predictable daily volume for capacity planning

#### Monthly Trends  
**Stable Performance:** Average transaction amount consistent at ~$400/month (Jan-Sep)
- **October Anomaly:** ~50% volume drop (partial month - data ends Oct 14)
- **Forecasting Reliability:** Consistent monthly patterns enable accurate projections

*[📸 Screenshot Placeholder: Weekly and Monthly Patterns]*

---

### 👥 Customer Behavior Insights

#### High-Value Customer Analysis
**Top 20 Customers Identified** with detailed spending profiles including:
- Transaction frequency patterns
- Customer lifetime spans  
- Geographic distribution
- Spending consistency

#### Geographic Distribution
Analysis reveals customer concentration patterns across states, enabling targeted regional strategies.

*[📸 Screenshot Placeholder: Top Customers Table]*

---

### 🏪 Merchant Performance & Market Structure

#### Market Concentration
**Critical Finding:** Top 2 merchants control ≥20% of total transaction volume
- **Johnson PLC** leads merchant performance
- **High market concentration risk** - dependency on few key partners

#### Industry Dominance
**Travel Category Monopoly:** All top 15 merchants operate in travel sector
- **Sector concentration risk**
- **Limited category diversification** in top performers

#### Customer Diversification Health
**Positive Indicator:** All top 15 merchants achieve ~50% customer diversity ratio
- **Strong customer acquisition** across merchants
- **Healthy competitive landscape** beyond top 2 players

*[📸 Screenshot Placeholder: Merchant Performance Analysis]*

---

## 🎯 Strategic Business Implications

### 💼 Key Opportunities
1. **Premium Category Strategy:** Investigate travel's high-value model for replication
2. **Electronics Growth:** 2nd largest category with expansion potential (currently 19.88%)
3. **Customer Loyalty:** 50% diversity suggests room for retention programs

### ⚠️ Risk Management Priorities  
1. **Revenue Concentration:** 58% dependency on travel category
2. **Merchant Dependency:** Top 2 merchants control >20% volume
3. **Seasonal Patterns:** Monitor Q4 performance (data gap Nov-Dec)

### 📈 Forecasting Insights
- **Predictable Daily Volume:** ~14% distribution enables capacity planning
- **Stable Monthly Performance:** $400 average supports budgeting
- **Category Stability:** Consistent ratios enable category-specific strategies

---

## 🔧 Technical Implementation Notes

**Data Quality:** High-quality dataset with consistent formatting and complete transaction records through October 14, 2023.

**SQL Complexity Demonstrated:**
- Advanced aggregations and statistical functions
- Multi-table joins with proper relationships
- Window functions for ranking and percentiles
- Complex percentage calculations with proper formatting

*[📸 Screenshot Placeholder: Technical Query Examples]*

---

> **Analysis Methodology:** This comprehensive exploration utilized advanced SQL techniques including CTEs, window functions, statistical aggregations, and multi-dimensional grouping to extract actionable business intelligence from raw transaction data.

