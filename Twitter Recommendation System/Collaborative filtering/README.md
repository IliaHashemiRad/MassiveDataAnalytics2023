# Collaborative Filtering - Tweet Recommendation

## 📖 Overview

This project implements a user-based collaborative filtering recommendation system for Twitter. The system analyzes user interaction patterns (retweets, replies, quotes) to find similar users and recommend tweets that similar users have engaged with.

## 🎯 Objectives

- Build a personalized tweet recommendation engine
- Implement collaborative filtering using user-user similarity
- Handle various types of Twitter interactions
- Scale to large social media datasets using Apache Spark

## 🔧 Technologies Used

- **Apache Spark (RDD API):** For distributed processing
- **PySpark:** Python interface for Spark
- **K-Nearest Neighbors (KNN):** For finding similar users
- **Collaborative Filtering:** User-based recommendation algorithm
- **JSON Processing:** For handling Twitter API data

## 📊 Key Features

### 1. **Data Processing**
- Parse Twitter JSON data with nested structures
- Extract user-tweet interactions
- Handle retweets, replies, quotes, and original tweets
- Build user-tweet interaction matrix

### 2. **Rating System**
The system assigns ratings based on interaction types:
- **Retweet:** User shares content → High rating
- **Reply:** User engages with content → Medium rating
- **Quote:** User adds commentary → High rating
- **Original Tweet:** User's own content → Highest rating

### 3. **User Similarity**
- Compute user-user similarity based on rating vectors
- Use cosine similarity or Pearson correlation
- Identify K most similar users (K-Nearest Neighbors)
- Weight similarities for recommendation scoring

### 4. **Recommendation Generation**
- For target user, find K similar users
- Aggregate ratings from similar users
- Apply weighted average based on similarity scores
- Rank tweets by predicted rating
- Filter out already-seen tweets

## 📁 Files

- **MDA2023-HW3.ipynb:** Main Jupyter notebook with complete implementation
- **Report.pdf:** Detailed project report with methodology and results

## 🚀 Getting Started

### Prerequisites
```bash
pip install pyspark
```

### Running the Project

1. Open the Jupyter notebook:
```bash
jupyter notebook MDA2023-HW3.ipynb
```

2. Ensure Twitter dataset is available in JSON format

3. Run all cells sequentially to generate recommendations

## 🔍 Algorithm Details

### Step 1: User-Tweet Matrix Construction
```
Input: Twitter interaction data
Process:
  1. Parse JSON tweets
  2. Extract user-tweet pairs
  3. Assign ratings based on interaction type
  4. Build sparse user-tweet matrix
Output: User-tweet rating matrix
```

### Step 2: Find Similar Users
```
Input: Target user, rating matrix
Process:
  1. Get target user's rating vector
  2. Compute similarity with all other users
  3. Sort by similarity score
  4. Select top K similar users
Output: K nearest neighbors
```

### Step 3: Generate Recommendations
```
Input: Target user, K similar users, rating matrix
Process:
  1. For each unseen tweet:
    - Get ratings from similar users
    - Compute weighted average
    - Weight by user similarity
  2. Sort tweets by predicted rating
  3. Return top N recommendations
Output: Ranked list of recommended tweets
```

## 📈 Performance Metrics

The system can be evaluated using:
- **Precision@K:** Accuracy of top-K recommendations
- **Recall@K:** Coverage of relevant items in top-K
- **Mean Average Precision (MAP):** Overall recommendation quality
- **Coverage:** Percentage of items that can be recommended

## 💡 Key Insights

- **Cold Start Problem:** New users/tweets lack interaction history
- **Sparsity:** Most users interact with few tweets
- **Scalability:** Distributed computing handles large-scale data
- **Diversity:** Balance between accuracy and recommendation diversity

## 🎯 Advantages

✅ Intuitive and explainable recommendations
✅ No need for content features
✅ Discovers unexpected relevant content
✅ Adapts to changing user preferences

## ⚠️ Challenges

- Requires sufficient user interaction data
- Computational complexity for similarity calculation
- Sparsity issues in user-tweet matrix
- Popularity bias toward trending content

## 🔧 Optimization Strategies

1. **Dimensionality Reduction:** Use matrix factorization
2. **Approximate KNN:** Use LSH for faster neighbor search
3. **Hybrid Methods:** Combine with content-based filtering
4. **Caching:** Store precomputed similarities

## 📚 Further Reading

For detailed methodology, algorithm explanations, experimental results, and performance analysis, please refer to **Report.pdf**.

---

*This project demonstrates classic collaborative filtering techniques applied to social media recommendations.*
