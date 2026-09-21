Document Clustering & Topic Modeling — 20 Newsgroups
An unsupervised NLP pipeline that clusters ~4,300 real newsgroup posts into topics without using their labels, then checks how well the clusters line up with the true categories.

Dataset: 20 Newsgroups (via sklearn.datasets.fetch_20newsgroups), restricted to 5 categories: sci.med, sci.space, comp.graphics, rec.sport.hockey, talk.politics.guns.

What it does
Preprocessing — lowercases text, strips URLs/emails/file paths, removes stopwords (plus newsgroup-specific boilerplate like nntp, writes, article), and lemmatizes.
TF-IDF vectorization — 8,000 features, unigrams + bigrams, min_df=5 / max_df=0.85 to cut noise.
K-Means clustering — elbow method to pick k, then clusters at k=5 with k-means++ init.
LDA topic modeling — 5 topics fit on a separate count-vectorized matrix.
Dimensionality reduction — PCA (TruncatedSVD) and t-SNE for 2D visualization of cluster structure.
Evaluation — silhouette score, cluster purity, NMI, and ARI against the ground-truth labels.
Results
Metric	Score
Silhouette (cosine)	0.018
Cluster Purity	0.669
NMI	0.565
ARI	—
The silhouette score looks low in isolation, but that's expected for sparse, high-dimensional TF-IDF vectors (8,000 features, ~99% sparsity) — most documents end up roughly equidistant from each other in that space. Purity and NMI are more informative here: hockey and medicine clusters came out very clean (>0.99 purity), while space and medicine posts overlapped more in vocabulary, pulling many documents into one large cluster (49% of the corpus). LDA topics for graphics, space, and hockey mapped cleanly onto the known categories; one topic came out more generic, likely absorbing cross-category posts.

Project structure
.
├── document_clustering.py   # full pipeline, runs end-to-end
├── requirements.txt
├── plots/                   # generated on run: EDA, elbow, LDA topics, PCA, t-SNE, confusion heatmap
└── README.md
Running it
bash
pip install -r requirements.txt
python document_clustering.py
First run downloads the 20 Newsgroups dataset and NLTK stopword/lemmatizer data automatically. Plots are saved to plots/.

Notes
Random seeds are fixed (random_state=42) throughout for reproducibility.
Silhouette is computed on a random sample of 2,000 documents (cosine distance is O(n²), too slow on the full corpus).
t-SNE is run on a 50-dimensional PCA projection rather than the raw sparse matrix, for speed.


