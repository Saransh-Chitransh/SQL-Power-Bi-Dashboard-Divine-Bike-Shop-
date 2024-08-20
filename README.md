# SQL-Power-Bi-Dashboard-Divine-Bike-Shop-
Made a Power BI interactive Dashboard by getting a new table from coding in SQL to get desired data from 3 workbooks and connecting Excel > SQL > Power BI

**code I used to get desired data from 3 workbooks

with cte as (
select * from bike_share_yr_0
union all
select * from bike_share_yr_1)
select
dteday, season, a.yr, weekday, hr, rider_type, riders,
price, COGS,
riders*price as revenue,
riders*price - COGS*riders as profit
from cte a
left join cost_table b
on a.yr = b.yr;
