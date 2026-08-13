# 🎬 Netflix Movies and TV Shows Data Analysis using SQL

![PostgreSQL](https://img.shields.io/badge/Database-PostgreSQL-336791?style=for-the-badge\&logo=postgresql\&logoColor=white)
![SQL](https://img.shields.io/badge/Language-SQL-blue?style=for-the-badge)
![Dataset](https://img.shields.io/badge/Dataset-Netflix%20Titles-red?style=for-the-badge)

## 📌 Project Overview

This project analyzes the **Netflix Movies and TV Shows dataset** using **PostgreSQL** to answer 15 practical business questions related to Netflix's content library.

The analysis focuses on understanding content distribution, ratings, countries, genres, release trends, directors, actors, movie durations, and content classification.

The project demonstrates how SQL can be used to transform raw data into meaningful business insights through aggregation, filtering, string manipulation, Common Table Expressions (CTEs), window functions, subqueries, and conditional logic.

---

## 🎯 Objectives

The main objectives of this project are to:

* Analyze the distribution of Movies and TV Shows on Netflix.
* Identify the most common content ratings.
* Analyze Netflix content by year, country, genre, and release trends.
* Identify the longest movies and TV shows with multiple seasons.
* Analyze directors and actors appearing in Netflix content.
* Examine Indian content and Indian actors.
* Identify content without director information.
* Categorize content based on keywords related to violence.
* Practice advanced SQL techniques on a real-world dataset.

---

## 📊 Dataset

The dataset used in this project is the **Netflix Movies and TV Shows dataset** published by Shivam Bansal on Kaggle.

**Dataset:** Netflix Movies and TV Shows
**Records:** 8,807
**Columns:** 12

### Dataset Source

[Kaggle — Netflix Movies and TV Shows Dataset](https://www.kaggle.com/datasets/shivamb/netflix-shows)

### Main Columns

| Column         | Description                            |
| -------------- | -------------------------------------- |
| `show_id`      | Unique identifier for each title       |
| `type`         | Movie or TV Show                       |
| `title`        | Title of the content                   |
| `director`     | Director(s) of the content             |
| `cast`         | Actors appearing in the content        |
| `country`      | Country/countries of production        |
| `date_added`   | Date the content was added to Netflix  |
| `release_year` | Original release year                  |
| `rating`       | Content rating                         |
| `duration`     | Movie duration or number of TV seasons |
| `listed_in`    | Genre/category of the content          |
| `description`  | Short description of the title         |

---

## 🗂️ Project Structure

```text
netflix-sql-analysis/
│
├── netflix_titles.csv
├── Schemas.sql
├── Business Problems Netflix.sql
├── Solutions of 15 business problems.sql
└── README.md
```

### File Description

**`netflix_titles.csv`**
Contains the raw Netflix Movies and TV Shows dataset.

**`Schemas.sql`**
Creates the `netflix` table and defines the database schema required for analysis.

**`Business Problems Netflix.sql`**
Contains the 15 business questions addressed in this project.

**`Solutions of 15 business problems.sql`**
Contains the SQL queries used to solve each of the 15 business problems.

---

# 🔍 Business Problems

The project answers the following 15 business questions:

### 1. Movies vs TV Shows

Count the number of Movies and TV Shows available on Netflix.

### 2. Most Common Rating

Find the most frequently occurring rating for Movies and TV Shows separately.

### 3. Movies Released in a Specific Year

Retrieve all movies released in a selected year, such as 2020.

### 4. Top 5 Countries by Content

Identify the five countries contributing the highest number of Netflix titles.

### 5. Longest Movie

Determine the movie with the longest duration.

### 6. Recently Added Content

Identify Netflix content added within the last five years.

### 7. Content by a Specific Director

Find all Movies and TV Shows directed by **Rajiv Chilaka**.

### 8. TV Shows with More Than 5 Seasons

Identify TV Shows that have more than five seasons.

### 9. Content by Genre

Count the number of Netflix titles belonging to each genre/category.

### 10. Indian Content Release Trends

Analyze yearly Netflix content releases from India and identify the top five years based on the calculated release percentage.

### 11. Documentary Movies

Find all movies classified as documentaries.

### 12. Missing Director Information

Identify Netflix titles for which director information is unavailable.

### 13. Salman Khan's Movies

Find movies featuring **Salman Khan** released within the last ten years.

### 14. Top 10 Indian Actors

Identify the top 10 actors who have appeared in the highest number of movies produced in India.

### 15. Content Classification

Classify Netflix content as:

* **Bad** — description contains keywords related to `kill` or `violence`
* **Good** — description does not contain those keywords

Then count the number of titles in each category.

---

# 🛠️ SQL Concepts & Techniques Used

This project demonstrates several important SQL concepts:

### Basic SQL

* `SELECT`
* `WHERE`
* `GROUP BY`
* `ORDER BY`
* `LIMIT`
* `COUNT()`

### Intermediate SQL

* Aggregate functions
* Subqueries
* `CASE WHEN`
* String functions
* Date functions
* Filtering with `LIKE` and `ILIKE`

### Advanced SQL

* Common Table Expressions (CTEs)
* Window functions
* `RANK()`
* `PARTITION BY`
* `UNNEST()`
* `STRING_TO_ARRAY()`
* Type casting
* Nested queries

### Example

A window function is used to determine the most common rating for each content type:

```sql
RANK() OVER (
    PARTITION BY type
    ORDER BY rating_count DESC
)
```

String manipulation is also used to analyze columns containing multiple values, such as countries, directors, genres, and actors:

```sql
UNNEST(STRING_TO_ARRAY(country, ','))
```

---

# 🔄 Project Workflow

```text
Raw Netflix Dataset
        │
        ▼
Create PostgreSQL Table
        │
        ▼
Load Netflix Data
        │
        ▼
Data Exploration & Transformation
        │
        ▼
15 Business Questions
        │
        ▼
SQL Analysis
        │
        ▼
Business Insights
```

---

# 💡 Key Areas of Analysis

The analysis provides insights into several dimensions of Netflix's content library:

### Content Distribution

Comparison of Movies and TV Shows available on the platform.

### Geographic Distribution

Analysis of countries producing the largest amount of Netflix content.

### Content Ratings

Identification of the most common ratings across Movies and TV Shows.

### Genre Analysis

Understanding which genres have the highest representation.

### Release Trends

Analysis of yearly content releases, including trends in Indian content.

### People & Creators

Analysis of directors and actors appearing across Netflix titles.

### Content Characteristics

Analysis of movie duration, TV show seasons, missing director information, and keyword-based content classification.

---

# 🚀 How to Run the Project

## 1. Install PostgreSQL

Install PostgreSQL and open a PostgreSQL client such as **pgAdmin** or **DBeaver**.

## 2. Create the Database

Create a new PostgreSQL database for the project.

## 3. Create the Table

Run:

```text
Schemas.sql
```

This creates the `netflix` table.

## 4. Import the Dataset

Import:

```text
netflix_titles.csv
```

into the `netflix` table.

## 5. Run the Business Queries

Open:

```text
Solutions of 15 business problems.sql
```

and execute the queries individually or as required.

---

# 📈 Example Insights

The SQL analysis can be used to answer questions such as:

* How does Netflix's Movie library compare with its TV Show library?
* Which countries contribute the most content?
* What ratings dominate Netflix's content library?
* Which genres have the largest number of titles?
* Which years saw significant growth in Indian Netflix content?
* Which actors appear most frequently in Indian movies?
* How much content lacks director information?
* How does Netflix content distribution vary between Movies and TV Shows?

---

# 📚 What I Learned

Through this project, I strengthened my understanding of:

* Writing SQL queries for real-world datasets.
* Converting business questions into SQL problems.
* Data aggregation and grouping.
* Working with multi-valued string columns.
* Using CTEs and window functions.
* Applying date and string manipulation techniques.
* Using PostgreSQL-specific functions.
* Extracting business insights from structured data.

---

# 🔮 Future Improvements

Possible improvements to this project include:

* Adding an interactive dashboard using **Power BI** or **Tableau**.
* Performing additional exploratory data analysis.
* Cleaning and normalizing multi-valued columns such as actors, countries, and genres.
* Adding more advanced business questions.
* Creating visualizations for country, genre, rating, and release-year trends.
* Automating the data cleaning and loading process.
* Comparing Netflix's content growth across different time periods.

---

# 📁 Repository

The complete SQL analysis and dataset are available in this repository:

**GitHub:** https://github.com/mohitvish13-maker/netflix-sql-analysis

---

# 👨‍💻 Author

**Mohit Vishwakarma**

Chemical Engineering Undergraduate
National Institute of Technology, Raipur

GitHub: [mohitvish13-maker](https://github.com/mohitvish13-maker)

---

## ⭐ If you found this project useful

Feel free to explore the SQL queries, experiment with the dataset, and build upon the analysis.
