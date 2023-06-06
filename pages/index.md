# Welcome to Evidence!

Build polished data products with SQL and Markdown.

## Run SQL


Write queries using markdown code fences ` ``` `:

```orders_by_month
select
  date_trunc('month', order_datetime) as order_month,
  category,
  count(*) as number_of_orders,
  sum(sales) as sales_usd0k,
  sum(sales)/count(*) as average_order_value_usd2
from orders

group by 1,2
order by 4
```

## Make Charts

Charts can be included in a single line of code:

<BarChart 
  data={orders_by_month} 
  title = 'Sales by Month, USD' 
  y=sales_usd0k
  series=category
/>


