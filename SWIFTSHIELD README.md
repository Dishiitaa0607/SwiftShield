# 🛵 SwiftShield — AI-Powered Parametric Income Insurance for Swiggy Delivery Partners

> **Guidewire DEVTrails 2026 | University Hackathon**
> Protecting India's Last-Mile Heroes from Uncontrollable Income Loss

---

## Table of Contents

1. [Problem Statement](#1-problem-statement)
2. [Our Solution](#2-our-solution)
3. [Persona — Meet Karthi](#3-persona--meet-karthi)
4. [Scenarios & Application Workflow](#4-scenarios--application-workflow)
5. [Weekly Premium Model](#5-weekly-premium-model)
6. [Affordability Justification](#6-affordability-justification)
7. [Parametric Triggers](#7-parametric-triggers)
8. [AI/ML Integration Plan](#8-aiml-integration-plan)
9. [Fraud Detection](#9-fraud-detection)
10. [Adversarial Defense & Anti-Spoofing Strategy](#10-adversarial-defense--anti-spoofing-strategy)
11. [Platform Choice](#11-platform-choice)
12. [Tech Stack](#12-tech-stack)
13. [Repository Structure](#13-repository-structure)
14. [Development Plan](#14-development-plan)

---

## 1. Problem Statement

India's platform-based delivery partners are the backbone of our fast-paced digital economy.
External disruptions such as extreme weather, flooding, and civic events can reduce their working
hours and cause them to lose **20–30% of their monthly earnings**.

Currently, gig workers have **no income protection** against these uncontrollable events. When
disruptions occur, they bear the full financial loss with no safety net.

> **Coverage Scope: LOSS OF INCOME ONLY.**
> We strictly exclude vehicle repairs, health insurance, life insurance, and accident medical bills.

---

## 2. Our Solution

**SwiftShield** is an AI-enabled parametric insurance platform built exclusively for **Swiggy food
delivery partners**. It monitors external disruptions in a worker's delivery zone and automatically
triggers a payout — with zero manual claim filing required.

> _"A verified disruption hits Karthi's zone → SwiftShield detects it → money reaches his UPI
> within 2 hours. No forms. No waiting."_

### Why Parametric Insurance?

```
IF  rainfall in Semmencherry zone > 40mm in 3 hours
AND Karthi's weekly policy is active
AND fraud check passes
THEN auto-pay ₹450 to Karthi's UPI
```

No manual review. No disputes. Instant protection aligned with how gig workers actually earn.

| Feature | Traditional Insurance | SwiftShield |
|---|---|---|
| Claim Process | Manual, 7–30 days | Zero-touch, automated |
| Pricing | Fixed monthly | Dynamic weekly |
| Coverage | Health / Vehicle / Life | Income loss only |
| Payout Speed | Weeks | Within 2 hours |

---

## 3. Persona — Meet Karthi

```
Name           : Karthikeyan R. (Karthi)
Age            : 28
Platform       : Swiggy Food Delivery Partner
City           : Chennai, Tamil Nadu
Delivery Zones : Semmencherry / Perumbakkam
Vehicle        : Honda Activa (2-wheeler)
Work Hours     : 10 AM – 10 PM (6 days/week)
Daily Earnings : ₹750 – ₹1,100 (avg. ₹900/day)
Weekly Earnings: ₹4,800 – ₹6,000
Payout Cycle   : Weekly (every Monday via Swiggy)
Savings Buffer : Less than ₹5,000 — cannot absorb even 2 disrupted days
```

**Why Semmencherry and Perumbakkam?**
These are rapidly growing residential areas in Chennai's OMR corridor with a high density of
food delivery demand. However, both zones are low-lying and flood-prone during the northeast
monsoon, making delivery workers here especially vulnerable to income loss from waterlogging
and heavy rain — a perfect fit for parametric income insurance.

---

## 4. Scenarios & Application Workflow

### Scenario 1 — Heavy Monsoon Rain

**Situation:**
It is November, peak northeast monsoon season. Heavy rain starts at 4 PM in Semmencherry.
Within 30 minutes, the low-lying streets near Perumbakkam lake are flooded. Karthi's Activa
cannot navigate the waterlogged roads. Swiggy reduces order assignments in the zone.
Karthi loses the entire 4 PM – 9 PM evening rush — his most profitable window — costing
him around ₹480 in lost earnings.

**SwiftShield Response:**
OpenWeatherMap API detects rainfall exceeding 45mm in 3 hours in Karthi's zone. Trigger
fires automatically. GPS confirms Karthi was active before rain began. Payout of ₹480
credited to his UPI by 7:30 PM — while the rain is still falling.

> **Trigger:** Environmental — heavy rainfall | **Payout:** ₹480

---

### Scenario 2 — Waterlogging / Flood Alert

**Situation:**
After 2 continuous days of rain, the Greater Chennai Corporation issues a waterlogging alert
for Perumbakkam and Semmencherry. The roads connecting restaurant hubs to residential
areas are impassable. Even though it is not raining now, Karthi cannot reach pickup points.
He loses a full working day.

**SwiftShield Response:**
GCC/IMD flood alert API (mocked) detects a zone-level waterlogging alert for Karthi's
registered zones. This triggers a separate "post-rain disruption" payout covering the aftermath
window. Full-day payout of ₹700 processed automatically. Karthi gets a WhatsApp message:
"Waterlogging alert active in your zone. ₹700 protection credited."

> **Trigger:** Environmental — official flood/waterlogging alert | **Payout:** ₹700

---

### Scenario 3 — Sudden Bandh / Local Strike

**Situation:**
A sudden bandh is called on a Tuesday morning in Chennai. By 8 AM, roads near
Semmencherry are blocked by protesters. Swiggy reduces order availability in affected zones.
Restaurants are shuttered. Karthi cannot operate from 9 AM to 5 PM, losing nearly a full
day's earnings of ₹720.

**SwiftShield Response:**
NewsAPI detects a verified bandh covering Karthi's delivery zones, cross-validated against
the Swiggy order-drop signal in the area. GPS confirms Karthi was in the affected zone.
Full-day payout of ₹720 sent within 2 hours of confirmed zone-level disruption.

> **Trigger:** Social — unplanned civic event / strike | **Payout:** ₹720

---

### Scenario 4 — Platform Outage During Peak Hours

**Situation:**
On a Sunday afternoon, Swiggy's app goes down due to a server outage. Orders stop for
over 90 minutes during the peak lunch window (12 PM – 2 PM). Karthi sits idle at a
restaurant in Perumbakkam, losing ₹300–₹350 in deliveries he would have completed.

**SwiftShield Response:**
Platform API monitor detects zero order assignments in Karthi's zone for 90+ continuous
minutes during designated peak hours. Cross-validated with Swiggy's status signal (simulated).
Claim auto-initiated. Payout of ₹320 sent within 90 minutes of outage detection.

> **Trigger:** Platform disruption — app outage during peak hours | **Payout:** ₹320

---

### Application Workflow

```
STEP 1 — ONBOARDING (One-time, ~3 minutes)
→ Karthi opens SwiftShield PWA on Android
→ Enters Swiggy Partner ID + Mobile Number → OTP verified
→ Selects delivery zones: Semmencherry, Perumbakkam
→ App fetches 8-week earnings history (Swiggy API, simulated)
→ AI generates Risk Profile Score (1–10) + recommends coverage tier

STEP 2 — WEEKLY POLICY PURCHASE (Every Monday)
→ AI shows personalized premium: "This week: ₹44 | Max payout: ₹1,800"
→ Karthi pays via UPI (GPay / PhonePe) — one tap
→ Policy active Mon 00:00 – Sun 23:59
→ Confirmation sent via WhatsApp + push notification

STEP 3 — BACKGROUND MONITORING (Always-On)
→ Weather API polled every 15 minutes for Semmencherry / Perumbakkam
→ Flood/civic alert API checked every 10 minutes
→ News API scanned every 10 minutes
→ Swiggy platform signal checked every 5 minutes
→ Karthi does nothing — fully passive

STEP 4 — AUTO TRIGGER & CLAIM
→ Disruption threshold crossed in Karthi's zone
→ System verifies: policy active? ✓ | fraud check passed? ✓
→ Claim auto-created — Karthi never needs to open the app

STEP 5 — PAYOUT
→ UPI transfer sent within 90 minutes of trigger
→ WhatsApp alert: "₹480 credited for rain disruption in your zone"
→ Dashboard updated with claim record
```

---

## 5. Weekly Premium Model

Swiggy pays delivery partners weekly. A weekly premium of ₹25–₹65 matches Karthi's cash
flow naturally — affordable, flexible, and easy to understand.

### Coverage Tiers

| Tier | Weekly Premium | Max Weekly Payout |
|---|---|---|
| Basic Shield | ₹25/week | ₹800 |
| Standard Shield | ₹42/week | ₹1,800 |
| Full Shield | ₹65/week | ₹3,000 |

### Dynamic Pricing Formula

```
PREMIUM = BASE_RATE × Zone_Risk × Season_Factor × Loyalty_Discount

Zone_Risk        : 0.8–1.5  (Semmencherry/Perumbakkam = 1.3, flood-prone zones)
Season_Factor    : 0.9–1.5  (NE Monsoon Oct–Dec = 1.5 | Summer = 1.2 | Winter = 0.9)
Loyalty_Discount : 0.95 after 4 continuous weeks | 0.90 after 12 continuous weeks
```

**Example — Karthi, November, 6 weeks continuous coverage:**
```
Base (Standard)   : ₹35
Zone Risk (1.3)   : ₹45.5
Season (1.3)      : ₹59.2
Loyalty (0.95)    : ₹56.2  →  Final: ₹56/week | Max payout: ₹1,800
```

### Payout Calculation

```
Daily Income Baseline = Last 4 weeks' average daily earnings

Payout = Daily Income × Severity Factor

  Full day (bandh, major flood)       : × 0.80  →  ~₹720
  Evening block (rain 4–9 PM)         : × 0.50  →  ~₹450
  Peak-hour outage (platform down)    : × 0.35  →  ~₹315
  Waterlogging full-day alert         : × 0.80  →  ~₹720
```

---

## 6. Affordability Justification

A common concern with gig worker insurance is whether they can actually afford it. Here is
why SwiftShield's weekly pricing model works for Karthi specifically.

### The Math

```
Karthi's average weekly earnings        : ₹5,200
SwiftShield Standard Shield premium    : ₹42/week
Premium as % of weekly income          : 0.8%  (less than 1 rupee per hour worked)

Without insurance — one disrupted day  : ₹900 lost  (17% of weekly income gone)
With insurance    — one disrupted day  : ₹42 paid, ₹720 received back
Net gain from a single claim           : ₹678
```

### Why ₹42/week Feels Affordable

| Comparison | Cost |
|---|---|
| SwiftShield weekly premium | ₹42 |
| One cup of chai per day (7 days) | ₹70 |
| One missed delivery due to rain | ₹120–₹180 lost |
| One disrupted evening rush | ₹450–₹550 lost |

For ₹42, Karthi is protected against losses that are **10–17x larger** than the premium.
This is the core value proposition — the premium is a rounding error compared to what
a single disrupted day costs him.

### Break-Even Analysis

```
Karthi needs just ONE claim every 13 weeks to fully recover all premiums paid.

Chennai's northeast monsoon alone causes 3–4 disruptions per month (Oct–Dec).
That is 9–12 disruptions per quarter — far above the 1 needed to break even.
```

### Why Weekly (Not Monthly) Matters

A ₹42 weekly deduction feels like loose change. A ₹168 monthly lump sum feels like a bill.
Same money — completely different psychology. Weekly pricing removes the mental barrier
to purchasing insurance for low-income workers living week to week.

---

## 7. Parametric Triggers

| # | Trigger | Data Source | Threshold | Payout | Type |
|---|---|---|---|---|---|
| T1 | Heavy Rainfall | OpenWeatherMap API | > 40mm in 3 hours | ₹400–₹550 | Environmental |
| T2 | Waterlogging / Flood Alert | GCC / IMD API (mock) | Zone-level official alert | ₹600–₹800 | Environmental |
| T3 | Bandh / Curfew / Strike | NewsAPI (free tier) | Confirmed zone-level closure | ₹600–₹800 | Social |
| T4 | Platform Outage | Swiggy signal (mock) | 0 assignments for 90+ min in peak hours | ₹250–₹400 | Platform |

All triggers are monitored passively in the background. No action required from Karthi.

---

## 8. AI/ML Integration Plan

### Premium Calculation Model
```
Type    : XGBoost Regressor
Inputs  : Zone ID, historical disruption count, week of year,
          7-day weather forecast score, worker claim history, tenure
Output  : Weekly premium in ₹
Retrain : Every Sunday night with new data
```

### Risk Profile Scorer (at Onboarding)
```
Type    : Rule-based + Random Forest
Inputs  : Zone flood/rain index, working hours, shift timing, season
Output  : Risk Score 1–10 → recommended coverage tier
```

### Fraud Anomaly Detector
```
Type    : Isolation Forest + rule-based checks
Inputs  : GPS vs disruption zone, claim frequency, payout amount,
          number of independent sources confirming event,
          zone-wide order drop signal
Output  : Fraud Score 0–100 → auto-approve / hold / reject
```

### Predictive Disruption Forecaster (Admin Dashboard)
```
Type    : Time-series regression (LSTM)
Inputs  : 7-day weather forecast, IMD signals, historical patterns
Output  : Disruption probability % per zone for next 7 days
Use     : Admin alerts + proactive worker notifications
```

---

## 9. Fraud Detection

Every claim passes through 3 layers before payout:

**Layer 1 — Location Check**
Worker's last GPS ping must be within the disrupted zone within 30 minutes of the trigger.
GPS spoofing detected by cross-checking against cell tower data (mocked).

**Layer 2 — Anomaly Check**
Flag if claim frequency > 2× historical weekly average. Flag if worker claims 2 triggers
within 4 hours. Flag if > 85% of all workers in a zone claim the same event simultaneously.

**Layer 3 — Event Verification**
Rain trigger: confirmed by 2 weather APIs. Bandh: confirmed by 2+ news sources.
Platform outage: zone-wide order drop confirmed, not just one worker.

| Fraud Score | Action |
|---|---|
| 0–30 | Auto-approve → instant payout |
| 31–60 | Auto-approve → 24-hr background audit |
| 61–80 | Hold → request location confirmation from worker |
| 81–100 | Reject → notify with reason + 72-hr appeal window |

---

## 10. Adversarial Defense & Anti-Spoofing Strategy

> **Crisis context:** A syndicate of 500 delivery workers exploited a beta parametric platform
> by using GPS-spoofing apps to fake their location inside a red-alert weather zone — triggering
> mass false payouts and draining the liquidity pool. Simple GPS verification is no longer enough.
> This section documents how SwiftShield detects and defeats coordinated spoofing attacks.

---

### 10.1 The Differentiation — Genuine Worker vs GPS Spoofer

A genuine delivery partner caught in a disruption leaves a rich, consistent trail of signals
across multiple independent data sources. A GPS spoofer can fake one signal — but faking all
of them simultaneously is computationally and behaviourally impossible.

SwiftShield runs a **5-signal corroboration check** on every claim. A genuine Karthi passes
all 5 without doing anything. A spoofer fails at least 2–3.

```
SIGNAL 1 — App activity pattern
  Genuine  : Karthi's app shows active delivery sessions BEFORE the disruption started.
             He was logged in, accepting orders, moving between pickup and drop points.
  Spoofer  : No prior app activity. App opened for the first time minutes before the trigger.
             Detection: last_active_session < 30 min before trigger → flag

SIGNAL 2 — Swiggy order history cross-match
  Genuine  : Karthi's Swiggy account shows active orders in Semmencherry zone today.
             His last delivery was 22 minutes before the rain trigger.
  Spoofer  : No Swiggy orders in the zone today. Account inactive or orders from
             a completely different zone.
             Detection: zero_orders_in_zone_today = true → flag

SIGNAL 3 — Device sensor consistency
  Genuine  : Phone accelerometer shows movement patterns consistent with riding an Activa —
             vibration, speed changes, stop-start patterns of navigating traffic.
  Spoofer  : Device is stationary (at home). Accelerometer flat. No motion detected.
             Detection: accelerometer_variance < threshold for 60+ min → flag

SIGNAL 4 — Network cell tower triangulation
  Genuine  : Cell tower pings place Karthi's device in Semmencherry / Perumbakkam.
             Cell tower location and GPS location agree within 200m.
  Spoofer  : GPS says Semmencherry. Cell tower says Velachery (home location).
             Detection: |gps_location - cell_tower_location| > 500m → flag

SIGNAL 5 — Battery and connectivity behaviour
  Genuine  : In heavy rain, network is patchy. GPS pings may drop for 5–10 min windows.
             Battery drains faster from navigation + headlights.
  Spoofer  : Perfect, uninterrupted GPS signal with zero dropout in a "severe weather" zone.
             Suspiciously stable connectivity during a declared network-disrupting event.
             Detection: gps_signal_perfect during red_alert_event = true → flag
```

**ML model input:** All 5 signals feed the Isolation Forest fraud detector as additional
features alongside the existing GPS, claim frequency, and payout anomaly checks.

---

### 10.2 The Data — Detecting a Coordinated Fraud Ring

A lone fraudster is hard to catch. A syndicate of 500 acting together is easy — because
coordination creates statistically impossible patterns in the data.

**Ring-level signals SwiftShield monitors:**

```
PATTERN 1 — Simultaneous claim spike
  Normal   : Claims arrive staggered as workers individually notice they cannot work.
             Spread over 45–90 minutes after a disruption event.
  Attack   : 200+ claims arrive within a 4-minute window of the trigger firing.
             Real disruptions do not produce synchronized human responses.
  Detection: claims_in_4min_window > (zone_policy_count × 0.15) → ring_alert

PATTERN 2 — Telegram/social coordination signal
  Method   : Monitor for abnormal pre-trigger spikes in claim submissions.
             If claims start spiking BEFORE the weather threshold is officially crossed,
             it means workers were pre-warned via an external channel.
  Detection: claim_submission_time < trigger_fire_time → coordination_flag

PATTERN 3 — Device fingerprint clustering
  Method   : Hash the device model + OS version + app version of every claimant.
             In a real population of 500 workers, device diversity is high.
             In a coordinated ring, spoofing apps are shared — device fingerprints cluster.
  Detection: if top_3_device_fingerprints > 40% of claims → syndicate_flag

PATTERN 4 — Geographic impossibility check
  Method   : Cross-reference claimed zone with home address registered at onboarding.
             Flag workers claiming disruption in a zone that is 15+ km from their
             registered home and where they have never previously made a delivery.
  Detection: zone_distance_from_home > 15km AND no_prior_deliveries_in_zone → flag

PATTERN 5 — Claim-to-premium ratio outlier
  Method   : Track lifetime claim-to-premium ratio per worker.
             Genuine workers claim ~1 per 8–10 weeks on average.
             Fraud ring members claim every single trigger event.
  Detection: claims_per_week > 3× zone_average → individual_flag
             if 50+ workers hit individual_flag simultaneously → ring_confirmed
```

**When a ring is confirmed:**
- All pending claims from flagged workers in that event are moved to manual review queue
- Liquidity pool freeze is NOT triggered (honest workers' pending claims continue)
- Admin dashboard raises a `RING_ALERT` with the cluster of flagged worker IDs
- Individual payout cap applied: max 1 payout per worker per event, regardless of ring size

---

### 10.3 The UX Balance — Protecting Honest Workers

The biggest risk of a strong fraud system is false positives — penalizing Karthi for having
a genuine network drop during the very storm he is caught in. SwiftShield uses a
**presumption of innocence** model: honest workers are never blocked, only delayed.

```
RULE 1 — GPS dropout is NOT a red flag during a disruption
  Problem  : Heavy rain in Semmencherry genuinely disrupts GPS and network signals.
             A flagging system that treats GPS dropout as fraud will punish honest workers.
  Solution : If GPS drops during an active red-alert weather event, the system
             HOLDS the claim (does not reject) and uses the last confirmed location
             as the zone reference. Worker gets benefit of the doubt.
             Hold window: 2 hours. Auto-approve if no other fraud signals present.

RULE 2 — Two-tap location confirmation (not a form)
  Problem  : Asking a worker to fill out a fraud declaration form during a storm
             is a terrible user experience and creates drop-off.
  Solution : If fraud score is 61–80, Karthi gets a single WhatsApp message:
             "We detected a disruption in your zone. Tap YES to confirm you are
             currently in Semmencherry / Perumbakkam."
             One tap. No form. Confirmation takes 3 seconds.
             Auto-approve after tap. No further action needed from Karthi.

RULE 3 — First-time flag gets benefit of the doubt
  Problem  : A new worker with no claim history has no baseline to compare against.
             Treating their first claim as suspicious is unfair.
  Solution : Workers with < 4 weeks of claim history receive automatic approval
             for their first 2 claims regardless of fraud score, with background audit.
             Trust is earned. Fraud risk is low for new, unconnected workers.

RULE 4 — Appeal window is always open
  Problem  : Even the best fraud system has false positives.
  Solution : Every rejected claim includes:
             - A plain-language reason (e.g. "Your GPS location did not match the alert zone")
             - A 72-hour appeal window accessible from the dashboard
             - One-tap appeal submission with optional photo/video evidence
             Approved appeals automatically improve the worker's trust score.

RULE 5 — Transparent fraud score explanation
  Problem  : A black-box rejection feels unfair and destroys trust in the platform.
  Solution : When a claim is held or rejected, the worker sees exactly which signal
             triggered the flag — in simple language, not technical terms.
             Example: "Your device showed no movement for the past hour. This is
             unusual for an active delivery shift. Tap to confirm your location."
```

**Honest worker experience during a genuine disruption:**

```
Karthi is riding in Semmencherry when rain starts.
His GPS drops for 8 minutes due to network congestion.

Without RULE 1  : System flags GPS dropout → claim held → Karthi confused and unpaid.
With RULE 1     : System sees red-alert event + GPS dropout → uses last known location
                  → no flag raised → claim auto-approved → ₹480 credited in 90 min.

Karthi never noticed anything was different. He just got paid.
```

---

## 11. Platform Choice

**Decision: Progressive Web App (PWA)**

Semmencherry and Perumbakkam are suburban zones where most delivery workers use
budget Android phones on prepaid data plans. A PWA installs directly from the browser
with no Play Store friction, works on low-end Android, supports offline policy viewing, and
enables push notifications. All critical alerts are also sent via WhatsApp as a fallback —
meaning Karthi does not even need to open the app to receive a payout.

---

## 12. Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React.js PWA, Tailwind CSS, Recharts, Leaflet.js |
| Backend | Python 3.11 + FastAPI |
| Auth | Firebase Authentication (OTP login) |
| Background Jobs | Celery + Redis (trigger monitoring) |
| Database | PostgreSQL (Supabase free tier) |
| Cache | Redis (Upstash free tier) |
| ML | scikit-learn + XGBoost, served via FastAPI |
| Weather API | OpenWeatherMap (free tier) |
| Flood / Alerts | IMD / GCC API (mocked) |
| News API | NewsAPI.org (free tier) |
| Platform API | Swiggy Partner API (simulated) |
| Payments | Razorpay Test Mode (UPI mock) |
| Hosting | Vercel (frontend) + Render.com (backend) |
| CI/CD | GitHub Actions |

---

## 13. Repository Structure

```
swiftshield/
│
├── README.md                          ← This file (Phase 1 submission)
│
├── docs/
│   ├── architecture.png               ← System architecture diagram
│   └── wireframes/                    ← UI wireframe images
│       ├── 01-onboarding.png
│       ├── 02-policy-purchase.png
│       ├── 03-dashboard.png
│       └── 04-claim-status.png
│
├── frontend/                          ← React PWA
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Onboarding.jsx
│   │   │   ├── PolicyPurchase.jsx
│   │   │   ├── Dashboard.jsx
│   │   │   └── ClaimStatus.jsx
│   │   ├── services/
│   │   │   ├── api.js                 ← Backend API calls
│   │   │   └── notifications.js       ← FCM push handler
│   │   └── App.jsx
│   └── package.json
│
├── backend/                           ← Python FastAPI
│   ├── main.py                        ← FastAPI app entry point
│   ├── routers/
│   │   ├── auth.py                    ← OTP login endpoints
│   │   ├── policies.py                ← Policy create/renew/fetch
│   │   ├── claims.py                  ← Claim management
│   │   └── payouts.py                 ← UPI payout processing
│   ├── services/
│   │   ├── fraud_engine.py            ← 3-layer fraud scoring
│   │   ├── trigger_monitor.py         ← Celery background jobs
│   │   ├── payment_service.py         ← Razorpay integration
│   │   └── notification_service.py    ← WhatsApp + FCM
│   ├── models/
│   │   └── db_models.py               ← PostgreSQL table definitions
│   └── requirements.txt
│
├── ml/                                ← AI/ML models
│   ├── data/
│   │   └── synthetic_dataset.csv      ← Training data
│   ├── notebooks/
│   │   ├── premium_model.ipynb        ← XGBoost premium calculator
│   │   ├── risk_scorer.ipynb          ← Onboarding risk profile
│   │   └── fraud_detector.ipynb       ← Isolation Forest model
│   └── models/
│       ├── premium_model.pkl          ← Trained model (saved)
│       └── fraud_model.pkl
│
└── .github/
    └── workflows/
        └── ci.yml                     ← GitHub Actions CI/CD
```

---

## 14. Development Plan

Execution Strategy:

SwiftShield is designed using a progressive delivery model, ensuring early functionality and iterative enhancement:
Phase 2 prioritizes a fully working prototype demonstrating end-to-end automation
Phase 3 enhances the system with AI/ML, fraud detection, and scalability features

This approach minimizes execution risk while maximizing demonstration impact.

Phase 1 — Ideation & Foundation

Defined delivery persona and real-world disruption scenarios
Designed end-to-end application workflow
Developed weekly pricing model aligned with gig worker income cycles
Identified parametric triggers and payout logic
Selected scalable tech stack and system architecture
Created UI wireframes for onboarding, policy, and dashboard

Phase 2 — Core Platform Implementation

Objective: Demonstrate a complete parametric insurance lifecycle
Core Capabilities:
Seamless onboarding with OTP-based authentication
Rule-based risk profiling and dynamic weekly premium calculation
Policy creation aligned with weekly earnings cycle

Implementation of initial parametric triggers:
Environmental (rainfall)
Platform disruption (order outage)
Automated claim initiation based on trigger validation
Instant payout simulation (mock UPI transfer)
Worker dashboard displaying coverage, claims, and earnings protection
This phase ensures a zero-touch claim experience, validating the core value proposition.

Phase 3 — Intelligence & Optimization

Objective: Enhance system accuracy, trust, and scalability
AI/ML Enhancements:
Machine learning-based premium prediction
Risk scoring using historical and environmental data
Fraud Detection Framework:
GPS-based location verification
Claim anomaly detection
Multi-source event validation
Fraud scoring and decision engine

Expanded Automation:
Additional triggers (flood alerts, civic disruptions)
Real-time monitoring with background job processing

Financial Integration:

Payment gateway integration (Razorpay test mode)
Simulated instant payout workflow

Advanced Analytics:

Worker dashboard with earnings protection insights
Admin dashboard with risk analytics and claim trends

Final Outcome:

SwiftShield delivers a fully automated, AI-powered parametric insurance platform that:
Protects gig workers from income loss due to external disruptions
Eliminates manual claims through real-time trigger-based automation
Enables instant payouts aligned with weekly earning cycles
Ensures trust through intelligent fraud detection mechanisms

## 📎 Submission Links

| System Architecture Diagram | https://tinywebs.site/6ye6vP |
| UI Wireframes | https://tinywebs.site/nX7NeO |

---

> **Team Name:** Se7en
> **Institution:** Srm Institute of Science and Technology, Kattankulathur
> 
>