
## Successful Queries
SELECT date, ordered_quantity FROM df WHERE official_sku = 'BC-001' AND channel = 'Amazon' AND CAST(date AS DATE) >= CURRENT_DATE - INTERVAL '1 year' LIMIT 100; """

## Common Errors
Catalog Error: Scalar Function with name curdate does not exist. 
Binder Error: No function matches the given name and argument types 'date_sub(DATE, INTERVAL)'. 
Binder Error: Cannot compare values of type VARCHAR and type TIMESTAMP - an explicit cast is required. 
