# Movie Recommendation System

A Python-based Movie Recommendation System developed as part of the **Horizon Internship Program**. This project uses Content-Based Filtering with Cosine Similarity to recommend movies based on user preferences and movie similarities.

The project was created to gain practical experience in data analysis, recommendation systems, data visualization, and machine learning concepts using Python.

---

## Project Description

## Project Description

This project was developed during the **Horizon Internship Program** as a practical machine learning and data analysis project. The objective was to build an interactive Movie Recommendation System that helps users discover movies based on similarity, genre preferences, and user rating behavior. It also has a Genre Explorer to browse top-rated movies by genre, and a section for personalized user-based recommendations.

The dataset used is the [MovieLens dataset](https://grouplens.org/datasets/movielens/), which contains movies and user ratings data. The main idea behind the recommendation logic is Cosine Similarity — basically measuring how "close" two movies are based on user rating patterns.

I built this entirely in Jupyter Notebook and used `ipywidgets` to make it interactive, so the user doesn't have to change any code to use it.

---

## Features

### 1. Movie Recommendation System
- User types a movie title and searches for it
- The system finds the closest matching title from the dataset
- Displays the top N similar movies along with their cosine similarity scores and genres
- Shows a bar chart visualizing the similarity scores

### 2. Genre Explorer
- User selects a genre from a dropdown (e.g., Sci-Fi, Action, Drama)
- Displays the top N movies in that genre ranked by average rating
- Shows number of ratings alongside average ratings
- Bar chart visualization with color-coded bars

### 3. Personalized User Recommendations
- User enters a User ID from the dataset
- Shows the top-rated movies that user has already watched
- Recommends movies the user hasn't seen yet, based on what similar users liked
- Shows an aggregated similarity score and a recommendation chart

---

## Technologies Used

| Tool/Library | Purpose |
|---|---|
| Python 3 | Main programming language |
| Jupyter Notebook | Development environment |
| Pandas | Data loading and manipulation |
| NumPy | Numerical operations |
| Scikit-learn | Cosine similarity calculation |
| Matplotlib | Plotting charts |
| Seaborn | Styling the plots |
| ipywidgets | Interactive UI elements inside the notebook |

---

## Dataset Information

This project uses the **MovieLens** dataset from [GroupLens Research](https://grouplens.org/datasets/movielens/).

| File | Description
|---|---|
| `movies.csv` | Contains movie IDs, titles, and genres
| `ratings.csv` | Contains user ratings for movies

> **Important:** `ratings.csv` is **not included** in this repository because it exceeds GitHub's file size limit (the file is over 100MB). You need to download it manually and place it in the project folder before running the notebook.

## Project Workflow

```
Load Data (movies.csv + ratings.csv)
        ↓
Preprocess & Merge Datasets
        ↓
Create User-Movie Rating Matrix
        ↓
Apply Cosine Similarity
        ↓
┌───────────────────────────────────────────────┐
│                                               │
▼                   ▼                           ▼
Movie Search     Genre Explorer        User Recommendations
(item-based)     (filter + rank)       (user-based filtering)
        │                   │                   │
        └───────────────────┴───────────────────┘
                            ↓
                  Display Results + Charts
                  (via ipywidgets UI)
```

**Brief explanation of each step:**

1. **Load Data** — `movies.csv` and `ratings.csv` are loaded using Pandas
2. **Preprocessing** — Datasets are merged on `movieId`; missing values are handled
3. **Rating Matrix** — A pivot table is created with users as rows and movies as columns
4. **Cosine Similarity** — Scikit-learn's `cosine_similarity` computes similarity between movies or users
5. **Recommendations** — Top N results are fetched, filtered, and displayed with charts

---

## Future Improvements

Some things I'd like to add or improve if I work on this further:

- **Add Collaborative Filtering** using matrix factorization (like SVD or ALS) to improve recommendation quality
- **Build a proper web interface** using Flask or Streamlit so it doesn't require Jupyter Notebook to run
- **Add movie posters** by connecting to the TMDb API
- **Include more filters** like year range, minimum rating count, or director-based search
- **Better cold-start handling** for new users who haven't rated many movies yet
- **Deploy online** so anyone can try it without installing anything

---

## Conclusion

This project gave me a good opportunity to understand how recommendation systems work in practice. I got to learn about collaborative and content-based filtering concepts, work with a real-world dataset, and also build a basic interactive interface using `ipywidgets` inside a Jupyter Notebook.

It was a bit challenging to handle the large dataset and optimize the similarity computations, but overall it was a valuable learning experience. Working on this helped me understand how platforms like Netflix or Amazon might approach building similar features at a much larger scale.