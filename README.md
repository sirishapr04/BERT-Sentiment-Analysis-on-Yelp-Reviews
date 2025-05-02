
# Yelp Restaurant Business Analysis

## Project Background 

Yelp is a web and mobile platform where users can discover, review, and share experiences about local businesses through crowd-sourced reviews. It allows users to submit reviews, photos, and tips, while also browsing ratings and insights from others. Yelp covers a wide range of businesses, from restaurants to services, and offers features like search filters, business profiles, and customer feedback.

## Problem Statement

In the highly competitive restaurant industry, it is essential for stakeholders to understand the factors that drive business success. This project leverages the Yelp dataset to explore the relationship between user engagement (such as reviews) and key success metrics (including review count and ratings) for restaurants.

## Research Objectives

1. Does elite users have a greater influence on restaurant visibility and ratings compared to non-elite users, leading to a disproportionate contribution to restaurant success?
2. How does sentiment classification of Yelp reviews into positive and negative categories influence restaurant ratings and customer engagement, and what role do elite users play in shaping sentiment trends?

## Data Overview

This dataset is a curated subset of Yelp, containing comprehensive information about businesses across eight major metropolitan areas in the USA and Canada.

The original data is provided by Yelp in the form of six JSON files: business, review, user, tip, checkin, and photos.

Compressed Dataset Size: 4.04 GB

Uncompressed Dataset Size: 8.65 GB

Dataset Coverage: From 2004 to 2022

Dataset Source: https://business.yelp.com/data/resources/open-dataset/

## Analysis

### Research Question 1
Do elite users have a greater influence on restaurant visibility and ratings compared to non-elite users?

Key Findings:

### Ratings Comparison

Elite users give significantly higher ratings (avg: 4.10) than non-elite users (avg: 3.78)

T-test: T = 187.48, p < 0.001 → Statistically significant difference

### Restaurant Visibility

Strong positive correlation between elite reviews and total reviews (r = 0.9336) →
Elite users boost restaurant exposure

### Rating Trends Over Time

Elite users' ratings are consistently higher and more stable (steady increase from 3.96 → 4.21)

Non-elite users show greater volatility (decline after 2019)

![image](https://github.com/user-attachments/assets/f93d7cb3-bbc5-4140-b3e9-d1a0a6d6b0e9)


### Review Characteristics

Textual content analysis (Review Length): Elite reviews are almost 2x longer (85 vs 47 words)

Lexical Diversity (Unique Words): Elite reviews use more unique words (73 vs 42)

Readability (Flesch Reading Ease score): Elite reviews are slightly easier to read (Score: 61.6 vs 60.7)

### Conclusion
Elite users significantly influence restaurant ratings, visibility, and contribute richer, higher-quality, and more consistent reviews compared to non-elite users.

### Research Question 2
How does sentiment classification of Yelp reviews influence restaurant ratings and customer engagement, and what role do elite users play in shaping sentiment trends?

### Unsupervised Sentiment Classification

Used BERT embeddings (all-MiniLM-L6-v2) + KMeans Clustering (n=2)

Accuracy: 87% vs proxy labels (Stars 4–5: Positive, Stars 1–2: Negative)

Avoided heavy text cleaning to preserve semantic meaning and BERT can handle raw text very well

### Limitations of Star Ratings

Ratings often mismatch with actual review sentiment

Inconsistencies from user biases and mixed reviews

![image](https://github.com/user-attachments/assets/cd7e6ca8-d6d0-41b2-ab96-2add7d5208a7)
An example showing positive sentiment but low star rating – traditional metrics can mislead!

### New Success Metrics (Text-Based)

Positive Review Ratio: Positive reviews / Total reviews

Sentiment Net Score: (Positive – Negative) / Total reviews

Weighted Sentiment Score: Give more weight to longer, detailed reviews

Sentiment Trend: Monitor changes in positivity over time

### Real-World Value

Harder to manipulate than stars → Authentic customer insights

Detect hidden gems or early warning signs of issues

Helps forecast churn and predict future restaurant success

### Conclusion
Unsupervised sentiment analysis provides a more reliable and actionable measure of restaurant quality and customer engagement than traditional star ratings.

