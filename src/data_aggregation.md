# Data Aggregation

The following aggregations were performed to analyze critic scores and global sales across different game genres.

## Tables Created

1. **sports_critic_score**
   - Stores the average critic score for Sports games.

2. **shooter_critic_score**
   - Stores the average critic score for Shooter games.

3. **all_games**
   - Stores summary statistics (minimum, maximum, and average global sales) for all games.

4. **sport_games**
   - Stores summary statistics (minimum, maximum, and average global sales) for Sports games.

5. **shooter_games**
   - Stores summary statistics (minimum, maximum, and average global sales) for Shooter games.

6. **shooter_games_sale_count**
   - Stores aggregated data used to build a histogram of global sales for Shooter games.

7. **sport_games_sale_count**
   - Stores aggregated data used to build a histogram of global sales for Sports games.

---

## SQL Code Used

```sql
-- Average critic score for Sports games
CREATE TABLE sports_critic_score AS 
SELECT AVG(Critic_Score) AS sports_critic_score
FROM sales
WHERE Genre = 'Sports';

-- Average critic score for Shooter games
CREATE TABLE shooter_critic_score AS 
SELECT AVG(Critic_Score) AS shooter_critic_score
FROM sales
WHERE Genre = 'Shooter';

-- Summary statistics for all games
CREATE TABLE all_games AS 
SELECT 
    MIN(Global_Sales) AS min_global_sales,
    MAX(Global_Sales) AS max_global_sales,
    AVG(Global_Sales) AS average_global_sales
FROM sales;

-- Summary statistics for Sports games
CREATE TABLE sport_games AS 
SELECT 
    MIN(Global_Sales) AS min_global_sales,
    MAX(Global_Sales) AS max_global_sales,
    AVG(Global_Sales) AS average_global_sales
FROM sales
WHERE Genre = 'Sports';

-- Summary statistics for Shooter games
CREATE TABLE shooter_games AS 
SELECT 
    MIN(Global_Sales) AS min_global_sales,
    MAX(Global_Sales) AS max_global_sales,
    AVG(Global_Sales) AS average_global_sales
FROM sales
WHERE Genre = 'Shooter';

-- Histogram data for Shooter games (global sales distribution)
CREATE TABLE shooter_games_sale_count AS 
SELECT 
    Global_Sales AS global_sales,
    COUNT(*) AS count
FROM sales
WHERE Genre = 'Shooter'
GROUP BY Global_Sales;

-- Histogram data for Sports games (global sales distribution)
CREATE TABLE sport_games_sale_count AS 
SELECT 
    Global_Sales AS global_sales,
    COUNT(*) AS count
FROM sales
WHERE Genre = 'Sports'
GROUP BY Global_Sales;
