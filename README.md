<h1 align="center" style="font-size:48px; font-weight:900; color:#0A5FFF;">
  ONLINE COURSE RECOMMENDATION SYSTEM
</h1>




<img width="1024" height="1536" alt="image" src="https://github.com/user-attachments/assets/6c74d714-7711-4b7e-9ed1-6106f408ae04" />

An end-to-end recommendation system that suggests relevant online courses to learners based on preferences, history, and engagement.

## ✅ Overview

The **Online Course Recommendation System** suggests personalized course recommendations to learners based on their interests, behavior, and prior interactions.  
By analyzing course metadata and user activity, the system helps improve learning outcomes and user engagement.

This project integrates **EDA, content-based filtering, collaborative filtering, and hybrid approaches** to build a recommendation pipeline.

---

✅ Business Objective

Online learning platforms face difficulty in helping learners discover the most suitable courses from large catalogs.
This project aims to build a Recommendation System that suggests courses to users based on:

✅ User behavior
✅ Previous learning history
✅ Engagement patterns
✅ Course characteristics

This solution improves user satisfaction and platform conversion rates.

✅ Problem Statement

Build a recommendation engine that provides personalized course suggestions using:

✔ Collaborative Filtering
✔ Content-Based Filtering
✔ Hybrid Recommendation

The output is a ranked list of recommended courses for each user.

✅ Dataset Description

Each row represents a user–course interaction.

Feature	Description
user_id	Unique learner ID
course_id	Unique course ID
course_name	Name of course
instructor	Instructor name
course_duration_hours	Duration in hours
certification_offered	Yes/No
difficulty_level	Beginner / Intermediate / Advanced
rating	User rating (1–5)
enrollment_numbers	Total enrolled learners
course_price	Price in USD
feedback_score	Sentiment (0.0–1.0)
study_material_available	Yes/No
time_spent_hours	Avg student time
previous_courses_taken	No. of past courses taken

📌 Data Source → Provided XLSX
📌 Data Volume → tabular user–course interaction

✅ Target

Develop a system that can accurately suggest courses users would most likely enroll in and benefit from.

## ✅ Project Workflow

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/67a2da79-8321-4665-b750-80b59b23a90e" />


1️⃣ Data Understanding  
2️⃣ EDA  
3️⃣ Preprocessing  
4️⃣ Feature Engineering  
5️⃣ Recommendation Model  
6️⃣ Evaluation  
7️⃣ Deployment  

## ✅ Techniques Used

✔ **Content-Based Filtering**  
Recommends courses based on similarity in metadata  
(title, difficulty, duration, topic, etc.)

✔ **Collaborative Filtering**  
Recommends courses based on similar users’ interactions  

✔ **Hybrid Approach**  
Combines CB + CF for better personalization  

---

🧠 Recommendation Summary & Inference

Goal: Recommend the most relevant courses to each learner using hybrid recommendations (content + collaborative).

What the system does

Content-Based Filtering (CBF)
Builds a similarity space from course metadata (e.g., course_name, instructor, difficulty_level, course_duration_hours, certification_offered, study_material_available, tags if present).
Typical stack: TF-IDF/CountVectorizer → cosine similarity.

Collaborative Filtering (CF)
Learner–course interaction matrix using rating, time_spent_hours, previous_courses_taken (and/or implicit feedback like enrollments).
Typical stack: Matrix factorization (LightFM/Surprise SVD) → top-N recommendations.

Hybrid Ranking
Combines both signals:

final_score = α * CF_score + (1-α) * CBF_similarity


with sensible defaults (e.g., α=0.6).
Cold-start users get CBF + popularity; cold-start items get CBF.

Personalization Controls
Optional filters by difficulty_level, price range (course_price), certification_offered, or minimum rating.

Expected insights (to validate in EDA)

Courses offering certification and study materials tend to rank higher for most users.

Beginner/Intermediate levels are requested more frequently than Advanced.

High ratings and high enrollments correlate with recommendation popularity.

Feedback score (~ sentiment) and time spent are strong engagement signals; they boost CF weights.

Evaluation (suggested)

Ranking metrics: Precision@K / Recall@K / MAP@K / NDCG@K (e.g., K=5 or 10).

Offline split: time-aware or leave-one-out per user to avoid leakage.

Ablations: CBF only vs CF only vs Hybrid.

✅ Conclusion

We implemented a hybrid course recommendation engine that blends collaborative filtering (learn from similar users) and content-based filtering (learn from course attributes).

The hybrid approach addresses cold-start and sparsity, while keeping strong personalization for active users.

With a clean Streamlit UI and simple deployment path, this system is production-friendly and easy to iterate.

## ✅ Key Insights

📌 Users prefer courses where:  
✅ Certification is available  
✅ Difficulty level is Beginner or Intermediate  
✅ High enrollments  
✅ High user rating  
✅ Study material available  

📌 Higher time-spent = more likely to recommend  

---

## ✅ Folder Structure

📦 Online-Course-Recommendation
│
├── data/
│ └── online_course_recommendation.xlsx
├── notebooks/
│ └── ONLINE_COURSE_RECOMMENDATION.ipynb
├── images/
│ ├── course_recommendation_banner.png
│ ├── workflow_course.png
├── models/
│ └── recommendation.pkl
├── app/
│ └── app.py
├── README.md
└── requirements.txt


## ✅ Tech Stack

| Category | Tools |
|----------|-------|
Language | Python  
Data | Pandas, NumPy  
ML | sklearn, Surprise/LightFM  
Deployment | Streamlit / Flask  
Viz | Seaborn, Matplotlib  
Versioning | Git + GitHub  

---

## ✅ Future Enhancements

🔹 Include real-time user feedback  
🔹 Deep learning–based recommenders  
🔹 Adaptive recommendation based on learning path  
🔹 Recommendation explanations  

---

🚀 Deployment

The Online Course Recommendation System is successfully deployed using Streamlit, allowing users to interact with the recommendation engine through a clean, responsive UI.

✅ Online Deployment (Streamlit Cloud)

You can run or host this application easily via Streamlit Cloud.

🔗 Live App
(https://recommendation-system-project.streamlit.app/)

## deplopyment page screenshot
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/b0d6711b-5eeb-4f1a-b5a5-fd05b6867210" />

## 👤 Author

**Shashank R**  
A passionate Data Science enthusiast focused on building real-world predictive ML models, 
recommendation systems, and end-to-end product deployments.

📧 Email: shashankphenomenon@gmail.com 
🔗 LinkedIn: https://www.linkedin.com/in/your-profile  

