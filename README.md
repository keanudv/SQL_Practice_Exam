# SQL_Practice_Exam

1:
SELECT COUNT(orderID) AS num_order, OrderDate
FROM Orders
WHERE OrderDate BETWEEN '1996-08-1' AND '1996-06-31'
GROUP BY OrderDate ORDER BY num_order DESC;

2:
SELECT P.ProductName, SUM(OD.Quantity) AS TotalQty
FROM Products AS P JOIN OrderDetials AS OD ON P.ProductID = OD.ProductID
GROUP BY P.ProductName ORDER BY TotalQty DESC;

3:
SELECT C.CustomerName, SUM(OD.Quantity) AS TotalOrdQty
FROM Customer AS C JOIN Orders AS O ON C.CustomerID = O.CustomerID JOIN OrderDetails AS OD ON OD.OrderID = O.OrderID
GROUP BY C.CustomerName
HAVING SUM(OD.Quantity) > 100
ORDER BY TotalOrdQty DESC;

4:
SELECT E.LastName, COUNT(O.OrderID) AS NumOrdWorkOn
FROM Employee AS E JOIN Order AS O On E.EmployeeID = O.EmployeeID
GROUP BY E.LastName
ORDER BY NumOrdWorkOn DESC;

5:
SELECT S.ShipperName, COUNT(O.ShipperID) AS NumOrdShipped
FROM Shipper AS S JOIN Orders AS O ON S.ShipperID = O.ShipperID
GROUP BY S.ShipperName ORDER BY NumOrdShipped DESC;

6: 
SELECT C.CategoryName, COUNT(P.CategoryID) AS NumOfCate
FROM Categories AS C JOIN Products As P ON C.CategoryID = P.CategoryID
GROUP BY NumOfCate ORDER BY NumOfCate Desc;
