# Simulator Interface Description

**Sundarbans Biodiversity AI — User Interface Guide**  
**Date:** February 2026

---

## Table of Contents

1. [Interface Overview](#1-interface-overview)
2. [Navigation Bar](#2-navigation-bar)
3. [Hero Section](#3-hero-section)
4. [Parameter Input Panel](#4-parameter-input-panel)
5. [Results Panel](#5-results-panel)
6. [Knowledge Section](#6-knowledge-section)
7. [User Workflow](#7-user-workflow)

---

## 1. Interface Overview

The Climate Simulator provides an interactive web-based interface for modeling climate scenarios and predicting their impact on Sundarbans biodiversity.

### 1.1 Page Layout

```
┌──────────────────────────────────────────────────────────────────────────────┐
│                           NAVIGATION BAR                                      │
├──────────────────────────────────────────────────────────────────────────────┤
│                           HERO SECTION                                        │
│                    "Climate Simulator" Title & Badge                          │
├──────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌─────────────────────────────┐  ┌─────────────────────────────┐           │
│  │                             │  │                             │           │
│  │    PARAMETER INPUT          │  │    RESULTS PANEL            │           │
│  │    PANEL (LEFT)             │  │    (RIGHT)                  │           │
│  │                             │  │                             │           │
│  │  • Tabbed Interface         │  │  • 3-Page Carousel          │           │
│  │  • Climate Sliders          │  │  • Metrics / Risk / AI      │           │
│  │  • Action Buttons           │  │  • Page Navigation          │           │
│  │                             │  │                             │           │
│  └─────────────────────────────┘  └─────────────────────────────┘           │
│                                                                              │
├──────────────────────────────────────────────────────────────────────────────┤
│                        KNOWLEDGE SECTION                                      │
│               (Data Sources, Lagged Variables, Risk Thresholds)              │
├──────────────────────────────────────────────────────────────────────────────┤
│                              FOOTER                                           │
└──────────────────────────────────────────────────────────────────────────────┘
```

### 📸 SCREENSHOT 1: Full Page Overview
> **Add screenshot here:** Capture the entire simulator page showing both panels, navigation, and hero section.
> 
> **Filename suggestion:** `ss_01_full_page_overview.png`

---

## 2. Navigation Bar

### 2.1 Description

The navigation bar features a glassmorphism design with the project branding and main navigation links.

### 2.2 Components

| Element | Description |
|---------|-------------|
| **Logo** | "SUNDARBANS" (top) + "BIODIVERSITY AI" (green, bottom) |
| **HOME** | Links to landing page (`index.html`) |
| **ABOUT** | Links to about section (`index.html#about`) |
| **SIMULATOR** | Current page (highlighted as active) |
| **FAQ** | Links to FAQ section (`index.html#faq`) |

### 2.3 Visual Style

- **Background:** Semi-transparent glass effect
- **Styling:** Frosted glass (`glass-nav` class)
- **Active Link:** Highlighted green text

### 📸 SCREENSHOT 2: Navigation Bar
> **Add screenshot here:** Close-up of the navigation bar with logo and menu items visible.
> 
> **Filename suggestion:** `ss_02_navigation_bar.png`

---

## 3. Hero Section

### 3.1 Description

The hero section introduces the simulator with a badge, title, and subtitle explaining the purpose.

### 3.2 Components

```
┌──────────────────────────────────────────────────────────────────────────────┐
│                                                                              │
│         ┌─────────────────────────────────────┐                              │
│         │ 🔲 AI-Powered Ecosystem Analysis     │  ← Badge                    │
│         └─────────────────────────────────────┘                              │
│                                                                              │
│                    ╔═══════════════════════════╗                             │
│                    ║    Climate Simulator      ║  ← Main Title               │
│                    ╚═══════════════════════════╝                             │
│                                                                              │
│         Model climate scenarios and predict their impact                     │
│         on biodiversity using machine learning            ← Subtitle         │
│                                                                              │
│                        ✨ Hero Glow Effect ✨                                │
└──────────────────────────────────────────────────────────────────────────────┘
```

### 3.3 Visual Elements

| Element | Style |
|---------|-------|
| Badge | Chip with microchip icon |
| Title | Large, bold "Climate Simulator" |
| Subtitle | Descriptive text below title |
| Glow | Ambient lighting effect behind content |
| Particles | Floating animated particles in background |

### 📸 SCREENSHOT 3: Hero Section
> **Add screenshot here:** Hero section showing badge, title, subtitle, and background particles.
> 
> **Filename suggestion:** `ss_03_hero_section.png`

---

## 4. Parameter Input Panel

### 4.1 Overview

The left panel contains all climate parameter controls organized in a tabbed interface.

### 4.2 Panel Header

```
┌──────────────────────────────────────────────────────────────────────────────┐
│  ⚙️  Simulation Parameters                                        ● Ready   │
│      Configure climate variables                                             │
└──────────────────────────────────────────────────────────────────────────────┘
```

| Element | Description |
|---------|-------------|
| Icon | Sliders icon (`fa-sliders-h`) |
| Title | "Simulation Parameters" |
| Subtitle | "Configure climate variables" |
| Status | Green dot + "Ready" indicator |

### 📸 SCREENSHOT 4: Parameter Panel Header
> **Add screenshot here:** Top portion of the parameter panel showing header and status indicator.
> 
> **Filename suggestion:** `ss_04_parameter_header.png`

---

### 4.3 Parameter Tabs

Three tabs organize the 10 input parameters:

```
┌─────────────────┬─────────────────┬─────────────────┐
│  ☁️ Current     │  🕐 Lagged      │  🛰️ POWER Data  │
│    (Active)     │                 │                 │
└─────────────────┴─────────────────┴─────────────────┘
```

#### Tab 1: Current Climate (Default Active)

| Parameter | Range | Default | Unit |
|-----------|-------|---------|------|
| Air Temperature | 20 - 35 | 28 | °C |
| Relative Humidity | 40 - 95 | 70 | % |

### 📸 SCREENSHOT 5: Current Climate Tab
> **Add screenshot here:** Current tab showing Air Temperature and Humidity sliders.
> 
> **Filename suggestion:** `ss_05_tab_current.png`

---

#### Tab 2: Lagged Parameters

| Parameter | Range | Default | Unit |
|-----------|-------|---------|------|
| Temperature (3M Lag) | 20 - 35 | 27 | °C |
| Humidity (3M Lag) | 40 - 95 | 72 | % |

### 📸 SCREENSHOT 6: Lagged Tab
> **Add screenshot here:** Lagged tab showing 3-month lag temperature and humidity sliders.
> 
> **Filename suggestion:** `ss_06_tab_lagged.png`

---

#### Tab 3: NASA POWER Satellite Data

| Parameter | Range | Default | Unit | Description |
|-----------|-------|---------|------|-------------|
| T2M (1-Month Lag) | 20 - 35 | 28 | °C | 2m Air Temperature |
| RH2M (1-Month Lag) | 40 - 95 | 70 | % | 2m Relative Humidity |
| T2M (3-Month Lag) | 20 - 35 | 27 | °C | 2m Air Temperature |
| RH2M (3-Month Lag) | 40 - 95 | 72 | % | 2m Relative Humidity |
| T2M (6-Month Lag) | 20 - 35 | 26 | °C | 2m Air Temperature |
| RH2M (6-Month Lag) | 40 - 95 | 75 | % | 2m Relative Humidity |

### 📸 SCREENSHOT 7: POWER Data Tab
> **Add screenshot here:** POWER Data tab showing all 6 satellite-derived sliders (may need scrolling).
> 
> **Filename suggestion:** `ss_07_tab_power.png`

---

### 4.4 Slider Control Design

Each parameter uses a premium slider design:

```
┌──────────────────────────────────────────────────────────────────────────────┐
│                                                                              │
│  Air Temperature                                                    │  28 │  │
│  Degrees Celsius (°C)                                               └────┘  │
│                                                                              │
│  ┌──────────────────────────────────────────────────────────────────────┐   │
│  │█████████████████████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░│ ◉ │
│  └──────────────────────────────────────────────────────────────────────┘   │
│  20°C                                                               35°C    │
│                                                                              │
└──────────────────────────────────────────────────────────────────────────────┘
```

| Component | Purpose |
|-----------|---------|
| Label | Parameter name (e.g., "Air Temperature") |
| Unit | Measurement unit (e.g., "Degrees Celsius (°C)") |
| Value Display | Current value in box (updates live) |
| Slider Track | Filled portion shows position |
| Thumb | Draggable control point |
| Min/Max Labels | Range boundaries |

### 📸 SCREENSHOT 8: Slider Close-up
> **Add screenshot here:** Close-up of a single slider showing label, value display, track, and range labels.
> 
> **Filename suggestion:** `ss_08_slider_closeup.png`

---

### 4.5 Action Buttons

```
┌──────────────────────────────────────────────────────────────────────────────┐
│                                                                              │
│      ┌─────────────────────────────┐    ┌─────────────────────────┐         │
│      │  ▶  Run Simulation          │    │  ↩  Reset               │         │
│      │       (Primary Button)       │    │    (Secondary Button)   │         │
│      └─────────────────────────────┘    └─────────────────────────┘         │
│                                                                              │
└──────────────────────────────────────────────────────────────────────────────┘
```

| Button | Icon | Action |
|--------|------|--------|
| **Run Simulation** | Play icon | Sends parameters to API, displays results |
| **Reset** | Undo icon | Resets all sliders to default values |

**Button States:**
- Default: Green gradient with glow effect
- Hover: Enhanced glow, slight scale
- Processing: Spinner icon + "Processing..." text
- Disabled: Grayed out during API call

### 📸 SCREENSHOT 9: Action Buttons
> **Add screenshot here:** Both action buttons in default state.
> 
> **Filename suggestion:** `ss_09_action_buttons.png`

### 📸 SCREENSHOT 10: Processing State
> **Add screenshot here:** Run Simulation button showing spinner and "Processing..." state.
> 
> **Filename suggestion:** `ss_10_processing_state.png`

---

## 5. Results Panel

### 5.1 Overview

The right panel displays simulation results in a 3-page carousel format.

### 5.2 Panel Header

```
┌──────────────────────────────────────────────────────────────────────────────┐
│  📈  Analysis Results                                          ● ○ ○        │
│      AI-powered predictions                                  (Page Dots)    │
└──────────────────────────────────────────────────────────────────────────────┘
```

### 📸 SCREENSHOT 11: Results Panel Header
> **Add screenshot here:** Results panel header with page indicator dots.
> 
> **Filename suggestion:** `ss_11_results_header.png`

---

### 5.3 Initial State (Before Simulation)

```
┌──────────────────────────────────────────────────────────────────────────────┐
│                                                                              │
│                              🌿                                              │
│                                                                              │
│                       Ready to Simulate                                      │
│                                                                              │
│         Configure your climate parameters and click                          │
│         "Run Simulation" to analyze the potential impact                     │
│         on species richness in the Sundarbans ecosystem.                     │
│                                                                              │
└──────────────────────────────────────────────────────────────────────────────┘
```

### 📸 SCREENSHOT 12: Initial State
> **Add screenshot here:** Results panel in initial "Ready to Simulate" state before running simulation.
> 
> **Filename suggestion:** `ss_12_initial_state.png`

---

### 5.4 Loading State

```
┌──────────────────────────────────────────────────────────────────────────────┐
│                                                                              │
│                           ◠ ◡ ◠ ◡ ◠                                         │
│                         (Spinner Animation)                                  │
│                                                                              │
│                      Processing Simulation                                   │
│                   Analyzing ecosystem impact...                              │
│                                                                              │
└──────────────────────────────────────────────────────────────────────────────┘
```

### 📸 SCREENSHOT 13: Loading State
> **Add screenshot here:** Results panel showing loading spinner during API call.
> 
> **Filename suggestion:** `ss_13_loading_state.png`

---

### 5.5 Results Page 1: Key Metrics

```
┌──────────────────────────────────────────────────────────────────────────────┐
│  📊 Key Metrics                                                    1 / 3    │
├──────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌────────────────┐  ┌────────────────┐  ┌────────────────┐                 │
│  │ 🚩 Baseline    │  │ 🧠 Predicted   │  │ ⇄ Change (Δ)  │                 │
│  │    Richness    │  │    Richness    │  │               │                 │
│  │                │  │                │  │               │                 │
│  │    180.00      │  │    165.50      │  │    -14.50     │                 │
│  │                │  │                │  │               │                 │
│  │  Reference     │  │  Under         │  │  Difference   │                 │
│  │  ecosystem     │  │  simulated     │  │  from         │                 │
│  │  state         │  │  conditions    │  │  baseline     │                 │
│  └────────────────┘  └────────────────┘  └────────────────┘                 │
│                                                                              │
│  ┌──────────────────────────────────────────────────────────────────────┐   │
│  │  💓 Ecosystem Health Index                                          │   │
│  │  ┌───────────────────────────────────────────────────────────────┐  │   │
│  │  │████████████████████████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░│  │   │
│  │  └───────────────────────────────────────────────────────────────┘  │   │
│  │  Critical              Stable              Thriving                 │   │
│  └──────────────────────────────────────────────────────────────────────┘   │
│                                                                              │
└──────────────────────────────────────────────────────────────────────────────┘
```

**Metrics Displayed:**

| Metric | Icon | Description | Color |
|--------|------|-------------|-------|
| Baseline Richness | 🚩 | Reference value (180 species) | Blue |
| Predicted Richness | 🧠 | ML model prediction | Purple |
| Change (Δ) | ⇄ | Delta from baseline | Green/Red |
| Health Index | 💓 | 0-100% progress bar | Gradient |

### 📸 SCREENSHOT 14: Results Page 1 - Key Metrics
> **Add screenshot here:** Page 1 showing all three metric cards and ecosystem health bar.
> 
> **Filename suggestion:** `ss_14_page1_metrics.png`

---

### 5.6 Results Page 2: Risk Assessment

```
┌──────────────────────────────────────────────────────────────────────────────┐
│  🛡️ Risk Assessment                                                2 / 3    │
├──────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│                    Ecosystem Risk Assessment                                 │
│                  Based on species richness change                            │
│                                                                              │
│                           ╭─────────╮                                        │
│                          ╱           ╲                                       │
│                         ╱      △      ╲                                      │
│                        ╱       │       ╲                                     │
│                       ╱        │  ╲      ╲                                   │
│                      ╱    ─────│─────╲    ╲                                  │
│                     ╱          ↑         ╲                                   │
│                    ╱       (Needle)       ╲                                  │
│                   ╱___________________________╲                              │
│                                                                              │
│              Low Risk     Moderate     High Risk                             │
│                                                                              │
│                    ┌──────────────────────┐                                  │
│                    │ 🛡️ MODERATE RISK     │  ← Risk Badge                   │
│                    └──────────────────────┘                                  │
│                                                                              │
│         Moderate ecosystem pressure identified. Species                      │
│         richness is notably affected under these conditions.                 │
│         Implement adaptive management strategies.                            │
│                                                                              │
└──────────────────────────────────────────────────────────────────────────────┘
```

**Risk Gauge Components:**

| Component | Description |
|-----------|-------------|
| Gauge Arc | Semi-circle showing risk spectrum |
| Needle | Points to current risk level |
| Labels | "Low Risk" / "Moderate" / "High Risk" |
| Risk Badge | Colored chip showing risk level |
| Message | Detailed explanation of risk |

**Risk Badge Colors:**

| Risk Level | Badge Color |
|------------|-------------|
| Low Risk | Green |
| Moderate Risk | Yellow/Orange |
| High Risk | Red |

### 📸 SCREENSHOT 15: Results Page 2 - Risk Gauge (Low Risk)
> **Add screenshot here:** Page 2 showing gauge with needle in LOW RISK zone (left side).
> 
> **Filename suggestion:** `ss_15_page2_risk_low.png`

### 📸 SCREENSHOT 16: Results Page 2 - Risk Gauge (Moderate Risk)
> **Add screenshot here:** Page 2 showing gauge with needle in MODERATE RISK zone (center).
> 
> **Filename suggestion:** `ss_16_page2_risk_moderate.png`

### 📸 SCREENSHOT 17: Results Page 2 - Risk Gauge (High Risk)
> **Add screenshot here:** Page 2 showing gauge with needle in HIGH RISK zone (right side).
> 
> **Filename suggestion:** `ss_17_page2_risk_high.png`

---

### 5.7 Results Page 3: AI Insights & Export

```
┌──────────────────────────────────────────────────────────────────────────────┐
│  💡 AI Insights                                                    3 / 3    │
├──────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌──────────────────────────────────────────────────────────────────────┐   │
│  │  🤖 AI Interpretation                                               │   │
│  │                                                                      │   │
│  │  Based on the simulated climate parameters, our AI model predicts   │   │
│  │  a species richness index of 165.50, compared to the baseline of    │   │
│  │  180.00. This represents an 8.1% decrease in biodiversity           │   │
│  │  (Δ = -14.50). Some species may experience habitat pressure.        │   │
│  │  Proactive conservation measures can help mitigate potential        │   │
│  │  impacts.                                                           │   │
│  └──────────────────────────────────────────────────────────────────────┘   │
│                                                                              │
│  ┌──────────────────────────────────────────────────────────────────────┐   │
│  │  🌿 Conservation Recommendations                                    │   │
│  │                                                                      │   │
│  │  • 🛡️ Enhance existing conservation buffer zones                   │   │
│  │  • 🌱 Continue mangrove nursery development programs                │   │
│  │  • 🔭 Increase wildlife monitoring frequency in sensitive areas     │   │
│  │  • 💧 Implement sustainable water management practices              │   │
│  └──────────────────────────────────────────────────────────────────────┘   │
│                                                                              │
│            ┌────────────────────────────────────────────────┐               │
│            │  📤 Export Analysis Report                     │               │
│            └────────────────────────────────────────────────┘               │
│                                                                              │
└──────────────────────────────────────────────────────────────────────────────┘
```

**Page 3 Components:**

| Component | Description |
|-----------|-------------|
| AI Interpretation | Natural language analysis of results |
| Conservation Recommendations | Risk-based action items (4-5 items) |
| Export Button | Downloads analysis report |

### 📸 SCREENSHOT 18: Results Page 3 - AI Insights
> **Add screenshot here:** Page 3 showing AI interpretation, conservation list, and export button.
> 
> **Filename suggestion:** `ss_18_page3_insights.png`

---

### 5.8 Page Navigation

```
┌──────────────────────────────────────────────────────────────────────────────┐
│                                                                              │
│   ┌────────────────┐  ┌──────────────────────────────┐  ┌────────────────┐  │
│   │ ◀ Previous     │  │████████░░░░░░░░░░░░░░░░░░░░░│  │ Next ▶         │  │
│   └────────────────┘  └──────────────────────────────┘  └────────────────┘  │
│                            (Progress Bar)                                    │
└──────────────────────────────────────────────────────────────────────────────┘
```

| Element | Function |
|---------|----------|
| Previous Button | Navigate to previous page (disabled on page 1) |
| Progress Bar | Shows current position (1/3, 2/3, 3/3) |
| Next Button | Navigate to next page (disabled on page 3) |
| Page Dots | Click to jump to specific page |

### 📸 SCREENSHOT 19: Page Navigation Controls
> **Add screenshot here:** Bottom navigation showing Previous/Next buttons and progress bar.
> 
> **Filename suggestion:** `ss_19_page_navigation.png`

---

## 6. Knowledge Section

### 6.1 Description

Below the main simulator, an educational section explains key concepts.

### 6.2 Layout

```
┌──────────────────────────────────────────────────────────────────────────────┐
│                    Understanding the Simulation                              │
│             Key concepts to help you interpret the results                   │
├──────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐              │
│  │  📊 Data        │  │  🕐 Lagged      │  │  ⚠️ Risk        │              │
│  │     Sources     │  │     Variables   │  │     Thresholds  │              │
│  │                 │  │                 │  │                 │              │
│  │  NASA POWER     │  │  Ecosystems     │  │  High: Δ ≤ -15  │              │
│  │  satellite data │  │  respond to     │  │  Mod:  Δ ≤ -5   │              │
│  │  combined with  │  │  climate        │  │  Low:  Δ > -5   │              │
│  │  ground-truth   │  │  changes over   │  │                 │              │
│  │  observations   │  │  time...        │  │                 │              │
│  └─────────────────┘  └─────────────────┘  └─────────────────┘              │
│                                                                              │
└──────────────────────────────────────────────────────────────────────────────┘
```

**Knowledge Cards:**

| Card | Icon | Content |
|------|------|---------|
| Data Sources | 📊 | NASA POWER + ground-truth biodiversity data |
| Lagged Variables | 🕐 | Explains delayed ecosystem response |
| Risk Thresholds | ⚠️ | High/Moderate/Low risk definitions |

### 📸 SCREENSHOT 20: Knowledge Section
> **Add screenshot here:** All three knowledge cards visible with icons and descriptions.
> 
> **Filename suggestion:** `ss_20_knowledge_section.png`

---

## 7. User Workflow

### 7.1 Step-by-Step Guide

```
╔══════════════════════════════════════════════════════════════════════════════╗
║                         USER WORKFLOW DIAGRAM                                ║
╠══════════════════════════════════════════════════════════════════════════════╣
║                                                                              ║
║   STEP 1                    STEP 2                    STEP 3                 ║
║   ┌─────────┐              ┌─────────┐              ┌─────────┐              ║
║   │  Open   │              │ Adjust  │              │  Run    │              ║
║   │Simulator│ ──────────▶  │ Sliders │ ──────────▶  │Simulate │              ║
║   │  Page   │              │         │              │         │              ║
║   └─────────┘              └─────────┘              └─────────┘              ║
║                                                           │                  ║
║                                                           ▼                  ║
║   STEP 6                    STEP 5                    STEP 4                 ║
║   ┌─────────┐              ┌─────────┐              ┌─────────┐              ║
║   │ Export  │              │  View   │              │  View   │              ║
║   │ Report  │ ◀──────────  │   AI    │ ◀──────────  │ Metrics │              ║
║   │         │              │ Insights│              │         │              ║
║   └─────────┘              └─────────┘              └─────────┘              ║
║                                                                              ║
╚══════════════════════════════════════════════════════════════════════════════╝
```

### 7.2 Detailed Steps

| Step | Action | UI Element |
|------|--------|------------|
| 1 | Open simulator page | Navigate to `simulator.html` |
| 2 | Select parameter tab | Click "Current", "Lagged", or "POWER Data" |
| 3 | Adjust climate values | Drag sliders to desired values |
| 4 | Run simulation | Click "Run Simulation" button |
| 5 | View Page 1 metrics | Baseline, Prediction, Delta, Health |
| 6 | Navigate to Page 2 | Click Next or page dot |
| 7 | View risk assessment | Gauge, badge, message |
| 8 | Navigate to Page 3 | Click Next or page dot |
| 9 | Read AI insights | Interpretation & recommendations |
| 10 | Export report | Click "Export Analysis Report" |
| 11 | Reset and repeat | Click "Reset" to start over |

---

## 8. Screenshot Checklist

Use this checklist to capture all required screenshots:

| # | Screenshot | Description | Filename |
|---|------------|-------------|----------|
| 1 | Full Page Overview | Complete simulator page | `ss_01_full_page_overview.png` |
| 2 | Navigation Bar | Logo and menu items | `ss_02_navigation_bar.png` |
| 3 | Hero Section | Badge, title, subtitle | `ss_03_hero_section.png` |
| 4 | Parameter Header | Panel header with status | `ss_04_parameter_header.png` |
| 5 | Current Tab | Temperature & humidity sliders | `ss_05_tab_current.png` |
| 6 | Lagged Tab | 3-month lag sliders | `ss_06_tab_lagged.png` |
| 7 | POWER Tab | All 6 satellite sliders | `ss_07_tab_power.png` |
| 8 | Slider Close-up | Single slider detail | `ss_08_slider_closeup.png` |
| 9 | Action Buttons | Run & Reset buttons | `ss_09_action_buttons.png` |
| 10 | Processing State | Button with spinner | `ss_10_processing_state.png` |
| 11 | Results Header | Panel header with dots | `ss_11_results_header.png` |
| 12 | Initial State | "Ready to Simulate" | `ss_12_initial_state.png` |
| 13 | Loading State | Spinner animation | `ss_13_loading_state.png` |
| 14 | Page 1 Metrics | Three cards + health bar | `ss_14_page1_metrics.png` |
| 15 | Page 2 Low Risk | Gauge needle left | `ss_15_page2_risk_low.png` |
| 16 | Page 2 Moderate | Gauge needle center | `ss_16_page2_risk_moderate.png` |
| 17 | Page 2 High Risk | Gauge needle right | `ss_17_page2_risk_high.png` |
| 18 | Page 3 Insights | AI text + recommendations | `ss_18_page3_insights.png` |
| 19 | Page Navigation | Prev/Next + progress bar | `ss_19_page_navigation.png` |
| 20 | Knowledge Section | Three tip cards | `ss_20_knowledge_section.png` |

---

## 9. Technical Details

### 9.1 Technologies Used

| Technology | Purpose |
|------------|---------|
| HTML5 | Page structure |
| CSS3 | Styling, glassmorphism, animations |
| JavaScript | Interactivity, API calls |
| Font Awesome | Icons |
| Montserrat | Typography |
| FastAPI | Backend API |

### 9.2 API Endpoint

```
POST http://localhost:3005/simulate
Content-Type: application/json
```

### 9.3 Responsive Design

The interface is designed for desktop use with the following breakpoints:
- Container width: Flexible with max-width
- Two-panel layout: Side-by-side on desktop
- Glass panels: Adaptive sizing

---

**Document Generated:** February 2026  
**Repository:** github.com/Sasanka14/ai_biodiversity_sundarbans
