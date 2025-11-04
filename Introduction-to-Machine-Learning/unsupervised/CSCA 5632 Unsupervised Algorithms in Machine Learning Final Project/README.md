# 🔬 Longevity Community Topic Analysis (Reddit: BLP)

This project uses **unsupervised machine learning** to analyze and compare the core interests of three major health and longevity communities on Reddit: **r/PeterAttia**, **r/Longevity**, and **r/Biohackers**.

The goal was to move beyond anecdotal observation and scientifically map *what* each community talks about, and *how* their conversations differ in the context of the overall longevity movement.

---

## 🛠️ Methodology: The BERTopic Pipeline

This project was built using a robust, multi-step pipeline focused on data integrity and visual comparison:

1.  **Data Collection & Cleaning:** Over **48,000 unique posts** were scraped, cleaned, and deduplicated.
2.  **Topic Modeling:** **BERTopic** was used, combining S-BERT for robust embeddings, UMAP for dimensionality reduction, and HDBSCAN for density-based clustering.
3.  **Topic Refinement:** Outliers were reduced, and topics were stabilized to ensure the final set was globally consistent across all three subreddits.
4.  **Comparative Visualization:**
    * **Topic Contribution:** A stacked bar chart was generated to quantify the percentage of documents each subreddit contributed to every topic.
    * **Spatial Analysis:** UMAP was used to generate a 2x2 grid, visually comparing how each subreddit's documents occupy the shared topic space.
    * **Hierarchy:** A dendrogram was used to map how specific topics (e.g., "Strength Training") fall under larger umbrella concepts (e.g., "Exercise").

---

## 💻 Tech Stack

* **Language:** Python 3.9+
* **Modeling:** BERTopic
* **Clustering/Reduction:** HDBSCAN, UMAP
* **Data Handling:** Pandas, NumPy
* **Visualization:** Plotly, Matplotlib, Seaborn

---
