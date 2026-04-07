# Research and Development

![Python](https://img.shields.io/badge/Python-3.11+-3776AB?logo=python&logoColor=white)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Research%20%2B%20Engineering-0F766E)
![Computer Vision](https://img.shields.io/badge/Computer%20Vision-YOLO%20%7C%20MOT-111827)
![FastAPI](https://img.shields.io/badge/FastAPI-Backend-009688?logo=fastapi&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-F37626?logo=jupyter&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-Portfolio-181717?logo=github)

## A research-driven engineering portfolio for real-world AI systems

This repository brings together experiments, prototypes, and applied systems across machine learning, computer vision, backend engineering, and data science. It reflects a practical research mindset: build with intent, evaluate with rigor, and keep the work connected to problems that matter in the real world.

I am an aspiring engineer focused on turning data, models, and APIs into useful systems. The projects here are designed to show not only technical curiosity, but also the ability to structure experiments, reason about model behavior, and translate ideas into working software.

## Project Showcase

### 1. AI Biodiversity Sundarbans

**Short Description**  
Climate-driven biodiversity simulation for the Sundarbans ecosystem, combining geospatial data, wildlife observations, lag-based feature engineering, and a FastAPI prediction service.

**Tech Stack**  
Python, pandas, NumPy, GeoPandas, scikit-learn, FastAPI, Pydantic, joblib, Jupyter

**Key Features**
- Ingests climate, wildlife, and mangrove boundary data.
- Engineers temporal lag features to capture delayed ecological effects.
- Serves predictions through a FastAPI `/simulate` endpoint.
- Computes risk levels from predicted species richness changes.
- Connects backend logic with a browser-based simulator and documentation pages.

**Model**  
Random Forest-style regression workflow with lagged climate inputs and scenario-based biodiversity forecasting.

**Demo Video**  
YOUTUBE_LINK_HERE

**Screenshots**  
SCREENSHOT_PATH

**Results**  
R²: 0.85, MAE: 12.3, RMSE: 16.8 for the best documented model in the methodology notes. Replace with the latest validated metrics if the model is retrained.

**Backend Design**
- `backend/app.py` exposes the main FastAPI application.
- `backend/schemas.py` validates the 10-feature simulation payload.
- `backend/model_loader.py` loads the serialized model artifact.
- `backend/simulator.py` orders inputs, predicts species richness, and maps the delta to a risk level.

**How It Works**
1. The frontend collects climate parameters and lag values.
2. The API validates the request with Pydantic.
3. The backend converts the payload into the model’s feature order.
4. The model predicts species richness.
5. The simulator calculates delta from the baseline and returns a risk classification.

---

### 2. Traffic Congestion System

**Short Description**  
Computer vision research project for vehicle detection, traffic counting, and congestion analysis using Ultralytics YOLO experiments and custom dataset annotations.

**Tech Stack**  
Python, Ultralytics, YOLO, OpenCV, Jupyter, PyTorch, computer vision tooling

**Key Features**
- Trains and evaluates YOLO-based vehicle detection models.
- Works with a custom Roboflow-style image dataset.
- Explores lane-wise vehicle counting and MOT-assisted traffic analysis.
- Stores runs, predictions, and training artifacts for iterative experimentation.

**Model**  
Ultralytics YOLO experiments, including YOLOv8 and YOLOv9 variants, with additional notes on YOLO11 exploration.

**Demo Video**  
YOUTUBE_LINK_HERE

**Screenshots**  
SCREENSHOT_PATH

**Results**  
Placeholder: mAP / precision / recall / FPS should be added from the best trained run once you finalize the preferred experiment.

**How It Works**
- Notebook workflows load a labeled vehicle dataset.
- A YOLO model is initialized through Ultralytics.
- The model is trained or fine-tuned on the dataset.
- Predictions are used for vehicle counting and congestion reasoning.
- Results and weights are stored under the project assets and run directories.

---

### 3. Water Quality Predictions

**Short Description**  
Machine learning project for predicting water potability from tabular water-quality features, with emphasis on preprocessing, imbalance handling, and model comparison.

**Tech Stack**  
Python, pandas, NumPy, scikit-learn, XGBoost, Seaborn, Matplotlib, Jupyter

**Key Features**
- Predicts whether water is potable or unsafe.
- Handles missing values through preprocessing.
- Addresses class imbalance with SMOTE.
- Compares multiple classifiers and inspects feature importance.
- Provides notebook-based analysis and visualization.

**Model**  
Random Forest and XGBoost classification workflow with preprocessing, resampling, and evaluation.

**Demo Video**  
YOUTUBE_LINK_HERE

**Screenshots**  
SCREENSHOT_PATH

**Results**  
Placeholder: add final accuracy, F1-score, ROC-AUC, or cross-validation scores here.

**How It Works**
1. The dataset is loaded and cleaned.
2. Missing values are imputed and imbalance is corrected.
3. Models are trained and compared.
4. Performance metrics and feature importance are reviewed.
5. The notebook records the best-performing configuration.

---

### 4. Backend APIs

**Short Description**  
Python backend architecture for climate simulation and AI-assisted predictions, built to demonstrate API design, schema validation, model loading, and service-oriented thinking.

**Tech Stack**  
Python, FastAPI, Pydantic, joblib, pandas, scikit-learn, CORS middleware

**Key Features**
- Clean REST API design with health and simulation endpoints.
- Input validation through typed schemas.
- Model loading from a persisted artifact.
- Feature ordering and request-to-model transformation.
- Risk scoring logic for interpretability.

**System Design**
- `models` stores serialized ML artifacts.
- `schemas` defines request and response contracts.
- `simulator` converts model outputs into domain-specific interpretation.
- `app.py` acts as the API entry point and CORS-enabled service layer.

**How It Works**
- A request enters the API as structured JSON.
- Pydantic validates the feature values.
- The backend builds a model-ready dataframe.
- The trained model produces a prediction.
- The service returns a clean JSON response with baseline, prediction, delta, and risk level.

**Demo Video**  
YOUTUBE_LINK_HERE

**Screenshots**  
SCREENSHOT_PATH

**Results**  
Placeholder: add endpoint latency, response example, or integration screenshot if available.

## Tech Stack Overview

**Languages**  
Python, SQL-style tabular analysis, notebook-based experimentation

**ML / AI**  
scikit-learn, XGBoost, YOLO, Random Forest, regression, classification, feature engineering

**Backend**  
FastAPI, Pydantic, CORS middleware, JSON APIs, joblib model loading

**Data / CV / Analysis**  
pandas, NumPy, GeoPandas, Matplotlib, Seaborn, OpenCV, Ultralytics

**Tools**  
Git, GitHub, Jupyter, notebooks, dataset annotation workflows

## Engineering Depth

This repository demonstrates more than isolated notebooks. It shows the shape of an engineer who can work across the full problem stack:

- Real-world problem solving with ecological, environmental, and infrastructure use cases.
- Machine learning pipelines that move from data cleaning to validation to model persistence.
- Computer vision systems built around object detection and traffic understanding.
- Backend architecture that turns models into accessible services.
- Documentation discipline that makes the work easier to inspect, reuse, and extend.

## How To Run

The projects are organized as separate workspaces, so install dependencies and run them from the relevant project directory.

### 1. Install dependencies

```bash
cd ai_biodiversity_sundarbans
pip install -r requirements.txt

cd ../Water_Quality_Predictions
pip install -r requirements.txt

cd "../traffic - congestion"
pip install -r requirement.txt
```

### 2. Run the biodiversity backend

```bash
cd ai_biodiversity_sundarbans
uvicorn backend.app:app --reload --port 3005
```

If your local entry point is the package-style app instead, use the FastAPI module that exposes the same service contract.

### 3. Run the notebooks

```bash
cd ai_biodiversity_sundarbans/notebooks
jupyter notebook
```

For the other projects, open the relevant notebook folder and launch Jupyter from there.

## Future Improvements

- Model optimization through more robust tuning, validation, and error analysis.
- Deployment of selected projects as APIs or cloud-hosted services.
- UI integration for richer dashboards, demos, and decision support.
- Automated evaluation scripts for reproducible experiment tracking.
- Stronger packaging of notebooks into reusable modules.

## Contribution

Contributions are welcome. A simple workflow is enough:

1. Fork the repository.
2. Create a feature branch.
3. Make a focused improvement.
4. Test the change in the relevant project folder.
5. Open a pull request with a clear summary of what changed and why.

## Closing Statement

This repository is a record of steady technical growth: from experiments to systems, from prediction to interpretation, from data to usable software. The goal is not just to build models, but to build tools that are reliable, understandable, and worth using. That is the kind of engineering mindset that turns research into impact.