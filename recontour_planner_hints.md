Date last edited: 10/13/2024 at 8:50pm ET

## Notes
### Available datasets and tables, in the format dataset.table:
AAA_General_Core_Tables.official_sku_database
AACC_inventoryadjustment.brands_amazonorders
AACC_inventoryadjustment.brands_amazonreturns
COGS.cogs_all_brands
Ebay.ebay_sales
Etsy.etsy_ListingsByShop
Etsy.etsy_Reviews
Etsy.etsy_sales
amazon_bsr_and_other.bsr_weekly
amazon_orders.amz_numberorders_per_datesku
amazon_orders.amz_returns_report
amz_salestraffic.amz_salestraffic_date
names.txt
shopify.shopify_customers_orders_data
shopify.shopify_orders
shopify.shopify_products
shopify.shopify_refunds
walmart.walmart_customer_reviews
walmart.walmart_inventory
walmart.walmart_orders
walmart.walmart_returns

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
