
## Successful Queries

### Get data on a particular SKU from Amazon
SELECT date, ordered_quantity FROM df WHERE official_sku = 'BC-001' AND channel = 'Amazon' AND CAST(date AS DATE) >= CURRENT_DATE - INTERVAL '1 year' LIMIT 100; """

### Extract all sales data for the current month from Amazon, including SKU and ordered quantity
SELECT date, official_sku, ordered_quantity 
FROM df 
WHERE channel = 'Amazon' 
AND strftime('%Y-%m', date::DATE) = strftime('%Y-%m', CURRENT_DATE)

## Common Errors
Catalog Error: Scalar Function with name curdate does not exist. 
Binder Error: No function matches the given name and argument types 'date_sub(DATE, INTERVAL)'. 
Binder Error: Cannot compare values of type VARCHAR and type TIMESTAMP - an explicit cast is required. 

