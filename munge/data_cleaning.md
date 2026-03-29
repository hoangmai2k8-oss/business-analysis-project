# Data Cleaning and Transformation

The following transformations were applied to prepare the dataset for analysis:

## Steps Performed

1. **Created a new table**
   - A new table called `sales_genre` was created using data from the original `sales` table.

2. **Selected relevant columns**
   - Extracted key fields including `Genre`, `Global_Sales`, and `Critic_Score`.

3. **Rounded sales values**
   - Applied the `ROUND()` function to the `Global_Sales` column to simplify numeric values.

4. **Filtered data**
   - Retained only records where `Critic_Score` is greater than 0.

5. **Sorted data**
   - Ordered the dataset by `Critic_Score` in descending order to highlight top-rated entries.

---

## SQL Code Used

```sql
-- Step 1: Create a new table
CREATE TABLE sales_genre AS 
SELECT * FROM sales;

-- Step 2: Select relevant columns
SELECT Genre, Global_Sales, Critic_Score 
FROM sales_genre;

-- Step 3: Round Global_Sales values
SELECT ROUND(Global_Sales) AS Global_Sales_Rounded 
FROM sales_genre;

-- Step 4 & 5: Filter and sort data
SELECT * 
FROM sales_genre 
WHERE Critic_Score > 0 
ORDER BY Critic_Score DESC;
