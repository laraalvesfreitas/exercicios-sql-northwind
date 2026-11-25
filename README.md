# Exercícios para Relembrar SQL 🗄️

Lista de exercícios práticos em SQL utilizando o banco de dados Northwind (W3Schools), cobrindo consultas básicas, filtros, ordenação, funções de agregação e JOINs.

Lista de consultas básicas e intermediárias para praticar `SELECT`, `WHERE`, `ORDER BY`, `LIMIT`, funções de agregação (`COUNT`, `SUM`), `GROUP BY` e `JOIN`.

> **Ambiente:** Todos os exercícios foram testados no [W3Schools Try-SQL Editor](https://w3schools.com) utilizando o banco de dados **Northwind** (`Customers`, `Products`, `Orders`, `OrderDetails`, `Categories`, `Suppliers` e `Employees`).

---

### 1. Liste todos os clientes.
```sql
SELECT * 
FROM Customers;
```

### 2. Mostre apenas `CustomerName`, `City` e `Country` de todos os clientes.
```sql
SELECT CustomerName, City, Country  
FROM Customers;
```

### 3. Liste os clientes do país Brazil.
```sql
SELECT * 
FROM Customers
WHERE Country = 'Brazil';
```

### 4. Liste os produtos com preço maior que 50.
```sql
SELECT * 
FROM Products 
WHERE Price > 50;
```

### 5. Liste os produtos ordenados do mais caro para o mais barato.
```sql
SELECT * 
FROM Products 
ORDER BY Price DESC;
```

### 6. Mostre os 5 produtos mais baratos (`LIMIT`).
```sql
SELECT *
FROM Products 
ORDER BY Price ASC
LIMIT 5;
```

### 7. Quantos clientes existem no total? (`COUNT`)
```sql
SELECT COUNT(*) AS Total_Clientes
FROM Customers;
```

### 8. Liste o nome do produto e o nome do fornecedor (`Products` + `Suppliers`).
```sql
SELECT 
    Products.ProductName, 
    Suppliers.SupplierName
FROM Products
JOIN Suppliers ON Products.SupplierID = Suppliers.SupplierID;
```

### 9. Liste o nome do produto e o nome da categoria (`Products` + `Categories`).
```sql
SELECT 
    Products.ProductName, 
    Categories.CategoryName
FROM Products
JOIN Categories ON Products.CategoryID = Categories.CategoryID;
```

### 10. Qual é a receita total por pedido? (`Quantity * Price`, juntando `OrderDetails` e `Products`)
```sql
SELECT 
    OrderDetails.OrderID, 
    SUM(OrderDetails.Quantity * Products.Price) AS Receita_Total
FROM OrderDetails
JOIN Products ON OrderDetails.ProductID = Products.ProductID
GROUP BY OrderDetails.OrderID;
```



