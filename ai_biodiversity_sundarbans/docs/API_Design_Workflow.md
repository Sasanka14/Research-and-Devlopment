# API Design and Workflow

## 1. Architecture Overview

```
┌─────────────────┐     HTTP POST     ┌─────────────────┐     Prediction     ┌─────────────────┐
│    Frontend     │ ───────────────►  │   FastAPI       │ ────────────────►  │   ML Model      │
│  (JavaScript)   │ ◄─────────────── │   Backend       │ ◄──────────────── │  (Random Forest)│
│                 │   JSON Response   │   Port: 3005    │      Result        │                 │
└─────────────────┘                   └─────────────────┘                    └─────────────────┘
```

## 2. API Endpoint

| Method | Endpoint    | Description                          |
|--------|-------------|--------------------------------------|
| POST   | `/simulate` | Run biodiversity prediction          |
| GET    | `/`         | Health check                         |

**Base URL:** `http://localhost:3005`

## 3. Request Schema (SimulationInput)

```json
{
  "air_temperature": 28.5,      // Current temp (10-45°C)
  "humidity": 75.0,             // Current humidity (0-100%)
  "temp_lag_3": 27.8,           // Temperature 3 months ago
  "hum_lag_3": 72.0,            // Humidity 3 months ago
  "T2M_lag_1": 29.0,            // NASA POWER temp - 1 month lag
  "RH2M_lag_1": 74.0,           // NASA POWER humidity - 1 month lag
  "T2M_lag_3": 28.2,            // NASA POWER temp - 3 month lag
  "RH2M_lag_3": 71.5,           // NASA POWER humidity - 3 month lag
  "T2M_lag_6": 26.5,            // NASA POWER temp - 6 month lag
  "RH2M_lag_6": 68.0            // NASA POWER humidity - 6 month lag
}
```

## 4. Response Schema (SimulationOutput)

```json
{
  "baseline": 180.0,            // Reference species count
  "prediction": 165.5,          // Predicted species count
  "delta": -14.5,               // Change from baseline
  "risk_level": "Moderate Risk" // Risk classification
}
```

## 5. Workflow Sequence

```
┌──────────┐     ┌──────────┐     ┌──────────┐     ┌──────────┐     ┌──────────┐
│  User    │────►│  Input   │────►│  API     │────►│  Model   │────►│  Display │
│  Adjust  │     │  Validate│     │  Process │     │  Predict │     │  Results │
│  Sliders │     │  (Pydantic)   │  (Backend)│     │  (RF)    │     │  (UI)    │
└──────────┘     └──────────┘     └──────────┘     └──────────┘     └──────────┘
     │                 │                │                │                │
     ▼                 ▼                ▼                ▼                ▼
  10 params      Constraint       JSON to ML       Species         Risk Gauge +
  adjusted       validation       DataFrame        prediction      Recommendations
```

**Step-by-Step:**

1. **User Input**: Adjusts climate parameters via sliders
2. **Validation**: Pydantic validates constraints (temp: 10-45°C, humidity: 0-100%)
3. **Feature Ordering**: Backend arranges 10 features in model-expected order
4. **ML Prediction**: Random Forest model predicts species count
5. **Risk Classification**: Delta calculated → Risk level assigned
6. **Response Delivery**: JSON returned to frontend → UI updated

## 6. Risk Classification Logic

| Delta Range       | Risk Level    |
|-------------------|---------------|
| δ < -15           | High Risk     |
| -15 ≤ δ < -5      | Moderate Risk |
| δ ≥ -5            | Low Risk      |

## 7. Error Handling

| HTTP Code | Scenario                  | Response                              |
|-----------|---------------------------|---------------------------------------|
| 200       | Success                   | SimulationOutput JSON                 |
| 400       | Invalid parameters        | `{"detail": "Simulation failed: ..."}` |
| 500       | Model not loaded          | `{"detail": "Model not available"}`   |

## 8. CORS Configuration

```python
app.add_middleware(
    CORSMiddleware,
    allow_origins=["*"],
    allow_methods=["*"],
    allow_headers=["*"],
)
```

Enables cross-origin requests from any frontend domain.

## 9. Technology Stack

| Component      | Technology        |
|----------------|-------------------|
| Framework      | FastAPI           |
| Validation     | Pydantic          |
| ML Model       | scikit-learn RF   |
| Data Handling  | pandas DataFrame  |
| Frontend       | Vanilla JavaScript|

---

**Summary:** The API follows a clean REST design with a single predictive endpoint. User inputs 10 climate parameters → backend validates and orders features → ML model predicts species count → risk level computed → JSON response rendered as interactive visualizations.
