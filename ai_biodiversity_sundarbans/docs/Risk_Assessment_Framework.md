# Risk Assessment Framework

**Sundarbans Biodiversity AI — Risk Classification System**  
**Date:** February 2026

---

## Table of Contents

1. [Framework Overview](#1-framework-overview)
2. [Risk Classification Logic](#2-risk-classification-logic)
3. [Risk Level Definitions](#3-risk-level-definitions)
4. [Ecosystem Health Index](#4-ecosystem-health-index)
5. [Visual Risk Indicators](#5-visual-risk-indicators)
6. [Conservation Action Matrix](#6-conservation-action-matrix)
7. [Interpretation Guidelines](#7-interpretation-guidelines)

---

## 1. Framework Overview

### 1.1 Purpose

The Risk Assessment Framework translates ML model predictions into actionable conservation guidance. It converts numerical species richness predictions into categorical risk levels that inform decision-making.

### 1.2 Core Concept

```
Climate Parameters → ML Model → Species Prediction → Delta Calculation → Risk Level
                                                           ↓
                                              Conservation Recommendations
```

### 1.3 Key Components

| Component | Purpose |
|-----------|---------|
| **Baseline** | Reference species richness (180 species) |
| **Prediction** | ML model output for given climate scenario |
| **Delta (Δ)** | Difference from baseline (prediction - baseline) |
| **Risk Level** | Categorical assessment (Low/Moderate/High) |
| **Health Index** | Percentage-based ecosystem condition |

---

## 2. Risk Classification Logic

### 2.1 Delta Calculation

The fundamental metric is the **Delta (Δ)** — the deviation from baseline biodiversity:

```python
BASELINE_SPECIES = 180.0  # Reference baseline

prediction = model.predict(X)
delta = prediction - BASELINE_SPECIES
```

**Interpretation:**
- **Positive Delta (Δ > 0):** Species richness exceeds baseline → Healthy ecosystem
- **Negative Delta (Δ < 0):** Species richness below baseline → Ecosystem stress

### 2.2 Risk Threshold Logic

```python
def calculate_risk_level(delta):
    if delta < -15:
        risk = "High Risk"
    elif delta < -5:
        risk = "Moderate Risk"
    else:
        risk = "Low Risk"
    return risk
```

### 2.3 Risk Threshold Diagram

```
Delta (Δ) Scale — Species Richness Change from Baseline
═══════════════════════════════════════════════════════════════════════════════

         HIGH RISK          MODERATE RISK           LOW RISK
      ◄─────────────────►◄─────────────────►◄─────────────────────────────────►
      
  -30   -25   -20   -15   -10    -5     0    +5    +10   +15   +20   +25   +30
   │     │     │     │     │     │     │     │     │     │     │     │     │
   ▼     ▼     ▼     ▼     ▼     ▼     ▼     ▼     ▼     ▼     ▼     ▼     ▼
   
  ████████████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░
        CRITICAL          CAUTION            STABLE          THRIVING
        
   │←────────────────→│←──────────────→│←────────────────────────────────────→│
         Δ < -15           -15 ≤ Δ < -5              Δ ≥ -5

```

---

## 3. Risk Level Definitions

### 3.1 Three-Tier Risk Classification

```
╔══════════════════════════════════════════════════════════════════════════════╗
║                           RISK LEVEL CLASSIFICATION                          ║
╠══════════════════════════════════════════════════════════════════════════════╣
║                                                                              ║
║  ┌────────────────────────────────────────────────────────────────────────┐  ║
║  │                            LOW RISK                                    │  ║
║  │                          (Delta ≥ -5)                                  │  ║
║  │                                                                        │  ║
║  │  • Ecosystem demonstrates resilience                                   │  ║
║  │  • Species richness within acceptable range                            │  ║
║  │  • Current conservation efforts are sufficient                         │  ║
║  │  • Continue routine monitoring                                         │  ║
║  └────────────────────────────────────────────────────────────────────────┘  ║
║                                  │                                           ║
║                                  ▼                                           ║
║  ┌────────────────────────────────────────────────────────────────────────┐  ║
║  │                         MODERATE RISK                                  │  ║
║  │                      (-15 ≤ Delta < -5)                                │  ║
║  │                                                                        │  ║
║  │  • Elevated ecosystem pressure detected                                │  ║
║  │  • Species richness notably affected                                   │  ║
║  │  • Implement adaptive management strategies                            │  ║
║  │  • Increase monitoring frequency                                       │  ║
║  └────────────────────────────────────────────────────────────────────────┘  ║
║                                  │                                           ║
║                                  ▼                                           ║
║  ┌────────────────────────────────────────────────────────────────────────┐  ║
║  │                           HIGH RISK                                    │  ║
║  │                          (Delta < -15)                                 │  ║
║  │                                                                        │  ║
║  │  • Critical ecosystem stress detected                                  │  ║
║  │  • Severe threat to species diversity                                  │  ║
║  │  • Immediate conservation intervention required                        │  ║
║  │  • Activate emergency protocols                                        │  ║
║  └────────────────────────────────────────────────────────────────────────┘  ║
║                                                                              ║
╚══════════════════════════════════════════════════════════════════════════════╝
```

### 3.2 Detailed Risk Characteristics

#### LOW RISK (Δ ≥ -5)

| Attribute | Description |
|-----------|-------------|
| **Species Loss** | ≤ 5 species below baseline |
| **Percentage Change** | ≤ 2.8% decline |
| **Ecosystem State** | Stable / Resilient |
| **Indicator** | Green |
| **Action Level** | Standard Operations |

**System Message:**
> "Ecosystem demonstrates resilience to the simulated conditions. Current conservation efforts appear sufficient. Continue monitoring for early warning signs."

#### MODERATE RISK (-15 ≤ Δ < -5)

| Attribute | Description |
|-----------|-------------|
| **Species Loss** | 6-15 species below baseline |
| **Percentage Change** | 2.8% - 8.3% decline |
| **Ecosystem State** | Stressed / Pressured |
| **Indicator** | Yellow/Orange |
| **Action Level** | Enhanced Monitoring |

**System Message:**
> "Moderate ecosystem pressure identified. Species richness is notably affected under these conditions. Implement adaptive management strategies and increase monitoring frequency."

#### HIGH RISK (Δ < -15)

| Attribute | Description |
|-----------|-------------|
| **Species Loss** | > 15 species below baseline |
| **Percentage Change** | > 8.3% decline |
| **Ecosystem State** | Critical / Endangered |
| **Indicator** | Red |
| **Action Level** | Emergency Response |

**System Message:**
> "Critical ecosystem stress detected. The simulated climate conditions pose a severe threat to species diversity. Immediate conservation intervention is strongly recommended."

---

## 4. Ecosystem Health Index

### 4.1 Health Calculation Algorithm

The Ecosystem Health Index converts delta into a 0-100% scale:

```javascript
function calculateEcosystemHealth(delta) {
    let health;
    
    if (delta >= 0) {
        // Positive delta = full health
        health = 100;
    } else if (delta < -20) {
        // Severe decline = minimum threshold
        health = Math.max(10, 20 + delta);
    } else {
        // Linear scaling: each -1 delta = -4% health
        health = 100 + (delta * 4);
    }
    
    // Clamp between 10-100%
    return Math.max(10, Math.min(100, health));
}
```

### 4.2 Health Index Scale

```
Ecosystem Health Index (0-100%)
═══════════════════════════════════════════════════════════════════════════════

Delta (Δ)    Health %    Visual Bar                              Status
────────────────────────────────────────────────────────────────────────────────
  +10         100%       ██████████████████████████████████████  THRIVING
   +5         100%       ██████████████████████████████████████  EXCELLENT
    0         100%       ██████████████████████████████████████  HEALTHY
   -5          80%       ██████████████████████████████░░░░░░░░  STABLE
  -10          60%       ████████████████████████░░░░░░░░░░░░░░  STRESSED
  -15          40%       ████████████████░░░░░░░░░░░░░░░░░░░░░░  CRITICAL
  -20          20%       ████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░  SEVERE
  -25          10%       ████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░  MINIMUM

                         0%              50%              100%
```

### 4.3 Health-Risk Correlation

| Health Range | Risk Level | Ecosystem State |
|--------------|------------|-----------------|
| 80-100% | Low Risk | Resilient, thriving |
| 40-79% | Moderate Risk | Stressed, needs attention |
| 10-39% | High Risk | Critical, emergency response |

---

## 5. Visual Risk Indicators

### 5.1 Risk Gauge (Needle Display)

The UI displays a gauge where the needle position indicates risk severity:

```javascript
function calculateGaugeAngle(delta, riskLevel) {
    // Angle range: -90° (Low) to +90° (High)
    let angle;
    
    if (delta > 0) {
        angle = -80;  // Very low risk zone
    } else if (delta > -5) {
        // Low risk: -80° to -20°
        angle = -60 + ((-delta) / 5) * 40;
    } else if (delta > -15) {
        // Moderate risk: -20° to +30°
        angle = -20 + ((-delta - 5) / 10) * 50;
    } else {
        // High risk: +30° to +80°
        angle = Math.min(80, 30 + ((-delta - 15) / 10) * 50);
    }
    
    return angle;
}
```

### 5.2 Gauge Visualization

```
                     Risk Assessment Gauge
═══════════════════════════════════════════════════════════════

                          HIGH RISK
                             ▲
                            ╱│╲
                           ╱ │ ╲
                          ╱  │  ╲
                         ╱   │   ╲
                        ╱    │    ╲
              MODERATE ╱     │     ╲ MODERATE
                      ╱      │      ╲
                     ╱       │       ╲
                    ╱        │        ╲
           LOW    ╱__________|__________╲    LOW
          RISK   ╱                        ╲   RISK
                ╱__________________________╲
                
               -90°        0°          +90°
                │           │            │
             LOW RISK   MODERATE     HIGH RISK
             (Safe)     (Caution)    (Critical)

   Needle Position Examples:
   ────────────────────────────────────────────────────────────
   Delta = +5   →  Angle = -80°  (Far left, very safe)
   Delta = -3   →  Angle = -36°  (Left zone, low risk)
   Delta = -10  →  Angle = +5°   (Center, moderate risk)
   Delta = -20  →  Angle = +55°  (Right zone, high risk)
   Delta = -30  →  Angle = +80°  (Far right, extreme risk)
```

### 5.3 Color Coding System

| Risk Level | Primary Color | Badge Color | Hex Code |
|------------|---------------|-------------|----------|
| Low Risk | Green | Light Green Background | #22c55e |
| Moderate Risk | Orange/Yellow | Yellow Background | #f59e0b |
| High Risk | Red | Red Background | #ef4444 |

---

## 6. Conservation Action Matrix

### 6.1 Risk-Based Recommendations

```
╔══════════════════════════════════════════════════════════════════════════════╗
║                      CONSERVATION ACTION MATRIX                              ║
╠════════════════╦═════════════════════════════════════════════════════════════╣
║                ║                                                             ║
║   LOW RISK     ║  ✓ Maintain current conservation efforts                    ║
║   (Δ ≥ -5)     ║  ✓ Continue long-term ecological data collection            ║
║                ║  ✓ Expand community education programs                      ║
║                ║  ✓ Focus on habitat connectivity enhancement                ║
║                ║                                                             ║
╠════════════════╬═════════════════════════════════════════════════════════════╣
║                ║                                                             ║
║  MODERATE      ║  ⚠ Enhance existing conservation buffer zones               ║
║  RISK          ║  ⚠ Continue mangrove nursery development                    ║
║  (-15≤Δ<-5)    ║  ⚠ Increase wildlife monitoring frequency                   ║
║                ║  ⚠ Implement sustainable water management                   ║
║                ║                                                             ║
╠════════════════╬═════════════════════════════════════════════════════════════╣
║                ║                                                             ║
║   HIGH RISK    ║  ⛔ Implement emergency habitat protection immediately      ║
║   (Δ < -15)    ║  ⛔ Increase mangrove reforestation in vulnerable zones     ║
║                ║  ⛔ Monitor water salinity & establish freshwater reserves  ║
║                ║  ⛔ Activate species relocation programs                    ║
║                ║  ⛔ Engage communities in rapid response initiatives        ║
║                ║                                                             ║
╚════════════════╩═════════════════════════════════════════════════════════════╝
```

### 6.2 Detailed Action Items

#### LOW RISK Actions

| Icon | Action | Priority |
|------|--------|----------|
| ✓ | Maintain current conservation efforts and monitoring schedules | Standard |
| 📊 | Continue long-term ecological data collection | Ongoing |
| 🎓 | Expand community education and eco-tourism programs | Enhancement |
| 🌿 | Focus on habitat connectivity enhancement projects | Strategic |

#### MODERATE RISK Actions

| Icon | Action | Priority |
|------|--------|----------|
| 🛡️ | Enhance existing conservation buffer zones | High |
| 🌱 | Continue mangrove nursery development programs | High |
| 🔭 | Increase wildlife monitoring frequency in sensitive areas | Elevated |
| 💧 | Implement sustainable water management practices | Medium |

#### HIGH RISK Actions

| Icon | Action | Priority |
|------|--------|----------|
| ⚠️ | Implement emergency habitat protection protocols immediately | CRITICAL |
| 🌳 | Increase mangrove reforestation efforts in vulnerable zones | CRITICAL |
| 🌊 | Monitor water salinity levels and establish freshwater reserves | URGENT |
| 🐟 | Activate species relocation programs for endangered fauna | URGENT |
| 👥 | Engage local communities in rapid response conservation initiatives | HIGH |

---

## 7. Interpretation Guidelines

### 7.1 Output Interpretation Template

The system generates human-readable interpretations following this pattern:

```
Based on the simulated climate parameters, our AI model predicts a species 
richness index of [PREDICTION], compared to the baseline of [BASELINE]. 
This represents a [DELTA%]% [increase/decrease] in biodiversity 
(Δ = [+/-][DELTA]).

[RISK-SPECIFIC STATEMENT]
```

### 7.2 Risk-Specific Statements

**LOW RISK:**
> "The mangrove ecosystem shows strong adaptive capacity under these conditions. Biodiversity indicators remain within healthy ranges."

**MODERATE RISK:**
> "Some species may experience habitat pressure. Proactive conservation measures can help mitigate potential impacts."

**HIGH RISK:**
> "The ecosystem is under significant stress. Key indicator species may face population decline, and habitat connectivity could be compromised."

### 7.3 Example Interpretations

#### Scenario 1: Low Risk
```
Input:  Temperature = 28°C, Humidity = 70%
Output: Prediction = 182.5, Baseline = 180.0
Delta:  +2.5 (Δ = +2.50)
Risk:   LOW RISK

Interpretation:
"Based on the simulated climate parameters, our AI model predicts a species 
richness index of 182.50, compared to the baseline of 180.00. This represents 
a 1.4% increase in biodiversity (Δ = +2.50). The mangrove ecosystem shows 
strong adaptive capacity under these conditions. Biodiversity indicators 
remain within healthy ranges."
```

#### Scenario 2: Moderate Risk
```
Input:  Temperature = 34°C, Humidity = 55%
Output: Prediction = 168.5, Baseline = 180.0
Delta:  -11.5 (Δ = -11.50)
Risk:   MODERATE RISK

Interpretation:
"Based on the simulated climate parameters, our AI model predicts a species 
richness index of 168.50, compared to the baseline of 180.00. This represents 
a 6.4% decrease in biodiversity (Δ = -11.50). Some species may experience 
habitat pressure. Proactive conservation measures can help mitigate potential 
impacts."
```

#### Scenario 3: High Risk
```
Input:  Temperature = 38°C, Humidity = 45%
Output: Prediction = 155.2, Baseline = 180.0
Delta:  -24.8 (Δ = -24.80)
Risk:   HIGH RISK

Interpretation:
"Based on the simulated climate parameters, our AI model predicts a species 
richness index of 155.20, compared to the baseline of 180.00. This represents 
a 13.8% decrease in biodiversity (Δ = -24.80). The ecosystem is under 
significant stress. Key indicator species may face population decline, and 
habitat connectivity could be compromised."
```

---

## 8. Framework Summary

### 8.1 Quick Reference Card

```
╔══════════════════════════════════════════════════════════════════════════════╗
║                    RISK ASSESSMENT QUICK REFERENCE                           ║
╠══════════════════════════════════════════════════════════════════════════════╣
║                                                                              ║
║  BASELINE: 180 species                                                       ║
║                                                                              ║
║  ┌─────────────┬────────────┬─────────────┬───────────────────────────────┐  ║
║  │ Risk Level  │ Delta (Δ)  │ Health %    │ Response                      │  ║
║  ├─────────────┼────────────┼─────────────┼───────────────────────────────┤  ║
║  │ LOW         │ Δ ≥ -5     │ 80-100%     │ Standard monitoring           │  ║
║  │ MODERATE    │ -15≤Δ<-5   │ 40-79%      │ Adaptive management           │  ║
║  │ HIGH        │ Δ < -15    │ 10-39%      │ Emergency intervention        │  ║
║  └─────────────┴────────────┴─────────────┴───────────────────────────────┘  ║
║                                                                              ║
║  FORMULA:                                                                    ║
║  Delta = Prediction - 180.0                                                  ║
║  Health = max(10, min(100, 100 + delta × 4))                                 ║
║                                                                              ║
╚══════════════════════════════════════════════════════════════════════════════╝
```

### 8.2 Decision Flow

```
                         ┌─────────────────────┐
                         │  Input Climate      │
                         │  Parameters         │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │  ML Model           │
                         │  Prediction         │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │  Calculate Delta    │
                         │  Δ = pred - 180     │
                         └──────────┬──────────┘
                                    │
                    ┌───────────────┼───────────────┐
                    │               │               │
                    ▼               ▼               ▼
              ┌───────────┐  ┌───────────┐  ┌───────────┐
              │  Δ ≥ -5   │  │ -15≤Δ<-5  │  │  Δ < -15  │
              │           │  │           │  │           │
              │ LOW RISK  │  │ MODERATE  │  │ HIGH RISK │
              │   🟢      │  │   🟡      │  │   🔴      │
              └─────┬─────┘  └─────┬─────┘  └─────┬─────┘
                    │              │              │
                    ▼              ▼              ▼
              ┌───────────┐  ┌───────────┐  ┌───────────┐
              │ Standard  │  │ Enhanced  │  │ Emergency │
              │ Monitoring│  │ Management│  │ Response  │
              └───────────┘  └───────────┘  └───────────┘
```

---

**Document Generated:** February 2026  
**Repository:** github.com/Sasanka14/ai_biodiversity_sundarbans
