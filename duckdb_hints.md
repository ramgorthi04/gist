
## Successful Queries

### Get data on a particular SKU
SELECT date, ordered_quantity FROM df WHERE official_sku = 'BC-001' AND CAST(date AS DATE) >= CURRENT_DATE - INTERVAL '1 year';

### Get all SKUs and their sales for the current month, including SKU and ordered quantity. Make sure to CAST date AS DATE.
SELECT date, official_sku, ordered_quantity 
FROM df 
AND strftime('%Y-%m', date::DATE) = strftime('%Y-%m', CURRENT_DATE)

## Common Errors
Catalog Error: Scalar Function with name curdate does not exist. 
Binder Error: Cannot compare values of type VARCHAR and type TIMESTAMP - an explicit cast is required. 
