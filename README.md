# B2B-SALES-PIPLELINE-ANALYSIS

## Project Background 

In today’s competitive B2B landscape, effectively managing high-value sales opportunities is critical for businesses to drive revenue, optimize sales strategies, and maintain a competitive edge. The sales pipeline generates vast amounts of data on leads, deal values, and sales rep performance, presenting an opportunity to transform this data into actionable insights. The challenge lies in identifying top-performing sales reps, understanding pipeline dynamics, and addressing bottlenecks to improve conversion rates and maximize deal value.  

This project was undertaken to develop a Power BI report analyzing sales pipeline metrics for high-value Technology leads (deal value > $20,000). The report leverages a comprehensive dataset capturing key metrics such as `lead_id`, `sales_rep`, `lead_status`, `deal_value`, `industry`, and more. The project aims to empowers sales leaders to make data-driven decisions to enhance rep performance, optimize pipeline management, and achieve revenue goals.  

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

Deliverables
- Power BI [B2B.pbix](https://github.com/Numb3rNinja/B2B-SALES-PIPELINE-DASHBOARD.git) file with the dashboard.
- SQL [queries](https://github.com/Numb3rNinja/SQL-Queries-for-B2B-Analysis.git) used for analysis.

# Executive Summary
**Overview of Findings**  
The sales pipeline for high-value Technology leads (deal value > $20,000) is robust, with 1,160 leads and a total pipeline value of $294.7M. However, the overall conversion rate of 13.28% (154 won deals) indicates room for improvement in closing deals. Mary Perkins leads in conversion rate (23.21%), while Randall Clarke dominates in total deal value ($17.3M). Christopher Figueroa secures the highest average deal value ($282K). Pipeline progression analysis reveals a bottleneck between Negotiation (175 leads) and Won (154 leads), suggesting challenges in finalizing deals.  
![Image](https://github.com/user-attachments/assets/73432562-7c60-45f3-b8f7-d3cb4c3bf0be)

## Insights Deep-Dive
**Pipeline Progression**

Analysis of pipeline progression reveals the distribution of leads across pipeline stages: 143 in New, 171 in Contacted, 193 in Qualified, 186 in Proposal, 175 in Negotiation, 154 in Won, and 138 in Lost. This progression highlights a strong lead qualification process, as the pipeline peaks at the Qualified stage with 193 leads, a 34.9% increase from the New stage. However, the subsequent drop to 186 leads in Proposal (-3.6%) and 175 in Negotiation (-5.9% from Proposal) indicates moderate attrition in mid-pipeline stages, suggesting potential inefficiencies in moving leads from qualification to negotiation. The most significant bottleneck occurs between Negotiation (175 leads) and Won (154 leads), with only 88% of Negotiation leads converting to closed deals, while 138 leads (11.9% of the total pipeline) are lost. This drop-off underscores challenges in finalizing deals, possibly due to pricing disputes, contract complexities, or competitive pressures. 
![Image](https://github.com/user-attachments/assets/d2a433f5-c033-449f-8775-bcd83ba87bf5)

**Total Deal Value by Sales Rep**

Evaluation of total deal value by sales representative (Technology, Deal Value > $20K) highlights the top 10 sales reps driving revenue: Randall Clarke ($17,300,863), Nancy Holmes ($16,920,594), Samuel Estrada ($16,850,687), Gregory Williams ($16,712,566), Sherry Garcia ($16,677,425), Jennifer Hanson ($16,428,140), Christopher Figueroa ($16,363,576), Michael Daniel ($16,271,424), Alexis Frazier ($15,876,971), and Randall Davis ($15,847,890). Randall Clarke’s leadership in total deal value, contributing $17.3M, positions him as a cornerstone of the sales team, closely followed by Nancy Holmes and Samuel Estrada, each within $450K of Clarke’s total. The tight range of deal values among the top 10 ($15.8M–$17.3M) indicates consistent performance among high performers, with no single rep dominating disproportionately. This consistency suggests a well-distributed allocation of high-value leads, but it also raises questions about whether top reps are maximizing their potential or if additional resources could push their totals higher. Notably, the top 10 reps collectively account for a significant portion of the $294.7M pipeline value, emphasizing their critical role in revenue generation. However, their performance must be evaluated alongside conversion rates to ensure they are not only securing high-value deals but also closing them efficiently. For instance, Randall Clarke’s high deal value contrasts with his moderate 12.31% conversion rate, suggesting a focus on larger deals over volume, which may warrant a strategic review to balance quantity and quality.
![Image](https://github.com/user-attachments/assets/f10316b3-45b9-47e6-a145-c800db27496f)

**Average Deal Value by Sales Rep**

Evaluation of average deal value by sales representative (Technology, Deal Value > $20K)* provides deeper insight into deal size trends, with the top five reps being Christopher Figueroa ($282,130.62), Mary Perkins ($277,337.47), Jennifer Hanson ($273,802.34), Samuel Estrada ($271,785.27), and Randall Clarke ($266,167.12). Christopher Figueroa’s average deal value of $282K, the highest among all reps, indicates a strategic focus on securing larger deals, potentially through targeting enterprise clients or negotiating premium contracts. Mary Perkins and Jennifer Hanson, with averages of $277K and $273K, respectively, also demonstrate strength in landing high-value deals, aligning with their presence in other performance metrics. Samuel Estrada and Randall Clarke’s appearance in both total and average deal value rankings underscores their versatility, balancing high deal volumes with substantial deal sizes. The average deal value across the pipeline ($254,030) serves as a benchmark, and these top reps exceed it by 4.8%–11.1%, highlighting their ability to target premium opportunities. However, the variation in average deal values (e.g., $266K–$282K among the top five) suggests differences in sales approaches, such as Figueroa’s focus on fewer, larger deals versus Clarke’s broader deal portfolio. Sales leaders should investigate these strategies to identify best practices for scaling across the team, particularly for reps with lower average deal values.
![Image](https://github.com/user-attachments/assets/2485d0a5-e1c2-4417-97ea-8d47e41f17ab)

**Conversion Rate by Sales Rep**

Assessment of conversion rates by sales representative (Technology, Deal Value > $20K) offers a critical lens on sales rep effectiveness, with Mary Perkins leading at a 23.21% conversion rate (13 won out of 56 leads), followed by Marrissa Gibson (19.64%, 11 won out of 56 leads) and Michael Daniel (19.40%, 13 won out of 67 leads). Perkins’ exceptional performance, converting nearly one in four leads, suggests a highly effective approach to deal-closing, possibly through strong relationship-building or tailored solutions for Technology clients. Gibson and Daniel’s high conversion rates, despite handling similar or higher lead volumes, indicate scalable strategies that could benefit the broader team. In contrast, top deal value performers like Randall Clarke (12.31%, 8 won out of 65 leads) and Nancy Holmes (15.63%, 10 won out of 64 leads) show moderate conversion rates, suggesting they prioritize larger deals over closing volume. This trade-off is evident when comparing Clarke’s $17.3M total deal value to his 12.31% conversion rate, indicating a focus on high-stakes opportunities that may require longer sales cycles. At the lower end, reps like Michael Mack (4.55%, 2 won out of 44 leads) and Gregory Williams (7.58%, 5 won out of 66 leads) struggle significantly, with conversion rates well below the pipeline average of 13.23%. These low performers may be hindered by unqualified leads, ineffective sales tactics, or lack of experience with high-value Technology clients. The wide range of conversion rates (4.55%–23.21%) highlights disparities in rep performance, necessitating targeted interventions to elevate underperformers while leveraging top performers’ strategies.
![Image](https://github.com/user-attachments/assets/8bbcc703-7ba0-4900-a83b-5c0b2a9ab53c)

### Recommendations
**Optimize Negotiation-to-Won Conversion**:  
- Pipeline progression shows a drop from Negotiation (175) to Won (154). Implement training on advanced negotiation tactics and deal-closing strategies to address this bottleneck.  
- Analyze lost deals (138) to identify common reasons (e.g., pricing, contract terms) and adjust offerings accordingly.  

**Leverage Top Performers**:  
- **Mary Perkins**: Her 23.21% conversion rate is exceptional. Study her approach to closing deals and share best practices through team workshops.  
- **Christopher Figueroa**: His $282K average deal value suggests expertise in securing large deals. Pair him with high-value leads to maximize revenue.  
- **Randall Clarke and Samuel Estrada**: Their high total deal values ($17.3M and $16.8M) and strong average deal values ($266K and $271K) make them versatile performers. Use them as mentors for underperforming reps.  

**Support Low Performers**:  
- Reps like Michael Mack (4.55% conversion) and Gregory Williams (7.58% conversion) need targeted coaching. Pair them with high-conversion reps like Mary Perkins for shadowing opportunities.  
- Review their lead assignments to ensure they’re not overwhelmed with unqualified leads.  

**Strategic Resource Allocation**:  
- Allocate high-value leads to reps with strong average deal values (e.g., Christopher Figueroa, Mary Perkins).  
- Shift resources from low-conversion reps to those with proven success to optimize pipeline outcomes.  

**Enhance Pipeline Health**:  
- The 13.28% overall conversion rate is moderate. Implement a lead scoring refinement to prioritize high-potential leads early in the pipeline.  
- Use predictive analytics to identify leads likely to reach Negotiation and Won stages, reducing time spent on low-probability leads.



























