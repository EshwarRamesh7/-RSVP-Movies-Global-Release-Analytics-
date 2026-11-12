# RSVP Movies — SQL Analytics for Global Release Strategy
## Project explanation and interview preparation

### Project summary
This SQL case study analyses movie metadata, genres, ratings, people and role mappings for RSVP Movies, an Indian production company considering an international release. It explores release patterns, genre performance, ratings, votes, production houses, directors and actors, then uses those patterns to frame business recommendations.

**60-second interview pitch**

“I used SQL to analyse a relational movie database for RSVP Movies, which was planning a global release. I explored the underlying tables, checked data completeness, combined movie, genre and rating information, and used aggregations, subqueries, CTEs and window functions to rank genres, movies, production houses and talent. The goal was to demonstrate how structured data analysis can support decisions about genre, release timing, partners and creative talent.”

### Business problem
A production company planning a global release needs evidence about audience preferences and market patterns. The project addresses which genres have the largest film counts, how release volumes vary by year and month, which films and production companies have strong ratings, which directors and actors are associated with highly rated films, and how votes and ratings differ across countries and release periods.

### Relational model and SQL techniques
The SQL script references `movie`, `genre`, `ratings`, `names`, `director_mapping` and `role_mapping`.

The work includes table profiling, null checks, joins, filtering with WHERE and LIKE, aggregations with GROUP BY, nested queries, CTEs, and ranking with window functions.

The grain of each table matters. A film can have multiple genres and several people/roles. Joining one-to-many tables can multiply rows, so use appropriate distinct counts and aggregate at the correct grain.

### Interview questions and suggested answers

**1. What is a primary key?**  
A primary key uniquely identifies a record in a table and cannot contain duplicate or null values. It provides a reliable identifier for joins.

**2. What is a foreign key?**  
A foreign key references a key in another table and helps enforce referential integrity between related records.

**3. What is the difference between INNER JOIN and LEFT JOIN?**  
INNER JOIN returns rows with a match on both sides. LEFT JOIN returns every row from the left table and matching rows from the right; unmatched right-side values are NULL.

**4. Why might a join produce more rows than the left table?**  
If one record on the left matches multiple records on the right, the result contains multiple rows. This is common in movie-to-genre and movie-to-role relationships.

**5. Why use COUNT(DISTINCT movie_id)?**  
It counts unique films even when a join produces multiple rows for the same movie. The correct count depends on the question and table grain.

**6. What is a CTE?**  
A Common Table Expression is a named temporary result defined with WITH. It makes complex SQL easier to structure and reuse within a single statement.

**7. What is the difference between WHERE and HAVING?**  
WHERE filters rows before grouping. HAVING filters groups after aggregation.

**8. What is a window function?**  
It calculates a value across a related set of rows without collapsing the result into one row per group. Ranking functions compare films or genres while retaining row-level detail.

**9. What is the difference between RANK and DENSE_RANK?**  
RANK leaves gaps after ties; DENSE_RANK does not. For values 100, 100 and 90, RANK produces 1, 1 and 3, while DENSE_RANK produces 1, 1 and 2.

**10. How would you find the top 10 films by average rating?**  
Join movie metadata with ratings, order by average rating descending and apply a ranking function. Decide whether ties at the 10th position should be included; a simple LIMIT may exclude tied records.

**11. How do you handle NULL values in SQL?**  
Use IS NULL or IS NOT NULL to test for them, and choose a business-appropriate handling method. NULL means unknown or missing, not zero or an empty string.

**12. How would you validate the analysis?**  
Check row counts before and after joins, confirm uniqueness and keys, reconcile aggregates to source tables, test edge cases and verify that ranking logic handles ties as intended.

### Findings and business interpretation
The SQL file contains comments about release patterns, genre counts, ratings and talent. These are query-level observations. Re-run the SQL against the source database before quoting figures or converting them into a firm release strategy. Some queries should be reviewed for ordering and tie handling.

### Limitations
- The SQL file and executive summary are present, but the original database dump is not listed in the repository.
- Query outputs should be validated against the exact source tables.
- Joins across one-to-many mappings may inflate counts unless the grain is controlled.
- Observational patterns in film data do not establish what will cause a future release to succeed.

### Resume bullet
Analysed a relational movie database using MySQL, applying joins, subqueries, CTEs, aggregations and window functions to explore genre trends, ratings, audience votes and production talent for a global-release case study.

### Files
- [SQL analysis](../IMDB_solution%20file.sql)
- [Executive summary](../Executive%20Summary.pdf)
