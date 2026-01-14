# ✈️ Flight Delay Predictor

A machine learning project that predicts **flight delays** using historical flight data, airport information, and weather-related features.  
The project covers the **complete ML lifecycle** — from data ingestion and EDA to model prediction, visualization, and dashboarding.

🔗 Project Link:  
https://github.com/PranshuSama/BigDataEngProjects/tree/main/Flight%20Delay%20Predictor

---

## 📌 Project Objectives
- Analyze historical flight delay patterns
- Identify key factors influencing delays
- Build a predictive model for flight delays
- Visualize insights using plots and dashboards
- Generate prediction outputs for further analysis

---

## 📂 Project Structure

```text
Flight Delay Predictor/
├── Data/
│   ├── airports.csv
│   ├── flight_delay/
│   │   ├── flight_data_2024.csv
│   │   ├── flight_data_2024_sample.csv
│   │   └── flight_data_2024_data_dictionary.csv
│   └── usa_rain_prediction_dataset_2024_2025.csv
│
├── images/
│   ├── feature_importance_bar.png
│   ├── delay_distribution_bar.png
│   └── prediction_scatter.png
│
├── Flight_Delay_Predictor.ipynb
├── Feature Importance.csv
├── Visualization.csv
├── Visualization.lvdash.json
├── feature_importance.lvdash.json
├── prediction.csv
├── prediction_with_probability.csv
├── prediction_with_probability.lvdash.json
└── flight_delay_predictor_dashboard.html

📊 Visualizations

🔹 Feature Importance

Displays the most influential features contributing to flight delays.

🔹 Delay Distribution

Shows the distribution of flight delays across the dataset.

🔹 Prediction Scatter Plot

Visualizes predicted delay probability with respect to key operational and weather features.

📈 Interactive Dashboard

An interactive dashboard is included to explore predictions and insights visually.
	•	Dashboard File: flight_delay_predictor_dashboard.html
	•	Dashboard Configurations: .lvdash.json files

The dashboard enables exploration of:
	•	Feature importance
	•	Delay probability trends
	•	Time-based and weather-based patterns

📓 Jupyter Notebook

The complete workflow is implemented in:

📘 Flight_Delay_Predictor.ipynb

It includes:
	•	Data loading and preprocessing
	•	Exploratory Data Analysis (EDA)
	•	Feature engineering
	•	Model training and evaluation
	•	Prediction generation
	•	Visualization creation

⸻

🛠️ Tech Stack
	•	Programming Language: Python
	•	Data Analysis: Pandas, NumPy
	•	Visualization: Matplotlib, Seaborn
	•	Machine Learning: Scikit-learn
	•	Notebook Environment: Jupyter Notebook
	•	Version Control: Git & GitHub

⸻

🚀 How to Run the Project
	1.	Clone the repository:
      git clone https://github.com/PranshuSama/BigDataEngProjects.git

  2.	Navigate to the project directory:
      cd "Flight Delay Predictor"

	3.	Open the notebook:
      jupyter notebook Flight_Delay_Predictor.ipynb

🔮 Future Enhancements
	•	Hyperparameter tuning to improve model performance
	•	Comparison with advanced models (Random Forest, XGBoost)
	•	Real-time data ingestion
	•	Deployment as a web application or API

Thanks,
Pranshu
