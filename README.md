<p align="center">
  <img src="./logo.png" alt="ORBIT Logo" width="200"/>
</p>

<h1 align="center">ORBIT</h1>
<h3 align="center">System Operating Around Riders</h3>
<h4 align="center"><em>Autonomous Earnings Resilience Algorithm</em></h4>

<p align="center">
  <strong>"We don't just insure against acts of God; we insure against the realities of the City."</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Phase-1%20%7C%20Foundation-blue?style=flat-square" alt="Phase 1"/>
  <img src="https://img.shields.io/badge/Stack-FastAPI%20%7C%20Flutter%20%7C%20PostGIS-green?style=flat-square" alt="Stack"/>
  <img src="https://img.shields.io/badge/AI%2FML-XGBoost%20%7C%20Scikit--learn-orange?style=flat-square" alt="AI/ML"/>
  <img src="https://img.shields.io/badge/Domain-InsurTech%20%7C%20Q--Commerce-red?style=flat-square" alt="Domain"/>
  <img src="https://img.shields.io/badge/License-MIT-lightgrey?style=flat-square" alt="License"/>
</p>

<p align="center">
  <a href="#"><strong>📂 Repository</strong></a> &nbsp;·&nbsp;
  <a href="#"><strong>🎬 Phase 1 Pitch Video</strong></a>
</p>

---

## 📋 Table of Contents

1. [Executive Summary](#1--executive-summary)
2. [Persona-Based Scenarios & Application Workflow](#2--persona-based-scenarios--application-workflow)
3. [The Weekly Premium Model & The "Yield Curve"](#3--the-weekly-premium-model--the-yield-curve)
4. [Parametric Triggers Defined](#4--parametric-triggers-defined)
5. [Justification: Web vs. Mobile Platform](#5--justification-web-vs-mobile-platform)
6. [AI/ML Integration & 4-Layer Fraud Defense](#6--aiml-integration--4-layer-fraud-defense-the-hackathon-usp)
7. [Technical Architecture](#7--technical-architecture)
8. [Tech Stack & Development Plan](#8--tech-stack--development-plan)

---

## 1 · Executive Summary

**ORBIT** is an **AI-powered, parametric insurance platform** built exclusively for India's **Quick-Commerce (Q-Commerce) delivery partners** — the riders of Zepto, Blinkit, Swiggy Instamart, and similar platforms.

### The Core Mission

Gig workers lack safety nets against **hyper-local, uncontrollable external disruptions** — flash floods, VIP traffic gridlocks, severe smog — that steal their working hours. **ORBIT** provides a **weekly financial safety net** that protects a gig worker's **INCOME** during these events.

> [!IMPORTANT]
> **Scope of Coverage:** This platform strictly covers **Wage / Income Loss** and explicitly **excludes** health, life, accidents, or vehicle repair coverage.

---

## 2 · Persona-Based Scenarios & Application Workflow

**Target Persona:** Q-Commerce Delivery Partners — 10-minute delivery riders operating in high-density urban zones (Bengaluru, Delhi, Mumbai).

---

### Scenario A — *The Micro-Gridlock (Social Disruption)*

| Stage | Details |
|---|---|
| **Context** | Raju is a Blinkit rider in Bengaluru. A sudden, unannounced political rally (VIP movement) causes a severe 2 km traffic gridlock. Raju is trapped for 90 minutes. He hasn't met with an accident, but his **time and income are stolen**. |
| **Action** | Raju opens the ORBIT app and taps **"File Claim: I am Stuck"**. |
| **Resolution** | The app instantly queries the **TomTom Live Traffic API** and verifies a severe velocity drop in his exact geohash. To prevent fraud, the app checks his phone's **accelerometer** (verifying micro-vibrations of engine idling) and validates that **4 other insured riders** in his 500 m radius are also stationary (**Swarm Consensus**). |
| **Outcome** | The claim is **auto-approved**. The AI calculates his projected earnings for that 90-minute Friday window (**₹180**) and locks it in his **Micro-Escrow**. At end-of-shift — once the system verifies he didn't secretly complete the delivery via an alleyway — the ₹180 is instantly transferred to his **UPI**. |

---

### Scenario B — *The Flash Flood (Environmental Disruption)*

| Stage | Details |
|---|---|
| **Context** | A sudden torrential downpour floods Sector 44. The Q-Commerce platform pauses operations. |
| **Action** | **Purely parametric** — no rider action required. The OpenWeather API pushes a **>15 mm/hr** rain alert for Sector 44. |
| **Resolution** | The ORBIT backend **automatically triggers** an income-loss event for all active riders geofenced in Sector 44. |
| **Outcome** | **No manual claim needed.** Riders are automatically compensated based on their **AI Yield Curve** for the hours the zone remains red-flagged. |

---

## 3 · The Weekly Premium Model & The "Yield Curve"

Gig workers operate on **weekly payout cycles**. Our financial model is strictly aligned with a **Weekly Pricing Cycle**, calculated dynamically every **Sunday** using AI.

### 🧠 The AI Yield Curve

> Standard insurance pays a flat rate. Our ML model analyzes a rider's **historical earnings** to generate an **Expected Earnings Curve** — predicting, for example, that they earn ₹150/hr on Tuesday afternoons but **₹300/hr** on Friday nights. When a disruption occurs, ORBIT pays the **exact area under the curve** for the lost time.

### 💵 Dynamic Weekly Premium Calculation

| Component | Amount | Logic |
|---|---|---|
| **Base Premium** | ₹20 / week | Flat weekly contribution for minimum coverage. |
| **Zone Volatility Risk** | +₹5 | Applied if the rider's primary geofence is historically prone to waterlogging or traffic gridlocks. |
| **Weather Forecast Risk** | +₹3 | Applied if IMD predicts extreme heat or rain for the upcoming week. |
| **Loyalty Adjustment** | −10% | Discount for top-tier, consistently active riders. |
| **Collection** | — | Automatically deducted via **UPI Auto-Pay** mandate every Sunday night. |

---

## 4 · Parametric Triggers Defined

We target specific, **data-backed external parameters** to initiate "Loss of Income" claims:

| Disruption Type | Trigger Parameter *(Data Source)* | Impact on Worker | Payout Logic |
|---|---|---|---|
| **Micro-Gridlocks** | TomTom / Google Maps API showing **>80% velocity drop** in a 1 km grid. | Trapped in traffic; cannot fulfill orders. | AI Yield Curve — exact match for minutes lost. |
| **Extreme Rain** | OpenWeather API records **>15 mm** rain per hour. | App halts orders; riding is unsafe. | AI Yield Curve — match for duration of storm. |
| **Severe Heatwave** | API records localized temperature **>45 °C**. | Dangerous to ride outdoors mid-day. | Lump-sum shift replacement for **1 PM – 4 PM**. |
| **Severe Smog** | AQI API reads **>450** (Severe Plus). | Visibility drops; stamina impacts. | Fixed daily compensation for reduced capacity. |

---

## 5 · Justification: Web vs. Mobile Platform

> **Decision: Mobile Application (Flutter)**

| Criterion | Justification |
|---|---|
| **User Environment** | Gig workers **exclusively use smartphones** for their livelihood. A web application is entirely unsuited for their operational environment. |
| **Technical Necessity** | Our primary AI Fraud Defense — **Adaptive Sensor Fusion** — requires direct **native access** to the smartphone's hardware (Accelerometer, Gyroscope, Barometer) and **background Geolocation** tracking. PWAs and Web platforms **cannot** reliably access background physical sensors or granular location telemetry needed to detect GPS spoofing. |

---

## 6 · AI/ML Integration & 4-Layer Fraud Defense *(The Hackathon USP)*

To completely eliminate **moral hazard** and **fake claims**, ORBIT utilizes a highly novel **4-layer validation architecture** powered by AI:

### Layer 1 — Adaptive Sensor Fusion *(Hardware-Agnostic ML)*

Uses **local device sensors** to prevent GPS spoofing:
- **Barometer** — detects sudden atmospheric pressure drops correlated with storm claims.
- **Accelerometer** — reads physical micro-vibrations (engine idling in traffic).
- **Zero vibrations = Rider is at home spoofing GPS → Claim rejected.**

### Layer 2 — Swarm Consensus *(Proof of Gridlock)*

- PostGIS database groups claimants into **500 m hex-grids**.
- The AI cross-checks the velocity of **other insured riders** in that hex.
- If **one** claims gridlock but **four others** are moving at 40 km/h → **claim is flagged as fraud**.

### Layer 3 — Platform State Handshake *(Anti-Moral Hazard)*

- Simulated API call to the gig platform (Zomato / Zepto).
- Payouts release **only** if `Trip_State` = `"Cancelled"` or `"Delayed"`.
- If `Trip_State` = `"Completed"` (rider found a shortcut & got paid) → **claim auto-aborted** *(Anti-Double Dipping)*.

### Layer 4 — Telemetry Validation

- Post-claim, AI continuously monitors **GPS velocity**.
- Sustained forward movement (20–30 km/h) toward the destination → **payout auto-halted**.

---

## 7 · Technical Architecture

```mermaid
graph TD
    subgraph Client ["📱 Mobile App — Flutter"]
        UI["Rider Dashboard UI"]
        Sensors["Adaptive Sensor Module<br/>(Accelerometer · GPS · Barometer)"]
        UI <--> Sensors
    end

    subgraph External ["☁️ 3rd-Party Services"]
        WeatherAPI["OpenWeather / IMD API"]
        TrafficAPI["TomTom Live Traffic (Mock)"]
        GigAPI["Gig Platform Simulator<br/>(Zomato / Zepto)"]
        Razorpay["Razorpay UPI Sandbox"]
    end

    subgraph Backend ["⚙️ Backend — FastAPI / Python"]
        API_GW["API Gateway & Auth"]
        Premium_Calc["Dynamic Premium Engine"]
        Trigger_Engine["Parametric Trigger Engine"]
        Fraud_Engine["4-Layer Fraud Defense AI"]
        Escrow["Micro-Escrow Manager"]
    end

    subgraph Data ["🗄️ Data & ML Layer"]
        PostGIS[("PostgreSQL + PostGIS")]
        ML_Yield["XGBoost Yield Curve Model"]
    end

    Client -->|"File Claim / Send Telemetry"| API_GW
    API_GW --> Trigger_Engine
    API_GW <--> Premium_Calc
    Trigger_Engine --> Fraud_Engine
    Fraud_Engine --> Escrow
    Escrow -->|"EOD Settlement"| Razorpay

    Premium_Calc <--> ML_Yield
    Trigger_Engine <--> PostGIS
    Fraud_Engine <--> PostGIS
    ML_Yield <--> PostGIS

    Premium_Calc -->|"Fetch Weekly Forecast"| WeatherAPI
    Trigger_Engine -->|"Live Check"| WeatherAPI
    Trigger_Engine -->|"Live Check"| TrafficAPI
    Fraud_Engine -->|"Swarm Consensus"| PostGIS
    Fraud_Engine -->|"Trip State Handshake"| GigAPI
```

---

## 8 · Tech Stack & Development Plan

### 🧰 Tech Stack

| Layer | Technology | Rationale |
|---|---|---|
| **Frontend** | Flutter (Dart) | Cross-platform with native sensor integration and high-performance rendering. |
| **Backend** | Python — FastAPI | High concurrency, native ML library support. |
| **Database** | PostgreSQL + PostGIS | Geo-hashing, geofencing, and Swarm Consensus queries. |
| **AI / ML** | Scikit-learn · XGBoost | Time-series Expected Earnings Yield Curve generation. |
| **Mock Services** | Flask | Simulating Zepto / Zomato `Trip_State` payloads. |
| **Payments** | Razorpay UPI Sandbox | Micro-Escrow settlement loop. |

---

### 🗓️ 6-Week Execution Timeline

#### Phase 1 — Foundation & Strategy *(Current → March 20)*

- [x] Define core architecture, persona logic, and Yield Curve mathematics.
- [x] Draft detailed requirement documentation *(this README)*.
- [ ] Create minimal UI/UX flow diagrams for the Q-Commerce persona.
- [ ] Record the 2-minute strategy pitch video.

#### Phase 2 — Core Automation & API Mocks *(March 21 → April 4)*

- [ ] **Backend:** Build the AI Yield Curve Logic using a mock CSV dataset of historical gig-worker earnings.
- [ ] **APIs:** Develop the Parametric Trigger Engine integrating OpenWeather API and mocked TomTom Traffic APIs.
- [ ] **Integration:** Build the Mock "Platform State" API for the `Trip_State` Handshake.
- [ ] **Deliverable:** 2-minute demo video — dynamic premium calculation + automated claim trigger.

#### Phase 3 — Deep Tech Fraud Defense & Scaling *(April 5 → April 17)*

- [ ] **Data / ML:** Implement Swarm Consensus logic using PostGIS.
- [ ] **Frontend:** Implement Adaptive Sensor Fusion module in Flutter (Accelerometer data on "File Claim").
- [ ] **Fintech:** Build the Micro-Escrow Razorpay payout loop (Sandbox).
- [ ] **Admin:** Develop a React.js Insurer Dashboard — *Live Disruptions* & *Fraud Attempts*.
- [ ] **Deliverable:** Final 5-minute walkthrough, Final Pitch Deck (PDF), fully documented executable codebase.

---

<p align="center">
  <strong>Built with 🛰️ for <a href="#">Guidewire DEVTrails 2026</a></strong><br/>
  <sub>ORBIT — Because every rider deserves an orbit of protection.</sub>
</p>
