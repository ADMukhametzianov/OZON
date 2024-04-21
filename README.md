## Тестовое задание в Ozon
### Задание 4
Ответ: D
### Задание 5
```sql
SELECT DATE_TRUNC('month', Sales.Date) AS Month,
  CASE
    WHEN Sales.Price < 500 THEN 'Ценовая группа 1'
    WHEN Sales.Price BETWEEN 500 AND 1000 THEN 'Ценовая группа 2'
    WHEN Sales.Price > 1000 THEN 'Ценовая группа 3'
  END AS Price_Group,
  SUM(Sales.Price * Sales.Qty) AS Sales_in_Rubles
FROM Sales
GROUP BY Month, Price_Group
ORDER BY Month, Price_Group;
```
### Задание 6
```sql
SELECT Students.ID, Students.Name
FROM Students LEFT JOIN Marks ON Students.ID = Marks.ID
WHERE Marks.Mark IS NULL OR Marks.Mark >= 4
GROUP BY Students.ID, Students.Name
HAVING 
  COUNT(DISTINCT Marks.Subject) = 0 OR COUNT(DISTINCT CASE WHEN Marks.Mark < 4 THEN Marks.Subject END) = 0;
```
### Задание 7
Решение находится в файле "test_ozon.ipynb"
