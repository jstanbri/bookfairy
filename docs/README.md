# BookFairy

A project inspired by the book fairy instagram account. This script scrapes the books and book reviews and uses ml to create a book recommendation

1. Scraping Instagram Data
    Instagram doesn't offer a public API for scraping data, and scraping Instagram directly can be tricky due to rate limits, API restrictions, and terms of service. Therefore, scraping should be done cautiously and within legal bounds. Alternatively, Instagram Graph API (if approved by Instagram) can be used to access public data.

    Scraping Approach: Using `instagram-scraper`: This open-source Python tool allows for downloading public data.

2. Data Cleaning & Preprocessing
    Once you've scraped the data, you need to clean and preprocess it. You'll likely encounter issues like:

    HTML tags: Strip out unnecessary tags and content.
    Text normalization: Convert all text to lowercase, remove stopwords, punctuation, etc.
    Book identification: Parse out which posts refer to book titles and reviews, and handle variations in book naming.
    You could use regular expressions or natural language processing (NLP) libraries like spaCy or NLTK for text cleaning and normalization.

    ```python
    import re

    def clean_text(text):
        text = re.sub(r'[^a-zA-Z0-9\s]', '', text)  # Remove punctuation
        text = text.lower()  # Convert to lowercase
        return text
    ```

3. Sentiment Analysis of Reviews
    To get a deeper understanding of reviews, you can perform sentiment analysis to determine the sentiment (positive, neutral, negative) of each review.

    You can use libraries such as TextBlob or VADER for sentiment analysis.

4. Building the Recommendation Engine
Once you have the cleaned data and sentiment analysis, the next step is to build a recommendation engine. There are two main approaches to recommendation systems:

Content-based filtering: Recommends items similar to what a user has liked based on item features (e.g., genres, authors, etc.).
Collaborative filtering: Recommends items based on user behavior and similarities between users.
In this case, if you don’t have access to user-specific interaction data, you can focus on content-based filtering.

Approach:
Extract features from the book reviews (e.g., keywords, topics, sentiment).
Calculate similarity between books using cosine similarity or another metric.
Make recommendations based on the similarity between new books and existing ones.

##### For more information [contact](mailto:jstanbridge@gmail.com)
