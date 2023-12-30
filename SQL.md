# Where condition

CMD ) <b>select * from Customers where Country="UK";</b>
    
<table class="w3-table-all notranslate"><tbody><tr><th align="left">CustomerID</th><th align="left">CustomerName</th><th align="left">ContactName</th><th align="left">Address</th><th align="left">City</th><th align="left">PostalCode</th><th align="left">Country</th></tr><tr><td valign="top">4</td><td valign="top">Around the Horn</td><td valign="top">Thomas Hardy</td><td valign="top">120 Hanover Sq.</td><td valign="top">London</td><td valign="top">WA1 1DP</td><td valign="top">UK</td></tr><tr><td valign="top">11</td><td valign="top">B's Beverages</td><td valign="top">Victoria Ashworth</td><td valign="top">Fauntleroy Circus</td><td valign="top">London</td><td valign="top">EC2 5NT</td><td valign="top">UK</td></tr><tr><td valign="top">16</td><td valign="top">Consolidated Holdings</td><td valign="top">Elizabeth Brown</td><td valign="top">Berkeley Gardens 12 Brewery </td><td valign="top">London</td><td valign="top">WX1 6LT</td><td valign="top">UK</td></tr><tr><td valign="top">19</td><td valign="top">Eastern Connection</td><td valign="top">Ann Devon</td><td valign="top">35 King George</td><td valign="top">London</td><td valign="top">WX3 6FW</td><td valign="top">UK</td></tr><tr><td valign="top">53</td><td valign="top">North/South</td><td valign="top">Simon Crowther</td><td valign="top">South House 300 Queensbridge</td><td valign="top">London</td><td valign="top">SW7 1RZ</td><td valign="top">UK</td></tr><tr><td valign="top">72</td><td valign="top">Seven Seas Imports</td><td valign="top">Hari Kumar</td><td valign="top">90 Wadhurst Rd.</td><td valign="top">London</td><td valign="top">OX15 4NB</td><td valign="top">UK</td></tr></tbody></table>

CMD ) <b>select * from Customers where CustomerID = 2;</b>

<table class="w3-table-all notranslate"><tbody><tr><th align="left">CustomerID</th><th align="left">CustomerName</th><th align="left">ContactName</th><th align="left">Address</th><th align="left">City</th><th align="left">PostalCode</th><th align="left">Country</th></tr><tr><td valign="top">2</td><td valign="top">Ana Trujillo Emparedados y helados</td><td valign="top">Ana Trujillo</td><td valign="top">Avda. de la Constitución 2222</td><td valign="top">México D.F.</td><td valign="top">05021</td><td valign="top">Mexico</td></tr></tbody></table>
<hr>

# MySQL AND, OR and NOT Operators

Query ) <b>select * from Customers where City="Berlin" and Country="Germany";</b>

<table class="w3-table-all notranslate"><tbody><tr><th align="left">CustomerID</th><th align="left">CustomerName</th><th align="left">ContactName</th><th align="left">Address</th><th align="left">City</th><th align="left">PostalCode</th><th align="left">Country</th></tr><tr><td valign="top">1</td><td valign="top">Alfreds Futterkiste</td><td valign="top">Maria Anders</td><td valign="top">Obere Str. 57</td><td valign="top">Berlin</td><td valign="top">12209</td><td valign="top">Germany</td></tr></tbody></table>

Query ) <h5>select * from Customers where City="Berlin" or Country ="Germany";</h5>


<h4>Query ) select * from Customers where NOT City="London";</h4>

<b>Combining AND, OR and NOT</b>

Query <h4>select * from Customers where Country="Germany" and ( City="Berlin" or City="München");</h4>

Query <h4>select * from Customers where not Country="Germany" and not City="USA";</h4>

<br>
<hr>

# The MySQL ORDER BY Keyword

Query ) select * from Customers order by City;

selected column नाव ने  alphabetical order ne table order hoil

<h4> Asending decending order</h4>

Query ) <h4>select * from Customers order by City DESC;

Query ) <h4>select * from Customers order by City ASC;

# ORDER BY Several Columns Example

Query ) select * from Customers order by ContactName, City;

Query ) select * from Customers order by City ASC, Country DESC;

<hr>
<hr>

# The MySQL INSERT INTO Statement

Query ) INSERT INTO Customers (CustomerName, City, Country) VALUES ('Cardinal', 'Stavanger', 'Norway');

<hr>
<hr>

# MySQL NULL Values

<b>The IS NULL Operator</b>

Query ) select * from Customers where City is null;

<b> The IS NOT NULL Operator <b>

Query ) select City, Address from Customers where Address is not null;

<hr>
<hr>

# MySQL UPDATE Statement

Query ) update Customers set City="Pune" where CustomerID = 1;

<hr>
<hr>

<br>

# Delete All Records

Delete single record 

Query ) delete from Customers where CustomerID =1;

Delete all records

Query ) delete from Customers;

<hr>
<hr>

# MySQL LIMIT Clause

Query ) select * from Customers limit 2;

<table class="w3-table-all notranslate"><tbody><tr><th align="left">CustomerID</th><th align="left">CustomerName</th><th align="left">ContactName</th><th align="left">Address</th><th align="left">City</th><th align="left">PostalCode</th><th align="left">Country</th></tr><tr><td valign="top">1</td><td valign="top">Alfreds Futterkiste</td><td valign="top">Maria Anders</td><td valign="top">Obere Str. 57</td><td valign="top">Berlin</td><td valign="top">12209</td><td valign="top">Germany</td></tr><tr><td valign="top">2</td><td valign="top">Ana Trujillo Emparedados y helados</td><td valign="top">Ana Trujillo</td><td valign="top">Avda. de la Constitución 2222</td><td valign="top">México D.F.</td><td valign="top">05021</td><td valign="top">Mexico</td></tr></tbody></table>


Query ) select * from Customers limit 2 OFFSET 5;

<table class="w3-table-all notranslate"><tbody><tr><th align="left">CustomerID</th><th align="left">CustomerName</th><th align="left">ContactName</th><th align="left">Address</th><th align="left">City</th><th align="left">PostalCode</th><th align="left">Country</th></tr><tr><td valign="top">6</td><td valign="top">Blauer See Delikatessen</td><td valign="top">Hanna Moos</td><td valign="top">Forsterstr. 57</td><td valign="top">Mannheim</td><td valign="top">68306</td><td valign="top">Germany</td></tr><tr><td valign="top">7</td><td valign="top">Blondel père et fils</td><td valign="top">Frédérique Citeaux</td><td valign="top">24, place Kléber</td><td valign="top">Strasbourg</td><td valign="top">67000</td><td valign="top">France</td></tr></tbody></table>

Query ) select * from Customers where Country="Germany" limit 3;

<table class="w3-table-all notranslate"><tbody><tr><th align="left">CustomerID</th><th align="left">CustomerName</th><th align="left">ContactName</th><th align="left">Address</th><th align="left">City</th><th align="left">PostalCode</th><th align="left">Country</th></tr><tr><td valign="top">1</td><td valign="top">Alfreds Futterkiste</td><td valign="top">Maria Anders</td><td valign="top">Obere Str. 57</td><td valign="top">Berlin</td><td valign="top">12209</td><td valign="top">Germany</td></tr><tr><td valign="top">6</td><td valign="top">Blauer See Delikatessen</td><td valign="top">Hanna Moos</td><td valign="top">Forsterstr. 57</td><td valign="top">Mannheim</td><td valign="top">68306</td><td valign="top">Germany</td></tr><tr><td valign="top">17</td><td valign="top">Drachenblut Delikatessend</td><td valign="top">Sven Ottlieb</td><td valign="top">Walserweg 21</td><td valign="top">Aachen</td><td valign="top">52066</td><td valign="top">Germany</td></tr></tbody></table>


<hr>
<hr>

# MySQL MIN() and MAX() Functions

Query ) select min(Price) from Products;

<table class="w3-table-all notranslate"><tbody><tr><th align="left">min(Price)</th></tr><tr><td valign="top">2.50</td></tr></tbody></table>

Query ) select max(Price) from Products;

<table class="w3-table-all notranslate"><tbody><tr><th align="left">max(Price)</th></tr><tr><td valign="top">263.50</td></tr></tbody></table>



<hr>
<hr>
<br>

# MySQL COUNT(), AVG() and SUM() Functions

Query ) select count(*) from Products;

<table class="w3-table-all notranslate"><tbody><tr><th align="left">count(*)</th></tr><tr><td valign="top">77</td></tr></tbody></table>

Query ) select AVG(Price) from Products;

<table class="w3-table-all notranslate"><tbody><tr><th align="left">AVG(Price)</th></tr><tr><td valign="top">28.866364</td></tr></tbody></table>

Query ) select sum(Price) from Products;

<table class="w3-table-all notranslate"><tbody><tr><th align="left">sum(Price)</th></tr><tr><td valign="top">2222.71</td></tr></tbody></table>

<hr>
<hr>

# MySQL LIKE Operator


Query ) select * from Customers where Address like "%a"

<table class="w3-table-all notranslate"><tbody><tr><th align="left">CustomerID</th><th align="left">CustomerName</th><th align="left">ContactName</th><th align="left">Address</th><th align="left">City</th><th align="left">PostalCode</th><th align="left">Country</th></tr><tr><td valign="top">54</td><td valign="top">Océano Atlántico Ltda.</td><td valign="top">Yvonne Moncada</td><td valign="top">Ing. Gustavo Moncada 8585 Piso 20-A</td><td valign="top">Buenos Aires</td><td valign="top">1010</td><td valign="top">Argentina</td></tr></tbody></table>


