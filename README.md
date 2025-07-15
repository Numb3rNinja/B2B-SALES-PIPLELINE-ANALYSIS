# B2B-SALES-PIPLELINE-ANALYSIS

## Project Background

In today’s competitive B2B landscape, effectively managing high-value sales opportunities is critical for businesses to drive revenue, optimize sales strategies, and maintain a competitive edge. The sales pipeline generates vast amounts of data on leads, deal values, and sales rep performance, presenting an opportunity to transform this data into actionable insights. The challenge lies in identifying top-performing sales reps, understanding pipeline dynamics, and addressing bottlenecks to improve conversion rates and maximize deal value.  

This project was undertaken to develop a Power BI report analyzing sales pipeline metrics for high-value Technology leads (deal value > $20,000). The report leverages a comprehensive dataset capturing key metrics such as `lead_id`, `sales_rep`, `lead_status`, `deal_value`, `industry`, and more. By providing an interactive dashboard with KPI cards, a funnel chart, bar charts, column charts, and tables, the report empowers sales leaders to make data-driven decisions to enhance rep performance, optimize pipeline management, and achieve revenue goals.  

**Key Insights and Recommendations Focused On**:  
- **Pipeline Progression**: Analysis of leads across pipeline stages (New, Contacted, Qualified, Proposal, Negotiation, Won, Lost) to identify bottlenecks and conversion efficiency.  
- **Total Deal Value by Sales Rep**: Evaluation of total deal value by sales rep to identify top performers and allocate high-value leads effectively.  
- **Average Deal Value by Sales Rep**: Examination of average deal sizes to understand which reps secure larger deals.  
- **Conversion Rates by Sales Rep**: Assessment of conversion rates to highlight reps with the highest effectiveness in closing deals.  
- **Overall Pipeline Metrics**: Summary of total leads, pipeline value, and conversion rates to provide a holistic view of pipeline health.  
An interactive Power BI dashboard was developed to visualize these focus areas, offering dynamic filters and visuals (e.g., funnel chart, bar chart, column chart, table) to explore sales rep performance, pipeline stages, and deal outcomes.

---

### Data Structure & Initial Checks  
The dataset forms the backbone of the B2B Sales Pipeline Performance Report, structured to support detailed analysis of lead progression and sales rep effectiveness for high-value Technology leads.  

**Table Columns**:  
- `lead_id`: Unique identifier for each lead (text).  
- `company_name`: Name of the prospect’s company (text).  
- `contact_name`: Primary contact person (text).  
- `contact_email`: Contact’s email address (text).  
- `contact_phone`: Contact’s phone number (text).  
- `industry`: Industry of the company (categorical, e.g., Technology).  
- `lead_source`: Origin of the lead (categorical, e.g., Inbound - Website).  
- `lead_status`: Current pipeline stage (categorical, e.g., New, Contacted, Qualified, Proposal, Negotiation, Closed Won, Closed Lost).  
- `deal_value`: Estimated deal value (decimal).  
- `currency`: Currency of the deal (text, e.g., USD).  
- `created_date`: Date lead was added (date).  
- `last_contacted`: Date of last interaction (date).  
- `next_action`: Next step in the sales process (text).  
- `next_action_date`: Scheduled date for next action (date).  
- `sales_rep`: Assigned sales representative (text).  
- `probability_of_close`: Likelihood of closing (integer, percentage).  
- `expected_close_date`: Anticipated close date (date).  
- `notes`: Additional context (text).  
- `lead_score`: Qualification score (integer).  
- `pain_points`: Prospect’s challenges (text).  
- `competitor`: Competing solutions (text).  
- `contract_length`: Proposed contract duration (text).  
- `stage_last_updated`: Date of last status update (date).  
- `account_type`: Type of account (categorical, e.g., Enterprise).  
- `region`: Geographic region (text).  

**Key Early Checks**:  
- **Data Type Validation**: Confirmed appropriate data types: `lead_id`, `company_name`, `contact_email`, `contact_phone`, `sales_rep`, `notes`, `pain_points`, `competitor`, `contract_length`, `currency`, `region` as text; `industry`, `lead_source`, `lead_status`, `account_type` as categorical; `created_date`, `last_contacted`, `next_action_date`, `stage_last_updated`, `expected_close_date` as dates; `deal_value` as decimal; `probability_of_close`, `lead_score`, `hashtag_count` as integers.  
- **Missing or Null Values**: Checked for missing data in critical columns (e.g., `deal_value`, `lead_status`, `sales_rep`). Handled minimal missing values by excluding incomplete records or filling with defaults (e.g., 0 for `deal_value`).  
- **Duplicate Records**: Verified `lead_id` uniqueness to eliminate duplicate leads, removing duplicates in Power Query if found.  
- **Categorical Consistency**: Standardized `lead_status` (e.g., 'Closed Won' vs. 'closed won') using `UPPER(TRIM())` to ensure accurate grouping, addressing previous issues with zero conversion rates.  
- **Outlier Detection**: Inspected `deal_value` and `lead_score` for outliers (e.g., unusually high deal values) to flag potential data errors.  
- **Date Consistency**: Ensured date fields were uniformly formatted and covered the relevant period.






























