# NammaFlow Hackathon Presentation Deck Outline (15 Slides)

This document contains a consolidated, high-impact slide-by-slide content guide for a **15-slide** hackathon presentation (ideal for a 5 to 7-minute pitch).

---

### Slide 1: Title Slide
*   **Slide Title**: NammaFlow
*   **Subtitle**: Data-Driven Event Congestion Forecasting & Tactical Mitigation Optimizer
*   **Visuals**: High-tech dashboard screenshot or glowing network logo, Hackathon logo.
*   **Content**:
    *   Team Name & Presenters.
    *   *Tagline*: Bridging AI predictions and ground-level traffic response.
*   **Speaker Notes**: *"Hello judges, today we are presenting NammaFlow, an AI-powered control room platform built to predict event-driven congestion and optimize police deployment in Bengaluru."*

---

### Slide 2: The Operational Challenge & Today's Gaps
*   **Slide Title**: The Crisis: Event-Driven Congestion
*   **Visuals**: Photo of Bengaluru traffic jam, warning icons.
*   **Content**:
    *   **The Issue**: Sudden traffic bottlenecks caused by rallies, sports, festivals, and construction.
    *   **The Gap**: No advance impact measurement, experience-driven manual dispatching, and zero post-event learning.
*   **Speaker Notes**: *"Unexpected road blockages and planned events create massive gridlocks. Today's response is experience-driven, leading to suboptimal police dispatching and no system to learn from the past."*

---

### Slide 3: NammaFlow Solution & Core Pillars
*   **Slide Title**: The Solution: NammaFlow
*   **Visuals**: Laptop mockup showing the dark-themed dashboard, 3-column pillar layout.
*   **Content**:
    *   An intelligent, closed-loop command center.
    *   **Predictive**: Forecasts Congestion Severity and Resolution Duration.
    *   **Prescriptive**: Automatically generates tactical checklists for manpower, barricades, and diversions.
    *   **Self-Learning**: Updates predictions based on ground-truth feedback.
*   **Speaker Notes**: *"NammaFlow is a closed-loop platform that uses machine learning to forecast incident impact, prescribe tactical deployments, and continuously self-calibrate using ground feedback."*

---

### Slide 4: Technology Stack & Architecture
*   **Slide Title**: Platform System Architecture
*   **Visuals**: Flow block diagram (Frontend -> FastAPI -> ML Models -> JSON Storage).
*   **Content**:
    *   **Frontend**: HTML5, Vanilla CSS3 (Glassmorphic theme), Leaflet.js (maps), Chart.js (graphs).
    *   **Backend Server**: FastAPI (Python), Uvicorn.
    *   **ML Engine**: Scikit-Learn (Random Forest), Pandas, Numpy, Joblib.
    *   **Storage**: Persistent JSON append database (`feedback.json`).
*   **Speaker Notes**: *"We built this using FastAPI for high-performance backend routing, Scikit-Learn for ML pipelines, and a lightweight Vanilla CSS interface for a high-tech dashboard feel."*

---

### Slide 5: The incident Dataset & Preprocessing
*   **Slide Title**: Harnessing Localized Traffic Data
*   **Visuals**: Data metric badges, snippet of the CSV table.
*   **Content**:
    *   **8,173** historical traffic incident records in Bengaluru.
    *   **Preprocessing**: Bounding box coordinate filtering, missing value imputation, and resolution duration cap (0-48 hours) to eliminate outlier noise.
*   **Speaker Notes**: *"We processed a database of over 8,000 incident reports in Bengaluru. We filtered out coordinate noise and capped resolution times to clean the data for modeling."*

---

### Slide 6: Feature Engineering & Centroid Mapping
*   **Slide Title**: Spatial-Temporal Engineering
*   **Visuals**: Icons for clock, calendar, and map pin.
*   **Content**:
    *   **Temporal Features**: Hour, weekday, month, and Peak Hour flags (commute hours).
    *   **Geographical Centroids**: Calculated mean coordinates for 55 police station jurisdictions to handle auto-coordinates fallback.
*   **Speaker Notes**: *"We engineered peak commute flags and calculated mean centroids for 55 police jurisdictions, mapping local geography and timing context."*

---

### Slide 7: Machine Learning Engine (Models)
*   **Slide Title**: The AI Engine: Congestion Score & Models
*   **Visuals**: Random Forest icons, Accuracy/R2 metrics in bold.
*   **Content**:
    *   **Impact Score Formula**: $\text{Score} = \text{Base(Cause)} \times \text{Priority} \times \text{Closure} \times \text{Corridor} \times \text{Peak}$.
    *   **Severity Classifier (RandomForest)**: Predicts Low/Medium/High/Critical. **Accuracy: 99.0%**.
    *   **Duration Regressor (RandomForest)**: Predicts resolution minutes. **R2 Score: 86%**.
*   **Speaker Notes**: *"Using a custom impact score, our Random Forest Classifier achieves 99% accuracy in predicting severity. Our Regressor estimates resolution duration with an 86% R2 score."*

---

### Slide 8: Prescriptive Recommendations & Rerouting Heuristics
*   **Slide Title**: Prescribing Actionable Blueprints
*   **Visuals**: Resource table (Severity vs Manpower vs Barricades).
*   **Content**:
    *   **Manpower & Barricades**: Outputs optimized officer counts, role breakdowns, and barricades.
    *   **Dynamic Junction Querying**: Queries the dataset to recommend the top 3 nearest historical control junctions for detours.
*   **Speaker Notes**: *"We translate predictions to blueprints. The system prescribes officer counts and dynamically queries the database for the nearest historical detour junctions."*

---

### Slide 9: Demo Part 1: Landing & Historical Hotspots
*   **Slide Title**: Live Demo: Historical Hotspot Map & Analytics
*   **Visuals**: Screenshot of the map with color-coded circles, charts.
*   **Content**:
    *   Visualizing 800 sampled incidents on a dark-themed Leaflet map.
    *   Interactive popups showing incident metadata.
    *   Chart.js graphs breaking down causes and peak commute hours.
*   **Speaker Notes**: *"Let's jump into the live demo. Our landing tab aggregates incident history, plotting hotspots on an interactive map alongside cause and time-of-day analytics."*

---

### Slide 10: Demo Part 2: Interactive Simulator
*   **Slide Title**: Live Demo: Mitigation Simulator
*   **Visuals**: Screenshot of the input form and map pin.
*   **Content**:
    *   Flexible parameter configuration (cause, priority, timing).
    *   **Click-to-Pin**: Clicking on the map automatically snaps coordinates into the simulator form.
*   **Speaker Notes**: *"In the Planner tab, operators simulate incidents. Clicking directly on the map automatically snaps the coordinates into our parameter form."*

---

### Slide 11: Demo Part 3: Predictive & Prescriptive Output
*   **Slide Title**: Live Demo: Tactical Blueprints
*   **Visuals**: Screenshot of the glowing purple and blue prediction/mitigation cards.
*   **Content**:
    *   Pulsing Severity Badges and resolution time stopwatch.
    *   Manpower requirements and officer task distribution.
    *   Barricade count and placement descriptions.
*   **Speaker Notes**: *"Running the simulator outputs a High severity forecast lasting 523 minutes, alongside a blueprint for 8 officers and 15 warning barricades."*

---

### Slide 12: Demo Part 4: Detour Mapping Visualization
*   **Slide Title**: Live Demo: Visual Rerouting on Map
*   **Visuals**: Map close-up showing red incident pin, amber detour pins, and dashed lines.
*   **Content**:
    *   Incident site marked in Red.
    *   Recommended diversion control points (e.g. Bilekahalli Junc) marked in Amber.
    *   Dashed detour lines linking points.
*   **Speaker Notes**: *"On the map, we see amber pins mapped at Bilekahalli Junction and Jayadeva Junction, with dashed detour routing lines connecting them."*

---

### Slide 13: Demo Part 5: Closed-Loop Feedback
*   **Slide Title**: Live Demo: Closing the Incident
*   **Visuals**: Screenshot of the incident closure feedback form.
*   **Content**:
    *   Logging actual outcomes (actual duration, officers deployed).
    *   1 to 5 star rating given by ground officers.
    *   Direct validation of recommended plans.
*   **Speaker Notes**: *"Once resolved, ground officers log the actual resources used and rate the plan's effectiveness out of 5 stars, feeding the learning system."*

---

### Slide 14: Demo Part 6: Continuous Self-Learning
*   **Slide Title**: Live Demo: Post-Event Learning Dashboard
*   **Visuals**: Screenshot of Tab 3 (Accuracy Progression line graph, KPIs).
*   **Content**:
    *   Confidence levels, severity accuracy rates, and manpower savings metrics.
    *   **Self-Calibration Curve**: Accuracy rising and MAE dropping over feedback counts.
*   **Speaker Notes**: *"On submission, the dashboard redirects to the Learning tab. We see the system confidence rating, manpower hours saved, and a progression curve showing the AI self-calibrating."*

---

### Slide 15: Cloud Deployment & Conclusion
*   **Slide Title**: Deployment, Scale & Q&A
*   **Visuals**: Render, Vercel, and Docker logos.
*   **Content**:
    *   **Hybrid Hosting**: Vercel (CDN Frontend) + Render (Dockerized FastAPI ML Backend).
    *   **Scale**: Easily scalable to other cities by swapping the CSV dataset.
    *   *Summary*: Quantified impacts, optimized deployments, and closed-loop self-learning.
*   **Speaker Notes**: *"NammaFlow is fully dockerized and deployed in a hybrid Vercel/Render cloud. It scales to any city by simply swapping the dataset. Thank you, and we are open for questions!"*
