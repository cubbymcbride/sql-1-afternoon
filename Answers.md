1. Create a table called person that records a person's id, name, age, height ( in cm ), city, favorite_color. 
    * id should be an auto-incrementing id/primary key - Use type: SERIAL
    CREATE TABLE person ( person_id SERIAL, name VARCHAR(200), age INTEGER, height INTEGER, city VARCHAR(200), favorite_color VARCHAR(200) );

2. Add 5 different people into the person database. 
    * Remember to not include the person_id because it should auto-increment.
    INSERT INTO person ( name, age, height, city, favorite_color ) VALUES ( 'Caleb McBride', 23, 182, 'Springville', 'White' );
    INSERT INTO person ( name, age, height, city, favorite_color ) VALUES ( 'Donna McBride', 46, 150, 'Oakley', 'Magenta' );
    INSERT INTO person ( name, age, height, city, favorite_color ) VALUES ( 'Ton McBride', 25, 160, 'Oakley', 'Black' );
    INSERT INTO person ( name, age, height, city, favorite_color ) VALUES ( 'Max McBride', 25, 160, 'Springville', 'Purple' );
    INSERT INTO person ( name, age, height, city, favorite_color ) VALUES ( 'Jacob McBride', 25, 180, 'Twin Falls', 'Red' );

3. List all the people in the person table by height from tallest to shortest.
    Select * from person order by height desc

4. List all the people in the person table by height from shortest to tallest.
    Select * from person order by height asc

5. List all the people in the person table by age from oldest to youngest.
    select * from person order by age desc

6. List all the people in the person table older than age 20.
    select * from person where age > 26;

7. List all the people in the person table that are exactly 18.
    select * from person where age = 18;

8. List all the people in the person table that are less than 20 and older than 30.
    select * from person where age < 20 or age > 30;

9. List all the people in the person table that are not 27 (Use not equals).
    select * from person where age != 27;

10. List all the people in the person table where their favorite color is not red.
    select * from person where favorite_color != 'Red';

11. List all the people in the person table where their favorite color is not red and is not blue.
    select * from person where favorite_color != 'Red' and favorite_color !='Blue';

12. List all the people in the person table where their favorite color is orange or green.
    select * from person where favorite_color != 'Orange' or favorite_color !='Green';

13. List all the people in the person table where their favorite color is orange, green or blue (use IN).
    select * from person where favorite_color in ('Orange', 'Green', 'Blue');

14. List all the people in the person table where their favorite color is yellow or purple (use IN).
    select * from person where favorite_color in ('Yellow', 'Purple');



1. Create a table called orders that records: person_id, product_name, product_price, quantity.
    CREATE TABLE orders ( person_id SERIAL, product_name VARCHAR(200), product_price NUMERIC, quantity INTEGER );

2. Add 5 orders to the orders table.
    * Make orders for at least two different people.
    insert into orders ( person_id, product_name, product_price, quantity) values ( 1, 'Hotdog', 1, 1);
    insert into orders ( person_id, product_name, product_price, quantity) values ( 0, 'Pizza', 1, 1);
    insert into orders ( person_id, product_name, product_price, quantity) values ( 0, 'Pickle', 2, 4);
    insert into orders ( person_id, product_name, product_price, quantity) values ( 0, 'Sandwich', 3, 15);
    insert into orders ( person_id, product_name, product_price, quantity) values ( 0, 'Chips', 1, 15);
    insert into orders ( person_id, product_name, product_price, quantity) values ( 0, 'Hamburger', 4, 23);

    * person_id should be different for different people.


3. Select all the records from the orders table.
    select * from orders;

4. Calculate the total number of products ordered.
    select SUM(quantity) from orders;

5. Calculate the total order price.
    select SUM(product_price * quantity) from orders;

6. Calculate the total order price by a single person_id.
    select SUM(product_price * quantity) from orders where person_id = 0;



1. Add 3 new artists to the artist table. ( It's already created )
    INSERT into artist ( name ) values ( 'For The Win' );
    INSERT into artist ( name ) values ( 'Real Friends' );
    INSERT into artist ( name ) values ( 'Famous Friends' );

2. Select 10 artists in reverse alphabetical order.
    select * from artist order by name desc limit 10;

3. Select 5 artists in alphabetical order.
    select * from artist order by name asc limit 5;

4. Select all artists that start with the word 'Black'.
    select * from artist where name like 'Black%';

5. Select all artists that contain the word 'Black'.
    select * from artist where name like '%Black%';



1. List all employee first and last names only that live in Calgary.
    select first_name, last_name from employee where city = 'Calgary';

2. Find the birthdate for the youngest employee.
    select MAX(birth_date) from employee;

3. Find the birthdate for the oldest employee.
    select MIN(birth_date) from employee;


4. Find everyone that reports to Nancy Edwards (Use the ReportsTo column).
    * You will need to query the employee table to find the Id for Nancy Edwards
    select * from employee where reports_to = 2;

5. Count how many people live in Lethbridge.
    select COUNT(*) from employee where city = 'Lethbridge';



1. Count how many orders were made from the USA.
    select COUNT(*) from invoice where billing_country = 'USA';

2. Find the largest order total amount.
    select MAX(total) from invoice;

3. Find the smallest order total amount.
    select MIN(total) from invoice;

4. Find all orders bigger than $5.
    select * from invoice where total > 5;

5. Count how many orders were smaller than $5.
    select COUNT(*) from invoice where total < 5;

6. Count how many orders were in CA, TX, or AZ (use IN).
    select COUNT(*) from invoice where billing_state in ('CA', 'TX', 'AZ');

7. Get the average total of the orders.
    select AVG(total) from invoice;

8. Get the total sum of the orders.
    select SUM(total) from invoice;
