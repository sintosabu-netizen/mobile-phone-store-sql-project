Project title – Mobile Phone Store Sales Analysis 

Tool used - MySQL Workbench

Data source - it's custom build

ER diagram - <img width="1536" height="1024" alt="ER diagaram" src="https://github.com/user-attachments/assets/325c5562-4de5-4709-b7c6-ec385f09f2e3" />

Key business question answered - 

1. Which phones are priced above ₹30,000?

    SELECT * FROM phones
    WHERE price > 30000;

   <img width="319" height="189" alt="Screenshot 2026-09-17 124350" src="https://github.com/user-attachments/assets/c6bc92a9-4993-427f-8524-d3ccb3402532" />

2. what is average price of all phones?

   select avg(price) as average_price
   from phones;

   <img width="203" height="95" alt="Screenshot 2026-09-17 124527" src="https://github.com/user-attachments/assets/2cdcb4ca-63cd-4064-8112-835daa548205" />

   3. Which customers purchased Apple phones?

      select distinct c.first_name,
      c.last_name
      From customers c 
      join sales s on c.customer_id =
      s.customer_id
      join phones p on s.phone_id = 
      p.phone_id
      where p.brand = 'apple';

      <img width="172" height="137" alt="Screenshot 2026-09-17 124724" src="https://github.com/user-attachments/assets/351ea4ac-9eb0-4ce4-92d8-560b18a170dc" />
   
      4. Which brand has the highest price
    select p.brand,sum(s.total_amount)
    as total_sales
    from phones p
    join sales s on p.phone_id =
    s.phone_id
    group by p.brand
    order by total_sales desc
    limit 1;
    
    <img width="133" height="74" alt="Screenshot 2026-09-17 133245" src="https://github.com/user-attachments/assets/dca17332-8cf1-428b-aaf0-a7543d0c5895" />

    5. Which customers made more than one purchase?
   
   select customer_id, count(*) as 
  purchase_count
  from sales
  group by customer_id
  having count(*) > 1;

<img width="185" height="245" alt="Screenshot 2026-09-17 133622" src="https://github.com/user-attachments/assets/1ee81618-2242-4446-ad13-f43bd16e0ab0" />

What I learned

I learned how to use MySQL to analyze mobile phone store data using WHERE, COUNT, SUM, and AVG. I also practiced JOIN, GROUP BY, HAVING, and subqueries to answer business questions using multiple related tables.







