# Movie & Book Recommender System

## Overview
This project implements a hybrid recommendation system that generates personalized suggestions for books and movies in both:

- **Within-domain** (books → books, movies → movies)
- **Cross-domain** (books → movies, movies → books)

The system is enhanced with **Reddit-based sentiment analysis**, allowing recommendations to reflect real community opinions.

---

## Key Features
- Hybrid recommendation system (Collaborative + Content-Based)
- Cross-domain recommendation using shared tag embeddings
- Dimensionality reduction (PCA) + similarity search (LSH)
- Topic modeling (LDA) + clustering (K-Means)
- Reddit API integration for sentiment-based reranking

---

## Tech Stack
- **Python**
- pandas, numpy, scikit-learn
- NLP: TextBlob
- PySpark (RankingMetrics)
- Reddit API

---

## Project Structure
movie-book-recommender-system
│
├── notebooks
│ ├── 0_preprocessing.ipynb
│ ├── 1_within_domain_model.ipynb
│ ├── 2_cross_domain_model.ipynb
│ ├── 3_evaluation.ipynb
│ ├── 4_reddit_enrichment_books.ipynb
│ └── 5_reddit_enrichment_movies.ipynb
│
├── model_output
│ ├── book_user_recs.csv
│ ├── book_to_movies.json
│ ├── movie_user_recs.csv
│ └── movies_to_books.json
│
└── README.md




---

## Methodology

### 1. Data Preprocessing
- Unified tag vocabulary across books and movies
- Filtered items by release year (post-1980)
- Cleaned and transformed metadata and ratings

---

### 2. Within-Domain Recommendations
- ALS collaborative filtering on user-item interactions
- Content-based model using:
  - LDA (topic modeling)
  - K-Means clustering
- Hybrid scoring combining both approaches

---

### 3. Cross-Domain Recommendations
- Shared tag representation for books and movies
- PCA for dimensionality reduction (40 dimensions)
- LSH for efficient nearest-neighbor search

---

### 4. Reddit-Based Enrichment
- Scraped posts and comments via Reddit API
- Computed sentiment scores using TextBlob
- Reranked recommendations using sentiment weighting

---

## Evaluation
- Precision@K
- Recall@K
- NDCG
- Implemented using PySpark RankingMetrics

---

## Data
Due to size constraints, raw datasets are not included.

To reproduce results:
- Use publicly available book and movie datasets
- Ensure tag alignment between domains

---

## Results
The system successfully:
- Generates personalized recommendations
- Bridges domains (books ↔ movies)
- Improves ranking quality using social sentiment signals

---

## References
- Kotkov et al. (2021) – Tag relevance prediction  
- Vig et al. (2012) – Tag genome  
- Kotkov et al. (2022) – Tag Genome Dataset for Books  

---

## Author
Developed in a team of three as part of a university project.
