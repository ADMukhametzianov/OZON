## Тестовое задание в Ozon
Решение заданий 1-3 находятся в файле "OZON_excel".

### Задание 1
Ответ: 
1.1. Меньше;
1.2. 1,75

### Задание 2
Ответ:
Прибыль при первом варианте постоянна и составляет 900 руб. Прибыль при втором варианте зависит от цены продажи товара на OZON. Если цена продажи составляет > 531 руб, то при втором варианте прибыль OZON больше.

### Задание 3
Ответ: не может быть, так конверсия тоталя состоит из отношения сумм заказов и просмотров по категориям.

### Задание 4
Ответ: D, так как правое соединение вернет все записи из правой таблицы и любые соответствующие записи из левой таблицы, и условие фильтрации в условии соединения (second.filter_column >= 42) еще больше ограничит результаты из второй таблицы, увеличив количество возвращаемых записей.

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

### Задание 8
Сначала нужно разобрать, не произошел ли какой-то сбой с внесением данных в систему. Если все ок, то можно посмотреть на следующие факторы, которые были именно в этот период (сентябрь 22): маркетинговые кампании (акции), изменение цен данной группы товаров, изменение ассортимента продукции или изменение дизайна сайта.
