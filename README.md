# Player Feedback Analysis Using Unsupervised NLP

**Exploring recurring player complaints in Steam reviews using TF-IDF and Non-negative Matrix Factorization (NMF).**

## Project Overview

Omega Strikers was one of my favorite online multiplayer games, but its declining playerbase eventually made it difficult to find matches and continue playing.

As someone who enjoyed the game, I became curious about what other players thought went wrong. I decided to analyze its Steam reviews using unsupervised Natural Language Processing (NLP), both to identify recurring complaints and to further develop my practical machine learning skills.

**Research Question:** What recurring themes appear in negative Omega Strikers Steam reviews?

## Dataset

The dataset consists of 10,000 English-language Steam reviews collected through the Steam Reviews API.

| Metric | Count |
|---|---:|
| Total reviews collected | 10,000 |
| Positive reviews | 8,400 |
| Negative reviews | 1,600 |
| Negative reviews after initial cleaning | 1,585 |
| Negative reviews used for topic modeling | 1,085 |

The final analysis focuses on negative reviews containing at least 10 words, with duplicate reviews removed.

## Methodology

1. **Data Collection:** Retrieved Steam reviews using the Steam Reviews API.
2. **Data Cleaning:** Removed missing values, formatting tags, URLs, and unnecessary characters.
3. **Text Vectorization:** Converted review text into numerical features using TF-IDF with unigrams and bigrams.
4. **Topic Modeling:** Applied NMF to discover recurring themes without predefined topic labels.
5. **Model Refinement:** Experimented with review-length filtering and custom stopwords to improve topic interpretability.
