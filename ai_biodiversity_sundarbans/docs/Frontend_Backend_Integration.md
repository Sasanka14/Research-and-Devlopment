# Frontend–Backend Integration

## 1. Integration Architecture

```
┌────────────────────────────────────────────────────────────────────────────┐
│                              FRONTEND (JavaScript)                          │
│  ┌─────────────┐    ┌─────────────┐    ┌─────────────┐    ┌─────────────┐  │
│  │   Sliders   │───►│  Collect    │───►│   fetch()   │───►│   Display   │  │
│  │  (10 params)│    │  getParams  │    │   POST      │    │   Results   │  │
│  └─────────────┘    └─────────────┘    └─────────────┘    └─────────────┘  │
└────────────────────────────────────────────────────────────────────────────┘
                                    │
                                    │ HTTP POST /simulate
                                    │ Content-Type: application/json
                                    ▼
┌────────────────────────────────────────────────────────────────────────────┐
│                              BACKEND (FastAPI)                              │
│  ┌─────────────┐    ┌─────────────┐    ┌─────────────┐    ┌─────────────┐  │
│  │   Validate  │───►│   Order     │───►│   Predict   │───►│   Return    │  │
│  │   Pydantic  │    │   Features  │    │   ML Model  │    │   JSON      │  │
│  └─────────────┘    └─────────────┘    └─────────────┘    └─────────────┘  │
└────────────────────────────────────────────────────────────────────────────┘
```

## 2. Configuration

**Frontend Configuration (`simulator.js`):**
```javascript
const API_BASE_URL = 'http://localhost:3005';
```

**Backend CORS Configuration (`app.py`):**
```python
app.add_middleware(
    CORSMiddleware,
    allow_origins=["*"],
    allow_methods=["*"],
    allow_headers=["*"],
)
```

## 3. Data Collection (Frontend)

The `getParameterValues()` function collects all 10 slider values:

```javascript
function getParameterValues() {
    const params = {};
    
    Object.keys(DEFAULT_VALUES).forEach(key => {
        const slider = document.getElementById(key);
        if (slider) {
            params[key] = parseFloat(slider.value);
        }
    });
    
    return params;
}
```

**Collected Parameters:**
| Parameter        | Slider ID        | Range      |
|------------------|------------------|------------|
| air_temperature  | `air_temperature`| 10–45°C    |
| humidity         | `humidity`       | 0–100%     |
| temp_lag_3       | `temp_lag_3`     | 10–45°C    |
| hum_lag_3        | `hum_lag_3`      | 0–100%     |
| T2M_lag_1        | `T2M_lag_1`      | 10–45°C    |
| RH2M_lag_1       | `RH2M_lag_1`     | 0–100%     |
| T2M_lag_3        | `T2M_lag_3`      | 10–45°C    |
| RH2M_lag_3       | `RH2M_lag_3`     | 0–100%     |
| T2M_lag_6        | `T2M_lag_6`      | 10–45°C    |
| RH2M_lag_6       | `RH2M_lag_6`     | 0–100%     |

## 4. API Request (Frontend → Backend)

```javascript
async function runSimulation() {
    const params = getParameterValues();
    
    const response = await fetch(`${API_BASE_URL}/simulate`, {
        method: 'POST',
        headers: {
            'Content-Type': 'application/json',
        },
        body: JSON.stringify(params)
    });

    const data = await response.json();
    displayResults(data);
}
```

**Request Payload Example:**
```json
{
  "air_temperature": 28,
  "humidity": 70,
  "temp_lag_3": 27,
  "hum_lag_3": 72,
  "T2M_lag_1": 28,
  "RH2M_lag_1": 70,
  "T2M_lag_3": 27,
  "RH2M_lag_3": 72,
  "T2M_lag_6": 26,
  "RH2M_lag_6": 75
}
```

## 5. Backend Processing

**Validation (Pydantic Schema):**
```python
class SimulationInput(BaseModel):
    air_temperature: float = Field(..., ge=10, le=45)
    humidity: float = Field(..., ge=0, le=100)
    # ... remaining fields
```

**Feature Ordering:**
```python
FEATURE_ORDER = [
    "humidity", "air_temperature", "temp_lag_3", "hum_lag_3",
    "T2M_lag_1", "RH2M_lag_1", "T2M_lag_3", "RH2M_lag_3",
    "T2M_lag_6", "RH2M_lag_6"
]

X = pd.DataFrame([[payload[f] for f in FEATURE_ORDER]],
                 columns=FEATURE_ORDER)
```

**ML Prediction:**
```python
prediction = float(model.predict(X)[0])
delta = prediction - BASELINE_SPECIES  # 180.0
```

## 6. API Response (Backend → Frontend)

**Response Format:**
```json
{
  "baseline": 180.0,
  "prediction": 165.5,
  "delta": -14.5,
  "risk_level": "Moderate Risk"
}
```

## 7. Results Rendering (Frontend)

```javascript
function displayResults(results) {
    // Animate metric values
    animateValue(elements.baselineValue, 0, results.baseline, 1000);
    animateValue(elements.predictionValue, 0, results.prediction, 1000);
    animateValue(elements.deltaValue, 0, results.delta, 1000, true);
    
    // Update risk gauge (needle rotation)
    updateRiskGauge(results.delta, results.risk_level);
    
    // Update ecosystem health bar
    updateEcosystemHealth(results.delta);
    
    // Update text interpretation
    updateInterpretation(results);
    
    // Update conservation recommendations list
    updateConservationRecommendations(results);
}
```

## 8. Error Handling

**Frontend Error Handler:**
```javascript
try {
    const response = await fetch(...);
    if (!response.ok) {
        throw new Error(`API Error: ${response.status}`);
    }
} catch (error) {
    showError('Unable to connect to the simulation server.');
}
```

**Backend Error Codes:**
| Code | Trigger                | Frontend Action          |
|------|------------------------|--------------------------|
| 200  | Success                | Display results          |
| 400  | Invalid parameters     | Show validation error    |
| 500  | Model not available    | Show connection error    |

**Error UI:**
```
┌─────────────────────────────────────┐
│          ⚠ Connection Error         │
│                                     │
│  Unable to connect to the           │
│  simulation server.                 │
│                                     │
│         [ 🔄 Retry ]                │
└─────────────────────────────────────┘
```

## 9. UI State Management

| State           | Loading Spinner | Results Panel | Simulate Button |
|-----------------|-----------------|---------------|-----------------|
| Initial         | Hidden          | Hidden        | Enabled         |
| Simulating      | Visible         | Hidden        | Disabled        |
| Success         | Hidden          | Visible       | Enabled         |
| Error           | Hidden          | Error Message | Enabled         |

**State Transitions:**
```javascript
// Before request
elements.loading.style.display = 'block';
elements.simulateBtn.disabled = true;

// After response
elements.loading.style.display = 'none';
elements.resultsContent.classList.add('visible');
elements.simulateBtn.disabled = false;
```

## 10. Integration Workflow Summary

```
1. [User]       Adjusts sliders → triggers input events
2. [Frontend]   getParameterValues() collects 10 params
3. [Frontend]   fetch() POST to /simulate with JSON body
4. [Backend]    Pydantic validates input constraints
5. [Backend]    Features ordered into DataFrame
6. [Backend]    Random Forest model predicts species count
7. [Backend]    Risk level calculated from delta
8. [Backend]    JSON response sent to frontend
9. [Frontend]   displayResults() parses response
10.[Frontend]   UI updated: gauge, metrics, recommendations
```

---

**Key Integration Points:**
- **Endpoint:** `POST http://localhost:3005/simulate`
- **Request:** JSON with 10 float parameters
- **Response:** JSON with baseline, prediction, delta, risk_level
- **CORS:** Fully enabled for local development
