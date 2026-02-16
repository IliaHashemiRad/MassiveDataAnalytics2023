# Twitter Recommendation System

## 📖 Overview

This collection contains two complementary approaches to building a tweet recommendation system using different machine learning and graph-based techniques. Both projects leverage Apache Spark for distributed processing of large-scale Twitter data.

## 🎯 Objectives

- Build personalized tweet recommendation engines
- Compare different recommendation strategies
- Handle large-scale social media interaction data
- Implement both collaborative filtering and graph-based approaches

## 📂 Projects

### 1. [Collaborative Filtering](./Collaborative%20filtering/)
**User-Based Recommendation System**

Uses collaborative filtering to recommend tweets based on similar users' preferences:
- Analyzes user-tweet interaction patterns
- Finds similar users using K-Nearest Neighbors
- Generates recommendations using weighted averages
- Considers retweets, replies, and quotes

**Key Technique:** User-user similarity and collaborative filtering

---

### 2. [Random Walk with Restart](./Random%20Walk%20with%20Restart/)
**Graph-Based Recommendation System**

Uses random walk on user interaction graphs to discover similar users:
- Constructs user interaction graphs
- Applies Random Walk with Restart algorithm
- Identifies similar users through visit frequency analysis
- Recommends tweets from similar users

**Key Technique:** Graph traversal and random walk algorithms

---

## 🔧 Technologies Used

- **Apache Spark (RDD API):** Distributed data processing
- **PySpark:** Python interface for Spark
- **Graph Algorithms:** Random walk implementations
- **Machine Learning:** Collaborative filtering, KNN
- **Social Network Analysis:** User interaction modeling

## 📊 Comparison

| Feature | Collaborative Filtering | Random Walk with Restart |
|---------|------------------------|--------------------------|
| Approach | Matrix-based | Graph-based |
| Similarity Metric | Rating vectors | Visit frequency |
| Complexity | O(n·k) for KNN | O(steps × neighbors) |
| Data Structure | User-tweet matrix | Interaction graph |
| Best For | Explicit preferences | Network effects |

## 🚀 Getting Started

### Prerequisites
```bash
pip install pyspark jupyter
```

### Running the Projects

Navigate to either project folder and open the respective Jupyter notebook:

```bash
# Collaborative Filtering
cd "Collaborative filtering"
jupyter notebook MDA2023-HW3.ipynb

# Random Walk with Restart
cd "Random Walk with Restart"
jupyter notebook MDA2023-HW4.ipynb
```

## 📈 Use Cases

- **Social Media Platforms:** Personalized content recommendations
- **News Aggregators:** Similar content discovery
- **E-commerce:** Product recommendations based on user behavior
- **Content Discovery:** Finding relevant content in large networks

## 💡 Key Insights

- **Collaborative Filtering:** Effective when users have rich interaction history
- **Graph-Based Methods:** Capture network effects and indirect relationships
- **Hybrid Approaches:** Combining both methods can yield better results
- **Scalability:** Both approaches scale well with Spark's distributed computing

## 📚 Further Reading

Each project folder contains detailed documentation and comprehensive reports explaining the methodology, implementation, and experimental results.

---

*These projects demonstrate different paradigms for recommendation systems in social networks.*
