<!DOCTYPE html>

<div align="center">
  <h1>Guillermo Ibanez | SQL Portfolio</h1>
  <h1><img src="https://user-images.githubusercontent.com/74038190/221352987-68da234d-4d62-4e9d-9d7f-098dc657c2dc.gif" width="700" height="150"><h1>
</div>

<html>
<head>
   <meta charset="UTF-8">
</head>
<body>

<h1>💳 Credit Card Transactions Analysis</h1>

<!-- ======================= INDEX ======================= -->
<h2>📋 Table of Contents</h2>
<ol>
   <li><a href="#introduction">🎯 Introduction</a></li>
   <li><a href="#technical-setup">🛠️ Technical Setup</a></li>
   <li><a href="#business-insights">📊 Data Exploration - Key Business Insights</a></li>
   <li><a href="#advanced-analytics">📈 Advanced SQL Analytics - Key Business Intelligence Insights</a></li>
</ol>

<hr style="border: 2px solid #333; margin: 30px 0;">

<!-- ======================= INTRODUCTION SECTION ======================= -->
<section id="introduction">
<h2>🎯 Introduction</h2>

<h3>Project Overview</h3>
<p>This repository demonstrates comprehensive SQL skills through analysis of credit card transaction data. The project showcases database design, complex queries, and business intelligence capabilities using PostgreSQL.</p>

<h3>📊 Dataset</h3>
<p><strong>Source:</strong> <a href="https://www.kaggle.com/datasets/rajatsurana979/comprehensive-credit-card-transactions-dataset">Comprehensive Credit Card Transactions Dataset</a> from Kaggle</p>

<p><strong>Description:</strong> Real-world financial transaction data including customer demographics, merchant information, transaction details, and fraud indicators.</p>

<p><strong>Dataset Specifications:</strong></p>
<ul>
<li><strong>Format:</strong> CSV files with 100,000 transaction records</li>
<li><strong>Time Span:</strong> 10 months (January 1 - October 14, 2023)</li>
<li><strong>Volume:</strong> $44.2M total transaction volume across 50K customers</li>
<li><strong>Scope:</strong> 87,758 active merchants across 6 product categories</li>
</ul>

</section>

<hr style="border: 3px solid #e74c3c; margin: 50px 0;">

<!-- ======================= TECHNICAL SETUP SECTION ======================= -->
<!-- [Keep all your existing technical setup content here - it's perfect as is] -->

<!-- ======================= BUSINESS INSIGHTS SECTION ======================= -->
<!-- [Keep all your existing business insights content here] -->

<hr style="border: 3px solid #9b59b6; margin: 50px 0;">

<!-- ======================= ADVANCED ANALYTICS SECTION ======================= -->
<section id="advanced-analytics">
<h2>📈 Advanced SQL Analytics - Key Business Intelligence Insights</h2>

<h3>🔍 Advanced Analysis Overview</h3>
<p>Building upon the foundational data exploration, this advanced analytics phase employed sophisticated SQL techniques including <strong>window functions</strong>, <strong>Common Table Expressions (CTEs)</strong>, <strong>statistical segmentation</strong>, and <strong>growth analysis</strong> to extract deeper business intelligence from the credit card transaction data.</p>

<p><strong>Advanced Techniques Demonstrated:</strong></p>
<ul>
<li><strong>LAG Functions:</strong> Month-over-month growth calculations</li>
<li><strong>NTILE & Percentile Analysis:</strong> Customer quartile segmentation</li>
<li><strong>Customer Lifetime Value Modeling:</strong> Multi-tier customer classification</li>
<li><strong>Statistical Distribution Analysis:</strong> Transaction size categorization</li>
</ul>

<p><em>[📸 Screenshot Placeholder: Advanced SQL Query Examples]</em></p>

<hr>

<h3>📊 Monthly Growth Pattern Analysis</h3>

<h4>Seasonal Transaction Volatility</h4>
<p><strong>Key Discovery:</strong> Monthly transaction data reveals a distinctive <strong>alternating growth pattern</strong> with significant seasonal implications for business planning.</p>

<p><strong>Growth Pattern Timeline:</strong></p>
<ul>
<li><strong>February:</strong> Notable decline in both transaction count and volume</li>
<li><strong>March:</strong> Strong recovery with ~12% growth in both metrics</li>
<li><strong>April-August:</strong> Consistent alternating pattern between growth and decline months</li>
<li><strong>August-September:</strong> Two consecutive months of decline</li>
</ul>

<h4>Post-Summer Spending Behavior</h4>
<p><strong>🚨 Critical Insight:</strong> The sustained decline in August and September suggests a <strong>seasonal spending pattern</strong> where customers reduce transaction activity following summer holiday expenditures.</p>

<p><strong>Business Implications:</strong></p>
<ul>
<li><strong>Predictable Seasonality:</strong> Alternating growth/decline pattern enables forecasting</li>
<li><strong>Post-Holiday Effect:</strong> Consecutive declines indicate budget recovery periods</li>
<li><strong>Planning Opportunity:</strong> Anticipate lower Q3 performance for resource allocation</li>
</ul>

<p><em>[📸 Screenshot Placeholder: Monthly Growth Analysis Results]</em></p>

<hr>

<h3>👥 Advanced Customer Segmentation Intelligence</h3>

<h4>Customer Value Distribution Analysis</h4>
<p>Our sophisticated customer tier analysis reveals significant <strong>market concentration</strong> and <strong>revenue distribution patterns</strong> critical for strategic decision-making.</p>

<h4>Customer Tier Breakdown by Spending Volume</h4>
<table>
<thead>
<tr>
<th>Customer Tier</th>
<th>Spending Criteria</th>
<th>% of Customers</th>
<th>% of Total Volume</th>
<th>Strategic Significance</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>High Value</strong></td>
<td>≥$2,000</td>
<td>~11.55%</td>
<td><strong>51.89%</strong></td>
<td>Revenue concentration</td>
</tr>
<tr>
<td><strong>Medium Value</strong></td>
<td>$1,000-$1,999</td>
<td>~11.73%</td>
<td>~30%</td>
<td>Growth potential</td>
</tr>
<tr>
<td><strong>Low Value</strong></td>
<td>&lt;$1,000</td>
<td><strong>76.72%</strong></td>
<td>~18%</td>
<td>Activation opportunity</td>
</tr>
</tbody>
</table>

<h4>🎯 Strategic Customer Intelligence</h4>
<p><strong>Critical Finding:</strong> Just <strong>11.55% of customers generate 51.89% of total transaction volume</strong> - a textbook demonstration of the Pareto Principle in customer value distribution.</p>

<p><strong>Business Strategy Implications:</strong></p>
<ul>
<li><strong>VIP Focus:</strong> High-value segment (11.55%) drives majority of revenue</li>
<li><strong>Untapped Potential:</strong> 76.72% of customers represent activation opportunities</li>
<li><strong>Resource Allocation:</strong> Disproportionate ROI from focusing on top-tier customers</li>
<li><strong>Risk Management:</strong> High revenue dependency on small customer segment</li>
</ul>

<p><em>[📸 Screenshot Placeholder: Customer Tier Analysis Results]</em></p>

<hr>

<h3>💰 Transaction Size Distribution Analysis</h3>

<h4>Micro-Transaction Dominance Pattern</h4>
<p>Advanced transaction categorization reveals a <strong>small-ticket transaction economy</strong> with significant implications for payment processing and customer behavior understanding.</p>

<p><strong>Transaction Size Distribution:</strong></p>
<ul>
<li><strong>Small Transactions ($100-$499):</strong> 43.47% of total transaction count</li>
<li><strong>Micro Transactions (&lt;$100):</strong> 33.26% of total transaction count</li>
<li><strong>Combined Small + Micro:</strong> <strong>76.73% of all transactions</strong></li>
</ul>

<h4>🔍 Transaction Behavior Insights</h4>
<p><strong>Key Discovery:</strong> Over three-quarters of all transactions (76.73%) fall into the small-to-micro category ($0-$499), indicating a predominantly <strong>routine spending pattern</strong> rather than major purchase behavior.</p>

<p><strong>Operational Implications:</strong></p>
<ul>
<li><strong>Payment Processing:</strong> Optimize for high-volume, low-value transactions</li>
<li><strong>Customer Experience:</strong> Streamline small transaction processing</li>
<li><strong>Fee Structure:</strong> Consider transaction size in pricing models</li>
<li><strong>Marketing Strategy:</strong> Focus on frequent, smaller purchases rather than large-ticket items</li>
</ul>

<p><em>[📸 Screenshot Placeholder: Transaction Size Distribution]</em></p>

<hr>

<h3>🎯 Advanced Analytics Business Impact</h3>

<h4>Strategic Decision Support</h4>
<p><strong>Revenue Concentration Risk:</strong> High dependency on 11.55% of customers for majority revenue requires <strong>customer retention strategies</strong> and <strong>diversification initiatives</strong>.</p>

<h4>Operational Optimization</h4>
<p><strong>Transaction Processing Focus:</strong> 76.73% micro/small transaction dominance suggests optimizing systems for <strong>high-frequency, low-value processing</strong> rather than occasional large transactions.</p>

<h4>Seasonal Planning Intelligence</h4>
<p><strong>Predictable Patterns:</strong> Alternating monthly growth/decline pattern with post-summer seasonality enables <strong>proactive resource planning</strong> and <strong>cash flow forecasting</strong>.</p>

<hr>

<h3>🔧 Advanced SQL Techniques Demonstrated</h3>

<p><strong>Technical Proficiency Showcased:</strong></p>
<ul>
<li><strong>Window Functions:</strong> LAG() for period-over-period analysis</li>
<li><strong>Statistical Segmentation:</strong> NTILE() for quartile analysis</li>
<li><strong>Complex CTEs:</strong> Multi-step analytical workflows</li>
<li><strong>Advanced Aggregations:</strong> Nested percentage calculations</li>
<li><strong>Business Logic Implementation:</strong> CASE statements for tier classification</li>
<li><strong>Performance Optimization:</strong> Efficient query structures for large datasets</li>
</ul>

<p><em>[📸 Screenshot Placeholder: Complex SQL Code Examples]</em></p>

<hr>

<blockquote>
<p><strong>Advanced Analytics Methodology:</strong> This sophisticated analysis leveraged enterprise-level SQL techniques including window functions, statistical segmentation, and growth trend analysis to transform raw transaction data into actionable business intelligence, demonstrating both technical SQL mastery and strategic business acumen.</p>
</blockquote>

</section>

</body>
</html>

