# Movie Industry Analysis with Pandas

## 1. Project Overview
#### 1.1. Introduction
This project aims to analyze movie industry data using Python, particularly the Pandas library, to gain insights into various aspects of the movie industry, such as rating distributions, genre popularity, and the financial performance of movies.

### 1.2. Objectives
The primary objectives of this project are:

To analyze the distribution of movie ratings.
To explore the relationship between movie budgets and box office revenues.
To identify trends in movie releases over the years.
To visualize the popularity of different movie genres.

## 2. Data Description
#### 2.1. Data Sources
The project uses multiple datasets that provide information on movies, genres, directors, countries, and languages. The data is sourced from a hypothetical or real-world database.

## 2.2. Datasets Used
**Movies Dataset**: Contains information on individual movies, including title, release year, rating, budget, box office revenue, etc.
**Genres Dataset**: Lists the genres associated with each movie.
**Directors Dataset**: Contains information on the directors of the movies.
**Countries Dataset**: Provides details on the countries where movies were produced.
**Languages Dataset**: Lists the languages spoken in the movies.

## 2.3. Data Preprocessing
Before analysis, the datasets were preprocessed by merging them into a single comprehensive dataframe. Duplicate columns (like genre_id, director_id, etc.) were removed after the merge to avoid redundancy.

## 3. Analysis and Methodology
#### 3.1. Merging the Datasets
The datasets were merged using common keys (genre_id, director_id, country_id, language_id) to form a unified dataframe. This allowed for a comprehensive analysis of the movie data.

# Merging the datasets
The datasets were merged using common keys (genre_id, director_id, country_id, language_id) to form a unified dataframe. This allowed for a comprehensive analysis of the movie data.
netflix_df = (
    movie_df
    .merge(genre_df, on='genre_id', how='left')
    .merge(director_df, on='director_id', how='left')
    .merge(country_df, on='country_id', how='left')
    .merge(language_df, on='language_id', how='left')
)

## 3.2. Data Cleaning
After merging, the following data cleaning steps were performed:

**Removing Duplicate Columns:** The redundant columns like genre_id, director_id, etc., were removed to streamline the dataset.
**Handling Missing Values:** Any missing values were either filled with appropriate placeholders or removed, depending on the context.

## 3.3. Exploratory Data Analysis (EDA)
Exploratory Data Analysis was performed to understand the data better and to identify patterns and trends. Key steps included:

**Analyzing the Distribution of Ratings:** A histogram was plotted to visualize how movie ratings are distributed.
**Examining Budget vs. Revenue:** A scatter plot was used to analyze the correlation between movie budgets and their box office revenues.
**Trend Analysis:** The number of movies released each year was plotted to observe any trends over time.
**Genre Popularity:** The popularity of different genres was analyzed by counting the number of movies in each genre.

## 4. Visualizations and Insights
#### 4.1. Distribution of IMDB Ratings
The distribution of IMDB ratings was visualized using a histogram. This helps in understanding how movies are rated on average.

plt.figure(figsize=(10, 6))
plt.hist(netflix_df['imbd_rating'], bins=20, color='skyblue', edgecolor='black')
plt.title('Distribution of IMDB Ratings')
plt.xlabel('IMDB Rating')
plt.ylabel('Number of Movies')
plt.grid(True)
plt.show()

**Insight:** The histogram reveals that most movies have ratings clustered around certain values, indicating the general perception of movie quality by audiences.

## 4.2. Budget vs. Box Office Revenue
A scatter plot was created to analyze the relationship between a movie’s budget and its box office revenue.

plt.figure(figsize=(10, 6))
plt.scatter(netflix_df['budget'], netflix_df['box_office_revenue'], alpha=0.5)
plt.title('Budget vs. Box Office Revenue')
plt.xlabel('Budget (in millions)')
plt.ylabel('Box Office Revenue (in millions)')
plt.grid(True)
plt.show()
Insight: The scatter plot may show a positive correlation, indicating that higher budgets tend to result in higher box office revenues, though outliers may exist.

## 4.3. Yearly Movie Releases
A line chart was plotted to visualize the number of movies released each year, helping to identify trends over time.

plt.figure(figsize=(10, 6))
movies_per_year = netflix_df.groupby('release_year').size()
movies_per_year.plot(kind='line')
plt.title('Number of Movies Released Each Year')
plt.xlabel('Year')
plt.ylabel('Number of Movies')
plt.grid(True)
plt.show()

**Insight:** The line chart may reveal periods of increased or decreased movie production, which could be linked to historical events or industry trends.

## 4.4. Genre Popularity
A bar chart was used to visualize the popularity of different genres by counting the number of movies in each genre.

plt.figure(figsize=(10, 6))
genre_counts = netflix_df['genre_name'].value_counts()
genre_counts.plot(kind='bar', color='orange', edgecolor='black')
plt.title('Popularity of Movie Genres')
plt.xlabel('Genre')
plt.ylabel('Number of Movies')
plt.xticks(rotation=45)
plt.grid(True)
plt.show()

**Insight:** This bar chart can highlight which genres are most popular, providing insights into audience preferences.

## 5. Results and Conclusion
#### 5.1. Key Findings
**Rating Distribution:** Most movies have moderate ratings, with fewer movies at the extremes of the rating scale.
**Budget and Revenue Correlation:** There is generally a positive correlation between a movie's budget and its box office revenue, though some low-budget movies perform exceptionally well.
**Trends in Movie Production:** The number of movies released annually has varied significantly over the years, potentially reflecting changes in the industry or external factors.
**Genre Popularity:** Certain genres, such as action and drama, tend to dominate the industry, reflecting audience preferences.

## 5.2. Conclusion
The analysis provides valuable insights into the movie industry, helping stakeholders understand key trends and factors influencing movie success. Future work could expand on these findings by incorporating additional data sources or exploring new analytical methods.

6. ## Future Work
6.1. Potential Extensions
Incorporating Additional Data: Future analysis could include data on streaming platforms, audience demographics, or social media mentions to provide a more comprehensive view.
Advanced Machine Learning Models: Predictive models could be developed to forecast box office revenues or movie ratings based on various features.

#### 6.2. Limitations
Data Quality: The accuracy of the analysis depends on the quality of the data. Any errors or omissions in the data could impact the results.
**Scope of Analysis** The analysis is limited to the datasets used and the questions addressed. Additional questions may require different data or methods.

7. ## Project Setup and Usage

#### 7.1. Installation
Virtual Environment: Setting up a virtual environment ensures that dependencies are managed and isolated, preventing conflicts between packages.
bash
Copy code

## Clone the repository
git clone https://github.com/esthyo/movie-industry-analysis.git

## Navigate to the project directory
cd movie-industry-analysis

## Activate the virtual environment
env\Scripts\activate

## Install required packages
pip install -r requirements.txt
7.2. Running the Analysis
To run the analysis, execute the following command:

bash
Copy code
python main_analysis.py
7.3. Dependencies
Python 3.x
Pandas
Matplotlib
Seaborn

## 8. Contributing
Contributions to the project are welcome. Please fork the repository, make your changes, and submit a pull request.

## 8.1. How to Contribute
Fork the repository.
Create a new branch for your feature or bug fix.
Commit your changes.
Push the branch to your fork.
Submit a pull request.

9. ## License
This project is licensed under the MIT License. See the LICENSE file for more details.

10. ## Contact Information
For any questions, suggestions, or contributions, please contact Esther Obiageli Ukwuani at joyben68@gmail.com.

11. ## Acknowledgments
Python Community: For the extensive libraries and resources.
Contributors: Thank you to everyone who contributed to this project.

