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

7. 