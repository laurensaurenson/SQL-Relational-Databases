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

14. SELECT COUNT(*), BillingCountry
FROM Invoice
GROUP BY BillingCountry

15. SELECT Playlist.Name, COUNT(*)
FROM Playlist
JOIN PlaylistTrack ON Playlist.PlaylistId = PlaylistTrack.PlaylistId
GROUP BY Playlist.PlaylistId

16. SELECT Track.Name, Album.Title, MediaType.Name, Genre.Name
FROM Track
JOIN Album ON Track.AlbumId = Album.AlbumId
JOIN MediaType ON Track.MediaTypeId = MediaType.MediaTypeId
JOIN Genre ON Track.GenreId = Genre.GenreId

17. SELECT *, COUNT(*)
FROM Invoice
JOIN InvoiceLine ON Invoice.InvoiceId = InvoiceLine.InvoiceId
GROUP BY Invoice.InvoiceId

18. SELECT Employee.FirstName || " " || Employee.LastName AS "Name", COUNT(*)
FROM Employee
JOIN Customer ON Employee.EmployeeId = Customer.SupportRepId
GROUP BY Employee.EmployeeId

19. SELECT Employee.FirstName || " " || Employee.LastName AS "Name", SUM(Invoice.Total)
FROM Employee
JOIN Customer ON Employee.EmployeeId = Customer.SupportRepId
JOIN Invoice ON Customer.CustomerId = Invoice.CustomerId
WHERE Invoice.InvoiceDate LIKE "2009%"
GROUP BY Employee.EmployeeId
ORDER BY SUM(Invoice.Total) DESC
LIMIT 1

20. SELECT Employee.FirstName || " " || Employee.LastName AS "Name", SUM(Invoice.Total)
FROM Employee
JOIN Customer ON Employee.EmployeeId = Customer.SupportRepId
JOIN Invoice ON Customer.CustomerId = Invoice.CustomerId
WHERE Invoice.InvoiceDate LIKE "2010%"
GROUP BY Employee.EmployeeId
ORDER BY SUM(Invoice.Total) DESC
LIMIT 1

21. SELECT Employee.FirstName || " " || Employee.LastName AS "Name", SUM(Invoice.Total)
FROM Employee
JOIN Customer ON Employee.EmployeeId = Customer.SupportRepId
JOIN Invoice ON Customer.CustomerId = Invoice.CustomerId
GROUP BY Employee.EmployeeId
ORDER BY SUM(Invoice.Total) DESC
LIMIT 1

22. SELECT Employee.FirstName || " " || Employee.LastName AS "Name", COUNT(Customer.CustomerId)
FROM Employee
JOIN Customer ON Employee.EmployeeId = Customer.SupportRepId
JOIN Invoice ON Customer.CustomerId = Invoice.CustomerId
GROUP BY Employee.EmployeeId

23. SELECT SUM(Total), BillingCountry
FROM Invoice
GROUP BY BillingCountry
ORDER BY Sum(Total) DESC

24. SELECT Track.Name, COUNT(*), Invoice.InvoiceDate
FROM Invoice
JOIN InvoiceLine ON Invoice.InvoiceId = InvoiceLine.InvoiceId
JOIN Track ON InvoiceLine.TrackId = Track.TrackId
WHERE Invoice.InvoiceDate LIKE "2013-%"
GROUP BY Track.Name
ORDER BY COUNT(*) DESC

25. SELECT Track.Name, COUNT(*), Invoice.InvoiceDate
FROM Invoice
JOIN InvoiceLine ON Invoice.InvoiceId = InvoiceLine.InvoiceId
JOIN Track ON InvoiceLine.TrackId = Track.TrackId
GROUP BY Track.Name
ORDER BY COUNT(*) DESC
LIMIT 5

26. SELECT Artist.Name
FROM Invoice
JOIN InvoiceLine ON Invoice.InvoiceId = InvoiceLine.InvoiceId
JOIN Track ON InvoiceLine.TrackId = Track.TrackId
JOIN Album ON Track.AlbumId = Album.AlbumId
JOIN Artist ON Album.ArtistId = Artist.ArtistId
GROUP BY Artist.Name
ORDER BY SUM(Invoice.Total) DESC
LIMIT 3

27. SELECT MediaType.Name
FROM Invoice
JOIN InvoiceLine ON Invoice.InvoiceId = InvoiceLine.InvoiceId
JOIN Track ON InvoiceLine.TrackId = Track.TrackId
JOIN MediaType ON Track.MediaTypeId = MediaType.MediaTypeId
GROUP BY MediaType.Name
ORDER BY SUM(Invoice.Total) DESC
LIMIT 1