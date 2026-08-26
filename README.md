# 🤖 Candidate Recommendation Bot for Slack

This project provides an automated solution for recommending top job candidates using Eightfold match scores, summarizing their fit and gaps, and posting structured messages into a Slack channel.

---

## 🎯 Challenge Overview

You are working for a recruiting firm using Eightfold to source candidates for various open roles. The goal is to:

- Select the **top 2 candidates** per position based on match score.
- Post this information to a designated **Slack channel**.
- Include a **rationale for candidate fit**, the **match score**, and **explanation for non-perfect scores**.

---

## 🧠 Eightfold Matching Overview

Eightfold assigns a **match score from 0 to 5** for each candidate-position pair, based on:

- Skills (acquired/inferred)
- Job titles and seniority
- Location and distance/remoteness
- Education, experience
- Similarity to ideal candidates

---

## 📤 Expected Slack Message

Each message should include:

- 🎯 **Position Title & Location**
- 🧑‍💼 Top 2 Candidates (name, location, profile link, resume link)
- 📈 Match Score
- ✅ Reasons why they are a great fit
- ⚠️ Explanation for any score less than 5

---

## 📁 Project Structure

```
├── main.py                  # Main Python script
├── api_matched_position.py  # For each candidate, it sends a GET request to Eightfold’s API using their profile_id
├── api_profiles.py          # It extracts Resume URL and Profile link and attached these fields as resume and link profile to each candidate in the JSON file
├── api_skills.py            # Retrieve each candidate’s skills based on their profile_id and joins the skills into a comma-separated string and Updates the skills field of each candidate in the data.json
├── data.json                # JSON with candidate & position data
└── README.md                # This file
```

## 📤 Example Slack Output
🔎 Top Candidates for Data Scientist in Barcelona

Position Summary: Seeking a data-driven individual with Python, SQL, and ML skills.

👤 Candidate 1: Alice Johnson (4.7/5.0)

📍 Location: Madrid

📝 Experienced data scientist with over 5 years of ML experience.

🔗 View Profile | Download Resume

🔧 Skills: Python, SQL, Machine Learning, Tableau

✅ 5 years of relevant experience, Strong skills in Python, SQL, Located in target location: Madrid

⚠️ Score of 4.7/5.0 indicates some alignment gaps with position requirements
