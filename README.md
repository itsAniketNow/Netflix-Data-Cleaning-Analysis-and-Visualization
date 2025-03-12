# Netflix Data Cleaning, Analysis, and Visualization

## 📌 Project Overview
This project involves analyzing the Netflix dataset to extract meaningful insights about content trends, release patterns, and genre distributions. The dataset is cleaned, processed, and visualized using Python, leveraging libraries such as Pandas and NumPy.

## 🔧 Tools & Technologies Used
- **Python**: Main programming language
- **Pandas**: Data manipulation and cleaning
- **NumPy**: Numerical operations
- **Matplotlib & Seaborn**: Data visualization
- **Jupyter Notebook**/**Google Colab**: For interactive analysis

## 📂 Dataset Details
The dataset contains information about Netflix shows and movies, including:
- `title` (Name of the show/movie)
- `type` (Movie or TV Show)
- `director` (Director's name)
- `cast` (Main actors)
- `country` (Country of production)
- `date_added` (Date added to Netflix)
- `release_year` (Year of release)
- `rating` (Content rating)
- `duration` (Duration in minutes or seasons)
- `listed_in` (Genres/categories)
- `description` (Short summary)

## 🛠️ Code Breakdown
1. **Loading the Dataset:**
   ```python
   import pandas as pd
   import numpy as np
   import matplotlib.pyplot as plt
   import seaborn as sns
   
   df = pd.read_csv("netflix_data.csv")
   ```

2. **Data Cleaning:**
   - Handled missing values using `df.dropna()` and `df.fillna()`
   - Converted `date_added` to datetime format
   - Extracted `year_added` from `date_added`

3. **Data Analysis & Exploration:**
   - Count of Movies vs. TV Shows
   ```python
   df['type'].value_counts().plot(kind='bar', title='Movies vs. TV Shows')
   ```
   - Most common genres/categories
   ```python
   from collections import Counter
   genres = Counter(",".join(df['listed_in'].dropna()).split(','))
   print(genres.most_common(10))
   ```
   - Trend of content added per year
   ```python
   df['year_added'].value_counts().sort_index().plot(kind='line')
   ```

4. **Data Visualization:**
   - Bar charts for top 10 countries producing Netflix content
   - Pie chart showing rating distribution
   - Heatmap for missing values

## 📊 Key Findings
- **Content Type:** The dataset contains more movies than TV shows.
- **Top Genres:** Drama, Comedy, and Documentaries are the most common genres.
- **Trending Years:** Most content has been added to Netflix after 2015.
- **Country Contributions:** The US, India, and the UK contribute the most content to Netflix.
- **Ratings Distribution:** TV-MA and PG-13 are the most frequent content ratings.

## 📌 Conclusion
This project provides a deep dive into Netflix's content trends, helping understand audience preferences and industry patterns. The dataset can be further explored for recommendation systems and predictive modeling.

## 🚀 Future Enhancements
- Sentiment analysis on descriptions
- Predictive analysis for content popularity
- Time series forecasting for future content additions

---

Feel free to contribute, report issues, or suggest improvements!

