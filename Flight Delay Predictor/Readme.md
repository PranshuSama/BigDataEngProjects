✈️ US Flight Delay Predictor: Big Data Machine Learning Pipeline
================================================================

**End-to-End Predictive Analytics on Databricks**

📌 Project Overview
-------------------

This project processes a massive scale of **12.8 Million flight and weather records** to predict domestic flight delays in the United States. By integrating historical flight data with high-resolution NOAA weather datasets, this pipeline identifies the specific factors that trigger delays.

The project successfully demonstrates that **Systemic Congestion** and **Departure Timing** (the "Snowball Effect") are significantly stronger predictors of delays than raw weather factors.

🛠️ Technical Stack
-------------------

*   **Platform:** Databricks (Azure)
    
*   **Engine:** PySpark (Spark SQL & MLlib)
    
*   **Storage:** Delta Lake / DBFS
    
*   **Language:** Python / SQL
    

🏗️ Data Engineering Pipeline
-----------------------------

### 1\. Multi-Source Ingestion & Cleaning

*   Ingested and cleaned **12.8M+ rows** of disparate flight and NOAA weather data.
    
*   Resolved the **IATA-to-City mapping problem**, bridging 3-letter airport codes (JFK, LAX) with geographic weather station locations.
    

### 2\. Feature Engineering (The "Signal" Boost)

*   **Airport Congestion:** Implemented **Spark Window Functions** to calculate real-time flight volume per airport per hour.
    
*   **Carrier Delay History:** Developed rolling averages of airline performance to capture operational efficiency.
    
*   **Time-of-Day Logic:** Vectorized departure hours to identify cumulative pressure on the national aviation system.
    

🤖 Machine Learning & Evaluation
--------------------------------

*   **Algorithm:** Random Forest Classifier (100 Trees).
    
*   **Performance:** Achieved a **0.7033 ROC Score**.
    
*   **Class Balancing:** Applied under-sampling to the majority ("On-Time") class to ensure the model learned the specific signatures of delayed flights.
    
*   **Accuracy Metrics:** Reached a **0.6473 Precision and Recall** score, effectively catching 2/3 of all actual delays.
    

📊 Business Intelligence & Dashboarding
---------------------------------------

The final results were deployed into an interactive **Databricks Dashboard** to reveal hidden patterns in the data:

### **The "Snowball Effect"**

*   **Key Finding:** Delay probability increases by over **400%** between 8:00 AM and 8:00 PM, regardless of weather conditions.
    
*   **Feature Importance Breakdown:**
    
    *   **Departure Hour:** 48.6% (Systemic Pressure).
        
    *   **Carrier History:** 34.1% (Operational Efficiency).
        
    *   **Weather Factors:** < 1% (Trigger vs. Root Cause).
        

🚀 Key Takeaways
----------------

1.  **Scalability:** Demonstrated the ability to join, clean, and model datasets exceeding 12 million records in a distributed environment.
    
2.  **Strategic Insight:** Identified the **5:00 AM – 9:00 AM** window as the most reliable time for US air travel.
    
3.  **Deployment:** Saved the finalized "Champion Model" to **DBFS** for persistent inference and operational reporting.
    

### **How to Use This Repository**

1.  **Notebooks:** Contains the Spark logic for Ingestion, Join Logic, and ML Training.
    
2.  **Models:** Documentation for loading the champion\_model\_v2 pipeline.
    
3.  **Visuals:** Includes exported PDF/HTML reports of the finalized Intelligence Dashboard.
    

### **About the Author**

I am a Data Engineer and Machine Learning enthusiast with a passion for uncovering stories hidden within massive datasets. My background includes a strong interest in **Art and Sketching** (as seen on my art account **@pranshudraws**), which I use to create intuitive and visually compelling data stories.
