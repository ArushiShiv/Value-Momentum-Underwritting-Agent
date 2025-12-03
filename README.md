# AI-Driven Insurance Underwriting Co-Pilot:-
[GenAI + Agentic AI + ML + Flask + Full-Stack Web App]

A production-grade, intelligent underwriting assistant that automates risk assessment, evaluates red flags, predicts customer interest, generates explainable AI-based reasoning, and recommends required documents — all through a modern full-stack dashboard.

# Project Overview :
Traditional insurance underwriting is slow and manually intensive. Underwriters must review customer details, evaluate risk, check past records, and manually decide policy issuance — leading to delays, inconsistency, and human error.
This project solves that.

The AI-Powered Underwriting Co-Pilot acts like a junior underwriter. It performs:
* Automated risk validation
* ML-based customer interest prediction
* Red-flag detection
* Composite risk scoring
* GenAI reasoning (summary → rationale → recommendation)
* Auto-generated document checklist
* Full-stack dashboard UI
* Chat-based AI assistant
  
This brings speed, transparency, accuracy, and explainability to underwriting.

# Key Features:

# 1. Business Rules Engine
(from app.py)
* Validates inputs
* Detects red flags (no license, damage history, no prior insurance, young driver, etc.)
* Generates warnings + error messages
* Produces a red-flag score (0–100)

# 2. ML Prediction Engine
Models used:
* XGBoost
* Random Forest
* Logistic Regression

Pipeline steps:
* Feature engineering
* Encoding & scaling
* SMOTE imbalance correction
* Train, evaluate, compare models
* Select best model (based on ROC-AUC)

All dependencies in requirements.txt

# 3. Composite Risk Scoring
 Final risk tier = f(ML probability + red-flag score + business rules)
* Low Risk – Auto approve
* Medium Risk – Manual review
* High Risk – Refer to senior / Reject

Underwriters see:
*ML probability
Underwriting risk
Business attractiveness
Full breakdown with scoring visuals

# 4. GenAI Multi-Stage Reasoning Agent
* Stage 1 — Summary
* Stage 2 — Rationale
* Stage 3 — Final Recommendation
* Stage 4 — Chat Co-Pilot

Uses OpenRouter API (from config.py)

# 5. Document Recommendation Engine
Documents depend on:
* Risk tier
* Red flags
* Vehicle condition
* Age group

Examples:
* RC, Aadhaar, PAN
* Previous insurance
* Damage assessment reports
* Bank statements
* Valuation reports
* Gap-coverage declarations

# 6. Full-Stack Dashboard UI
(from frontend template test)

Built with:
* HTML
* CSS
* JavaScript
* Flask templating

UI includes:
* Applicant form
* Risk score bar
* Red-flags panel
* AI insights cards
* Document panel
* Performance metrics
* Chat AI assistant

# Architecture Diagram:

Frontend (HTML/CSS/JS)
      ↓
Flask Backend
      ↓
Business Rules Engine → Red Flags
      ↓
ML Engine (XGBoost/RF/LR)
      ↓
Composite Risk Engine
      ↓
GenAI Reasoning Chain (Summary → Rationale → Recommendation)
      ↓
Document Recommendation Engine
      ↓
Final JSON to UI

# Project Structure:
* app.py – Main backend (ML + rules + GenAI + API)
* config.py – API keys & Flask config
* test.py – Testing script
* templates/ – Frontend HTML (index.html)
* static/
* css/ – Styles
* js/ – Scripts
* models/ – Saved ML models
* data/ – Training dataset (train.csv)
* requirements.txt – Dependencies
* README.md – Documentation
* logs/ – App logs (auto-created)

# How It Works (End-to-End Workflow):
* Underwriter fills form
* Backend validates + checks red flags
* ML predicts customer interest
* Composite risk score calculated
* Risk tier assigned
* GenAI generates explanation + reasoning
* Document engine lists required documents
* Chat co-pilot answers questions
* UI displays final results

 # Tech Stack:
Backend:
* Python (Flask)
* XGBoost, Random Forest, Logistic Regression
* SMOTE, Label Encoding, Scaling
* Joblib
* Requests (OpenRouter API)

Frontend:
* HTML, CSS, JavaScript
* Custom dashboard UI

AI/ML:
* GenAI reasoning pipeline
* Composite risk scoring
* Document intelligence

# Running the Project:
1. Clone Repository:
git clone <your_repo_url>
cd underwriting-copilot

2. Install Dependencies:
pip install -r requirements.txt

3. Set API Keys:
Edit config.py with your OpenRouter key:
OPENROUTER_API_KEY = "your-key"
FLASK_SECRET_KEY = "your-secret"

4. Run Flask App:
python app.py

5. Open in Browser:
http://127.0.0.1:5000/

# Results & Impact:
*  Faster underwriting
*  Consistent decisions
*  Red-flag based risk detection
*  Instant document recommendation
*  Fully explainable AI
*  Strong ML performance (ROC-AUC displayed on dashboard)
