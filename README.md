# Research & Development Portfolio

![Python](https://img.shields.io/badge/Python-3.11+-3776AB?logo=python&logoColor=white)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Research%20%2B%20Systems-0F766E)
![FastAPI](https://img.shields.io/badge/FastAPI-Backend-009688?logo=fastapi&logoColor=white)
![Computer Vision](https://img.shields.io/badge/Computer%20Vision-YOLO-111827)
![GitHub](https://img.shields.io/badge/GitHub-Portfolio-181717?logo=github)

## AI, systems, and real-world impact

This repository brings together applied research, machine learning pipelines, backend services, and computer vision experiments. It is structured as a serious engineering and research portfolio: evidence of curiosity, execution, and the discipline required to turn ideas into working systems.

## What’s Inside

| Area | Focus |
|------|-------|
| AI Biodiversity Sundarbans | Climate-aware biodiversity modeling and backend simulation |
| Traffic Congestion System | YOLO-based vehicle detection and traffic analysis |
| Water Quality Prediction | Tabular ML classification and evaluation |
| Backend Services | FastAPI modules for model serving and simulation |

## 👋 Meet the Developer Behind the Code

Hey! I'm Sasanka 👋 — a computer science student and aspiring software engineer who enjoys building practical, well-structured applications that solve real-world problems.

I work with JavaScript, TypeScript, React, and Next.js, and I'm building strength in full-stack development, data structures, and system thinking, with experience in Python, Java, and AI/ML. This repository is more than just a collection of code—it's a documented journey of learning, experimentation, and growth across multiple programming paradigms.

From crafting responsive web interfaces to architecting low-level systems in C, every project here represents a deliberate step toward becoming a well-rounded engineer who understands the full technology stack.

Outside of coding, I enjoy gaming 🎮, planning new projects 📋, and watching anime 🎌.

---

## Repository Snapshot

| Project | Core Problem | Primary Output |
|--------|-------------|----------------|
| AI Biodiversity Sundarbans | Predict biodiversity response under climate variation | Risk-aware biodiversity simulation |
| Traffic Congestion System | Detect vehicles and analyze congestion | YOLO detections and counting workflows |
| Water Quality Prediction | Classify water as potable or non-potable | ML classification notebook and results |
| Backend Services | Serve ML outputs through a clean API | Validation, prediction, and simulation endpoints |

## Project Showcase

### 1. AI Biodiversity Sundarbans

**Short Description**  
Climate-aware biodiversity modeling and simulation for the Sundarbans ecosystem, combining geospatial data, lag feature engineering, and a FastAPI backend.

**Tech Stack**  
Python, pandas, NumPy, GeoPandas, scikit-learn, FastAPI, Pydantic, joblib, Jupyter

**Key Features**
- Predicts biodiversity response from climate scenarios.
- Uses lagged temperature and humidity features.
- Exposes a `/simulate` API for scenario evaluation.
- Returns baseline, prediction, delta, and risk level.
- Connects notebook experimentation to a usable service.

**Model Used**  
Random Forest regression workflow with temporal feature engineering.

**Problem Being Solved**  
Estimating how climate variation can affect species richness in the Sundarbans.

**Outcome / Result**  
Documented validation suggests strong predictive performance, with the best model reporting R² around 0.85 in the methodology notes.

| Link Type | Reference |
|----------|-----------|
| 🔗 Live Demo | LIVE_LINK_HERE |
| 🎥 Demo Video | YOUTUBE_LINK_HERE |
| 📸 Screenshots | ./screenshots/ai-biodiversity-sundarbans.png |

**Backend / Architecture**  
The backend is organized around backend/app.py, backend/schemas.py, backend/model_loader.py, and backend/simulator.py. The API validates a 10-feature climate payload, loads a persisted model, converts the input into model-ready order, and returns a domain-specific risk assessment.

**Project Notes**  
This project blends geospatial data, time-lagged feature engineering, and service design into a single climate-response workflow.

### 2. Traffic Congestion System

**Short Description**  
Computer vision research project for vehicle detection, lane-level counting, and congestion analysis using Ultralytics YOLO experiments.

**Tech Stack**  
Python, Ultralytics, YOLO, OpenCV, PyTorch, Jupyter

**Key Features**
- Trains YOLO-based vehicle detectors.
- Works with a labeled custom dataset.
- Explores traffic counting and congestion patterns.
- Stores training artifacts and model runs for iteration.

**Model Used**  
YOLO experiments, including YOLOv8, YOLOv9, and YOLO11 exploration.

**Problem Being Solved**  
Detecting and counting vehicles accurately enough to support traffic congestion analysis.

**Outcome / Result**  
The notebooks show a full training and evaluation workflow with Ultralytics and custom datasets; insert final detection metrics such as mAP, precision, recall, or FPS once you finalize the preferred run.

| Link Type | Reference |
|----------|-----------|
| 🔗 Live Demo | LIVE_LINK_HERE |
| 🎥 Demo Video | YOUTUBE_LINK_HERE |
| 📸 Screenshots | ./screenshots/traffic-congestion-system.png |

**Key Implementation Notes**  
The project uses Ultralytics YOLO models and notebook-driven experimentation to train, inspect, and compare detection performance on a vehicle dataset.

**Project Notes**  
This work is centered on object detection, class counting, and iterative model selection for traffic analysis.

### 3. Water Quality Prediction

**Short Description**  
Machine learning classification project that predicts whether water is potable based on tabular water-quality measurements.

**Tech Stack**  
Python, pandas, NumPy, scikit-learn, XGBoost, Seaborn, Matplotlib, Jupyter

**Key Features**
- Handles missing values and preprocessing.
- Uses imbalance handling for better classification.
- Compares multiple models and evaluation metrics.
- Focuses on interpretability through visualization.

**Model Used**  
Random Forest and XGBoost classification workflow.

**Problem Being Solved**  
Classifying water samples as potable or non-potable from measured chemical properties.

**Outcome / Result**  
The notebook explores preprocessing, model comparison, and feature importance analysis; add the final accuracy, F1-score, or ROC-AUC once you lock the latest results.

| Link Type | Reference |
|----------|-----------|
| 🔗 Live Demo | LIVE_LINK_HERE |
| 🎥 Demo Video | YOUTUBE_LINK_HERE |
| 📸 Screenshots | ./screenshots/water-quality-prediction.png |

**Key Implementation Notes**  
This project emphasizes data cleaning, imbalance management, and supervised classification on a real-world tabular dataset.

**Project Notes**  
The core value here is disciplined preprocessing and model comparison on a noisy, practical classification problem.

### 4. Backend Services

**Short Description**  
Python backend modules for model loading, schema validation, and simulation logic, designed as a clean API layer for ML-driven workflows.

**Tech Stack**  
Python, FastAPI, Pydantic, pandas, scikit-learn, joblib, CORS middleware

**Key Features**
- FastAPI-based service design.
- Strict request and response schemas.
- Model loading from serialized artifacts.
- Simulation logic that transforms predictions into decision-friendly outputs.

**Architecture / Engineering Notes**  
The backend is split into modules for the API entry point, schema validation, model loading, and simulation logic. This separation keeps the service maintainable and makes the ML pipeline easier to extend.

**How It Works**  
Requests enter the API as structured JSON, are validated by Pydantic, transformed into model-ready data, passed through the ML model, and returned as a clean response that supports downstream interfaces.

| Link Type | Reference |
|----------|-----------|
| 🔗 Live Demo | LIVE_LINK_HERE |
| 🎥 Demo Video | YOUTUBE_LINK_HERE |
| 📸 Screenshots | ./screenshots/backend-services.png |

**Project Notes**  
This module set demonstrates a clean boundary between API delivery, model loading, and simulation logic.

---

## Architecture / Engineering Depth

This repository covers the practical layers of modern applied engineering:

| Capability | Evidence |
|------------|----------|
| Machine learning pipelines | Notebook-based data preparation, training, and evaluation |
| Backend API systems | FastAPI service design with typed schemas |
| Computer vision models | YOLO detection and traffic counting experiments |
| Data preprocessing and model evaluation | Tabular, geospatial, and climate-aware workflows |

It is not a random notebook dump. It is a structured body of work that shows how data, models, and systems can be stitched together into useful software.

## Tech Stack Overview

| Category | Tools |
|----------|-------|
| Languages | Python, C++, JavaScript |
| ML/AI | Scikit-learn, XGBoost, YOLO |
| Frontend | React, Next.js |
| Backend | FastAPI |
| Tools | Git, VS Code |

## Skills Demonstrated

- Problem solving
- ML model building
- Data handling
- Backend development
- System thinking

## Dataset & Models

Large datasets and serialized models are not included in this repository.

External resources and downloadable artifacts can be linked here:

- DATASET_LINK_HERE
- MODEL_DOWNLOAD_LINK_HERE

## How to Run

### 1. Clone the repository

```bash
git clone <YOUR_REPOSITORY_URL>
cd Research
```

### 2. Install requirements

Install the dependencies inside each project folder as needed.

```bash
cd ai_biodiversity_sundarbans
pip install -r requirements.txt

cd ../Water_Quality_Predictions
pip install -r requirements.txt

cd ../traffic - congestion
pip install -r requirement.txt
```

### 3. Run the backend

```bash
cd ai_biodiversity_sundarbans
uvicorn backend.app:app --reload --port 3005
```

### 4. Run the notebooks

```bash
cd ai_biodiversity_sundarbans/notebooks
jupyter notebook
```

Repeat the notebook launch inside the project you want to explore.

## Future Improvements

- Scale models with stronger validation and tuning.
- Deploy APIs to cloud or container platforms.
- Improve UI with more polished dashboards and demos.
- Add real-time systems for streaming or live inference.

## Contribution

1. Fork the repository.
2. Create a feature branch.
3. Make a focused change.
4. Test your update in the relevant project folder.
5. Open a pull request with a clear summary of the work.

## Closing Statement

This repository represents growth through discipline, repetition, and deliberate experimentation. The long-term goal is simple: keep building systems that are technically sound, research-aware, and genuinely useful. That is how engineering becomes credibility, and how credibility becomes impact.