Date last edited: 10/13/2024 at 8:50pm ET

## Notes
### Available datasets and tables, in the format dataset.table:
#### All Orders: 
* if sku ends with -US or -CA, remove
- Ebay/ebay_sales
- walmart/walmart_orders
- Etsy/etsy_sales
- amazon_orders/amz_numberorders_per_datesku
- shopify/shopify_orders

#### All Products and SKUs (across all channels): 
- AAA_General_Core_Tables/official_sku_database

#### COGS (all brands): 
- COGS/cogs_all_brands

#### Amazon BSR: 
- amazon_bsr_and_other/bsr_weekly

#### Returns/refunds
- amazon_orders/amz_returns_report
- walmart/walmart_returns
- shopify/shopify_refunds

#### Customer Reviews: 
- walmart/walmart_customer_reviews
- Etsy/etsy_Reviews.csv

#### Shopify Customer Order Data: 
- shopify/shopify_customers_orders_data

#### Listings by Shop: 
- shopify/shopify_products
- Etsy/etsy_ListingsByShop

## Successful Plans
### Get the name of a particular SKU
{
    "Plan": {
        "1": {
            "Request": "Get the name associated with the SKU BC-001",
            "DataNeeded": "AAA_General_Core_Tables.official_sku_database",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        }
    }
}

### Chart sales for a particular SKU
{
    "Plan": {
        "1": {
            "Request": "Extract all sales data for SKU 'BC-001' from Amazon over the last year, including ordered quantity.",
            "DataNeeded": "amazon_orders.amz_numberorders_per_datesku",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "2": {
            "Request": "Extract all sales data for SKU 'BC-001' from Walmart over the last year, including ordered quantity and sales revenue.",
            "DataNeeded": "walmart.walmart_orders",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "3": {
            "Request": "Extract all sales data for SKU 'BC-001' from eBay over the last year, including ordered quantity and sales revenue.",
            "DataNeeded": "Ebay.ebay_sales",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "4": {
            "Request": "Aggregate sales data from Amazon, Walmart, and eBay for SKU 'BC-001' over the last year and plot cumulative sales over time.",
            "DataNeeded": "1, 2, 3",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        }
    }
}
