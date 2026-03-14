UK House Price Prediction 🇬🇧 🏠

This repository contains a complete Machine Learning pipeline designed to predict property prices in the United Kingdom. The project utilises a Random Forest regression model and encompasses everything from data ingestion and feature engineering to model serialisation and inference.

📌 Project Overview
Predicting house prices is a classic regression problem. This project uses the Kaggle dataset of UK House Prices (2015–2024) to train an algorithm that understands the real estate market.

A significant challenge in this dataset is high cardinality (e.g., thousands of unique postcodes). To solve this, the project implements intelligent feature engineering by extracting the Outcode from the UK postcode, allowing the model to understand the neighbourhood's value without overfitting.

✨ Key Features
Automated Data Ingestion: Downloads the dataset directly via the kagglehub library.

Advanced Feature Engineering: Extracts the year from transaction dates and the 'Outcode' from complete postcodes to optimise geographical learning.

Outlier Handling: Automatically filters out the top 5% most expensive properties to focus the model on the regular housing market.

Visualisation: Generates a detailed Feature Importance bar chart with percentage labels to explain the model's decision-making process.

Synthetic Data Generation: Includes a script to generate 1,000 synthetic UK property records for testing.

Inference Pipeline: Automatically formats predicted prices into standard UK currency (£).

Model Serialisation: Saves the trained model as a .pkl file using joblib for future use in web applications or other projects.

🛠️ Tech Stack:
Language: Python

Data Science: Pandas, NumPy

Machine Learning: Scikit-Learn (RandomForestRegressor, LabelEncoder)

Visualisation: Matplotlib, Seaborn

Persistence: Joblib

🛠️ Prerequisites & Installation
To run this project, you will need Python installed along with the following libraries:

Bash
pip install pandas scikit-learn matplotlib seaborn kagglehub joblib ipython
🚀 How It Works
The script is divided into clear, logical steps:

Data Preparation: Loads the dataset and performs surgical cleaning. Text data is encoded using LabelEncoder.

Training: Splits the data (80% training, 20% testing) and trains a RandomForestRegressor (100 estimators, max depth of 20).

Evaluation: Calculates the Mean Absolute Error (MAE) and R² Score to assess model accuracy.

Simulation & Inference: Generates a casas_sem_preco.csv file with 1,000 random properties, feeds it to the trained model, and outputs a resultado_previsoes_uk.csv file with the newly predicted prices.

Export: The model is saved as modelo_previsao_casas_uk.pkl to a specified absolute path on the local machine.

📊 Results & Insights
The model's performance on the regular UK housing market yields solid predictive power. Furthermore, the Feature Importance chart clearly demonstrates which attributes (e.g., geographical location via Outcode, property type, or build year) hold the most weight when pricing a UK home.

💡 How to Use the Saved Model
Once the model is saved, you can easily load it into a new Python project to make instant predictions:

Python
import joblib

# Load the pre-trained model
model = joblib.load('modelo_previsao_casas_uk.pkl')

# Make a prediction with new data
# prediction = model.predict(new_house_data)
