# Random Walk with Restart - Tweet Recommendation

## 📖 Overview

This project implements a graph-based tweet recommendation system using the Random Walk with Restart (RWR) algorithm. The system models user interactions as a directed graph and uses random walk techniques to discover similar users and recommend relevant content.

## 🎯 Objectives

- Build a graph-based recommendation system
- Implement Random Walk with Restart algorithm
- Compare RWR with standard random walk
- Discover similar users through graph traversal
- Generate personalized tweet recommendations

## 🔧 Technologies Used

- **Apache Spark (RDD API):** For distributed graph processing
- **PySpark:** Python interface for Spark
- **Graph Algorithms:** Random walk implementations
- **Network Analysis:** User interaction modeling
- **JSON Processing:** For Twitter data

## 📊 Key Features

### 1. **Graph Construction**
- Build directed user-user interaction graph
- Edges represent interactions (retweets, replies, quotes)
- Edge weights based on interaction frequency
- Handle self-loops and multi-edges

### 2. **Random Walk with Restart (RWR)**
- Start from target user node
- Navigate to neighbors with probability based on edge weights
- Restart to origin with probability α (restart probability = 0.05)
- Track visit frequency for each node
- Run multiple walks to accumulate statistics

### 3. **Similarity Detection**
- Count visits to each user during random walks
- Higher visit frequency indicates stronger similarity
- Exclude the origin user from results
- Select top-K most frequently visited users

### 4. **Recommendation Generation**
- Retrieve tweets from similar users
- Rank by user similarity
- Filter already-seen content
- Return top-N recommendations

## 📁 Files

- **MDA2023-HW4.ipynb:** Main Jupyter notebook with complete implementation
- **Report.pdf:** Detailed project report with methodology and results

## 🚀 Getting Started

### Prerequisites
```bash
pip install pyspark
```

### Running the Project

1. Open the Jupyter notebook:
```bash
jupyter notebook MDA2023-HW4.ipynb
```

2. Ensure Twitter interaction dataset is available in JSON format

3. Run all cells sequentially to generate recommendations

## 🔍 Algorithm Details

### Step 1: Graph Construction
```
Input: Twitter interaction data
Process:
  1. Extract user-user interactions
  2. Count interaction frequencies
  3. Build adjacency list representation
  4. Normalize edge weights for probabilities
Output: Directed weighted graph
```

### Step 2: Random Walk with Restart
```
Input: User graph, start user, parameters
Parameters:
  - restart_probability (α): 0.05
  - num_steps: 10 per walk
  - num_walks: Multiple iterations
  
Process:
  For each walk:
    current = start_user
    For each step:
      if random() < α:
        current = start_user  # Restart
      else:
        current = random_neighbor(current)  # Walk
      visit_count[current] += 1
      
Output: Visit frequency for each user
```

### Step 3: Similar User Selection
```
Input: Visit counts, K
Process:
  1. Sort users by visit frequency
  2. Remove start user
  3. Select top K users
Output: K most similar users
```

### Step 4: Tweet Recommendation
```
Input: Similar users, tweet database
Process:
  1. Get tweets from similar users
  2. Weight by user similarity (visit count)
  3. Filter seen tweets
  4. Rank by weighted score
Output: Top-N recommended tweets
```

## 📈 Algorithm Parameters

| Parameter | Value | Description |
|-----------|-------|-------------|
| Restart Probability (α) | 0.05 | Probability of returning to start |
| Steps per Walk | 10 | Number of steps in each walk |
| Number of Walks | Multiple | Iterations for statistical stability |
| K (Similar Users) | Variable | Number of similar users to find |

## 💡 Key Insights

### Random Walk with Restart vs. Standard Random Walk

**RWR Advantages:**
- ✅ Biased toward locally connected users
- ✅ Maintains relevance to start user
- ✅ Fewer false positives
- ✅ More personalized recommendations

**Standard Random Walk Issues:**
- ⚠️ Can drift to unrelated parts of graph
- ⚠️ More false positives
- ⚠️ Less personalized results

### Why RWR Works

1. **Local Neighborhood Bias:** Frequently returns to origin, exploring nearby nodes
2. **Global Reachability:** Can still discover distant but relevant connections
3. **Natural Ranking:** Visit frequency naturally ranks similarity
4. **Robust to Noise:** Multiple walks average out random fluctuations

## 🎯 Advantages

✅ Captures indirect relationships (friends of friends)
✅ Natural handling of network structure
✅ Discovers hidden connections
✅ Scalable with distributed computing
✅ No need for explicit feature engineering

## ⚠️ Challenges

- Requires sufficient graph connectivity
- Computational cost of multiple random walks
- Parameter tuning (restart probability, steps)
- Cold start for isolated users

## 🔧 Optimization Strategies

1. **Approximate RWR:** Use shorter walks with more iterations
2. **Precomputation:** Cache frequently accessed neighborhoods
3. **Sparse Graph Storage:** Efficient adjacency list representation
4. **Parallel Walks:** Distribute random walks across cluster

## 📊 Experimental Findings

From the project analysis:
- **Restart Probability = 0.05:** Good balance between local and global exploration
- **10 Steps:** Sufficient for meaningful similarity detection
- **Comparison:** RWR significantly outperforms standard random walk
- **False Positives:** Standard RW has higher rate of irrelevant recommendations

## 🔬 Applications

- Social network friend recommendations
- Content discovery in social media
- Link prediction in networks
- Community detection
- Influence analysis

## 📚 Further Reading

For detailed methodology, algorithm explanations, comparative analysis, experimental results, and performance evaluation, please refer to **Report.pdf**.

### Related Algorithms
- **PageRank:** Special case with uniform restart distribution
- **Personalized PageRank:** Similar concept with different implementation
- **SimRank:** Alternative graph-based similarity measure

---

*This project demonstrates the power of graph-based algorithms for social network recommendations.*
