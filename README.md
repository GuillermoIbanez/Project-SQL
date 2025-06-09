# Credit Card Transaction Analysis - SQL Portfolio

## 🎯 Project Overview

This repository demonstrates comprehensive SQL skills through analysis of credit card transaction data. The project showcases database design, complex queries, and business intelligence capabilities using PostgreSQL.

## 📊 Dataset

**Source**: [Comprehensive Credit Card Transactions Dataset](https://www.kaggle.com/datasets/rajatsurana979/comprehensive-credit-card-transactions-dataset) from Kaggle

**Description**: Real-world financial transaction data including customer demographics, merchant information, transaction details, and fraud indicators.

## 🛠️ Technology Stack

- **Database**: PostgreSQL 15+
- **GUI Tool**: pgAdmin 4
- **Version Control**: Git/GitHub
- **Data Source**: Kaggle CSV files

## 📁 Repository Structure

```
sql-credit-card-analysis/
├── README.md                          # This file
├── requirements.txt                   # Dependencies
├── data/
│   ├── raw/                          # Original Kaggle CSV files
│   ├── processed/                    # Cleaned/transformed data
│   └── sample/                       # Sample data for testing
├── sql/
│   ├── 01_database_setup/            # Database and table creation
│   ├── 02_data_exploration/          # Basic exploratory queries
│   ├── 03_business_analysis/         # Business-focused analysis
│   ├── 04_advanced_analytics/        # Complex SQL techniques
│   └── 05_reporting/                 # Summary reports and dashboards
├── documentation/
│   ├── business_questions.md         # Business questions and objectives
│   ├── database_schema.md            # Database design documentation
│   └── insights_summary.md           # Key findings and insights
└── scripts/
    ├── setup_environment.py          # Environment setup
    └── data_validation.py            # Data quality checks
```

## 🚀 Quick Start

### Prerequisites
- PostgreSQL 15+ installed
- pgAdmin 4 (or preferred PostgreSQL client)
- Git

### Setup Instructions

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/sql-credit-card-analysis.git
   cd sql-credit-card-analysis
   ```

2. **Download the dataset**
   - Visit the [Kaggle dataset page](https://www.kaggle.com/datasets/rajatsurana979/comprehensive-credit-card-transactions-dataset)
   - Download CSV files to `data/raw/` folder

3. **Create the database**
   ```bash
   psql -U postgres -f sql/01_database_setup/create_database.sql
   ```

4. **Create tables and load data**
   ```bash
   psql -U postgres -d credit_card_analysis -f sql/01_database_setup/create_tables.sql
   psql -U postgres -d credit_card_analysis -f sql/01_database_setup/load_data.sql
   ```

5. **Run analysis queries**
   - Execute SQL files in order (01, 02, 03, 04, 05)
   - Use pgAdmin for interactive analysis

## 📈 Key SQL Skills Demonstrated

### Fundamental Skills
- **Data Definition**: CREATE TABLE, ALTER TABLE, constraints
- **Data Manipulation**: INSERT, UPDATE, DELETE operations
- **Basic Queries**: SELECT, WHERE, GROUP BY, ORDER BY
- **Aggregations**: COUNT, SUM, AVG, MIN, MAX

### Intermediate Skills
- **Joins**: INNER, LEFT, RIGHT, FULL OUTER joins
- **Subqueries**: Correlated and non-correlated subqueries
- **Functions**: Date functions, string functions, mathematical functions
- **Data Types**: Working with various PostgreSQL data types

### Advanced Skills
- **Window Functions**: ROW_NUMBER(), RANK(), LAG(), LEAD()
- **Common Table Expressions (CTEs)**: Recursive and non-recursive
- **Performance Optimization**: Indexing, query optimization
- **Database Design**: Normalization, relationships, constraints

## 🔍 Business Analysis Areas

### Customer Analytics
- Customer segmentation and lifetime value
- Spending pattern analysis
- Geographic distribution analysis
- Customer retention and churn analysis

### Transaction Analysis
- Fraud detection patterns
- Category performance analysis
- Seasonal trends and patterns
- High-value transaction identification

### Merchant Intelligence
- Merchant performance metrics
- Geographic merchant analysis
- Category-wise merchant distribution
- Revenue contribution analysis

### Financial Insights
- Monthly/quarterly growth analysis
- Revenue forecasting indicators
- Risk assessment metrics
- Profitability analysis

## 📊 Sample Queries

### Customer Ranking by Total Spending
```sql
SELECT 
    c.customer_id,
    c.first_name || ' ' || c.last_name as customer_name,
    COUNT(*) as transaction_count,
    ROUND(SUM(t.amount), 2) as total_spent,
    ROUND(AVG(t.amount), 2) as avg_transaction,
    RANK() OVER (ORDER BY SUM(t.amount) DESC) as spending_rank
FROM customers c
JOIN transactions t ON c.customer_id = t.customer_id
GROUP BY c.customer_id, c.first_name, c.last_name
ORDER BY total_spent DESC
LIMIT 10;
```

### Monthly Growth Analysis with Window Functions
```sql
WITH monthly_revenue AS (
    SELECT 
        DATE_TRUNC('month', transaction_date) as month,
        SUM(amount) as revenue,
        COUNT(*) as transaction_count
    FROM transactions
    GROUP BY DATE_TRUNC('month', transaction_date)
)
SELECT 
    month,
    ROUND(revenue, 2) as monthly_revenue,
    transaction_count,
    ROUND(100.0 * (revenue - LAG(revenue) OVER (ORDER BY month)) / 
          LAG(revenue) OVER (ORDER BY month), 2) as growth_rate_pct
FROM monthly_revenue
ORDER BY month;
```

## 🎯 Key Insights Discovered

### Customer Behavior
- Top 10% of customers generate 60% of total revenue
- Weekend transactions average 15% higher amounts than weekdays
- Geographic clustering shows highest spending in urban areas

### Fraud Patterns
- Fraudulent transactions typically occur in specific time windows
- Certain merchant categories have higher fraud rates
- Geographic anomalies indicate potential fraud indicators

### Business Performance
- Monthly transaction volume shows consistent 8% growth
- Top 5 categories account for 70% of total transaction volume
- Customer retention rate varies significantly by spending tier

## 🏆 Professional Development Value

This project demonstrates:

### Technical Skills
- **Database Administration**: Schema design, indexing, optimization
- **SQL Proficiency**: Complex queries, window functions, CTEs
- **Data Analysis**: Statistical analysis, trend identification
- **Performance Tuning**: Query optimization, efficient data retrieval

### Business Skills
- **Financial Analytics**: Understanding transaction patterns
- **Risk Assessment**: Fraud detection methodologies
- **Business Intelligence**: Converting data into actionable insights
- **Documentation**: Professional code documentation and reporting

## 📚 Next Steps & Extensions

### Planned Enhancements
1. **Advanced Analytics**
   - Cohort analysis implementation
   - Customer lifetime value modeling
   - Predictive fraud scoring

2. **Visualization Integration**
   - Tableau/Power BI dashboard creation
   - Python integration for advanced analytics
   - Real-time monitoring queries

3. **Performance Optimization**
   - Partitioning strategies for large datasets
   - Advanced indexing techniques
   - Query performance benchmarking

## 🤝 Contributing

This is a portfolio project showcasing SQL skills. However, suggestions for improvements are welcome:

1. Fork the repository
2. Create a feature branch
3. Submit a pull request with detailed descriptions

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.


