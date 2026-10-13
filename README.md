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
6. **Topic Analysis:** Examined representative reviews, interpreted discovered topics, and calculated dominant-topic frequencies.
7. **Exploratory Multi-Topic Analysis:** Tested whether individual reviews could be associated with multiple topics using NMF weights.

### Technologies Used

- Python
- Pandas and NumPy
- Scikit-learn
- Matplotlib
- Jupyter Notebook

## Key Findings

Eight recurring topics were identified from the negative reviews.

| Topic | Dominant Reviews | Percentage |
|---|---:|---:|
| General Gameplay Criticism | 275 | 25.35% |
| Team Performance and Communication | 148 | 13.64% |
| New-Player Experience | 142 | 13.09% |
| Beta vs. Full Release | 134 | 12.35% |
| Declining Playerbase | 117 | 10.78% |
| General Matchmaking | 115 | 10.60% |
| Perceived Waste of Time | 95 | 8.76% |
| Competitor Comparisons | 59 | 5.44% |

The results suggest that matchmaking quality, new-player experience, team-related frustrations, and changes introduced after beta are recurring concerns among negative reviewers.

General gameplay criticism was the largest topic, although this category also contained broad or overlapping complaints.

## Limitations

- NMF identifies statistical patterns in text rather than fully understanding the meaning of each review.
- Topic labels were assigned through qualitative interpretation.
- Individual reviews may discuss multiple complaints, but the primary distribution assigns each review to its highest-weighted topic.
- Reviews containing fewer than 10 words were excluded from the final topic model.
- Multi-topic assignments were sensitive to threshold selection and occasionally produced unrelated or missing topics.
- The results describe a filtered sample of negative Steam reviews, not the entire playerbase.

## Conclusion

This project demonstrates how unsupervised NLP can be used to explore unstructured customer feedback and identify recurring themes without manually labeling thousands of reviews.

Through iterative preprocessing, topic modeling, and qualitative evaluation, the analysis uncovered several recurring sources of player dissatisfaction while also highlighting the limitations of automated topic discovery.

Beyond investigating a game I personally enjoyed, the project provided practical experience in applying machine learning techniques to real-world text data.

## Repository Contents

- `player_negative_feedback_analysis_OS.ipynb`: Jupyter notebook containing the analysis, model experiments, visualizations, and findings.
- `omega_strikers_reviews.csv`: Steam review dataset used for the project.

## How to Run

1. Clone or download this repository.
2. Install the required Python packages:

   ```bash
   pip install pandas numpy scikit-learn matplotlib ipython
   ```

3. Open the Jupyter notebook in VS Code or JupyterLab.
4. Ensure the dataset CSV is in the same directory as the notebook.
5. Run the notebook cells in order.

**Note:** If the notebook references a different CSV filename, update the `pd.read_csv()` path to match the dataset included in this repository.
