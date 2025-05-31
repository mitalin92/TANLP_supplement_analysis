
# Beyond the Reviews: Understanding Wellness Intent and Supplement Experience through NLP

## Author
**Mitali Acharya**  
Data Science for Society and Business (DSSB)  
Constructor University, Bremen  

---

## Overview

This project explores how Natural Language Processing (NLP) can be used to extract meaningful wellness intent and supplement experience from user discussions on Reddit. It analyzes 31,105 unique comments collected from supplement-related subreddits such as r/Supplements, r/Nutrition, and r/Vitamins. The goal is to uncover the real concerns, emotional tones, and patterns behind supplement usage, going beyond surface-level product reviews.

---

## Motivation

Choosing the right multivitamin is often confusing due to conflicting reviews and marketing claims. When the author moved to a new country and had to figure out health and nutrition alone, they realized how difficult it was to make informed supplement choices. This personal struggle led to the research question:

> **How can NLP techniques extract wellness intent and lived supplement experiences from Reddit discussions to support personalized supplement recommendations?**

---

## Data Collection

- **Source**: Reddit  
- **Subreddits**: r/Supplements, r/Nutrition, r/Vitamins  
- **Tool Used**: Python Reddit API Wrapper (PRAW)  
- **Sample Size**: 36,130 raw comments; 31,105 unique processed comments

---

## Methodology

1. **Text Cleaning and Preprocessing**
   - HTML and URL removal, lowercasing, lemmatization
   - Used `spaCy` for efficient preprocessing

2. **Sentiment Analysis**
   - Rule-based: **VADER**
   - Transformer-based: **RoBERTa (cardiffnlp/twitter-roberta-base-sentiment)**

3. **Topic Modeling**
   - Technique: **CorEx** (Correlation Explanation)
   - Anchored topics for comments (Sleep, Anxiety, Energy, Gut Health, etc.)
   - Unsupervised discovery for titles (Mental Health, Product Quality, Diet, etc.)

4. **Supplement Entity Extraction**
   - Phrase-matching using a whitelist
   - Supplement frequency per topic calculated

---

## Key Findings

- **Most Discussed Brands**: Thorne, Centrum, Pure Encapsulations
- **Top Concerns**: Sleep, anxiety, fatigue, gut health, focus
- **Sentiment**:
  - VADER: Inflated positivity due to rule-based lexicon
  - RoBERTa: More balanced, neutral-dominant with subtle dissatisfaction captured
- **Discrepancy** between user curiosity (titles) and actual experiences (comments)

---

## Visualizations

- Supplement frequency bar charts
- Sentiment distribution comparisons (VADER vs. RoBERTa)
- Topic-wise supplement mapping
- Brand mentions per topic
- Sample preprocessed texts and model outputs

---

## Limitations

- Reddit bias (young, Western, tech-savvy)
- No verified health outcomes
- Limited to public Reddit data; unable to include Amazon/iHerb reviews
- No labeled training data for supervised learning

---

## Future Work

- Apply pipeline to platforms like PatientsLikeMe or WebMD
- Integrate product metadata and user goals for personalized supplement recommendation
- Use retrieval-augmented generation (RAG) for conversational query answering

---
