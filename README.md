# 🧠 Social Media Sentiment & Engagement Analysis (Spark SQL + DataFrames)

This project analyzes social media activity using Apache Spark — focusing on hashtag trends, user engagement across age groups, the influence of sentiment, and verified user reach.

We leverage **Spark SQL** and **DataFrame transformations** on structured data from `posts.csv` and `users.csv`.

---

## 📁 Dataset Used

- `users.csv`: Contains 100+ fictional user profiles (ID, username, age group, country, verification).
- `posts.csv`: Contains 300+ fictional social media posts with likes, retweets, hashtags, and sentiment scores.

Both were generated to simulate realistic engagement and sentiment patterns.

---

## 📊 Analysis Tasks

### ✅ 1. Hashtag Trends
- Extracted and exploded hashtags from all posts.
- Counted their frequency.
- Returned the **top 10 trending hashtags**.

📄 Output: `outputs/top_hashtags/part-00000*.csv`

---

### ✅ 2. Engagement by Age Group
- Joined `posts.csv` and `users.csv` on `UserID`.
- Grouped by `AgeGroup`.
- Calculated average likes and retweets.

📄 Output: `outputs/engagement_by_age/part-00000*.csv`

---

### ✅ 3. Sentiment vs Engagement
- Labeled each post as **Positive**, **Neutral**, or **Negative** using `SentimentScore`.
- Computed average likes and retweets for each sentiment type.

📄 Output: `outputs/sentiment_vs_engagement/part-00000*.csv`

---

### ✅ 4. Top Verified Users by Reach
- Defined **Reach = Likes + Retweets**.
- Filtered only verified users.
- Returned **top 5 verified users** by total reach.

📄 Output: `outputs/top_verified_users/part-00000*.csv`

---

## ⚙️ How to Run

1. Make sure you have Docker installed.
2. Clone this repo and navigate into it.
3. Start Spark with:

```bash
docker run -it --rm -v "$PWD":/app -w /app bitnami/spark /bin/bash

