VIII. Advanced SQL Topics - Facultatif (1 séance)
    
### 8.1. Vues

### AutoIncrement
### 8.2. Procédures stockées

### 8.3. Triggers

### 8.5. Using window functions
#### Définition
Fonctions de group by réparti sur un niveau (inf ou égal) à ce qui est sélectionné
```sql
OVER ( [PARTITION BY partition_expression] [ORDER BY sort_expression [ASC | DESC] [NULLS {FIRST | LAST }])

-- If you use multiple window functions in a query:

SELECT    
	wf1() OVER(PARTITION BY c1 ORDER BY c2),    
	wf2() OVER(PARTITION BY c1 ORDER BY c2)
FROM table_name;

-- you can use the `WINDOW` clause to shorten the query as shown in the following query:

SELECT
	wf1() OVER w,   
	wf2() OVER w,
FROM table_name
WINDOW w AS (PARTITION BY c1 ORDER BY c2);

```

#### Les fonctions

| Name                                                                                                     | Description                                                                                                                 |
| -------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| AVG                                                                                                      | Moyenne                                                                                                                     |
| MIN                                                                                                      | Minimum                                                                                                                     |
| MAX                                                                                                      | Maximum                                                                                                                     |
| SUM                                                                                                      | Somme                                                                                                                       |
| COUNT                                                                                                    | Nombre                                                                                                                      |
| [CUME_DIST](https://neon.tech/postgresql/postgresql-window-function/postgresql-cume_dist-function)       | Return the relative rank of the current row.                                                                                |
| [DENSE_RANK](https://neon.tech/postgresql/postgresql-window-function/postgresql-dense_rank-function)     | Rank the current row within its partition without gaps.                                                                     |
| [FIRST_VALUE](https://neon.tech/postgresql/postgresql-window-function/postgresql-first_value-function)   | Return a value evaluated against the first row within its partition.                                                        |
| [LAG](https://neon.tech/postgresql/postgresql-window-function/postgresql-lag-function)                   | Return a value evaluated at the row that is at a specified physical offset row before the current row within the partition. |
| [LAST_VALUE](https://neon.tech/postgresql/postgresql-window-function/postgresql-last_value-function)     | Return a value evaluated against the last row within its partition.                                                         |
| [LEAD](https://neon.tech/postgresql/postgresql-window-function/postgresql-lead-function)                 | Return a value evaluated at the row that is offset rows after the current row within the partition.                         |
| [NTILE](https://neon.tech/postgresql/postgresql-window-function/postgresql-ntile-function)               | Divide rows in a partition as equally as possible and assign each row an integer starting from 1 to the argument value.     |
| [NTH_VALUE](https://neon.tech/postgresql/postgresql-window-function/postgresql-nth_value-function)       | Return a value evaluated against the nth row in an ordered partition.                                                       |
| [PERCENT_RANK](https://neon.tech/postgresql/postgresql-window-function/postgresql-percent_rank-function) | Return the relative rank of the current row (rank-1) / (total rows – 1)                                                     |
| [RANK](https://neon.tech/postgresql/postgresql-window-function/postgresql-rank-function)                 | Rank the current row within its partition with gaps.                                                                        |
| [ROW_NUMBER](https://neon.tech/postgresql/postgresql-window-function/postgresql-row_number)              | Number the current row within its partition starting from 1.                                                                |