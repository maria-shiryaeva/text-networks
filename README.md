# Music Recommendations Based on Lyrics

## Overview

This project explores a content-based music recommendation approach using song lyrics. The goal is to find tracks with similar textual content by comparing their lyrics.

## Methodology

The recommendation system is based on **TF-IDF vectorization** and **cosine similarity**.

1. **Text preprocessing:** Tracks without lyrics are excluded from the recommendation process.
2. **TF-IDF vectorization:** Song lyrics are transformed into numerical feature vectors, representing the importance of words in individual tracks relative to the entire collection.
3. **Similarity calculation:** Cosine similarity is used to measure the similarity between song vectors. Since the TF-IDF vectors are L2-normalized, similarity can be calculated using their dot product.
4. **Recommendation:** Tracks with the highest similarity scores are selected as recommendations.

## Dataset Representation

The resulting TF-IDF matrix contains:

- **18,454 rows** — songs
- **102,102 columns** — unique terms

The matrix is stored in a sparse format (`text_tfidf.npz`) to handle high-dimensional textual data efficiently.

## Limitations and Further Improvements

TF-IDF captures lexical similarity but does not fully represent semantic relationships between texts. In particular, the approach does not account for:

- Synonyms and paraphrases;
- Word order and contextual meaning;
- Semantic similarity between texts that use different vocabulary.

This makes TF-IDF suitable for basic text-based recommendations and initial filtering, but less effective for deeper semantic matching.

Potential improvements include using contextual embeddings and transformer-based language models to capture semantic similarities between song lyrics.

## Technologies

- Python
- NumPy
- Pandas
- Scikit-learn
- Sparse matrices
- TF-IDF
- Cosine similarity
