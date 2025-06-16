# ✈️ Flight Delay Analysis using Azure, Databricks, Spark, & Power BI

This project analyzes U.S. domestic flight data to uncover trends in delays, cancellations, and airline performance using ETL processes. Data was processed using a Bronze-Silver-Gold architecture in Azure Databricks and visualized through interactive dashboards in Power BI.

## 🚀 Project Objectives

- Design a robust data ETL pipeline using medallion architecture (Bronze, Silver, Gold)
- Clean, transform, and enrich raw flight data from a Kaggle dataset
- Analyze delay trends across airlines, dates, and locations
- Build Power BI dashboards to communicate insights effectively

---

## 🛠️ Tools & Technologies

| Layer            | Tools / Services                            |
|------------------|---------------------------------------------|
| Data Processing  | Azure Databricks, PySpark, Delta Lake       |
| Storage          | Azure Data Lake Gen2 (mounted via DBFS)     |
| Visualization    | Microsoft Power BI                          |
| Languages        | Python (PySpark), SQL                       |

---

## 🧱 Data Pipeline Architecture

📂 **Bronze Layer**  
- Raw ingestion of Kaggle flight delay data  
- No transformations, preserves original structure

📂 **Silver Layer**  
- Removes duplicates, canceled, and diverted flights  
- Standardizes timestamps, formats numeric columns  
- Adds features like `YearMonth`, `FlightDateTS`

📂 **Gold Layer**  
- Aggregates and prepares curated datasets for reporting  
- Multiple derived tables created for specific insights

---

## 📊 Key Power BI Visualizations

1. **Average Arrival Delay by Airline and Departure Status**  
   - Source: `gold_delay_dist`  
   - Visual: Clustered Bar Chart  
   - X-axis: Airline  
   - Legend: Departed Late (Yes/No)  
   - Y-axis: Avg Arrival Delay (minutes)

2. **Daily Average Flight Delays (Jan 2024)**  
   - Source: `gold_delay_trend`  
   - Visual: Line Chart  
   - X-axis: FlightDate  
   - Y-axis: Avg Dep Delay, Avg Arr Delay

3. **Top Performing Airlines (On-Time %)**  
   - Source: `ontime_performance`  
   - Visual: Table  
   - Columns: Airline, % On-Time Arrivals

4. **Most Delayed Locations (by Count)**  
   - Source: `repeat_delayed_airports`  
   - Visual: Table or Bar Chart  
   - Columns: Origin City, # Delayed Flights


---


## 📈 Insights & Results

- Certain airlines have significantly higher average delays than others
- Some airports consistently face more delays than others
- January 2024 saw moderate daily delay fluctuation
- Majority of flights that are on-time vary widely between carriers


---


## 💡 Personal Takeaways

This project enabled me to demonstrate the core concepts and skills I gained from earning the following certifications:

- **Databricks Certified Data Analyst Associate**  
  Leveraged Databricks and PySpark to clean, transform, and analyze large-scale flight data in a pipeline format.
  
- **Microsoft Certified: Power BI Data Analyst Associate (PL-300)**  
  Created intuitive dashboards,  translated raw data into meaningful visualizations, and conveyed significant insights that can contribute to industrial decision-making.

- **Microsoft Certified: Fabric Analytics Engineer Associate (DP-600)**  
  Demonstrated abd experienced a robust comprehension of ELT pipelines, gold-layer modeling, and semantic layer preparation as covered by this certification. Designed a modern lakehouse architecture using Microsoft Fabric-compatible tools (Delta Lake, Data Lake Storage).

Another noteable takeaway- the hands-on experience regarding environment integration was an incredibly humbling process of learning, as this project was unguided. Specifically, the setup of a Microsoft Azure environment and an Azure databricks environment entailed transferring local data from Kaggle onto an Azure storage account and container, connecting to the data via Azure databricks, setting up a functional cluster for the notebook which required various configurations, then writing the dataframes to tables to be connected to via Power BI. This process quite daunting for the directionless, entry-level candidate who simply wished to work with data processing and data visualization. I experienced many shortcomings and dead-ends that demanded perseverance and adaptability, which are two attributes that cannot be accredited by a technical certification. 

Through this hands-on project, I strengthened my end-to-end data analytics workflow—from ingestion and transformation to visualization. It also helped me develop a deeper understanding of how to structure data for reporting, optimize queries, and design dashboards that effectively tell a story.


