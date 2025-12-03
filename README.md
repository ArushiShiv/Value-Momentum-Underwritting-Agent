# AI-Driven Insurance Underwriting Co-Pilot 

Intelligent Risk Assessment | ML + GenAI + Business Rules | Flask Web App

A powerful AI-assisted underwriting system that automates risk evaluation, explains decisions using GenAI, detects red flags, predicts customer behaviour using ML, and generates the required document checklist for underwriting — all inside one interactive dashboard.

# Project Overview:-

Traditional insurance underwriting is slow, manual, and inconsistent.
Underwriters must read customer details, analyse risk factors, assess vehicle condition, interpret past insurance history, and make decisions — which often causes:

* Delays in issuing decisions
* Inconsistent judgement
* Difficulty identifying red flags
* Lack of explainability
* Increased manual workload

# Solution: AI-Powered Underwriting Co-Pilot:-

* This project acts as a junior underwriter, combining:
* Machine Learning (XGBoost, Random Forest, Logistic Regression)
* Business Rule Validation + Red Flag Engine
* GenAI Multi-Stage Reasoning Chain
* Document Recommendation Engine
* Full-Stack Web Dashboard (HTML + CSS + JS + Flask)

# Features:-

# 1. Validation + Red Flag Detection Engine

From your app.py logic, the system validates:
* Age, premium, vintage ranges
* License, insurance history
* Vehicle age, condition
* Region codes, risk categories

Detects red flags such as:
* No driving license
* Previous vehicle damage
* No prior insurance
* Young driver (<25)
* Low premium despite damage
(Reference: Validation & red-flag logic inside BusinessRulesEngine in app.py)

# 2. ML-Based Risk Prediction

Machine learning predicts customer interest in buying insurance, using:
* XGBoost
* Random Forest
* Logistic Regression

Model training includes:
* Encoding
* Scaling
* SMOTE class balancing
* Evaluation (ROC-AUC, Precision, Recall, F1)

(Reference: Multi-Model Training Pipeline in EnhancedMultiModelPipeline)

 # 3. Composite Risk Scoring

A corrected risk logic combines:
* ML probability
* Red flag score
* Underwriting risk

Final Tier = Low / Medium / High
(Reference: EnhancedRiskTierEngine logic)

# 4. GenAI Multi-Stage Reasoning

The GenAI Agent performs:

* Stage 1: Summary
* Stage 2: Decision Rationale
* Stage 3: Underwriting Recommendation
* Stage 4: Follow-up Chat Co-Pilot

(Reference: GenAI Chain in EnhancedGenAIPromptChain)

 5. Document Recommendation Engine

Automatically generates documents required based on:
* Risk tier
* Red flags
* Vehicle history
* Age groups

(Reference: EnhancedDocumentRequestAgent in app.py)

# 6. Full-Stack Dashboard UI

Your frontend (from templates) contains:
* Clean form for applicant details
* Real-time risk score bar
* Risk tier badge
* AI explanations
* Document checklist
* Red flags list
* Chat-based assistant

(Reference: HTML structure in test.py frontend snippet showing dashboard UI elements)

# Architecture Overview:-

Frontend (HTML + CSS + JS)
       ↓
Flask Backend API
       ↓
Business Rules Engine
       ↓
ML Prediction Engine (XGBoost / RF / LR)
       ↓
Composite Risk Scorer
       ↓
GenAI Reasoning Chain (3 Stages)
       ↓
Document Recommendation Engine
       ↓
Interactive Dashboard Output

# Project Structure:-
/project-root
-> app.py                     # Main Flask backend logic :contentReference[oaicite:10]{index=10}
-> config.py                  # API keys & configuration :contentReference[oaicite:11]{index=11}
-> requirements.txt           # All Python dependencies :contentReference[oaicite:12]{index=12}
-> test.py                    # Frontend HTML+JS code (template) :contentReference[oaicite:13]{index=13}
-> templates/
   - index.html             # Dashboard UI
-> static/
    - css/
    - js/
-> models/                    # Trained ML models (saved using joblib)
-> data/
     -train.csv              # Dataset or synthetic dataset

# Installation & Setup:-

1. Clone the Repository
cd Insurance-Underwriting-AI-Copilot

2. Install Dependencies
pip install -r requirements.txt

3. Add API Key (OpenRouter)

Update config.py:

OPENROUTER_API_KEY = "your-key"

4. Run the App
python app.py


Your dashboard will be live at:

http://127.0.0.1:5000/

 # Tech Stack:-

Backend:
* Flask
* Python
* Requests (OpenRouter API)
* Joblib
* Scikit-Learn
* XGBoost
* Imbalanced-Learn

Frontend:
* HTML, CSS, JavaScript
* Interactive dashboard
* Chat-based AI assistant

AI & ML:
* Multi-model ML pipeline
* Risk tiering engine
* Feature engineering
* SMOTE balancing
* GenAI prompt chaining

# Results & Impact:-

Outcome:
* The system provides a fast, intelligent, and explainable underwriting experience.

 Impact:
* Faster underwriting decisions
*  AI-based explainability
*   Consistent risk evaluation
*   Reduced manual workload
*    Auto-generated documents

# Future Improvements:-

* Add OCR for reading documents
* Add user authentication
* Improve chat memory
* Deploy on cloud
* Add downloadable PDF reports
