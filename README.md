# SQL_Practice_Exam

1:
SELECT COUNT(orders)
FROM ORDERS
WHERE ORDERS BETWEEN ('01-01-1996', '01-31-1996');

2:
SELECT COUNT(ProductName)
FROM Products
GROUP BY ProductName ORDER BY ProductName desc;

3:
SELECT C.CustomerName, COUNT(O.OrderID) AS tot_order_qty
FROM Customer AS C JOIN Order AS O ON C.CustomerID = O.CustomerID JOIN OrderDetials AS OD ON OD.OrderID = O.OrderID
WHERE tot_order_qty > 100
GROUP BY CustomerName
ORDER BY desc;

4:
SELECT LastName, COUNT(OrderID) AS NumOrdWorkOn
FROM Employee AS E JOIN Order AS O On E.EmployeeID = O.EmployeeID
GROUP BY E.EmployeeID
ORDER BY NumOrdWorkOn desc;

5:
SELECT S.ShipperName, COUNT(O.ShipperID) NumOrdShipped
FROM Shipper AS S JOIN Orders AS O ON S.ShipperID = O.ShipperID
GROUP BY S.ShipperName ORDER BY NumOrdShipped Desc;

6: 
SELECT C.CategoryName, COUNT(P.CategoryID) AS NumOfCate
FROM Categories AS C JOIN Products As P ON C.CategoryID = P.CategoryID
GROUP BY NumOfCate ORDER BY NumOfCate Desc;
