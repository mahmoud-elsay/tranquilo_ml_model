Here's a well-structured `README.md` template for your GitHub project:  

---

#  Tranquilo Anxiety Level Classification model   

Welcome to the **Anxiety Level Classification** project! This repository contains a complete workflow for understanding and classifying anxiety levels using machine learning. It includes data exploration, model building, a Flask API for serving predictions, Dockerization for deployment, and a Streamlit web application.  

---

## 📋 Table of Contents  
- [Overview](#overview)  
- [Features](#features)  
- [Dataset Description](#dataset-description)  
- [How It Works](#how-it-works)  
- [Installation](#installation)  
- [Usage](#usage)  
- [Technologies Used](#technologies-used)  
- [Project Structure](#project-structure)  
- [Future Enhancements](#future-enhancements)  
- [License](#license)  

---

## 🌟 Overview  
The **Anxiety Level Classification** project aims to predict the severity of anxiety in individuals based on key features like age, gender, BMI, and self-reported mental health attributes. The solution includes:  
- **Exploratory Data Analysis (EDA):** Insights from the data.  
- **Machine Learning Model:** A Random Forest model trained for classification.  
- **Flask API:** Serves predictions via REST endpoints.  
- **Streamlit Web App:** Provides a user-friendly interface for prediction.  
- **Dockerization:** For easy deployment to platforms like Hugging Face Spaces.  

---

## ✨ Features  
1. **Machine Learning Model:** Predicts anxiety severity levels: None-Minimal, Mild, Moderate, or Severe.  
2. **Flask API:** A RESTful API to classify anxiety levels based on user inputs.  
3. **Streamlit Frontend:** Interactive UI for users to input data and receive predictions.  
4. **Docker Support:** Simplifies deployment and scaling of the application.  
5. **End-to-End Workflow:** Includes understanding, preprocessing, and modeling the dataset.  

---

## 📊 Dataset Description  
The dataset used for this project includes features that assess various psychological and physical aspects of individuals.  

### Key Features:  
| **Feature**            | **Description**                                   |  
|-------------------------|---------------------------------------------------|  
| `age`                  | Age of the participant.                           |  
| `gender`               | Gender of the participant.                        |  
| `bmi`                  | Body mass index.                                  |  
| `who_bmi`              | BMI category (underweight, normal, etc.).         |  
| `depressiveness`       | Self-reported depression status.                  |  
| `anxiousness`          | Self-reported anxiety status.                     |  
| `sleepiness`           | Self-reported sleepiness status.                  |  

For more details, see the **EDA Notebook**.  

---

## ⚙️ How It Works  
1. **Data Preprocessing:** Missing values are handled, and categorical features are encoded.  
2. **Model Training:** Multiple models were trained, including Random Forest, Logistic Regression, SVM, and XGBoost. The best-performing model (Random Forest) was tuned and saved as `model.pkl`.  
3. **Flask API:** A REST endpoint `/predict` takes user input (JSON) and returns the predicted anxiety level.  
4. **Dockerization:** The Flask app is containerized for easy deployment.  
5. **Streamlit Web App:** A lightweight web UI for predictions.  

---

## 🛠 Installation  

### Prerequisites:  
- Python 3.9+  
- Docker (optional, for deployment)  

### Clone the Repository  
```bash  
git clone https://github.com/mahmoud-elsay/tranquilo_ml_model 

```  

### Install Python Dependencies  
```bash  
pip install -r requirements.txt  
```  

---

## 🚀 Usage  

### Run Flask API Locally:  
```bash  
python app.py  
```  
The API will be available at `http://127.0.0.1:5000`.  

### Use the `/predict` Endpoint:  
Send a POST request with a JSON payload:  
```json  
{  
    "age": 25,  
    "gender": "male",  
    "bmi": 22.5,  
    "who_bmi": "normal",  
    "depressiveness": 1,  
    "depression_diagnosis": 0,  
    "depression_treatment": 0,  
    "anxiousness": 1,  
    "anxiety_diagnosis": 0,  
    "anxiety_treatment": 0,  
    "sleepiness": 1  
}  
```  
Response:  
```json  
{  
    "anxiety_level": "Moderate",  
    "anxiety_level_id": 2,  
    "statusCode": 200  
}  
```  

### Run Streamlit Web App:  
```bash  
streamlit run streamlit_app.py  
```  

### Build Docker Image:  
```bash  
docker build -t anxiety-classification .  
docker run -p 5000:5000 anxiety-classification  
```  

---

## 🛠 Technologies Used  
- **Languages & Frameworks:** Python, Flask, Streamlit  
- **Machine Learning:** Scikit-learn, XGBoost  
- **Deployment:** Docker  
- **Visualization:** Matplotlib, Seaborn  
- **Model Tuning:** GridSearchCV  

---

## 📂 Project Structure  

```plaintext  
anxiety-classification/  
├── app.py               # Flask API  
├── streamlit_app.py     # Streamlit web app  
├── Dockerfile           # Docker configuration  
├── model.pkl            # Trained ML model  
├── requirements.txt     # Python dependencies  
├── notebooks/           # Jupyter notebooks for EDA & modeling  
│   ├── EDA.ipynb        # Understanding the dataset  
│   └── modeling.ipynb   # Model building and evaluation  
├── Anxiety_data.csv     # Dataset  
└── README.md            # Project documentation  
```  

---

## 🔮 Future Enhancements  
- Add additional features for better predictions.  
 
- Extend the Streamlit app for interactive data visualization.  
- Experiment with other advanced machine learning models.  

---

## 📜 License  
This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.  

---
