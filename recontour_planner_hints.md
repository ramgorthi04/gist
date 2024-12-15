Date last edited: 10/21/2024 at 2:29pm ET


## Available datasets and tables, in the format dataset.table:

## amazon_orders.amz_orders_wbr
Data on Amazon orders, covering order dates, locations, channels, products, and financial details. Key columns:

- **purchase_date_PST**: Date of purchase in PST for timing analysis.
- **country**: Geographic insights, supporting regional sales analysis.
- **channel**: Sales channel for identifying market reach (e.g., Amazon, eBay).
- **brand**: Provides insights into brand performance.
- **official_sku**: Product tracking through official SKU for detailed inventory and product analysis.
- **order_status**: Order status (e.g., Shipped, Delivered) to monitor fulfillment and identify delays.
- **ordered_quantity**: Total quantity of each product ordered, enabling sales volume tracking.
- **gross_sales_not_including_vat**: Total sales value excluding VAT for revenue analysis.

---

## AAA_General_Core_Tables.official_sku_database
A product catalog covering various brands, countries, and channels. Key columns:

- **brand**: Analyze brand performance.
- **country**: Geographic distribution.
- **channel**: Sales channel analysis.
- **product_name**: Product-level insights.
- **official_sku**: Track product listings.

---

## Etsy.etsy_Reviews
Customer reviews data for Etsy products. Key columns:

- **shop_id**: Shop identifier.
- **listing_id**: Product identifier.
- **rating**: Review ratings.
- **review**: Customer feedback.
- **create_timestamp**: Review date.

**Potential Insights**:
- Assess product quality and customer satisfaction.
- Detect fraud and analyze customer behavior.

---

## Etsy.etsy_ListingsByShop
Product listings from Etsy, including stock, pricing, and customization options. Key columns:

- **listing_id**: Product identifier.
- **title**: Product name.
- **quantity**: Stock levels.
- **price**: Pricing details.
- **num_favorers**: Popularity metric.

---

## shopify.shopify_products
Product listings from Shopify stores. Key columns:

- **date**: Record date.
- **store**: Shopify store.
- **brand**: Product brand.
- **official_sku**: Product identifier.
- **price**: Product pricing.
- **inventory_quantity**: Stock levels.

---

## walmart_operand.walmart_orders
Transactional data from Walmart orders. Key columns:

- **date**: Order date.
- **brand**: Brand performance.
- **country**: Market insights.
- **official_sku**: Product identifier.
- **gross_sales**: Revenue before refunds.
- **customerOrderId** Customer Order ID
- **ordered_quantity** Number of items ordered

---

## walmart_operand.walmart_customer_reviews
Customer reviews from Walmart. Key columns:

- **date**: Review date.
- **brand**: Product brand.
- **country**: Market region.
- **sku**: Product identifier.
- **average_rating**: Review ratings.
- **number_negat_reviews**: Number of negative reviews.

---

## walmart_operand.walmart_returns
Product return data from Walmart. Key columns:

- **return_date**: Return date.\
- **official_sku** product identifier
- **brand**: Product brand.
- **returnreason**: Reason for return.

---

## walmart_operand.walmart_inventory
Walmart inventory data over time. Key columns:

- **date**: Record date.
- **sku**: Product identifier.
- **input_qty**: Quantity added to inventory.
- **availtosell_qty**: Available stock.

---

## Ebay.ebay_sales
Sales transactions from eBay stores. Key columns:

- **date**: Transaction date.
- **brand**: Product brand.
- **Custom_label**: SAME AS OFFICIAL_SKU
- **Item_title**: Product name.
- **sales**: Revenue generated.
- **units**: Number of units sold.
  
---

## COGS.cin7_stockvaluation_cogs_output
Comprehensive Cost of Goods Sold (COGS) data sorted by the most recent information available PER UNIT. 

- **months_year**: The month and year of the data record.
- **brand**: The brand associated with the product.
- **official_sku**: The stock-keeping unit identifier for the product.
- **Country**: The country where the cost data is relevant.
- **cogs**: The calculated cost of goods sold for the product.
---

## Etsy.etsy_sales
Sales records from Etsy. Key columns:

- **date**: Sale date.
- **brand**: Product brand.
- **country**: Country 
- **sales**: Revenue.
- **sku** SKU. 
- **quantity**: Units sold.

---

## shopify.shopify_orders
Transactional data from Shopify orders. Key columns:

- **process_date**: Order processing date.
- **official_sku**: Unique order identifier.
- **country**: Customer location.
- **gross_sales**: Revenue before refunds.
- **promo_amount**: promotion amount 

---

## shopify.shopify_refunds
Refund transactions from Shopify. Key columns:

- **official_sku**: Associated order identifier.
- **refund_date**: Refund processing date.
- **brand**: Product brand.
- **amount**: Refund value.

---

## amazon_orders.amz_returns_report
Amazon product returns. Key columns:

- **order_date**: Order date.
- **official_sku**: product identifier. 
- **return_date**: Return date.
- **reason**: Reason for return.
- **return_quantity**: Quantity returned.
- **reason**: reason for return

---

## amazon_bsr_and_other.bsr_weekly
Weekly Best Seller Rank (BSR) data for Amazon products. Key columns:

- **start_of_week**: Week start date.
- **brand**: Product brand.
- **avg_bsr**: Average Best Seller Rank.

---

## shopify.shopify_customers_orders_data
Customer-specific order data from Shopify. Key columns:

- **month**: Order month.
- **country** country.
- **brand**: Product brand.
- **customer_life** new or old customer.
- **customer_country**: Customer location.
- **gross_sales**: Total sales.
- **customer_name**
- **verified_email** 
---

## amazon_advertising.amz_ads_metrics_per_campaign_type
This dataset contains advertising metrics for Amazon campaigns, organized by campaign type, brand, and country. Key columns include:

- **date**: Tracking advertising performance over time.
- **campaign_type**: Type of Amazon ad campaign (e.g., Sponsored Products).
- **brand**: Brand associated with the campaign.
- **country**: Geographic region where the campaign was run.
- **channel**: Platform where the campaign was executed.
- **official_sky**: Specific product SKU targeted by the campaign.
- **ppc_spend**: Amount spent on pay-per-click advertising.
- **ppc_sales**: Revenue generated from pay-per-click ads.

---

## google_ads.gads_campaign_report
This dataset reports performance metrics for Google Ads campaigns run through Shopify. Key columns include:

- **date**: Date of campaign performance.
- **brand**: Brand associated with the campaign.
- **country**: Geographic region where the ad was shown.
- **channel**: Platform the ad was shown on (e.g., Shopify).
- **campaign name**: Name of the Google Ads campaign.
- **spend**: Total money spent on the ad campaign.
- **conversions_value**: Value generated from conversions.
- **clicks**: Number of clicks generated from the ad.
- **impressions**: Number of times the ad was viewed.
- **conversions**: Number of successful conversions generated by the ad.

---

## non_channels_ppc.non_channels_ppcmetrics
This dataset contains pay-per-click (PPC) advertising metrics segmented by week, brand, and channel. Key columns include:

- **Month**: The month of ad performance.
- **Year_US_Week**: Year and U.S. week number.
- **US_Week**: Week number in the U.S. calendar.
- **brand**: Brand running the PPC campaign.
- **country**: Geographic region where the campaign was executed.
- **channel**: Platform where the campaign ran (e.g., Shopify).
- **campaign_name**: Name of the PPC campaign.
- **ppc_spend**: Money spent on the PPC campaign.
- **ppc_sales**: Sales generated from the PPC campaign.
- **ppc_clicks**: Number of clicks generated from the PPC ad.
- **ppc_impressions**: Number of times the PPC ad was shown.
- **ppc_orders**: Number of orders resulting from the PPC campaign.
--- 


## Successful Plans
### Get the name of a particular SKU
{
  "Plan": {
    "1": {
      "Request": "Get the name associated with the SKU BC-001",
      "DataNeeded": "AAA_General_Core_Tables.official_sku_database",
      "RequiresCode": "False",
      "RequiresQuery": "True",
      "DesiredOutput": "product_name"
    }
  }
}


### Get the top SKU this month
{
    "Plan": {
        "1": {
            "Request": "Extract all sales data by SKU for this month.",
            "DataNeeded": "amazon_orders.amz_orders_wbr",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "purchase_date_PST, official_sku, gross_sales_not_including_vat, ordered_quantity"
        },
        "2": {
            "Request": "Extract all sales data by SKU for this month.",
            "DataNeeded": "walmart_operand.walmart_orders",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, official_sku, gross_sales, ordered_quantity"
        },
        "3": {
            "Request": "Extract all sales data by SKU for this month.",
            "DataNeeded": "Ebay.ebay_sales",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, Custom_label, sales, units"
        },
        "4": {
            "Request": "Extract all sales data by SKU for this month.",
            "DataNeeded": "shopify.shopify_orders",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "process_date, official_sku, gross_sales, promo_amount"
        },
        "5": {
            "Request": "Aggregate sales data from Amazon, Walmart, eBay, and Shopify to identify the best performing SKU this month.",
            "DataNeeded": "1, 2, 3, 4",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "Best performing SKU by sales revenue and units sold"
        },
        "6": {
            "Request": "Retrieve the product name for the best performing SKU identified.",
            "DataNeeded": "AAA_General_Core_Tables.official_sku_database, 5",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "product_name"
        }
    }
}


### Chart sales for a particular SKU
**NOTE** You must retrieve sales data from EVERY RELEVANT DATASET that contains orders information. You MUST BE THOROUGH.
{
    "Plan": {
        "1": {
            "Request": "Extract all sales data for SKU 'BC-001' from Amazon over the last year, including ordered quantity and sales revenue.",
            "DataNeeded": "amazon_orders.amz_orders_wbr",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "purchase_date_PST, official_sku, ordered_quantity, gross_sales_not_including_vat"
        },
        "2": {
            "Request": "Extract all sales data for SKU 'BC-001' from Walmart over the last year, including ordered quantity and sales revenue.",
            "DataNeeded": "walmart_operand.walmart_orders",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, official_sku, ordered_quantity, gross_sales"
        },
        "3": {
            "Request": "Extract all sales data for SKU 'BC-001' from eBay over the last year, including ordered quantity and sales revenue.",
            "DataNeeded": "Ebay.ebay_sales",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, Custom_label, units, sales"
        },
        "4": {
            "Request": "Extract all sales data for SKU 'BC-001' from Shopify over the last year, including ordered quantity and sales revenue.",
            "DataNeeded": "shopify.shopify_orders",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "process_date, official_sku, gross_sales, promo_amount"
        },
        "5": {
            "Request": "Aggregate sales data from Amazon, Walmart, eBay, and Shopify for SKU 'BC-001' over the last year and plot sales over time.",
            "DataNeeded": "1, 2, 3, 4",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "Chart of sales revenue and ordered quantity over time"
        }
    }
}


### Profitability for a particular SKU
{
    "Plan": {
        "1": {
            "Request": "Retrieve all sales data for product BKG-003 from Amazon, including gross sales and ordered quantity.",
            "DataNeeded": "amazon_orders.amz_orders_wbr",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "purchase_date_PST, official_sku, ordered_quantity, gross_sales_not_including_vat"
        },
        "2": {
            "Request": "Retrieve all sales data for product BKG-003 from Walmart, including gross sales and ordered quantity.",
            "DataNeeded": "walmart_operand.walmart_orders",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, official_sku, ordered_quantity, gross_sales"
        },
        "3": {
            "Request": "Retrieve all sales data for product BKG-003 from eBay, including sales revenue and units sold.",
            "DataNeeded": "Ebay.ebay_sales",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, Custom_label, units, sales"
        },
        "4": {
            "Request": "Retrieve all sales data for product BKG-003 from Shopify, including gross sales and ordered quantity.",
            "DataNeeded": "shopify.shopify_orders",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "process_date, official_sku, ordered_quantity, gross_sales"
        },
        "5": {
            "Request": "Retrieve all sales data for product BKG-003 from Etsy, including sales revenue and quantity sold.",
            "DataNeeded": "Etsy.etsy_sales",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, sku, quantity, sales"
        },
        "6": {
            "Request": "Retrieve the cost of goods sold (COGS) per unit for product BKG-003.",
            "DataNeeded": "COGS.cin7_stockvaluation_cogs_output",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "official_sku, cogs"
        },
        "7": {
            "Request": "Calculate the total revenue for product BKG-003 by aggregating sales data from all channels and the total quantity sold.",
            "DataNeeded": "1, 2, 3, 4, 5",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "Total revenue and total quantity sold for BKG-003"
        },
        "8": {
            "Request": "Calculate the total cost for product BKG-003 by multiplying the COGS per unit by the total quantity sold.",
            "DataNeeded": "6, 7",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "Total cost for BKG-003"
        },
        "9": {
            "Request": "Calculate the profit for product BKG-003 by subtracting the total cost from the total revenue.",
            "DataNeeded": "7, 8",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "Profit for BKG-003"
        }
    }
}


### Total Profit in a Month 
{
    "Plan": {
        "1": {
            "Request": "Retrieve all sales data for September 2024 from Amazon, including gross sales and ordered quantity.",
            "DataNeeded": "amazon_orders.amz_orders_wbr",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "purchase_date_PST, official_sku, ordered_quantity, gross_sales_not_including_vat"
        },
        "2": {
            "Request": "Retrieve all sales data for September 2024 from Walmart, including gross sales and ordered quantity.",
            "DataNeeded": "walmart_operand.walmart_orders",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, official_sku, ordered_quantity, gross_sales"
        },
        "3": {
            "Request": "Retrieve all sales data for September 2024 from eBay, including sales revenue and units sold.",
            "DataNeeded": "Ebay.ebay_sales",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, Custom_label, units, sales"
        },
        "4": {
            "Request": "Retrieve all sales data for September 2024 from Shopify, including gross sales and ordered quantity.",
            "DataNeeded": "shopify.shopify_orders",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "process_date, official_sku, ordered_quantity, gross_sales"
        },
        "5": {
            "Request": "Retrieve all sales data for September 2024 from Etsy, including sales revenue and quantity sold.",
            "DataNeeded": "Etsy.etsy_sales",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, sku, quantity, sales"
        },
        "6": {
            "Request": "Retrieve most recent cost of goods sold (COGS) per unit for all products.",
            "DataNeeded": "COGS.cin7_stockvaluation_cogs_output",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "official_sku, cogs"
        },
        "7": {
            "Request": "Calculate the total revenue for September 2024 by aggregating sales data from all channels.",
            "DataNeeded": "1, 2, 3, 4, 5",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "Total revenue for September 2024"
        },
        "8": {
            "Request": "Calculate the total cost for September 2024 by multiplying the COGS per unit by the total quantity sold per SKU.",
            "DataNeeded": "1, 2, 3, 4, 5, 6",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "Total cost for September 2024"
        },
        "9": {
            "Request": "Calculate the total profit for September 2024 by subtracting the total cost from the total revenue.",
            "DataNeeded": "7, 8",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "Total profit for September 2024"
        }
    }
}



### Return Rate of Particular SKU:

{
    "Plan": {
        "1": {
            "Request": "Retrieve all order data for SKU 'BKG-000' from Amazon over the past year, including ordered quantity.",
            "DataNeeded": "amazon_orders.amz_orders_wbr",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "purchase_date_PST, official_sku, ordered_quantity"
        },
        "2": {
            "Request": "Retrieve all return data for SKU 'BKG-000' from Amazon over the past year, including return quantity.",
            "DataNeeded": "amazon_orders.amz_returns_report",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "return_date, official_sku, return_quantity"
        },
        "3": {
            "Request": "Retrieve all order data for SKU 'BKG-000' from Walmart over the past year, including ordered quantity.",
            "DataNeeded": "walmart_operand.walmart_orders",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, official_sku, ordered_quantity"
        },
        "4": {
            "Request": "Retrieve all return data for SKU 'BKG-000' from Walmart over the past year, including return quantity.",
            "DataNeeded": "walmart_operand.walmart_returns",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "return_date, official_sku, returnreason, return_quantity"
        },
        "5": {
            "Request": "Retrieve all order data for SKU 'BKG-000' from Shopify over the past year, including ordered quantity.",
            "DataNeeded": "shopify.shopify_orders",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "process_date, official_sku, ordered_quantity"
        },
        "6": {
            "Request": "Retrieve all refund data for SKU 'BKG-000' from Shopify over the past year, including refund quantity.",
            "DataNeeded": "shopify.shopify_refunds",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "refund_date, official_sku, amount (representing refunded units)"
        },
        "7": {
            "Request": "Calculate the total ordered quantity for SKU 'BKG-000' from all channels over the past year including cancelled/refunded orders.",
            "DataNeeded": "1, 3, 5",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "Total ordered quantity for SKU 'BKG-000'"
        },
        "8": {
            "Request": "Calculate the total returned quantity for SKU 'BKG-000' from all channels over the past year.",
            "DataNeeded": "2, 4, 6",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "Total returned quantity for SKU 'BKG-000'"
        },
        "9": {
            "Request": "Calculate the return rate for SKU 'BKG-000' by dividing the total returned quantity by the total ordered quantity.",
            "DataNeeded": "7, 8",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "Return rate for SKU 'BKG-000'"
        }
    }
}


### Top 10 Most Profitable Products and Any Unprofitable: 
{
    "Plan": {
        "1": {
            "Request": "Retrieve all sales data for 2024 from Amazon, including gross sales and ordered quantity.",
            "DataNeeded": "amazon_orders.amz_orders_wbr",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "purchase_date_PST, official_sku, ordered_quantity, gross_sales_not_including_vat"
        },
        "2": {
            "Request": "Retrieve all sales data for 2024 from Walmart, including gross sales and ordered quantity.",
            "DataNeeded": "walmart_operand.walmart_orders",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, official_sku, ordered_quantity, gross_sales"
        },
        "3": {
            "Request": "Retrieve all sales data for 2024 from eBay, including sales revenue and units sold.",
            "DataNeeded": "Ebay.ebay_sales",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, Custom_label, units, sales"
        },
        "4": {
            "Request": "Retrieve all sales data for 2024 from Shopify, including gross sales and ordered quantity.",
            "DataNeeded": "shopify.shopify_orders",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "process_date, official_sku, ordered_quantity, gross_sales"
        },
        "5": {
            "Request": "Retrieve all sales data for 2024 from Etsy, including sales revenue and quantity sold.",
            "DataNeeded": "Etsy.etsy_sales",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, sku, quantity, sales"
        },
        "6": {
            "Request": "Retrieve the most recent cost of goods sold (COGS) per unit for all products.",
            "DataNeeded": "COGS.cin7_stockvaluation_cogs_output",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "official_sku, cogs"
        },
        "7": {
            "Request": "Calculate the total revenue and quantity sold for each SKU in 2024 by aggregating sales data from all channels.",
            "DataNeeded": "1, 2, 3, 4, 5",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "Total revenue and total quantity sold per SKU"
        },
        "8": {
            "Request": "Calculate the total cost for each SKU in 2024 by multiplying the COGS per unit by the total quantity sold.",
            "DataNeeded": "6, 7",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "Total cost per SKU"
        },
        "9": {
            "Request": "Calculate the profit for each SKU in 2024 by subtracting the total cost from the total revenue.",
            "DataNeeded": "7, 8",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "Profit per SKU"
        },
        "10": {
            "Request": "Identify the top 10 most profitable products based on the calculated profits.",
            "DataNeeded": "9",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "Top 10 most profitable SKUs with their profits"
        },
        "11": {
            "Request": "Highlight any products that are unprofitable and suggest actions.",
            "DataNeeded": "9",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "List of unprofitable SKUs with suggested actions"
        }
    }
}


### Calculate the lifetime value (LTV) of our top 100 customers, including their average order value, total number of orders, purchase frequency, and total revenue generated. FYI, the only customer data we have is in Shopify. Present this in a ranked table
{
  "Plan": {
    "1": {
      "Request": "Retrieve all customer order data from Shopify, including customer names, verified emails, and gross sales.",
      "DataNeeded": "shopify.shopify_customers_orders_data",
      "PaginationNeeded": "True",
      "RequiresCode": "False",
      "RequiresQuery": "True",
      "DesiredOutput": "customer_name, verified_email, gross_sales"
    },
    "2": {
      "Request": "Calculate the total revenue generated by each customer by summing their gross sales.",
      "DataNeeded": "1",
      "PaginationNeeded": "False",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "customer_name, total_revenue"
    },
    "3": {
      "Request": "Identify the top 100 customers based on total revenue generated.",
      "DataNeeded": "2",
      "PaginationNeeded": "False",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "top_100_customers"
    },
    "4": {
      "Request": "Calculate the total number of orders for each of the top 100 customers.",
      "DataNeeded": "1, 3",
      "PaginationNeeded": "False",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "customer_name, total_orders"
    },
    "5": {
      "Request": "Calculate the average order value for each of the top 100 customers by dividing total revenue by the total number of orders.",
      "DataNeeded": "2, 4",
      "PaginationNeeded": "False",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "customer_name, avg_order_value"
    },
    "6": {
      "Request": "Calculate the purchase frequency for each of the top 100 customers by dividing the total number of orders by the number of unique months they made purchases.",
      "DataNeeded": "1, 3",
      "PaginationNeeded": "False",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "customer_name, purchase_frequency"
    },
    "7": {
      "Request": "Compile a ranked table of the top 100 customers including their total revenue, total number of orders, average order value, and purchase frequency.",
      "DataNeeded": "2, 4, 5, 6",
      "PaginationNeeded": "False",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "ranked_table"
    }
  }
}


### Popular Product Variation/Extension of SKU for Month: 
{
  "Plan": {
    "1": {
      "Request": "Extract all sales data for SKU 'LB-006' from Amazon for October 2023, including ordered quantity and sales revenue.",
      "DataNeeded": "amazon_orders.amz_orders_wbr",
      "PaginationNeeded": "False",
      "RequiresCode": "False",
      "RequiresQuery": "True",
      "DesiredOutput": "purchase_date_PST, official_sku, ordered_quantity, gross_sales_not_including_vat"
    },
    "2": {
      "Request": "Extract all sales data for SKU 'LB-006' from Walmart for October 2023, including ordered quantity and sales revenue.",
      "DataNeeded": "walmart_operand.walmart_orders",
      "PaginationNeeded": "False",
      "RequiresCode": "False",
      "RequiresQuery": "True",
      "DesiredOutput": "date, official_sku, ordered_quantity, gross_sales"
    },
    "3": {
      "Request": "Extract all sales data for SKU 'LB-006' from eBay for October 2023, including units sold and sales revenue.",
      "DataNeeded": "Ebay.ebay_sales",
      "PaginationNeeded": "False",
      "RequiresCode": "False",
      "RequiresQuery": "True",
      "DesiredOutput": "date, Custom_label, units, sales"
    },
    "4": {
      "Request": "Extract all sales data for SKU 'LB-006' from Shopify for October 2023, including ordered quantity and sales revenue.",
      "DataNeeded": "shopify.shopify_orders",
      "PaginationNeeded": "False",
      "RequiresCode": "False",
      "RequiresQuery": "True",
      "DesiredOutput": "process_date, official_sku, ordered_quantity, gross_sales"
    },
    "5": {
      "Request": "Extract all sales data for SKU 'LB-006' from Etsy for October 2023, including quantity sold and sales revenue.",
      "DataNeeded": "Etsy.etsy_sales",
      "PaginationNeeded": "False",
      "RequiresCode": "False",
      "RequiresQuery": "True",
      "DesiredOutput": "date, sku, quantity, sales"
    },
    "6": {
      "Request": "Aggregate sales data from Amazon, Walmart, eBay, Shopify, and Etsy to identify the most popular variation of SKU 'LB-006' in October 2023.",
      "DataNeeded": "1, 2, 3, 4, 5",
      "PaginationNeeded": "False",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "most_popular_variation"
    }
  }
}



### Chart Product Extensions/Variations for SKU: 
{
    "Plan": {
        "1": {
            "Request": "Extract all sales data for product extensions of SKU 'LB-006' from Amazon for the year 2024, including ordered quantity and sales revenue.",
            "DataNeeded": "amazon_orders.amz_orders_wbr",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "purchase_date_PST, official_sku, ordered_quantity, gross_sales_not_including_vat"
        },
        "2": {
            "Request": "Extract all sales data for product extensions of SKU 'LB-006' from Walmart for the year 2024, including ordered quantity and sales revenue.",
            "DataNeeded": "walmart_operand.walmart_orders",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, official_sku, ordered_quantity, gross_sales"
        },
        "3": {
            "Request": "Extract all sales data for product extensions of SKU 'LB-006' from eBay for the year 2024, including ordered quantity and sales revenue.",
            "DataNeeded": "Ebay.ebay_sales",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, Custom_label, units, sales"
        },
        "4": {
            "Request": "Extract all sales data for product extensions of SKU 'LB-006' from Shopify for the year 2024, including ordered quantity and sales revenue.",
            "DataNeeded": "shopify.shopify_orders",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "process_date, official_sku, ordered_quantity, gross_sales"
        },
        "5": {
            "Request": "Extract all sales data for product extensions of SKU 'LB-006' from Etsy for the year 2024, including ordered quantity and sales revenue.",
            "DataNeeded": "Etsy.etsy_sales",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, sku, quantity, sales"
        },
        "6": {
            "Request": "Aggregate sales data from Amazon, Walmart, eBay, Shopify, and Etsy for product extensions of SKU 'LB-006' and divide by month, then chart over 2024.",
            "DataNeeded": "1, 2, 3, 4, 5",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "Monthly chart of total sales and ordered quantity for all extensions of SKU 'LB-006'"
        }
    }
}



### Group Sales By Reigon/Country: 
{
    "Plan": {
        "1": {
            "Request": "Retrieve all order data for October 2024 from Amazon, including purchase date and country.",
            "DataNeeded": "amazon_orders.amz_orders_wbr",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "purchase_date_PST, country, ordered_quantity"
        },
        "2": {
            "Request": "Retrieve all order data for October 2024 from Walmart, including order date and country.",
            "DataNeeded": "walmart_operand.walmart_orders",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, country, ordered_quantity"
        },
        "3": {
            "Request": "Retrieve all order data for October 2024 from eBay, including transaction date and country.",
            "DataNeeded": "Ebay.ebay_sales",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, country, units"
        },
        "4": {
            "Request": "Retrieve all order data for October 2024 from Shopify, including process date and country.",
            "DataNeeded": "shopify.shopify_orders",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "process_date, country, ordered_quantity"
        },
        "5": {
            "Request": "Retrieve all order data for October 2024 from Etsy, including sale date and country.",
            "DataNeeded": "Etsy.etsy_sales",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, country, quantity"
        },
        "6": {
            "Request": "Aggregate the number of orders from each region for October 2024 across all sales channels.",
            "DataNeeded": "1, 2, 3, 4, 5",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "region, total_orders"
        }
    }
}

### Plot the top 5 product extensions in one chart in 2024
{
    "Plan": {
        "1": {
            "Request": "Extract all sales data for product extensions from Amazon for the year 2024, including ordered quantity and sales revenue.",
            "DataNeeded": "amazon_orders.amz_orders_wbr",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "purchase_date_PST, official_sku, ordered_quantity, gross_sales_not_including_vat"
        },
        "2": {
            "Request": "Extract all sales data for product extensions from Walmart for the year 2024, including ordered quantity and sales revenue.",
            "DataNeeded": "walmart_operand.walmart_orders",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, official_sku, ordered_quantity, gross_sales"
        },
        "3": {
            "Request": "Extract all sales data for product extensions from eBay for the year 2024, including ordered quantity and sales revenue.",
            "DataNeeded": "Ebay.ebay_sales",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, Custom_label, units, sales"
        },
        "4": {
            "Request": "Extract all sales data for product extensions from Shopify for the year 2024, including ordered quantity and sales revenue.",
            "DataNeeded": "shopify.shopify_orders",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "process_date, official_sku, ordered_quantity, gross_sales"
        },
        "5": {
            "Request": "Extract all sales data for product extensions from Etsy for the year 2024, including ordered quantity and sales revenue.",
            "DataNeeded": "Etsy.etsy_sales",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, sku, quantity, sales"
        },
        "6": {
            "Request": "Aggregate sales data from Amazon, Walmart, eBay, Shopify, and Etsy to identify the top 5 product extensions based on total sales in 2024.",
            "DataNeeded": "1, 2, 3, 4, 5",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "top_5_product_extensions, month, sales"
        },
        "7": {
            "Request": "Plot the top 5 product extensions in one chart, divided by time and plotted over 2024.",
            "DataNeeded": "6",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "False",
            "DesiredOutput": "Chart of top 5 product extensions over time in 2024"
        }
    }
}


### Get Top 2 SKUs and Plot Over a Year
{
    "Plan": {
        "1": {
            "Request": "Extract all sales data by SKU for the year 2024 from Amazon, including ordered quantity and sales revenue.",
            "DataNeeded": "amazon_orders.amz_orders_wbr",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "purchase_date_PST, official_sku, ordered_quantity, gross_sales_not_including_vat"
        },
        "2": {
            "Request": "Extract all sales data by SKU for the year 2024 from Walmart, including ordered quantity and sales revenue.",
            "DataNeeded": "walmart_operand.walmart_orders",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, official_sku, ordered_quantity, gross_sales"
        },
        "3": {
            "Request": "Extract all sales data by SKU for the year 2024 from eBay, including ordered quantity and sales revenue.",
            "DataNeeded": "Ebay.ebay_sales",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, Custom_label, units, sales"
        },
        "4": {
            "Request": "Extract all sales data by SKU for the year 2024 from Shopify, including ordered quantity and sales revenue.",
            "DataNeeded": "shopify.shopify_orders",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "process_date, official_sku, ordered_quantity, gross_sales"
        },
        "5": {
            "Request": "Aggregate sales data from Amazon, Walmart, eBay, and Shopify to identify the top 2 SKUs for the year 2024 based on total sales revenue.",
            "DataNeeded": "1, 2, 3, 4",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "top_2_skus_by_revenue"
        },
        "6": {
            "Request": "Retrieve the product names for the top 2 SKUs identified.",
            "DataNeeded": "AAA_General_Core_Tables.official_sku_database, 5",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "sku, product_name"
        },
        "7": {
            "Request": "Plot the sales data over time for the top 2 SKUs identified, divided by time and plotted over time.",
            "DataNeeded": "1, 2, 3, 4, 5",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "time_series_chart_top_2_skus"
        }
    }
}



### Get the top 50 SKUs on a downward trajectory
{
    "Plan": {
        "1": {
            "Request": "Extract monthly sales data by SKU for each of the last three months (July, August, September 2024) from Amazon, including ordered quantity and order dates.",
            "DataNeeded": "amazon_orders.amz_orders_wbr",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "purchase_date_PST, official_sku, ordered_quantity"
        },
        "2": {
            "Request": "Extract sales data by SKU for the last three months (July, August, September 2024) from Walmart, including ordered quantity and order dates.",
            "DataNeeded": "walmart_operand.walmart_orders",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, official_sku, ordered_quantity"
        },
        "3": {
            "Request": "Extract sales data by SKU for the last three months (July, August, September 2024) from eBay, including ordered quantity and order dates.",
            "DataNeeded": "Ebay.ebay_sales",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, Custom_label, units"
        },
        "4": {
            "Request": "Extract sales data by SKU for the last three months (July, August, September 2024) from Shopify, including ordered quantity and order dates.",
            "DataNeeded": "shopify.shopify_orders",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "process_date, official_sku, ordered_quantity"
        },
        "5": {
            "Request": "Aggregate sales data from Amazon, Walmart, eBay, and Shopify to identify SKUs with decreasing sales over the last three months (July, August, September 2024).",
            "DataNeeded": "1, 2, 3, 4",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "skus_with_declining_sales"
        },
        "6": {
            "Request": "Identify the top 50 SKUs on a downward trajectory based on the aggregated sales data.",
            "DataNeeded": "5",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "top_50_declining_skus"
        },
        "7": {
            "Request": "Retrieve the full names of the top 50 SKUs identified as being on a downward trajectory.",
            "DataNeeded": "AAA_General_Core_Tables.official_sku_database, 6",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "sku, product_name"
        }
    }
}


### Average CPC and Conversion Rate by Channel
{
    "Plan": {
        "1": {
            "Request": "Retrieve PPC advertising metrics including PPC Spend, PPC Clicks, and PPC Orders for all channels.",
            "DataNeeded": "non_channels_ppc.non_channels_ppcmetrics",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "Month, channel, ppc_spend, ppc_clicks, ppc_orders"
        },
        "2": {
            "Request": "Retrieve Google Ads campaign data including Spend, Clicks, and Conversions for all channels.",
            "DataNeeded": "google_ads.gads_campaign_report",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, channel, spend, clicks, conversions"
        },
        "3": {
            "Request": "Retrieve Amazon advertising metrics including PPC Spend, PPC Sales, and PPC Clicks.",
            "DataNeeded": "amazon_advertising.amz_ads_metrics_per_campaign_type",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True",
            "DesiredOutput": "date, channel, ppc_spend, ppc_sales, ppc_clicks"
        },
        "4": {
            "Request": "Calculate the average CPC and conversion rate for each channel.",
            "DataNeeded": "1, 2, 3",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False",
            "DesiredOutput": "channel, avg_cpc, conversion_rate"
        },
        "5": {
            "Request": "Analyze the calculated average CPC and conversion rates to identify optimization opportunities.",
            "DataNeeded": "4",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "False",
            "DesiredOutput": "channel_optimization_recommendations"
        }
    }
}

