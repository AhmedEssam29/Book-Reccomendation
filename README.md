# Book Dataset Analysis and Recommendation System

This project is focused on analyzing and visualizing data from a book dataset and providing book recommendations based on features like publisher, author, language, and more. The dataset includes information on book titles, authors, average ratings, ISBN identifiers, publication dates, and publishers. Using Python libraries such as pandas, matplotlib, seaborn, and ipywidgets, the project performs data cleaning, feature engineering, exploratory data analysis, and interactive book recommendations.

## Dataset Overview
### The dataset contains information on 11,123 books with the following features:

- **bookID:** Unique identifier for each book.
- **title:** The title under which the book was published.
- **authors:** Name(s) of the book's authors.
- **average_rating:** The book's average rating.
- **isbn:** International Standard Book Number (10 digits).
- **isbn13:** 13-digit ISBN for identifying the book.
- **language_code:** The book's primary language.
- **num_pages:** Total number of pages in the book.
- **ratings_count:** Total number of ratings the book has received.
- **text_reviews_count:** Total number of text reviews for the book.
- **publication_date:** Date when the book was first published.
- **publisher:** The book's publisher.

# Project Structure
## Data Cleaning: 
Removes unnecessary columns, strips whitespace, and handles missing or duplicated values.

## Feature Engineering:

Extracts new features such as publication year.
Converts data types for appropriate columns, e.g., year as integer.
Drops unnecessary columns like bookID, isbn, and isbn13.
## Exploratory Data Analysis (EDA):

Visualizes top publishers, authors, and most common books.
Analyzes average ratings, rating counts, and the distribution of languages.
Uses Seaborn and Matplotlib for EDA plots and visualizations.
## Interactive Recommendations:

Recommends books based on publishers, authors, or language codes using the ipywidgets library.
Provides top-rated books for the selected publisher or author.

# Installation and Requirements:
## This project requires Python 3.x with the following libraries:

```bash

pip install pandas numpy matplotlib seaborn ipywidgets
```

# Usage:

1. Clone the repository and navigate to the project folder.
2. Load the dataset by running the notebook or script.
3. Perform data cleaning and feature engineering to prepare the dataset.
4. Run EDA cells to visualize insights into the data.
5. Use the interactive recommendation widget to get book recommendations by selecting specific publishers or authors.

## Example Code Snippet for Publisher Recommendations
```bash
@interact
def recommend_books_publisher(publisher_name=list(df['publisher'].value_counts().index)):
    recommendations = df[df['publisher'] == publisher_name][['title', 'average_rating']].sort_values(by='average_rating', ascending=False).head(10)
    return recommendations
```

# Exploratory Data Analysis (EDA) Highlights
- **Top Authors:** Displays the top 10 authors with the most books published.
- **Book Distribution by Year:** Shows the number of books published per year, identifying popular publication periods.
- **Language Analysis:** Analyzes the distribution of books across different languages.

# Future Enhancements
## Potential improvements include:

Adding user-based collaborative filtering for personalized recommendations.

Expanding analysis to include sentiment analysis on text reviews.

Exploring genre-based recommendations.

