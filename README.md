## 🚀 Research & Development Portfolio

<div align="center">

### Building Systems. Solving Problems. Growing as an Engineer.

[![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Research%20%2B%20Engineering-0F766E?style=flat-square)](#project-showcase)
[![FastAPI](https://img.shields.io/badge/FastAPI-Backend-009688?style=flat-square&logo=fastapi&logoColor=white)](#project-showcase)
[![Computer Vision](https://img.shields.io/badge/Computer%20Vision-YOLO-111827?style=flat-square)](#project-showcase)
[![GitHub](https://img.shields.io/badge/GitHub-Portfolio-181717?style=flat-square&logo=github)](https://github.com/Sasanka14)

**A curated collection of applied AI, backend engineering, and data science projects built with a research-first mindset.**

</div>

---

## 👋 Meet the Developer Behind the Code

Hey! I'm Sasanka 👋 — a computer science student and aspiring software engineer who enjoys building practical, well-structured applications that solve real-world problems.

I work with JavaScript, TypeScript, React, and Next.js, and I'm building strength in full-stack development, data structures, and system thinking, with experience in Python, Java, and AI/ML. This repository is more than just a collection of code—it's a documented journey of learning, experimentation, and growth across multiple programming paradigms.

From crafting responsive web interfaces to architecting low-level systems in C, every project here represents a deliberate step toward becoming a well-rounded engineer who understands the full technology stack.

Outside of coding, I enjoy gaming 🎮, planning new projects 📋, and watching anime 🎌.

---

## 📋 What's Inside?

This portfolio showcases:
- ✅ Applied machine learning pipelines for classification and regression
- ✅ Computer vision experiments for traffic detection and counting
- ✅ FastAPI backend services for model serving and simulation
- ✅ Notebook-based research, preprocessing, and evaluation workflows
- ✅ Clear documentation that connects experimentation to engineering

---

## 🎯 Project Showcase

### 1. AI Biodiversity Sundarbans

A climate-aware biodiversity modeling system for the Sundarbans ecosystem, combining geospatial data, wildlife observations, lag-based feature engineering, and backend simulation logic.

| Aspect | Details |
|--------|---------|
| **Tech Stack** | Python, pandas, NumPy, GeoPandas, scikit-learn, FastAPI, Pydantic, joblib, Jupyter |
| **Model Used** | Random Forest regression workflow with temporal features |
| **Problem Solved** | Predict biodiversity response under changing climate conditions |
| **Key Features** | Climate + wildlife ingestion, lag feature engineering, scenario simulation, risk scoring, FastAPI endpoint |
| **Live Demo** | 🔗 LIVE_LINK_HERE |
| **Demo Video** | 🎥 YOUTUBE_LINK_HERE |
| **Screenshots** | 📸 ./screenshots/ai-biodiversity-sundarbans.png |
| **Outcome** | Best documented model reports R² around 0.85 in the methodology notes |
| **Source Code** | 📂 [ai_biodiversity_sundarbans](./ai_biodiversity_sundarbans) |

**Backend Structure**  
The backend is organized around `backend/app.py`, `backend/schemas.py`, `backend/model_loader.py`, and `backend/simulator.py`. It validates a 10-feature climate payload, loads a persisted model, transforms inputs into the expected feature order, and returns a species-risk response.

---

### 2. Traffic Congestion System

A computer vision project focused on vehicle detection, traffic counting, and congestion analysis using Ultralytics YOLO experiments and custom dataset annotations.

| Aspect | Details |
|--------|---------|
| **Tech Stack** | Python, Ultralytics, YOLO, OpenCV, PyTorch, Jupyter |
| **Model Used** | YOLO experiments, including YOLOv8, YOLOv9, and YOLO11 exploration |
| **Problem Solved** | Detect and count vehicles for congestion reasoning |
| **Key Features** | Vehicle detection, lane-level counting, dataset labeling, iterative training, run tracking |
| **Live Demo** | 🔗 LIVE_LINK_HERE |
| **Demo Video** | 🎥 YOUTUBE_LINK_HERE |
| **Screenshots** | 📸 ./screenshots/traffic-congestion-system.png |
| **Outcome** | Notebook workflow demonstrates model training and evaluation; add final mAP / precision / recall once the preferred run is finalized |
| **Source Code** | 📂 [traffic - congestion](./traffic%20-%20congestion) |

**Research Notes**  
This project explores object detection in a real-world traffic setting, using Ultralytics models to train, inspect, and compare detection performance on a labeled vehicle dataset.

---

### 3. Water Quality Prediction

A tabular machine learning project that predicts whether water is potable using preprocessing, model comparison, and feature analysis.

| Aspect | Details |
|--------|---------|
| **Tech Stack** | Python, pandas, NumPy, scikit-learn, XGBoost, Seaborn, Matplotlib, Jupyter |
| **Model Used** | Random Forest and XGBoost classification workflow |
| **Problem Solved** | Classify water as potable or non-potable from measured features |
| **Key Features** | Missing value handling, imbalance correction, model comparison, feature importance analysis, visualization |
| **Live Demo** | 🔗 LIVE_LINK_HERE |
| **Demo Video** | 🎥 YOUTUBE_LINK_HERE |
| **Screenshots** | 📸 ./screenshots/water-quality-prediction.png |
| **Outcome** | Notebook tracks preprocessing and evaluation; add final accuracy, F1-score, or ROC-AUC once locked |
| **Source Code** | 📂 [Water_Quality_Predictions](./Water_Quality_Predictions) |

**Research Notes**  
The project emphasizes disciplined preprocessing and supervised classification on a noisy real-world dataset, with model comparison used to identify the best-performing approach.

---

## 🧠 Architecture / Engineering Depth

This repository demonstrates core engineering capabilities:

- **Machine Learning pipelines** for preprocessing, training, evaluation, and persistence
- **Backend API systems** for model serving and simulation (integrated with AI Biodiversity Sundarbans)
- **Computer Vision models** for detection, counting, and traffic understanding
- **Data preprocessing and model evaluation** across tabular, geospatial, and climate-driven problems

The result is not a loose set of notebooks. It is a portfolio of systems that connect research with practical software delivery.

---

## 🛠 Tech Stack Overview

| Category | Tools |
|----------|-------|
| **Languages** | Python, C++, JavaScript |
| **ML/AI** | Scikit-learn, XGBoost, YOLO |
| **Frontend** | React, Next.js |
| **Backend** | FastAPI |
| **Tools** | Git, VS Code |

---

## 💡 Skills Demonstrated

- Problem solving
- ML model building
- Data handling
- Backend development
- System thinking

---

## 📚 Dataset & Models

Large datasets and serialized models are not included in this repository.

External references and downloadable artifacts can be linked here:

- DATASET_LINK_HERE
- MODEL_DOWNLOAD_LINK_HERE

---

## 🚀 How to Run

### Clone the repository

```bash
git clone <YOUR_REPOSITORY_URL>
cd Research
```

### Install dependencies

Install dependencies inside the relevant project folder.

```bash
cd ai_biodiversity_sundarbans
pip install -r requirements.txt

cd ../Water_Quality_Predictions
pip install -r requirements.txt

cd ../traffic - congestion
pip install -r requirement.txt
```

### Run the backend

```bash
cd ai_biodiversity_sundarbans
uvicorn backend.app:app --reload --port 3005
```

### Run the notebooks

```bash
cd ai_biodiversity_sundarbans/notebooks
jupyter notebook
```

Open the other notebook folders from their respective project directories and launch Jupyter the same way.

---

## 🔭 Future Improvements

- Scale models with stronger validation and tuning
- Deploy APIs to cloud or container platforms
- Improve UI with richer dashboards and demo surfaces
- Add real-time systems for live inference and streaming use cases

---

## 🤝 Contributing

This repository is primarily a portfolio, but I welcome feedback and suggestions:

1. **Found a bug?** → Open an issue with reproduction steps
2. **Have an improvement?** → Fork, commit, and submit a pull request
3. **Want to collaborate?** → Reach out at [portfolio link / email]
4. **Suggestions?** → Discussions and issues are always welcome

### Code Style Guidelines
- Use meaningful variable names
- Comment complex logic
- Follow language-specific conventions
- Write clean, maintainable code

---

## 📞 Get in Touch

- 🌐 **Portfolio**: [sasankawrites.in](https://sasankawrites.in/)
- 💼 **LinkedIn**: [linkedin.com/in/sasankawrites](https://linkedin.com/in/sasankawrites)
- 🐙 **GitHub**: [github.com/Sasanka14](https://github.com/Sasanka14)
- 📧 **Email**: [sasankawrites.14@gmail.com](mailto:sasankawrites.14@gmail.com)
- 🎨 **Instagram**: [@sashank.codes_](https://instagram.com/sashank.codes_)

---

## 📄 License

This repository is licensed under the **MIT License** — see [`LICENSE`](./LICENSE) file for details.

You're free to fork, modify, and learn from these projects. If you find them helpful, a star ⭐ is appreciated!

---

<div align="center">

### 🌟 Building the Future, One Line of Code at a Time

*This repository represents more than just projects—it's a commitment to continuous learning, architectural thinking, and engineering excellence.*

**Thank you for visiting! Happy coding! 🚀**

</div>

---

### 📊 Repository Stats

```
Total Projects:        3
Primary Languages:     Python, JavaScript, HTML, CSS
Jupyter Notebooks:     8
Total Lines of Code:   4,381
  ├─ HTML:            1,443 lines
  ├─ CSS:             2,010 lines
  ├─ JavaScript:        746 lines
  └─ Python:            182 lines
Live Deployments:      1 (AI Biodiversity Backend)
Systems Built:         3 (ML Pipeline + Backend + CV)
Research Notebooks:    8
```

---

*Last Updated: April 8, 2026*