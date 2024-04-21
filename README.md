## Тестовое задание в Ozon
### Задание 4
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
### Задание 7
Решение находится в файле "test_ozon.ipynb"
