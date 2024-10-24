Date last edited: 10/21/2024 at 2:29pm ET


## Available datasets and tables, in the format dataset.table:

## amz_salestraffic.amz_salestraffic_date
Collection of sales and feedback data for Amazon sellers across countries and dates. Key columns include:

- **Date**: Time-series tracking.
- **Account**: Seller's name.
- **Country**: Geographic performance.
- **FeedbackReceived**: Total feedback entries.
- **NegativeFeedbackReceived**: Negative feedback entries.

**Potential Insights**:
- Identify feedback and geographical trends.
- Compare seller accounts and negative feedback impact.

---

## amazon_orders.amz_numberorders_per_datesku
Data on product orders, segmented by date, brand, country, and SKU. Key columns:

- **Date**: Order date for trend analysis.
- **Brand**: Brand-specific performance.
- **Country**: Geographic insights.
- **Official SKU**: Product-specific tracking.
- **Ordered Quantity**: Sales volume.

**Potential Insights**:
- Analyze sales trends, brand performance, and market expansion.
- Improve inventory management and promotional impact.

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

## walmart.walmart_orders
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

## walmart.walmart_customer_reviews
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

## walmart.walmart_returns
Product return data from Walmart. Key columns:

- **return_date**: Return date.
- **brand**: Product brand.
- **returnreason**: Reason for return.

**Potential Insights**:
- Identify trends in returns and brand performance.
- Optimize return processes and customer satisfaction.

---

## walmart.walmart_inventory
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
- **Item Title**: Product name.
- **Sales**: Revenue generated.
- **Units**: Number of units sold.

**Potential Insights**:
- Analyze sales trends and product performance.
- Optimize inventory and pricing strategies.

---

## COGS.cogs_all_brands
Cost data for products sold on Amazon. Key columns:

- **brand**: Product brand.
- **skus**: Product identifier.
- **fob_costs**: Base cost of the product.
- **costs_to_landed**: Shipping and additional costs.

**Potential Insights**:
- Analyze product cost structure and optimize pricing.
- Compare regional costs and supply chain efficiency.

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

Here is the dataset description format for the three screenshots you provided:

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
            "DataNeeded": "amazon_orders.amz_numberorders_per_datesku",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "True"
        },
        "2": {
            "Request": "Extract all sales data by SKU for this month.",
            "DataNeeded": "walmart.walmart_orders",
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
