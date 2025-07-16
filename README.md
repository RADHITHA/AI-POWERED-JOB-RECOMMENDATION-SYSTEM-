# AI-POWERED-JOB-RECOMMENDATION-SYSTEM-
AI POWERED JOB AND RESUME RECOMMENDATION SYSTEM

DESCRIPTION
This is an intelligent system that recommends jobs based on uploaded resumes using both rule-based and machine learning techniques. It parses PDF/DOCX resumes, extracts skills, matches them with job listings, performs skill gap analysis, and predicts job roles using trained ML models like Random Forest, SVM, Logistic Regression, and Naive Bayes.

FEATURES
- Resume parsing (PDF/DOCX)
- Skill extraction via regex/NLP
- Skill-based job recommendation
- Skill gap analysis showing missing skills
- Machine learning models:
  - Random Forest (highest F1-score)
  - Logistic Regression
  - Linear SVM
  - Naive Bayes
- F1-score-based model comparison
- Frontend using Flask + HTML/CSS
- Auto-opening web interface
- Displays company name and city for each job

PROJECT STRUCTURE
app.py                 - Flask backend
train_model.py         - ML model training and evaluation
skill_matcher.py       - Skill gap analysis logic
jobs.csv               - Job dataset
resume1.pdf            - Sample resume
templates/             - HTML templates (index, login, result)
  └── index.html
  └── login.html
  └── result.html
static/                - Static assets (CSS/images)
uploads/               - Resume upload storage
vectorizer.pkl         - TF-IDF vectorizer
best_model.pkl         - Trained best ML model
label_mapping.pkl      - Label decoder for job roles

ML MODELS & RESULTS
Machine Learning models are trained using TF-IDF vectors from job descriptions. train_model.py evaluates multiple models:

Model              | Accuracy | F1-Score (Weighted)
-------------------|----------|----------------------
Random Forest      | High     | Best
Logistic Regression| Medium   | Good
Linear SVM         | Medium   | Good
Naive Bayes        | Lower    | Fair

Selected Model: Random Forest (highest F1-score)

EVALUATION METRICS
- F1-Score (Weighted Average)
- Train-test split (70/30)
- Classification report for best model
- Accuracy, precision, recall also reported
- Bar chart plotted for model comparison

HOW TO RUN THE SYSTEM
1. Install dependencies:
   pip install -r requirements.txt

2. Train and evaluate ML models:
   python train_model.py

3. Start the Flask application:
   python app.py

4. The web interface will auto-open in your browser at:
   http://127.0.0.1:5000/login

HOW IT WORKS
- User logs in using username and password (default: user/password)
- Upload resume (PDF or DOCX)
- System parses resume and extracts skills
- Matches skills with job dataset (jobs.csv)
- Performs skill gap analysis
- Displays top job matches with matched and missing skills
- Uses trained ML model to predict likely job role

DATASET FORMAT
jobs.csv must include:
- title: Job role/title
- description: Required skills (comma-separated)
- companies: Company name
- locations: City

TECHNOLOGIES USED
- Python
- Flask
- HTML/CSS
- pdfminer.six, python-docx
- pandas, regex
- scikit-learn (ML)
- TfidfVectorizer
- Matplotlib

FUTURE IMPROVEMENTS
- Use BERT embeddings for better semantic matching
- Add database and user history tracking
- Deploy to cloud with Docker
- Use real job APIs for live data
