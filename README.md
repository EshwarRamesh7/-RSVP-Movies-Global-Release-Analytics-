# RSVP Movies — SQL Analytics for Global Release Strategy

A MySQL case study using movie metadata, genres, ratings and people/role mappings to explore factors relevant to a production company's global release strategy.

**Tools:** MySQL · SQL · Joins · Subqueries · CTEs · Aggregations · Window functions

## Business question

What patterns in genre volume, release timing, ratings, audience votes and production talent can help a production company frame decisions for an international release?

## Data model

The SQL script references relational tables including `movie`, `genre`, `ratings`, `names`, `director_mapping` and `role_mapping`. These tables connect film metadata with genres, ratings and people/roles.

## Analysis

The SQL script explores table sizes and missing values, release volumes by year and month, genre counts and ranking, average duration by genre, ratings and movie rankings, highly rated production companies, directors and actors associated with highly rated movies, and country-level vote comparisons.

The project demonstrates joins, subqueries, CTEs, grouping, filtering, conditional aggregation and window functions.

## Deliverables

- `IMDB_solution file.sql` — SQL analysis.
- `Executive Summary.pdf` — project summary.
- `docs/PROJECT_GUIDE_AND_INTERVIEW_QUESTIONS.md` — project explanation and interview preparation.

## Important interpretation note

Several joins involve one-to-many relationships, such as movie-to-genre and movie-to-role mappings. Aggregations should account for join multiplication. When counting films, use distinct movie identifiers where the join grain requires it. The script contains query-level output comments; validate results against the database before quoting specific figures.

## Interview preparation

See [Project explanation and interview questions](docs/PROJECT_GUIDE_AND_INTERVIEW_QUESTIONS.md).

## Author

**Eshwar Ramesh** · [GitHub](https://github.com/EshwarRamesh7) · [Portfolio](https://eshwarrameshportfolio.netlify.app) · [LinkedIn](https://www.linkedin.com/in/eshwar-ramesh-9a4652251)
