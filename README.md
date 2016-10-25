# sql

How many users are there?
  50 SELECT * FROM USERS
What are the 5 most expensive items?
  SELECT * FROM ITEMS ORDER BY PRICE DESC LIMIT 5
  Small Cotton Gloves|Automotive, Shoes & Beauty|Multi-layered modular service-desk|9984
  83|Small Wooden Computer|Health|Re-engineered fault-tolerant adapter|9859
  100|Awesome Granite Pants|Toys & Books|Upgradable 24/7 access|9790
  40|Sleek Wooden Hat|Music & Baby|Quality-focused heuristic info-mediaries|9390
  60|Ergonomic Steel Car|Books & Outdoors|Enterprise-wide secondary firmware|9341

What's the cheapest book? (Does that change for "category is exactly 'book'" versus "category contains 'book'"?)
  76|Ergonomic Granite Chair|Books|De-engineered bi-directional portal|1496
   SELECT * FROM ITEMS WHERE CATEGORY = "Books" ORDER BY PRICE DESC;

Who lives at "6439 Zetta Hills, Willmouth, WY"? Do they have another address?
|Corrine|Little|rubie_kovacek@grimes.net|43|40|6439 Zetta Hills|Willmouth|WY|15029
40|Corrine|Little|rubie_kovacek@grimes.net|44|40|54369 Wolff Forges|Lake Bryon|CA|31587
SELECT * FROM USERS INNER JOIN ADDRESSES ON USERS.ID = ADDRESSES.USER_ID;


Correct Virginie Mitchell's address to "New York, NY, 10108".
  39|Virginie|Mitchell|daisy.crist@altenwerthmonahan.biz
  SELECT * FROM USERS WHERE USERS.FIRST_NAME="Virginie";

 UPDATE addresses SET city = "New York", state= "NY", zip = "10108" WHERE USER_id="39";

How much would it cost to buy one of each tool?
  SUM (PRICE) 46477
 SELECT SUM (PRICE) FROM ITEMS WHERE CATEGORY LIKE "%Tools%";

How many total items did we sell?
 SELECT SUM ("quantity") FROM orders;
  2125

How much was spent on books?
  SELECT SUM (“quantity”) FROM orders WHERE CATEGORY like “%books%”
Simulate buying an item by inserting a User for yourself and an Order for that User.
