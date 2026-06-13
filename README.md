# document-clustering-topic-modelling
Unsupervised ML pipeline to cluster 20K news documents and discover hidden topics using K-Means, LDA, and t-SNE

📄 Document Clustering & Topic Modelling

🔍 Overview
An end-to-end unsupervised Machine Learning pipeline that automatically groups large collections of text documents into meaningful clusters and discovers hidden topics within them — without any labeled data.
Applied on the 20 Newsgroups dataset (~20,000 news articles across 20 categories), this project demonstrates the full NLP + ML pipeline from raw text to interpretable insights.

🎯 Problem Statement
Given a large collection of unlabeled documents:
Can we automatically group similar documents together?
Can we discover what "themes" or "topics" exist across the corpus?
Can we visualize the cluster structure in 2D?

🛠️ Tech Stack
LibraryPurposescikit-learnTF-IDF Vectorization, K-Means Clustering, t-SNEnltkText preprocessing, stopword removalgensimLDA Topic Modellingmatplotlib / seabornVisualizationspyLDAvisInteractive topic visualization dashboardpandas / numpyData handling

🧠 Concepts Covered:
TF-IDF Vectorization — Converting raw text to numerical features
K-Means Clustering — Grouping documents by vector similarity
Elbow Method — Finding optimal number of clusters (K)
Silhouette Score — Evaluating cluster quality
LDA (Latent Dirichlet Allocation) — Probabilistic topic modelling
Coherence Score — Evaluating topic quality
t-SNE — Dimensionality reduction for 2D cluster visualization
pyLDAvis — Interactive topic exploration

📁 Project Structure

document-clustering-topic-modelling/
│
├── document_clustering.ipynb   # Main notebook (in progress)
├── requirements.txt            # Dependencies
└── README.md


🔄 Pipeline

Raw Text
   ↓
Text Preprocessing (lowercasing, stopword removal, lemmatization)
   ↓
TF-IDF Vectorization
   ↓
K-Means Clustering ──────────────→ Elbow Method + Silhouette Score
   ↓                                         ↓
LDA Topic Modelling              t-SNE Cluster Visualization
   ↓
pyLDAvis Interactive Dashboard


📊 Results (In Progress)
MetricValueOptimal K (clusters)TBDSilhouette ScoreTBDLDA Coherence ScoreTBD

📦 Requirements
See requirements.txt

🗂️ Dataset
20 Newsgroups — A classic NLP benchmark dataset containing ~20,000 newsgroup posts across 20 categories including sports, politics, technology, religion, and more.

👤 Author
Lagudu Pooja Rani
3rd Year B.Tech | Indian Institute of Technology Jodhpur

3rd Year B.Tech | [Your College]

[LinkedIn] | [GitHub]
