# Scalable Final Project - Yelp Data Analysis

## Project Overview
This project was developed as part of the **Spring 2023 Final Project** for the **GSU RCB Masters** program. It focuses on analyzing Yelp data using **Apache Spark (PySpark)** for scalable and efficient data processing. The notebook includes data preprocessing, sentiment analysis, clustering, and visualization techniques to gain insights from Yelp reviews, business data, and user interactions.

The goal of this project is to enhance the credibility of Yelp reviews by identifying keywords that signify positivity or negativity. By analyzing these keywords, businesses can extract valuable insights into factors influencing customer satisfaction, enabling them to make targeted improvements. Ultimately, the project seeks to provide businesses with a tool to optimize operations based on customer feedback.


## Team Members
- Usman Jadoon  
- Hussein Mawaw  
- Paola Dumbi  
- Cole Brown  
- Ingara Mayeke  

## Dataset
The project utilizes the following datasets:
- `yelp_review.csv` - Contains customer reviews with ratings and text feedback.
- `yelp_business.csv` - Information about businesses listed on Yelp.
- `yelp_user.csv` - User profiles and their interactions with businesses.

These datasets are loaded into PySpark DataFrames for analysis.

## Technologies Used
- **Python**
- **Apache Spark (PySpark)**
- **Pandas**
- **Matplotlib**
- **TextBlob** (for sentiment analysis)
- **WordCloud** (for visualization)

## Installation and Setup
Before running the notebook, ensure you have the required libraries installed. You can install them using:
```bash
!pip install pyspark
!pip install textblob
!pip install wordcloud
```

### Google Colab Setup
The project is designed to run in **Google Colab**. To use the datasets stored in Google Drive, mount the drive:
```python
from google.colab import drive
drive.mount('/content/drive')
```

### Spark Initialization
Initialize a Spark session for distributed computing:
```python
from pyspark.context import SparkContext
from pyspark.sql.session import SparkSession
sc = SparkContext("local[*]")
spark = SparkSession(sc)
```

## Key Features and Workflow
1. **Data Loading:** Import Yelp datasets into PySpark DataFrames.
2. **Data Cleaning & Preprocessing:** Handle missing values, remove duplicates, and standardize text data.
3. **Sentiment Analysis:** Use **TextBlob** to analyze customer reviews and derive sentiment scores.
4. **Feature Engineering:** Tokenization, TF-IDF, and Stopwords Removal for text analysis.
5. **Clustering with K-Means:** Group businesses based on review sentiments and other relevant features.
6. **Visualization:** Generate word clouds and summary statistics using Matplotlib and WordCloud.

## Results and Insights
- **Sentiment Distribution Analysis:**
  - The majority of Yelp reviews had a neutral or slightly positive sentiment score.
  - Businesses in the **food and hospitality sector** tended to receive the most extreme sentiment scores (both highly positive and highly negative), indicating strong customer opinions.
  - Sentiment analysis revealed a correlation between **review length and sentiment polarity**, where longer reviews tended to provide detailed positive or negative feedback.

- **Business Category Trends:**
  - Businesses in **high-end dining and luxury services** often had higher sentiment polarity scores, whereas **fast food chains and budget-friendly businesses** had a more mixed distribution.
  - Negative sentiment was frequently associated with **poor customer service and long wait times**, while positive sentiment correlated with **quality of service and ambiance**.

- **User Engagement Insights:**
  - Users who left more reviews generally had a higher average sentiment score, suggesting that more engaged reviewers tend to be more positive.
  - First-time reviewers had a wider range of sentiment scores, indicating that extreme experiences (either good or bad) often trigger first-time reviews.

- **Clustering Results:**
  - K-Means clustering grouped businesses based on **review sentiments, average star ratings, and review frequency**.
  - Clusters revealed that businesses with **consistent high ratings** and **positive sentiment scores** attracted repeat customers.
  - Lower-rated businesses often had sentiment inconsistencies, showing mixed customer experiences.

- **Word Cloud Insights:**
  - Positive reviews frequently contained words like **“great,” “amazing,” “friendly,”** and **“delicious.”**
  - Negative reviews often included words like **“rude,” “disappointed,” “overpriced,”** and **“dirty.”**

## How to Run the Notebook
1. Open the notebook in **Google Colab** or a local Jupyter Notebook environment.
2. Mount Google Drive (if using Colab) and ensure datasets are accessible.
3. Run the notebook cells sequentially to process data and generate insights.

## Future Improvements
- Implement deep learning-based sentiment analysis models.
- Explore additional Yelp dataset attributes for enhanced insights.
- Improve clustering techniques with advanced feature engineering.


