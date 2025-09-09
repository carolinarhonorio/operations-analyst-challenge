# Operations Analyst Challenge  

This repository contains the solution for the **Operations Analyst Challenge**, where I was tasked with analyzing transactional data and creating visualizations to support business insights.  

---

## 📊 Project Overview  

The goal was to prepare a complete analysis (from raw data to business recommendations) addressing the following KPIs and questions:  

1. **Total Payment Volume (TPV)**  
   - Segmented by entity, product, and payment method.  
   - Comparison of products by TPV.  

2. **Average Ticket (TPV ÷ Transactions)**  
   - Calculated overall and segmented by entity, product, and payment method.  

3. **Transactional Insights**  
   - Impact of installments on transaction volume.  
   - Price tier analysis (performance across volume/transactions).  

4. **Anticipation Methods**  
   - Which anticipation methods are most used proportionally by each entity (PF vs. PJ)?  
   - How much each anticipation method represents in absolute monetary values.  

5. **Strategic Questions Answered**  
   - Which product has the highest TPV?  
   - How weekdays impact TPV?  
   - Which entity (PF vs. PJ) contributes most to volume and transactions?  
   - Which anticipation method is most relevant by entity?  

---

## 📂 Repository Structure  

- **looker_studio_challenge_operations_analyst.pdf**  
  Export of the interactive dashboard (static version).  

- **operations_analyst_data_raw_data.csv**  
  Original dataset provided.  

- **operations_analyst_data_cleaned_data.csv**  
  Pre-processed dataset with adjustments for readability and consistency.  

- **operations_analyst_data_calculated_kpis.csv**  
  Additional calculations (e.g., TPV share, average ticket per product).  

- **operations_analyst_data_compiled_values_only.xlsx**  
  Full dataset compiled in Excel format (values only, no formulas).  

- **operations_analyst_presentation.pdf**  
  Final slide deck with context, KPIs, insights, and recommendations.  

---

## 📈 Dashboard  

The interactive dashboard was built in **Looker Studio**, with dynamic filters and a consistent structure across pages:  

- **Overview**: Main KPIs (TPV, Transactions, Merchants, Average Ticket).  
- **Products**: TPV and transactions by product, with shares and average tickets.  
- **Entities (PF vs. PJ)**: Segmentation of KPIs by entity.  
- **Payment Methods**: TPV and transactions by debit, credit, and uninformed.  
- **Installments**: Impact of installment distribution on KPIs.  
- **Price Tiers**: Distribution of transactions and TPV across price tiers.  
- **Anticipation Methods**: Both proportional analysis (% by entity) and absolute values (R$).
- **Weekdays**: Distribution of TPV and transactions across weekdays. 

🔗 [Access the Interactive Dashboard](https://lookerstudio.google.com/s/gVQ7ZyNMmYk)  
*(Public access enabled as "Viewer")*  

---

## 📊 Data & Calculations  

- **Raw Data**: Original dataset provided (`.csv`).  
- **Cleaned Data**: Processed dataset, prepared for analysis.  
- **Calculated KPIs**: Aggregated metrics and derived values used in the dashboard.  
- **Google Sheets (with formulas)**: All transformations and KPI calculations are also available here:  
  👉 [View on Google Sheets](https://docs.google.com/spreadsheets/d/1IumEMGgjAW3dpKd4pYOPIdqtSQ6eNLmtJRcUis_k2mI/edit?usp=sharing)  

---

## 📝 Presentation  

A **slide deck** was prepared to complement the dashboard, summarizing:  

- Context and methodology.  
- Clear visualization highlights.  
- Strategic insights and recommendations.  

🔗 [Access the Presentation Here](https://docs.google.com/presentation/d/1QtwY_TI6rq-X0a1jA-xc9V0pvTjnGRkL1U9M4f8QFjs/edit?usp=sharing)  

---

## 🚀 How to Use  

1. Clone or download this repository.  
2. Explore the datasets (`.csv` and `.xlsx`) for detailed calculations.  
3. Open the PDF (`looker_studio_challenge_operations_analyst.pdf`) for the static dashboard export.  
4. Access the **interactive Looker Studio dashboard** via the link above.  
5. Open the PDF presentation (`operations_analyst_presentation.pdf`) for a summarized storyline of the analysis.  
6. Review all transformations and formulas directly in the shared **Google Sheets**.  

---

## 🔑 Key Highlights  

- Standardized naming conventions for clarity (`raw_data`, `cleaned_data`, `calculated_kpis`).  
- Dashboard structure replicated across all analysis pages.  
- Combination of **relative (%)** and **absolute (R$)** views for deeper insights.  
- Transparent workflow from raw data → cleaned data → KPIs → dashboard → presentation.  

---

## 🛠️ Tools & Skills  

- **Google Sheets** – Data cleaning, preprocessing, and KPI calculation.  
- **Looker Studio** – Interactive dashboards, charts, and visual storytelling.  
- **GitHub** – Project documentation and version control.  
- **Slides (Google Slides)** – Business storytelling and strategic recommendations.  

---

## 🧾 Technical Notes  (SQL)

Although SQL (BigQuery, Postgres) was suggested as a tool, this project was fully developed using **Google Sheets** for preprocessing and **Looker Studio** for visualizations.  

This choice was intentional given the dataset size and the scope of the challenge.  
- **Google Sheets** allowed for quick data cleaning, KPI calculation, and validation.  
- **Looker Studio** provided dynamic dashboards and clear visual storytelling.  

👉 In a production environment, SQL would be the natural choice for scalability. For example:  

- Using `GROUP BY` to aggregate **TPV and transactions by entity, product, or payment method**.  
- Applying `CASE WHEN` statements to derive categories such as **price tiers** or **anticipation methods**.  
- Leveraging `DATE_TRUNC()` or `EXTRACT()` to analyze KPIs by month, week, or weekday.  
- Building **scheduled queries** to refresh data automatically for dashboards.  

This would ensure efficiency in handling larger datasets and enable integration into automated BI pipelines.  

---

## 📌 Data Limitation: Merchant Numbers  

The dataset included a column for **quantity_of_merchants**, but it did not provide a unique merchant ID.  

As a result:  
- It was **not possible** to calculate the exact number of distinct merchants.  
- The metric was treated as an **aggregate estimate** rather than a precise count.  

To ensure transparency:  
- Merchant numbers were displayed as provided but not used for advanced segmentation.  
- The analysis instead focused on **TPV, transactions, average ticket, and anticipation methods**, which were fully supported by the dataset.  

👉 In a production environment, the presence of a **merchant_id** would enable more precise metrics such as *active merchants*, *merchant churn*, and *concentration analysis*.  

---

## 🤖 AI Assistant Proposal  

To extend the analysis into an operational workflow, I propose an **AI-powered assistant** that provides daily KPI monitoring and automated insights.  

**Workflow Overview:**  
1. **Data Ingestion**: Daily refresh of transactional data (via SQL or API).  
2. **KPI Calculation**: Automatic aggregation of TPV, average ticket, and segmentation by entity, product, and payment method.  
3. **Insight Generation**: Comparison vs. historical baselines (day, week, month).  
4. **Alert System**: Automatic detection of anomalies or significant drops in KPIs.  
5. **Delivery**: Insights distributed via Slack/Email/Chatbot integration.  

**Example Alerts:**  
- *“TPV for Pix transactions dropped -18% vs. last week. Investigate potential payment friction.”*  
- *“Average ticket for POS increased +12% compared to yesterday - driven by PJ transactions.”*  
- *“D0/Nitro anticipation usage by PF fell below historical baseline (-22%).”*  

This assistant would ensure **real-time visibility** of key metrics, reduce manual monitoring effort, and allow faster decision-making.  

---

## 🔄 Updates & Revisions  

- **Sep 08, 2025**: Corrected weekday calculation in the original dataset and updated Looker export.  
  - Fixed weekday numbering (now starting on Sunday).  
  - Updated weekday labels to English.  
  - Re-uploaded Looker Studio PDF export to reflect corrected metrics.  

---

## 👤 Author  

**Carolina Honorio**  
Operations & Data Analyst | Data-Driven Insights & Business Process Improvement  
