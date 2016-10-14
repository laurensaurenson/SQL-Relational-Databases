# SQL-Relational-Databases


1. SELECT  CustomerId, Country, FirstName || " " || LastName AS 'Name' FROM Customer
WHERE Country <> "USA"

2. SELECT  CustomerId, Country, FirstName || " " || LastName AS 'Name' FROM Customer
WHERE Country = "Brazil"

3. SELECT  Invoice.InvoiceId, Invoice.InvoiceDate, Customer.Country, Customer.FirstName || " " || Customer.LastName AS 'Name' 
FROM Invoice
JOIN Customer ON Customer.CustomerId = Invoice.CustomerId
WHERE Country = "Brazil"

4. SELECT  *
FROM Employee
WHERE Title = "Sales Support Agent"

5. SELECT  BillingCountry
FROM Invoice
GROUP BY BillingCountry

6. SELECT  Invoice.*
FROM Invoice
JOIN Customer ON Customer.CustomerId = Invoice.CustomerId
WHERE Customer.Country = "Brazil"

7. SELECT  Employee.FirstName || " " || Employee.LastName AS "EmployeeName", Invoice.*
FROM Invoice
JOIN Customer ON Customer.CustomerId = Invoice.CustomerId
JOIN Employee ON Customer.SupportRepId = Employee.EmployeeId

8. SELECT  Employee.FirstName || " " || Employee.LastName AS "EmployeeName", SUM(Invoice.Total), Customer.FirstName || " " || Customer.LastName AS "CustomerName", Invoice.BillingCountry 
FROM Invoice
JOIN Customer ON Customer.CustomerId = Invoice.CustomerId
JOIN Employee ON Customer.SupportRepId = Employee.EmployeeId
GROUP BY CustomerName

9. SELECT COUNT(*), SUM(Total)
FROM Invoice
WHERE InvoiceDate LIKE "2009%"

SELECT COUNT(*), SUM(Total)
FROM Invoice
WHERE InvoiceDate LIKE "2011%"

10. SELECT COUNT(*)
FROM InvoiceLine
WHERE InvoiceId = "37"

11. SELECT COUNT(*), InvoiceId
FROM InvoiceLine
GROUP BY InvoiceId

12. SELECT Track.Name, InvoiceLine.*
FROM InvoiceLine
JOIN Track ON InvoiceLine.TrackId = Track.TrackId

13. SELECT Artist.Name, Track.Name, InvoiceLine.*
FROM InvoiceLine
JOIN Track ON InvoiceLine.TrackId = Track.TrackId
JOIN  Album ON Track.AlbumId = Album.AlbumId
JOIN Artist ON Album.ArtistId = Artist.ArtistId

14. 