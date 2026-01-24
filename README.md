# 🎬 End-to-End Movie Review Sentiment Analysis System

An **industry-grade MLOps project** that predicts whether a given movie review expresses **positive or negative sentiment**.
This repository demonstrates the **complete lifecycle of a machine learning system**, from experimentation to production deployment on **AWS EKS**, with **CI/CD, DVC, MLflow, Docker, Kubernetes, Prometheus, and Grafana**.

---

## 🚀 Project Overview

This project builds a **text-based sentiment classification system** trained on movie review data. Given a user’s textual input describing a movie, the system predicts whether the sentiment is **Positive** or **Negative**.

What makes this project stand out is not just the ML model, but the **full MLOps pipeline**:

* Reproducible experiments using **MLflow**
* Data & model versioning using **DVC + S3**
* Automated **CI/CD pipelines** using **GitHub Actions**
* Containerized deployment using **Docker**
* Scalable serving on **AWS EKS (Kubernetes)**
* Production monitoring using **Prometheus & Grafana**

This is a **production-ready sentiment analysis system**, not just a notebook-based ML model.

---

## 🧠 Problem Statement

Movie reviews often contain rich textual feedback. Automatically classifying these reviews helps:

* Understand audience perception
* Power recommendation systems
* Support analytics for movie platforms

**Goal:**
Given a movie review as text, predict:

* `Positive` sentiment
* `Negative` sentiment

---

## 🗂️ Project Architecture

```
├── src/
│   ├── logger/
│   ├── data_ingestion.py
│   ├── data_preprocessing.py
│   ├── feature_engineering.py
│   ├── model_building.py
│   ├── model_evaluation.py
│   └── register_model.py
│
├── flask_app/
│   ├── app.py
│   ├── templates/
│   └── static/
│
├── dvc.yaml
├── params.yaml
├── Dockerfile
├── requirements.txt
├── .github/workflows/ci.yaml
└── README.md
```

---

## ⚙️ Tech Stack

### 🔹 Machine Learning & NLP

* Python 3.10
* Scikit-learn
* NLP preprocessing (tokenization, vectorization)

### 🔹 Experiment Tracking

* **MLflow** (hosted on **DagsHub**)

### 🔹 Data & Model Versioning

* **DVC**
* Remote storage: **AWS S3**

### 🔹 Backend & Serving

* **Flask** REST API
* **Docker** containerization

### 🔹 CI/CD & MLOps

* **GitHub Actions**
* **AWS ECR** for image registry
* **AWS EKS (Kubernetes)** for deployment

### 🔹 Monitoring

* **Prometheus** (metrics collection)
* **Grafana** (visual dashboards)

---

## 🔁 MLOps Pipeline

1. **Data Ingestion** – Load and validate movie review dataset
2. **Data Preprocessing** – Clean and normalize text
3. **Feature Engineering** – Convert text to numerical features
4. **Model Training** – Train sentiment classifier
5. **Model Evaluation** – Track metrics using MLflow
6. **Model Registration** – Register best model
7. **DVC Pipeline** – Reproducible pipeline with `dvc repro`
8. **CI/CD** – Automated testing, build & deployment
9. **Docker Image** – Built and pushed to AWS ECR
10. **EKS Deployment** – Scalable container orchestration
11. **Monitoring** – Metrics scraped by Prometheus and visualized in Grafana

---

## 🌐 API Usage

### Endpoint

```
POST /predict
```

### Sample Input

```json
{
  "text": "The movie was absolutely fantastic with great performances"
}
```

### Sample Output

```json
{
  "sentiment": "Positive"
}
```

---

## 🐳 Docker Usage

```bash
docker build -t capstone-app:latest .

docker run -p 8888:5000 \
  -e CAPSTONE_TEST=<your_dagshub_token> \
  capstone-app:latest
```

---

## ☸️ Kubernetes Deployment (EKS)

* Docker image pushed to **AWS ECR**
* Deployed using Kubernetes manifests
* Exposed via **LoadBalancer Service**
* Accessible using:

```
http://<external-ip>:5000
```
External-IP we will get using
```bash
kubectl get svc flask-app-service
```

---

## 📊 Monitoring & Observability

### Prometheus

* Scrapes metrics from Flask app

### Grafana

* Visual dashboards for:

  * API health
  * Request metrics
  * Model performance insights

---

## ✅ Key Highlights

✔ End-to-end production-ready MLOps project  
✔ Reproducible pipelines using DVC  
✔ Experiment tracking with MLflow (DagsHub)  
✔ CI/CD automation with GitHub Actions  
✔ Dockerized and Kubernetes deployed  
✔ AWS EKS + ECR integration  
✔ Monitoring with Prometheus & Grafana  

---

## 👤 Author

**Udit Srivastava**  
Interested in **MLOps, Data Science, and Scalable ML Systems**

---

⭐ If you like this project, consider giving it a star!
