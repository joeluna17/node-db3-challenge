# Database Queries

### Display the ProductName and CategoryName for all products in the database. Shows 76 records.

SELECT ProductName, CategoryName 
FROM Products
JOIN Categories 
On Products.CategoryID = Categories.CategoryID

### Display the OrderID and ShipperName for all orders placed before January 9, 1997. Shows 161 records.

SELECT OrderID , FirstName , LastName , OrderDate
FROM Orders
JOIN Employees 
ON Orders.EmployeeID == Employees.EmployeeID
Where Orders.OrderDate < "1997-01-09" 
Order By OrderDate Desc

### Display all ProductNames and Quantities placed on order 10251. Sort by ProductName. Shows 3 records.

SELECT ProductName, Quantity 
FROM OrderDetails
JOIN Products
ON OrderDetails.ProductID = Products.ProductID
WHERE OrderID = "10251"

### Display the OrderID, CustomerName and the employee's LastName for every order. All columns should be labeled clearly. Displays 196 records.

SELECT OrderID, CustomerName, LastName 
FROM Orders
JOIN Customers
ON Orders.CustomerID = Customers.CustomerID
JOIN Employees 
ON Orders.EmployeeID = Employees.EmployeeID

### (Stretch)  Displays CategoryName and a new column called Count that shows how many products are in each category. Shows 9 records.

SELECT CategoryName , Count(ProductID) as Count
FROM Products
JOIN Categories
ON Products.CategoryID = Categories.CategoryID
Group BY Categories.CategoryName

### (Stretch) Display OrderID and a  column called ItemCount that shows the total number of products placed on the order. Shows 196 records. 