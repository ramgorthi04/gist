Date last edited: 10/21/2024 at 2:29pm ET


## Available datasets and tables, in the format dataset.table:

## amazon_orders.amz_orders_wbr
Data on Amazon orders, covering order dates, locations, channels, products, and financial details. Key columns:

- **purchase_date_PST**: Date of purchase in PST for timing analysis.
- **country**: Geographic insights, supporting regional sales analysis.
- **channel**: Sales channel for identifying market reach (e.g., Amazon, eBay).
- **account**: Differentiates orders by Amazon account for account-specific analysis.
- **brand**: Provides insights into brand performance.
- **official_sku**: Product tracking through official SKU for detailed inventory and product analysis.
- **asin**: Amazon Standard Identification Number (ASIN) for tracking individual products.
- **order_status**: Order status (e.g., Shipped, Delivered) to monitor fulfillment and identify delays.
- **amazon_order_id**: Unique identifier for each order.
- **ordered_quantity**: Total quantity of each product ordered, enabling sales volume tracking.
- **gross_sales_including_vat**: Total sales value including VAT for revenue analysis.

**Potential Insights**:
- Analyze geographic sales distribution, brand performance, and channel effectiveness.
- Ensure tax compliance and calculate revenue with and without VAT.
- Track order statuses for logistics and customer service improvements.

---

## AAA_General_Core_Tables.official_sku_database
A product catalog covering various brands, countries, and channels. Key columns:

- **Brand**: Analyze brand performance.
- **Country**: Geographic distribution.
- **Channel**: Sales channel analysis.
- **Product Name**: Product-level insights.
- **Official SKU/ASIN**: Track product listings.

**Potential Insights**:
- Analyze pricing trends and channel performance.
- Inventory management and market strategy.

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

**Potential Insights**:
- Evaluate product performance and inventory management.
- Analyze customer preferences and operational efficiency.

---

## shopify.shopify_products
Product listings from Shopify stores. Key columns:

- **Date**: Record date.
- **Store**: Shopify store.
- **Brand**: Product brand.
- **Official SKU**: Product identifier.
- **Price**: Product pricing.
- **Inventory Quantity**: Stock levels.

**Potential Insights**:
- Analyze inventory, pricing, and brand performance.
- Track product lifecycles and sales trends.

---

## walmart_operand.walmart_orders
Transactional data from Walmart orders. Key columns:

- **Date**: Order date.
- **Brand**: Brand performance.
- **Country**: Market insights.
- **SKU**: Product identifier.
- **Gross Sales**: Revenue before refunds.

**Potential Insights**:
- Analyze sales trends, brand performance, and customer behavior.
- Optimize fulfillment methods and manage refunds.

---

## walmart_operand.walmart_customer_reviews
Customer reviews from Walmart. Key columns:

- **Date**: Review date.
- **Brand**: Product brand.
- **Country**: Market region.
- **SKU**: Product identifier.
- **Average_rating**: Review ratings.

**Potential Insights**:
- Assess product popularity and brand performance.
- Identify customer satisfaction trends.

---

## walmart_operand.walmart_returns
Product return data from Walmart. Key columns:

- **return_date**: Return date.
- **brand**: Product brand.
- **returnreason**: Reason for return.

**Potential Insights**:
- Identify trends in returns and brand performance.
- Optimize return processes and customer satisfaction.

---

## walmart_operand.walmart_inventory
Walmart inventory data over time. Key columns:

- **Date**: Record date.
- **SKU**: Product identifier.
- **input_qty**: Quantity added to inventory.
- **availtosell_qty**: Available stock.

**Potential Insights**:
- Monitor stock levels and sales activity.
- Forecast demand and optimize supply chain.

---

## Ebay.ebay_sales
Sales transactions from eBay stores. Key columns:

- **Date**: Transaction date.
- **Brand**: Product brand.
- **official_sku**: Official SKU.
- **Item Title**: Product name.
- **Sales**: Revenue generated.
- **Units**: Number of units sold.

**Potential Insights**:
- Analyze sales trends and product performance.
- Optimize inventory and pricing strategies.

---

## COGS.cin7_stockvaluation_cogs_output
Comprehensive Cost of Goods Sold (COGS) data sorted by the most recent information available PER UNIT. 

- **months_year**: The month and year of the data record.
- **date**: The specific date of the COGS entry.
- **brand**: The brand associated with the product.
- **official_sku**: The stock-keeping unit identifier for the product.
- **country**: The country where the cost data is relevant.
- **cogs**: The calculated cost of goods sold for the product.

**Potential Insights**:
- Track COGS trends over time for recent data.
- Assess brand-specific cost performance by region.
- Identify opportunities to reduce costs across supply chains.
---

## Etsy.etsy_sales
Sales records from Etsy. Key columns:

- **Date**: Sale date.
- **Brand**: Product brand.
- **Sales**: Revenue.
- **Quantity**: Units sold.

**Potential Insights**:
- Analyze sales trends, customer behavior, and geographical performance.
- Optimize inventory and marketing strategies.

---

## shopify.shopify_orders
Transactional data from Shopify orders. Key columns:

- **Process Date**: Order processing date.
- **Order ID**: Unique order identifier.
- **Country**: Customer location.
- **Gross Sales**: Revenue before refunds.

**Potential Insights**:
- Track sales, customer preferences, and product performance.
- Optimize order fulfillment and pricing strategies.

---

## shopify.shopify_refunds
Refund transactions from Shopify. Key columns:

- **order_id**: Associated order identifier.
- **refund_date**: Refund processing date.
- **brand**: Product brand.
- **amount**: Refund value.

**Potential Insights**:
- Analyze refund trends and financial impact.
- Identify product or service issues causing returns.

---

## amazon_orders.amz_returns_report
Amazon product returns. Key columns:

- **order_date**: Order date.
- **return_date**: Return date.
- **reason**: Reason for return.
- **return_quantity**: Quantity returned.

**Potential Insights**:
- Assess return reasons and product performance.
- Optimize customer service and logistics.

---

## amazon_bsr_and_other.bsr_weekly
Weekly Best Seller Rank (BSR) data for Amazon products. Key columns:

- **start_of_week**: Week start date.
- **brand**: Product brand.
- **avg_bsr**: Average Best Seller Rank.

**Potential Insights**:
- Track product performance and seasonal trends.
- Compare brands and identify market opportunities.

---

## shopify.shopify_customers_orders_data
Customer order data from Shopify. Key columns:

- **month**: Order month.
- **brand**: Product brand.
- **customer_country**: Customer location.
- **gross_sales**: Total sales.
- **customer_name**
- **verified_email**

**Potential Insights**:
- Analyze customer behavior and sales trends.
- Optimize marketing and sales strategies.

---

## amazon_advertising.amz_ads_metrics_per_campaign_type
This dataset contains advertising metrics for Amazon campaigns, organized by campaign type, brand, and country. Key columns include:

- **Date**: Tracking advertising performance over time.
- **Campaign Type**: Type of Amazon ad campaign (e.g., Sponsored Products).
- **Brand**: Brand associated with the campaign.
- **Country**: Geographic region where the campaign was run.
- **Channel**: Platform where the campaign was executed.
- **Official SKU**: Specific product SKU targeted by the campaign.
- **PPC Spend**: Amount spent on pay-per-click advertising.
- **PPC Sales**: Revenue generated from pay-per-click ads.

**Potential Insights**:
- Analyze the effectiveness of ad campaigns across different brands and countries.
- Correlate ad spend with revenue generation and optimize budget allocation.
- Identify underperforming campaigns and adjust strategies accordingly.

---

## google_ads.gads_campaign_report
This dataset reports performance metrics for Google Ads campaigns run through Shopify. Key columns include:

- **Date**: Date of campaign performance.
- **Brand**: Brand associated with the campaign.
- **Country**: Geographic region where the ad was shown.
- **Channel**: Platform the ad was shown on (e.g., Shopify).
- **Campaign Name**: Name of the Google Ads campaign.
- **Spend**: Total money spent on the ad campaign.
- **Conversions Value**: Value generated from conversions.
- **Clicks**: Number of clicks generated from the ad.
- **Impressions**: Number of times the ad was viewed.
- **Conversions**: Number of successful conversions generated by the ad.

**Potential Insights**:
- Measure campaign success by analyzing spend vs. conversion rates.
- Optimize Google Ads performance by evaluating click-through rates and conversion values.
- Identify geographic regions where campaigns are most effective.

---

## non_channels_ppc.non_channels_ppcmetrics
This dataset contains pay-per-click (PPC) advertising metrics segmented by week, brand, and channel. Key columns include:

- **Month**: The month of ad performance.
- **Year_US_Week**: Year and U.S. week number.
- **US_Week**: Week number in the U.S. calendar.
- **Brand**: Brand running the PPC campaign.
- **Country**: Geographic region where the campaign was executed.
- **Channel**: Platform where the campaign ran (e.g., Shopify).
- **Campaign Name**: Name of the PPC campaign.
- **PPC Spend**: Money spent on the PPC campaign.
- **PPC Sales**: Sales generated from the PPC campaign.
- **PPC Clicks**: Number of clicks generated from the PPC ad.
- **PPC Impressions**: Number of times the PPC ad was shown.
- **PPC Orders**: Number of orders resulting from the PPC campaign.

**Potential Insights**:
- Compare week-to-week PPC performance for different brands.
- Correlate PPC spend with sales and identify high-ROI campaigns.
- Track performance by country and channel to optimize targeting strategies.

--- 

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

### Get the top SKU this month
{
    "Plan": {
        "1": {
            "Request": "Extract all sales data by SKU for this month.",
            "DataNeeded": "amazon_orders.amz_orders_wbr",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "2": {
            "Request": "Extract all sales data by SKU for this month.",
            "DataNeeded": "walmart_operand.walmart_orders",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "3": {
            "Request": "Extract all sales data by SKU for this month.",
            "DataNeeded": "Ebay.ebay_sales",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "4": {
            "Request": "Extract all sales data by SKU for this month.",
            "DataNeeded": "shopify.shopify_orders",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "5": {
            "Request": "Aggregate sales data from Amazon, Walmart, eBay, and Shopify to identify the best performing SKU this month.",
            "DataNeeded": "1, 2, 3, 4",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "6": {
            "Request": "Retrieve the product name for the best performing SKU identified.",
            "DataNeeded": "AAA_General_Core_Tables.official_sku_database, 5",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        }
    }
}

### Chart sales for a particular SKU
**NOTE** You must retrieve sales data from EVERY RELEVANT DATASET that contains orders information. You MUST BE THOROUGH.
{
    "Plan": {
        "1": {
            "Request": "Extract all sales data for SKU 'BC-001' from Amazon over the last year, including ordered quantity.",
            "DataNeeded": "amazon_orders.amz_orders_wbr",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "2": {
            "Request": "Extract all sales data for SKU 'BC-001' from Walmart over the last year, including ordered quantity and sales revenue.",
            "DataNeeded": "walmart_operand.walmart_orders",
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
            "Request": "Extract all sales data for SKU 'BC-001' from Shopify over the last year, including ordered quantity and sales revenue.",
            "DataNeeded": "shopify.shopify_orders",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "5": {
            "Request": "Aggregate sales data from Amazon, Walmart, eBay, and Shopify for SKU 'BC-001' over the last year and plot sales over time.",
            "DataNeeded": "1, 2, 3, 4",
            "RequiresCode": "True",
            "RequiresQuery": "False"
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
            "RequiresQuery": "True"
        },
        "2": {
            "Request": "Retrieve all sales data for product BKG-003 from Walmart, including gross sales and ordered quantity.",
            "DataNeeded": "walmart_operand.walmart_orders",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "3": {
            "Request": "Retrieve all sales data for product BKG-003 from eBay, including sales revenue and units sold.",
            "DataNeeded": "Ebay.ebay_sales",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "4": {
            "Request": "Retrieve all sales data for product BKG-003 from Shopify, including gross sales and ordered quantity.",
            "DataNeeded": "shopify.shopify_orders",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "5": {
            "Request": "Retrieve all sales data for product BKG-003 from Etsy, including sales revenue and quantity sold.",
            "DataNeeded": "Etsy.etsy_sales",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "6": {
            "Request": "Retrieve the cost of goods sold (COGS) per unit for product BKG-003.",
            "DataNeeded": "COGS.cin7_stockvaluation_cogs_output",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "7": {
            "Request": "Calculate the total revenue for product BKG-003 by aggregating sales data from all channels and the total quantity sold.",
            "DataNeeded": "1, 2, 3, 4, 5",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "8": {
            "Request": "Calculate the total cost for product BKG-003 by multiplying the COGS per unit by the total quantity sold.",
            "DataNeeded": "6, 7",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "9": {
            "Request": "Calculate the profit for product BKG-003 by subtracting the total cost from the total revenue.",
            "DataNeeded": "7, 8",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
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
            "RequiresQuery": "True"
        },
        "2": {
            "Request": "Retrieve all sales data for September 2024 from Walmart, including gross sales and ordered quantity.",
            "DataNeeded": "walmart_operand.walmart_orders",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "3": {
            "Request": "Retrieve all sales data for September 2024 from eBay, including sales revenue and units sold.",
            "DataNeeded": "Ebay.ebay_sales",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "4": {
            "Request": "Retrieve all sales data for September 2024 from Shopify, including gross sales and ordered quantity.",
            "DataNeeded": "shopify.shopify_orders",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "5": {
            "Request": "Retrieve all sales data for September 2024 from Etsy, including sales revenue and quantity sold.",
            "DataNeeded": "Etsy.etsy_sales",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "6": {
            "Request": "Retrieve most recent cost of goods sold (COGS) per unit for all products.",
            "DataNeeded": "COGS.cin7_stockvaluation_cogs_output",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "7": {
            "Request": "Calculate the total revenue for September 2024 by aggregating sales data from all channels.",
            "DataNeeded": "1, 2, 3, 4, 5",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "8": {
            "Request": "Calculate the total cost for September 2024 by multiplying the COGS per unit by the total quantity sold per SKU.",
            "DataNeeded": "1, 2, 3, 4, 5, 6",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "9": {
            "Request": "Calculate the total profit for September 2024 by subtracting the total cost from the total revenue.",
            "DataNeeded": "7, 8",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        }
    },
    "Original user request": "Total profit Septemeber 2024  "
}


### Return Rate of Particular SKU:

{
    "Plan": {
        "1": {
            "Request": "Retrieve all order data for SKU 'BKG-000' from Amazon over the past year, including ordered quantity.",
            "DataNeeded": "amazon_orders.amz_orders_wbr",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "2": {
            "Request": "Retrieve all return data for SKU 'BKG-000' from Amazon over the past year, including return quantity.",
            "DataNeeded": "amazon_orders.amz_returns_report",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "3": {
            "Request": "Retrieve all order data for SKU 'BKG-000' from Walmart over the past year, including ordered quantity.",
            "DataNeeded": "walmart_operand.walmart_orders",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "4": {
            "Request": "Retrieve all return data for SKU 'BKG-000' from Walmart over the past year, including return quantity.",
            "DataNeeded": "walmart_operand.walmart_returns",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "5": {
            "Request": "Retrieve all order data for SKU 'BKG-000' from Shopify over the past year, including ordered quantity.",
            "DataNeeded": "shopify.shopify_orders",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "6": {
            "Request": "Retrieve all refund data for SKU 'BKG-000' from Shopify over the past year, including refund quantity.",
            "DataNeeded": "shopify.shopify_refunds",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "7": {
            "Request": "Calculate the total ordered quantity for SKU 'BKG-000' from all channels over the past year including cancelled/refunded orders.",
            "DataNeeded": "1, 3, 5",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "8": {
            "Request": "Calculate the total returned quantity for SKU 'BKG-000' from all channels over the past year.",
            "DataNeeded": "2, 4, 6",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "9": {
            "Request": "Calculate the return rate for SKU 'BKG-000' by dividing the total returned quantity by the total ordered quantity.",
            "DataNeeded": "7, 8",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
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
            "RequiresQuery": "True"
        },
        "2": {
            "Request": "Retrieve all sales data for 2024 from Walmart, including gross sales and ordered quantity.",
            "DataNeeded": "walmart_operand.walmart_orders",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "3": {
            "Request": "Retrieve all sales data for 2024 from eBay, including sales revenue and units sold.",
            "DataNeeded": "Ebay.ebay_sales",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "4": {
            "Request": "Retrieve all sales data for 2024 from Shopify, including gross sales and ordered quantity.",
            "DataNeeded": "shopify.shopify_orders",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "5": {
            "Request": "Retrieve all sales data for 2024 from Etsy, including sales revenue and quantity sold.",
            "DataNeeded": "Etsy.etsy_sales",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "6": {
            "Request": "Retrieve the most recent cost of goods sold (COGS) per unit for all products.",
            "DataNeeded": "COGS.cin7_stockvaluation_cogs_output",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "7": {
            "Request": "Calculate the total revenue and quantity sold for each SKU in 2024 by aggregating sales data from all channels.",
            "DataNeeded": "1, 2, 3, 4, 5",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "8": {
            "Request": "Calculate the total cost for each SKU in 2024 by multiplying the COGS per unit by the total quantity sold.",
            "DataNeeded": "6, 7",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "9": {
            "Request": "Calculate the profit for each SKU in 2024 by subtracting the total cost from the total revenue.",
            "DataNeeded": "7, 8",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "10": {
            "Request": "Identify the top 10 most profitable products based on the calculated profits.",
            "DataNeeded": "9",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "11": {
            "Request": "Highlight any products that are unprofitable and suggest actions.",
            "DataNeeded": "9",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
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
            "RequiresQuery": "True"
        },
        "2": {
            "Request": "Calculate the total revenue generated by each customer by summing their gross sales.",
            "DataNeeded": "1",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "3": {
            "Request": "Identify the top 100 customers based on total revenue generated.",
            "DataNeeded": "2",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "4": {
            "Request": "Calculate the total number of orders for each of the top 100 customers.",
            "DataNeeded": "1, 3",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "5": {
            "Request": "Calculate the average order value for each of the top 100 customers by dividing total revenue by the total number of orders.",
            "DataNeeded": "2, 4",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "6": {
            "Request": "Calculate the purchase frequency for each of the top 100 customers by dividing the total number of orders by the number of unique months they made purchases.",
            "DataNeeded": "1, 3",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "7": {
            "Request": "Compile a ranked table of the top 100 customers including their total revenue, total number of orders, average order value, and purchase frequency.",
            "DataNeeded": "2, 4, 5, 6",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        }
    }
}

### Popular Product Variation/Extension of SKU for Month: 
{
    "Plan": {
        "1": {
            "Request": "Extract all sales data for variations of SKU LB-006 for October 2023.",
            "DataNeeded": "amazon_orders.amz_orders_wbr",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "2": {
            "Request": "Extract all sales data for variations of SKU SKU LB-006 for October 2023.",
            "DataNeeded": "walmart_operand.walmart_orders",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "3": {
            "Request": "Extract all sales data for variations of SKU SKU LB-006 for October 2023.",
            "DataNeeded": "Ebay.ebay_sales",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "4": {
            "Request": "Extract all sales data for variations of SKU SKU LB-006 for October 2023.",
            "DataNeeded": "shopify.shopify_orders",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "5": {
            "Request": "Aggregate sales data from Amazon, Walmart, eBay, and Shopify to identify the most popular variation of SKU LB-006 in October 2023.",
            "DataNeeded": "1, 2, 3, 4",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
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
            "RequiresQuery": "True"
        },
        "2": {
            "Request": "Extract all sales data for product extensions of SKU 'LB-006' from Walmart for the year 2024, including ordered quantity and sales revenue.",
            "DataNeeded": "walmart_operand.walmart_orders",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "3": {
            "Request": "Extract all sales data for product extensions of SKU 'LB-006' from eBay for the year 2024, including ordered quantity and sales revenue.",
            "DataNeeded": "Ebay.ebay_sales",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "4": {
            "Request": "Extract all sales data for product extensions of SKU 'LB-006' from Shopify for the year 2024, including ordered quantity and sales revenue.",
            "DataNeeded": "shopify.shopify_orders",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "5": {
            "Request": "Extract all sales data for product extensions of SKU 'LB-006' from Etsy for the year 2024, including ordered quantity and sales revenue.",
            "DataNeeded": "Etsy.etsy_sales",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "6": {
            "Request": "Aggregate sales data from Amazon, Walmart, eBay, Shopify, and Etsy for product extensions of SKU 'LB-006' and divide by month, then chart over 2024.",
            "DataNeeded": "1, 2, 3, 4, 5",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
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
            "RequiresQuery": "True"
        },
        "2": {
            "Request": "Retrieve all order data for October 2024 from Walmart, including order date and country.",
            "DataNeeded": "walmart_operand.walmart_orders",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "3": {
            "Request": "Retrieve all order data for October 2024 from eBay, including transaction date and country.",
            "DataNeeded": "Ebay.ebay_sales",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "4": {
            "Request": "Retrieve all order data for October 2024 from Shopify, including process date and country.",
            "DataNeeded": "shopify.shopify_orders",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "5": {
            "Request": "Retrieve all order data for October 2024 from Etsy, including sale date and country.",
            "DataNeeded": "Etsy.etsy_sales",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "6": {
            "Request": "Aggregate the number of orders from each region for October 2024 across all sales channels.",
            "DataNeeded": "1, 2, 3, 4, 5",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
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
            "RequiresQuery": "True"
        },
        "2": {
            "Request": "Extract all sales data by SKU for the year 2024 from Walmart, including ordered quantity and sales revenue.",
            "DataNeeded": "walmart_operand.walmart_orders",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "3": {
            "Request": "Extract all sales data by SKU for the year 2024 from eBay, including ordered quantity and sales revenue.",
            "DataNeeded": "Ebay.ebay_sales",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "4": {
            "Request": "Extract all sales data by SKU for the year 2024 from Shopify, including ordered quantity and sales revenue.",
            "DataNeeded": "shopify.shopify_orders",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "5": {
            "Request": "Aggregate sales data from Amazon, Walmart, eBay, and Shopify to identify the top 2 SKUs for the year 2024 based on total sales revenue.",
            "DataNeeded": "1, 2, 3, 4",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "6": {
            "Request": "Retrieve the product names for the top 2 SKUs identified.",
            "DataNeeded": "AAA_General_Core_Tables.official_sku_database, 5",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "7": {
            "Request": "Plot the sales data over time for the top 2 SKUs identified, divided by time and plotted over time.",
            "DataNeeded": "1,2,3,4,5",
            "RequiresCode": "True",
            "RequiresQuery": "False"
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
            "RequiresQuery": "True"
        },
        "2": {
            "Request": "Extract sales data by SKU for the last three months (July, August, September 2024) from Walmart, including ordered quantity and order dates.",
            "DataNeeded": "walmart_operand.walmart_orders",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "3": {
            "Request": "Extract sales data by SKU for the last three months (July, August, September 2024) from eBay, including ordered quantity and order dates.",
            "DataNeeded": "Ebay.ebay_sales",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "4": {
            "Request": "Extract sales data by SKU for the last three months (July, August, September 2024) from Shopify, including ordered quantity and order dates.",
            "DataNeeded": "shopify.shopify_orders",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "5": {
            "Request": "Aggregate sales data from Amazon, Walmart, eBay, and Shopify to identify SKUs with decreasing sales over the last three months (July, August, September 2024).",
            "DataNeeded": "1, 2, 3, 4",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "6": {
            "Request": "Identify the top 50 SKUs on a downward trajectory based on the aggregated sales data.",
            "DataNeeded": "5",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "7": {
            "Request": "Retrieve the full names of the top 50 SKUs identified as being on a downward trajectory.",
            "DataNeeded": "AAA_General_Core_Tables.official_sku_database, 6",
            "RequiresCode": "False",
            "RequiresQuery": "True"
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
            "RequiresQuery": "True"
        },
        "2": {
            "Request": "Retrieve Google Ads campaign data including Spend, Clicks, and Conversions for all channels.",
            "DataNeeded": "google_ads.gads_campaign_report",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "3": {
            "Request": "Retrieve Amazon advertising metrics including PPC Spend, PPC Sales, and PPC Clicks.",
            "DataNeeded": "amazon_advertising.amz_ads_metrics_per_campaign_type",
            "PaginationNeeded": "True",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "4": {
            "Request": "Calculate the average CPC and conversion rate for each channel.",
            "DataNeeded": "1, 2, 3",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "5": {
            "Request": "Analyze the calculated average CPC and conversion rates to identify optimization opportunities.",
            "DataNeeded": "4",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "False"
        }
    }
}
