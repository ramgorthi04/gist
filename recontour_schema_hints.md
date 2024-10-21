non_channels_ppc.non_channels_ppcmetrics:  
  Month: DATE  
  Year_US_Week: INTEGER  
  US_Week: INTEGER  
  brand: STRING  
  country: STRING  
  channel: STRING  
  campaign_name: STRING  
  ppc_spend: FLOAT  
  ppc_sales: FLOAT  
  ppc_clicks: INTEGER  
  ppc_impressions: INTEGER  
  ppc_orders: INTEGER  

google_ads.gads_campaign_report:  
  date: DATE  
  brand: STRING  
  country: STRING  
  channel: STRING  
  campaign_name: STRING  
  spend: FLOAT  
  conversions_value: FLOAT  
  clicks: INTEGER  
  impressions: INTEGER  
  conversions: INTEGER  

amazon_advertising.amz_ads_metrics_per_campaign_type:  
  date: DATE  
  campaign_type: STRING  
  brand: STRING  
  country: STRING  
  channel: STRING  
  official_sku: STRING  
  ppc_spend: FLOAT  
  ppc_sales: FLOAT  

2020_salestraffic.allchannels_2020_reports_month:
  Year: INTEGER
  Month: INTEGER
  brand: STRING
  country: STRING
  channel: STRING
  product_sales: FLOAT
  units_ordered: INTEGER

2020_salestraffic.allchannels_2020_reports_week:
  Year_US_Week: INTEGER
  US_Week: INTEGER
  brand: STRING
  country: STRING
  channel: STRING
  product_sales: FLOAT
  units_ordered: INTEGER

2020_salestraffic.allorders_BKG_2020-01-01_2020-09-01:
  purchase_date_PST: TIMESTAMP
  purchase_date: TIMESTAMP
  order_status: STRING
  sales_channel: STRING
  sku: STRING
  asin: STRING
  quantity: INTEGER
  item_price: FLOAT
  Year: INTEGER
  Month: INTEGER
  ISO_Week: INTEGER
  US_Week: INTEGER
  Year_US_Week: INTEGER
  Week_Day_Name: STRING
  Week_Day_Number: INTEGER
  Date: DATE
  Day_Number: INTEGER
  init_PDT_date_in_UTC: DATETIME
  end_PDT_date_in_UTC: DATETIME

2020_salestraffic.allorders_BKG_US_2020-01-01:
  amazon_order_id: STRING
  merchant_order_id: STRING
  purchase_date: TIMESTAMP
  last_updated_date: TIMESTAMP
  order_status: STRING
  fulfillment_channel: STRING
  sales_channel: STRING
  order_channel: STRING
  url: STRING
  ship_service_level: STRING
  product_name: STRING
  sku: STRING
  asin: STRING
  number_of_items: STRING
  item_status: STRING
  tax_collection_model: STRING
  tax_collection_responsible_party: STRING
  quantity: INTEGER
  currency: STRING
  item_price: FLOAT
  item_tax: STRING
  shipping_price: STRING
  shipping_tax: STRING
  gift_wrap_price: STRING
  gift_wrap_tax: STRING
  item_promotion_discount: STRING
  ship_promotion_discount: STRING
  address_type: STRING
  ship_city: STRING
  ship_state: STRING
  ship_postal_code: STRING
  ship_country: STRING
  promotion_ids: STRING
  item_extensions_data: STRING
  is_business_order: BOOLEAN
  purchase_order_number: STRING
  price_designation_: STRING

2020_salestraffic.allorders_BKG_US_2020-04-01:
  amazon_order_id: STRING
  merchant_order_id: STRING
  purchase_date: TIMESTAMP
  last_updated_date: TIMESTAMP
  order_status: STRING
  fulfillment_channel: STRING
  sales_channel: STRING
  order_channel: STRING
  url: STRING
  ship_service_level: STRING
  product_name: STRING
  sku: STRING
  asin: STRING
  number_of_items: STRING
  item_status: STRING
  tax_collection_model: STRING
  tax_collection_responsible_party: STRING
  quantity: INTEGER
  currency: STRING
  item_price: STRING
  item_tax: STRING
  shipping_price: STRING
  shipping_tax: STRING
  gift_wrap_price: STRING
  gift_wrap_tax: STRING
  item_promotion_discount: STRING
  ship_promotion_discount: STRING
  address_type: STRING
  ship_city: STRING
  ship_state: STRING
  ship_postal_code: INTEGER
  ship_country: STRING
  promotion_ids: STRING
  item_extensions_data: STRING
  is_business_order: BOOLEAN
  purchase_order_number: STRING
  price_designation_: STRING

2020_salestraffic.allorders_BKG_US_2020-06-01:
  amazon_order_id: STRING
  merchant_order_id: STRING
  purchase_date: TIMESTAMP
  last_updated_date: TIMESTAMP
  order_status: STRING
  fulfillment_channel: STRING
  sales_channel: STRING
  order_channel: STRING
  url: STRING
  ship_service_level: STRING
  product_name: STRING
  sku: STRING
  asin: STRING
  number_of_items: STRING
  item_status: STRING
  tax_collection_model: STRING
  tax_collection_responsible_party: STRING
  quantity: INTEGER
  currency: STRING
  item_price: FLOAT
  item_tax: FLOAT
  shipping_price: FLOAT
  shipping_tax: FLOAT
  gift_wrap_price: STRING
  gift_wrap_tax: STRING
  item_promotion_discount: STRING
  ship_promotion_discount: FLOAT
  address_type: STRING
  ship_city: STRING
  ship_state: STRING
  ship_postal_code: STRING
  ship_country: STRING
  promotion_ids: STRING
  item_extensions_data: STRING
  is_business_order: BOOLEAN
  purchase_order_number: STRING
  price_designation_: STRING

2020_salestraffic.allorders_BKG_US_2020-07-01:
  amazon_order_id: STRING
  merchant_order_id: STRING
  purchase_date: TIMESTAMP
  last_updated_date: TIMESTAMP
  order_status: STRING
  fulfillment_channel: STRING
  sales_channel: STRING
  order_channel: STRING
  url: STRING
  ship_service_level: STRING
  product_name: STRING
  sku: STRING
  asin: STRING
  number_of_items: STRING
  item_status: STRING
  tax_collection_model: STRING
  tax_collection_responsible_party: STRING
  quantity: INTEGER
  currency: STRING
  item_price: FLOAT
  item_tax: FLOAT
  shipping_price: FLOAT
  shipping_tax: FLOAT
  gift_wrap_price: FLOAT
  gift_wrap_tax: STRING
  item_promotion_discount: STRING
  ship_promotion_discount: FLOAT
  address_type: STRING
  ship_city: STRING
  ship_state: STRING
  ship_postal_code: STRING
  ship_country: STRING
  promotion_ids: STRING
  item_extensions_data: STRING
  is_business_order: BOOLEAN
  purchase_order_number: STRING
  price_designation_: STRING

2020_salestraffic.allorders_BKG_US_2020-08-01:
  amazon_order_id: STRING
  merchant_order_id: STRING
  purchase_date: TIMESTAMP
  last_updated_date: TIMESTAMP
  order_status: STRING
  fulfillment_channel: STRING
  sales_channel: STRING
  order_channel: STRING
  url: STRING
  ship_service_level: STRING
  product_name: STRING
  sku: STRING
  asin: STRING
  number_of_items: STRING
  item_status: STRING
  tax_collection_model: STRING
  tax_collection_responsible_party: STRING
  quantity: INTEGER
  currency: STRING
  item_price: FLOAT
  item_tax: FLOAT
  shipping_price: FLOAT
  shipping_tax: FLOAT
  gift_wrap_price: STRING
  gift_wrap_tax: STRING
  item_promotion_discount: STRING
  ship_promotion_discount: FLOAT
  address_type: STRING
  ship_city: STRING
  ship_state: STRING
  ship_postal_code: STRING
  ship_country: STRING
  promotion_ids: STRING
  item_extensions_data: STRING
  is_business_order: BOOLEAN
  purchase_order_number: STRING
  price_designation_: STRING

2020_salestraffic.allorders_BKG_US_2020-09-01:
  amazon_order_id: STRING
  merchant_order_id: STRING
  purchase_date: TIMESTAMP
  last_updated_date: TIMESTAMP
  order_status: STRING
  fulfillment_channel: STRING
  sales_channel: STRING
  order_channel: STRING
  url: STRING
  ship_service_level: STRING
  product_name: STRING
  sku: STRING
  asin: STRING
  number_of_items: INTEGER
  item_status: STRING
  tax_collection_model: STRING
  tax_collection_responsible_party: STRING
  quantity: INTEGER
  currency: STRING
  item_price: FLOAT
  item_tax: FLOAT
  shipping_price: FLOAT
  shipping_tax: FLOAT
  gift_wrap_price: STRING
  gift_wrap_tax: STRING
  item_promotion_discount: FLOAT
  ship_promotion_discount: FLOAT
  address_type: STRING
  ship_city: STRING
  ship_state: STRING
  ship_postal_code: STRING
  ship_country: STRING
  promotion_ids: STRING
  item_extensions_data: STRING
  is_business_order: BOOLEAN
  purchase_order_number: STRING
  price_designation_: STRING

2020_salestraffic.amz_2020_business_reports_grouped:
  Date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  ordered_product_sales: FLOAT
  units_ordered: INTEGER
  total_order_items: INTEGER
  sessions: INTEGER
  units_refunded: INTEGER
  feedback_received: INTEGER
  negative_feedback_received: INTEGER

2020_salestraffic.etsy_2020_orderitems_reports_grouped:
  sale_date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  ordered_product_sales: FLOAT
  quantity: INTEGER

2020_salestraffic.etsysoldorderitems2020-10:
  Sale_Date: DATE
  Item_Name: STRING
  Buyer: STRING
  Quantity: INTEGER
  Price: FLOAT
  Coupon_Code: STRING
  Coupon_Details: STRING
  Discount_Amount: FLOAT
  Shipping_Discount: FLOAT
  Order_Shipping: INTEGER
  Order_Sales_Tax: INTEGER
  Item_Total: FLOAT
  Currency: STRING
  Transaction_ID: INTEGER
  Listing_ID: INTEGER
  Date_Paid: DATE
  Date_Shipped: DATE
  Ship_Name: STRING
  Ship_Address1: STRING
  Ship_Address2: STRING
  Ship_City: STRING
  Ship_State: STRING
  Ship_Zipcode: STRING
  Ship_Country: STRING
  Order_ID: INTEGER
  Variations: STRING
  Order_Type: STRING
  Listings_Type: STRING
  Payment_Type: STRING
  InPerson_Discount: STRING
  InPerson_Location: STRING
  VAT_Paid_by_Buyer: INTEGER
  SKU: STRING

2020_salestraffic.etsysoldorderitems2020-11:
  Sale_Date: DATE
  Item_Name: STRING
  Buyer: STRING
  Quantity: INTEGER
  Price: FLOAT
  Coupon_Code: STRING
  Coupon_Details: STRING
  Discount_Amount: FLOAT
  Shipping_Discount: FLOAT
  Order_Shipping: INTEGER
  Order_Sales_Tax: INTEGER
  Item_Total: FLOAT
  Currency: STRING
  Transaction_ID: INTEGER
  Listing_ID: INTEGER
  Date_Paid: DATE
  Date_Shipped: DATE
  Ship_Name: STRING
  Ship_Address1: STRING
  Ship_Address2: STRING
  Ship_City: STRING
  Ship_State: STRING
  Ship_Zipcode: STRING
  Ship_Country: STRING
  Order_ID: INTEGER
  Variations: STRING
  Order_Type: STRING
  Listings_Type: STRING
  Payment_Type: STRING
  InPerson_Discount: STRING
  InPerson_Location: STRING
  VAT_Paid_by_Buyer: INTEGER
  SKU: STRING

2020_salestraffic.etsysoldorderitems2020-12:
  Sale_Date: DATE
  Item_Name: STRING
  Buyer: STRING
  Quantity: INTEGER
  Price: FLOAT
  Coupon_Code: STRING
  Coupon_Details: STRING
  Discount_Amount: FLOAT
  Shipping_Discount: FLOAT
  Order_Shipping: INTEGER
  Order_Sales_Tax: INTEGER
  Item_Total: FLOAT
  Currency: STRING
  Transaction_ID: INTEGER
  Listing_ID: INTEGER
  Date_Paid: DATE
  Date_Shipped: DATE
  Ship_Name: STRING
  Ship_Address1: STRING
  Ship_Address2: STRING
  Ship_City: STRING
  Ship_State: STRING
  Ship_Zipcode: STRING
  Ship_Country: STRING
  Order_ID: INTEGER
  Variations: STRING
  Order_Type: STRING
  Listings_Type: STRING
  Payment_Type: STRING
  InPerson_Discount: STRING
  InPerson_Location: STRING
  VAT_Paid_by_Buyer: INTEGER
  SKU: STRING

2020_salestraffic.etsysoldorderitems2020-3:
  Sale_Date: DATE
  Item_Name: STRING
  Buyer: STRING
  Quantity: INTEGER
  Price: FLOAT
  Coupon_Code: STRING
  Coupon_Details: STRING
  Discount_Amount: FLOAT
  Shipping_Discount: FLOAT
  Order_Shipping: INTEGER
  Order_Sales_Tax: INTEGER
  Item_Total: FLOAT
  Currency: STRING
  Transaction_ID: INTEGER
  Listing_ID: INTEGER
  Date_Paid: DATE
  Date_Shipped: DATE
  Ship_Name: STRING
  Ship_Address1: STRING
  Ship_Address2: STRING
  Ship_City: STRING
  Ship_State: STRING
  Ship_Zipcode: STRING
  Ship_Country: STRING
  Order_ID: INTEGER
  Variations: STRING
  Order_Type: STRING
  Listings_Type: STRING
  Payment_Type: STRING
  InPerson_Discount: STRING
  InPerson_Location: STRING
  VAT_Paid_by_Buyer: INTEGER
  SKU: STRING

2020_salestraffic.etsysoldorderitems2020-4:
  Sale_Date: DATE
  Item_Name: STRING
  Buyer: STRING
  Quantity: INTEGER
  Price: FLOAT
  Coupon_Code: STRING
  Coupon_Details: STRING
  Discount_Amount: FLOAT
  Shipping_Discount: FLOAT
  Order_Shipping: INTEGER
  Order_Sales_Tax: INTEGER
  Item_Total: FLOAT
  Currency: STRING
  Transaction_ID: INTEGER
  Listing_ID: INTEGER
  Date_Paid: DATE
  Date_Shipped: DATE
  Ship_Name: STRING
  Ship_Address1: STRING
  Ship_Address2: STRING
  Ship_City: STRING
  Ship_State: STRING
  Ship_Zipcode: STRING
  Ship_Country: STRING
  Order_ID: INTEGER
  Variations: STRING
  Order_Type: STRING
  Listings_Type: STRING
  Payment_Type: STRING
  InPerson_Discount: STRING
  InPerson_Location: STRING
  VAT_Paid_by_Buyer: INTEGER
  SKU: STRING

2020_salestraffic.etsysoldorderitems2020-5:
  Sale_Date: DATE
  Item_Name: STRING
  Buyer: STRING
  Quantity: INTEGER
  Price: FLOAT
  Coupon_Code: STRING
  Coupon_Details: STRING
  Discount_Amount: FLOAT
  Shipping_Discount: FLOAT
  Order_Shipping: INTEGER
  Order_Sales_Tax: INTEGER
  Item_Total: FLOAT
  Currency: STRING
  Transaction_ID: INTEGER
  Listing_ID: INTEGER
  Date_Paid: DATE
  Date_Shipped: DATE
  Ship_Name: STRING
  Ship_Address1: STRING
  Ship_Address2: STRING
  Ship_City: STRING
  Ship_State: STRING
  Ship_Zipcode: STRING
  Ship_Country: STRING
  Order_ID: INTEGER
  Variations: STRING
  Order_Type: STRING
  Listings_Type: STRING
  Payment_Type: STRING
  InPerson_Discount: STRING
  InPerson_Location: STRING
  VAT_Paid_by_Buyer: INTEGER
  SKU: STRING

2020_salestraffic.etsysoldorderitems2020-6:
  Sale_Date: DATE
  Item_Name: STRING
  Buyer: STRING
  Quantity: INTEGER
  Price: FLOAT
  Coupon_Code: STRING
  Coupon_Details: STRING
  Discount_Amount: FLOAT
  Shipping_Discount: FLOAT
  Order_Shipping: INTEGER
  Order_Sales_Tax: INTEGER
  Item_Total: FLOAT
  Currency: STRING
  Transaction_ID: INTEGER
  Listing_ID: INTEGER
  Date_Paid: DATE
  Date_Shipped: DATE
  Ship_Name: STRING
  Ship_Address1: STRING
  Ship_Address2: STRING
  Ship_City: STRING
  Ship_State: STRING
  Ship_Zipcode: STRING
  Ship_Country: STRING
  Order_ID: INTEGER
  Variations: STRING
  Order_Type: STRING
  Listings_Type: STRING
  Payment_Type: STRING
  InPerson_Discount: STRING
  InPerson_Location: STRING
  VAT_Paid_by_Buyer: INTEGER
  SKU: STRING

2020_salestraffic.etsysoldorderitems2020-7:
  Sale_Date: DATE
  Item_Name: STRING
  Buyer: STRING
  Quantity: INTEGER
  Price: FLOAT
  Coupon_Code: STRING
  Coupon_Details: STRING
  Discount_Amount: FLOAT
  Shipping_Discount: FLOAT
  Order_Shipping: INTEGER
  Order_Sales_Tax: INTEGER
  Item_Total: FLOAT
  Currency: STRING
  Transaction_ID: INTEGER
  Listing_ID: INTEGER
  Date_Paid: DATE
  Date_Shipped: DATE
  Ship_Name: STRING
  Ship_Address1: STRING
  Ship_Address2: STRING
  Ship_City: STRING
  Ship_State: STRING
  Ship_Zipcode: STRING
  Ship_Country: STRING
  Order_ID: INTEGER
  Variations: STRING
  Order_Type: STRING
  Listings_Type: STRING
  Payment_Type: STRING
  InPerson_Discount: STRING
  InPerson_Location: STRING
  VAT_Paid_by_Buyer: INTEGER
  SKU: STRING

2020_salestraffic.etsysoldorderitems2020-8:
  Sale_Date: DATE
  Item_Name: STRING
  Buyer: STRING
  Quantity: INTEGER
  Price: FLOAT
  Coupon_Code: STRING
  Coupon_Details: STRING
  Discount_Amount: FLOAT
  Shipping_Discount: FLOAT
  Order_Shipping: INTEGER
  Order_Sales_Tax: INTEGER
  Item_Total: FLOAT
  Currency: STRING
  Transaction_ID: INTEGER
  Listing_ID: INTEGER
  Date_Paid: DATE
  Date_Shipped: DATE
  Ship_Name: STRING
  Ship_Address1: STRING
  Ship_Address2: STRING
  Ship_City: STRING
  Ship_State: STRING
  Ship_Zipcode: STRING
  Ship_Country: STRING
  Order_ID: INTEGER
  Variations: STRING
  Order_Type: STRING
  Listings_Type: STRING
  Payment_Type: STRING
  InPerson_Discount: STRING
  InPerson_Location: STRING
  VAT_Paid_by_Buyer: INTEGER
  SKU: STRING

2020_salestraffic.etsysoldorderitems2020-9:
  Sale_Date: DATE
  Item_Name: STRING
  Buyer: STRING
  Quantity: INTEGER
  Price: FLOAT
  Coupon_Code: STRING
  Coupon_Details: STRING
  Discount_Amount: FLOAT
  Shipping_Discount: FLOAT
  Order_Shipping: INTEGER
  Order_Sales_Tax: INTEGER
  Item_Total: FLOAT
  Currency: STRING
  Transaction_ID: INTEGER
  Listing_ID: INTEGER
  Date_Paid: DATE
  Date_Shipped: DATE
  Ship_Name: STRING
  Ship_Address1: STRING
  Ship_Address2: STRING
  Ship_City: STRING
  Ship_State: STRING
  Ship_Zipcode: STRING
  Ship_Country: STRING
  Order_ID: INTEGER
  Variations: STRING
  Order_Type: STRING
  Listings_Type: STRING
  Payment_Type: STRING
  InPerson_Discount: STRING
  InPerson_Location: STRING
  VAT_Paid_by_Buyer: INTEGER
  SKU: STRING

2020_salestraffic.salestraffic_2020_BCK_US:
  Date: DATE
  Ordered_Product_Sales: FLOAT
  Units_Ordered: INTEGER
  Total_Order_Items: INTEGER
  Sessions: INTEGER
  Units_Refunded: INTEGER
  Feedback_Received: INTEGER
  Negative_Feedback_Received: INTEGER

2020_salestraffic.salestraffic_2020_BKG_US:
  Date: DATE
  Ordered_Product_Sales: FLOAT
  Units_Ordered: INTEGER
  Total_Order_Items: INTEGER
  Sessions___Total: INTEGER
  Units_Refunded: INTEGER
  Feedback_Received: INTEGER
  Negative_Feedback_Received: INTEGER

2020_salestraffic.salestraffic_2020_LGB_CA:
  Date: DATE
  Ordered_product_sales: FLOAT
  Units_ordered: INTEGER
  Total_order_items: INTEGER
  Sessions: INTEGER
  Units_refunded: INTEGER
  Feedback_received: INTEGER
  Negative_feedback_received: INTEGER

2020_salestraffic.salestraffic_2020_LGB_US:
  Date: DATE
  Ordered_Product_Sales: FLOAT
  Units_Ordered: INTEGER
  Total_Order_Items: INTEGER
  Sessions: INTEGER
  Units_Refunded: INTEGER
  Feedback_Received: INTEGER
  Negative_Feedback_Received: INTEGER

2020_salestraffic.salestraffic_2020_RLL_US:
  Date: DATE
  Ordered_Product_Sales: FLOAT
  Units_Ordered: INTEGER
  Total_Order_Items: INTEGER
  Sessions: INTEGER
  Units_Refunded: INTEGER
  Feedback_Received: INTEGER
  Negative_Feedback_Received: INTEGER

2020_salestraffic.salestraffic_2020_SGC_US:
  Date: DATE
  Ordered_Product_Sales: FLOAT
  Units_Ordered: INTEGER
  Total_Order_Items: INTEGER
  Sessions: INTEGER
  Units_Refunded: INTEGER
  Feedback_Received: INTEGER
  Negative_Feedback_Received: INTEGER

2020_salestraffic.salestraffic_2020_SHK_US:
  Date: DATE
  Ordered_Product_Sales: FLOAT
  Units_Ordered: INTEGER
  Total_Order_Items: INTEGER
  Sessions: INTEGER
  Units_Refunded: INTEGER
  Feedback_Received: INTEGER
  Negative_Feedback_Received: INTEGER

2020_salestraffic.shop_2020_sales_reports_grouped:
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  gross_sales: FLOAT
  net_quantity: INTEGER

2020_salestraffic.shopify_2020_lgb_us_sales:
  Order_ID: INTEGER
  Sale_ID: INTEGER
  Date: TIMESTAMP
  Order: STRING
  Transaction_type: STRING
  Sale_type: STRING
  Sales_channel: STRING
  POS_location: STRING
  Billing_country: STRING
  Billing_region: STRING
  Billing_city: STRING
  Shipping_country: STRING
  Shipping_region: STRING
  Shipping_city: STRING
  Product_type: STRING
  Product_vendor: STRING
  Product: STRING
  Variant: STRING
  Variant_SKU: STRING
  Net_quantity: INTEGER
  Gross_sales: FLOAT
  Discounts: FLOAT
  Returns: FLOAT
  Net_sales: FLOAT
  Shipping: FLOAT
  Taxes: FLOAT
  Total_sales: FLOAT

2020_salestraffic.shopify_2020_sales_bkg_us:
  Order_ID: INTEGER
  Sale_ID: INTEGER
  Date: TIMESTAMP
  Order: STRING
  Transaction_type: STRING
  Sale_type: STRING
  Sales_channel: STRING
  POS_location: STRING
  Billing_country: STRING
  Billing_region: STRING
  Billing_city: STRING
  Shipping_country: STRING
  Shipping_region: STRING
  Shipping_city: STRING
  Product_type: STRING
  Product_vendor: STRING
  Product: STRING
  Variant: STRING
  Variant_SKU: STRING
  Net_quantity: INTEGER
  Gross_sales: FLOAT
  Discounts: FLOAT
  Returns: FLOAT
  Net_sales: FLOAT
  Shipping: FLOAT
  Taxes: FLOAT
  Total_sales: FLOAT

AAA_General_Core_Tables.CAD_USD_Historical:
  Date: DATE
  Close: FLOAT

AAA_General_Core_Tables.EUR_USD_Historical:
  Date: DATE
  Close: FLOAT

AAA_General_Core_Tables.GBP_USD_Historical:
  Date: DATE
  Close: FLOAT

AAA_General_Core_Tables.MXN_USD_Historical:
  Date: DATE
  Close: FLOAT

AAA_General_Core_Tables.PLN_USD_Historical:
  Date: DATE
  Close: FLOAT

AAA_General_Core_Tables.SEK_USD_Historical:
  Date: DATE
  Close: FLOAT

AAA_General_Core_Tables.TRY_USD_Historical:
  Date: DATE
  Close: FLOAT

AAA_General_Core_Tables.asp_fcast_ALL_brands_2023:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKU: STRING
  January_2023: FLOAT
  February_2023: FLOAT
  March_2023: FLOAT
  April_2023: FLOAT
  May_2023: FLOAT
  June_2023: FLOAT
  July_2023: FLOAT
  August_2023: FLOAT
  September_2023: FLOAT
  October_2023: FLOAT
  November_2023: FLOAT
  December_2023: FLOAT

AAA_General_Core_Tables.asp_fcast_ALL_brands_2024:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKU: STRING
  January_2024: FLOAT
  February_2024: FLOAT
  March_2024: FLOAT
  April_2024: FLOAT
  May_2024: FLOAT
  June_2024: FLOAT
  July_2024: FLOAT
  August_2024: FLOAT
  September_2024: FLOAT
  October_2024: FLOAT
  November_2024: FLOAT
  December_2024: FLOAT

AAA_General_Core_Tables.asp_fcast_ALL_brands_2025:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKU: STRING
  January_2025: FLOAT
  February_2025: FLOAT
  March_2025: FLOAT
  April_2025: FLOAT
  May_2025: FLOAT
  June_2025: FLOAT
  July_2025: FLOAT
  August_2025: FLOAT
  September_2025: FLOAT
  October_2025: FLOAT
  November_2025: FLOAT
  December_2025: FLOAT

AAA_General_Core_Tables.cogs_fcast:
  month: DATE
  brand: STRING
  country: STRING
  forecast_units: INTEGER
  cogs_month_sku_country: FLOAT

AAA_General_Core_Tables.currency_exchange_prices:
  Date: DATE
  Close: FLOAT
  country: STRING
  exch_currency: STRING

AAA_General_Core_Tables.full_calendar:
  Year: INTEGER
  Month: INTEGER
  ISO_Week: INTEGER
  US_Week: INTEGER
  Year_US_Week: INTEGER
  Week_Day_Name: STRING
  Week_Day_Number: INTEGER
  Date: DATE
  Day_Number: INTEGER
  start_of_week: DATE
  init_PDT_date_in_UTC: DATETIME
  end_PDT_date_in_UTC: DATETIME
  init_DST_date_in_UTC_westernEU: DATETIME
  end_DST_date_in_UTC_westernEU: DATETIME

AAA_General_Core_Tables.gbpusd_table:
  Date: DATE
  Close: FLOAT

AAA_General_Core_Tables.monthly_sellerboard_downloads:
  Account: STRING
  Country: STRING
  Month: STRING
  Brand: STRING
  official_sku: STRING
  _3PL_per_unit: FLOAT
  _3PL: FLOAT
  Product: STRING
  ASIN: STRING
  SKU: STRING
  Units: INTEGER
  Refunds: INTEGER
  Sales: FLOAT
  Promo: FLOAT
  Ads: FLOAT
  Sponsored_products__PPC_: FLOAT
  Sponsored_Display: FLOAT
  Sponsored_brands__HSA_: FLOAT
  Sponsored_Brands_Video: FLOAT
  Google_ads: STRING
  Facebook_ads: STRING
  __Refunds: STRING
  Sellable_Quota: STRING
  Refund___ost: FLOAT
  Amazon_fees: FLOAT
  Cost_of_Goods: FLOAT
  VAT: FLOAT
  Gross_profit: FLOAT
  Net_profit: FLOAT
  Estimated_payout: FLOAT
  Expenses: STRING
  Margin: FLOAT
  ROI: FLOAT
  BSR: INTEGER
  Real_ACOS: FLOAT
  Sessions: INTEGER
  Unit_Session_Percentage: FLOAT

AAA_General_Core_Tables.official_sku:
  brand: STRING
  product_name: STRING
  official_sku: STRING
  channels_sku_unique_column: STRING
  asin: STRING

AAA_General_Core_Tables.official_sku_database:
  brand: STRING
  country: STRING
  channel: STRING
  product_name: STRING
  official_sku: STRING
  asin: STRING
  ASP_T3M: FLOAT
  ASP_CurrentMonth: FLOAT

AAA_General_Core_Tables.productmaster_list:
  PRODUCT_NAME: STRING
  SHORT_NAME: STRING
  BRAND: STRING
  SKU: STRING
  ASIN: STRING
  STATUS: STRING
  STATUS_US: STRING
  STATUS_CA: STRING
  STATUS_MX: STRING
  STATUS_EU: STRING
  STATUS_UK: STRING
  PARENT_SKU: STRING
  PARENT_ASIN: STRING
  Other_SKUs: STRING
  UPC___EAN: STRING
  SUPPLIER_COMPANY: STRING
  SUPPLIER_SKU: STRING
  PRODUCTION_TIME__days_: INTEGER
  UNITS__CTN: INTEGER
  CTN_PLT: INTEGER
  MOQ: STRING
  SCHEDULE_B_NUMBER: STRING
  HS_CODE: STRING
  US_DUTY: STRING
  CA_DUTY: STRING
  EU_DUTY: FLOAT
  INCOTERM: STRING
  SPECIAL_IMPORT_REQMT: STRING
  VAT_NUMBER: STRING
  ACTIVE_REGION: STRING
  RRP__USD_: STRING
  RRP__CAD_: STRING
  RRP__MEX_: STRING
  RRP__EUR_: STRING
  COGS__USD_: STRING
  Product_Length_L_cm: STRING
  Product_Width_W_cm: STRING
  Product_Height_H_cm: STRING
  PRODUCT_NET_WEIGHT__KG_: STRING
  Package_Length_L_cm: STRING
  Package_Width_W_cm: STRING
  Package_Height_H_cm: STRING
  PACKAGE_NET_WEIGHT__KG_: STRING
  _Master_Carton_Length_L_cm: FLOAT
  _Master_Carton_Width_W_cm: STRING
  _Master_Carton_Heigth_H_cm: STRING
  CBM_CTN_m3: FLOAT
  MASTER_CARTON_GROSS_WEIGHT__KG_: FLOAT
  _Pallet_Length_L_cm: FLOAT
  _Pallet_Width_W_cm: FLOAT
  _Pallet_Heigth_H_cm: FLOAT
  CBM_PLT_m3: FLOAT
  PLT__GROSS_WEIGHT__KGs_: FLOAT
  _Product__L_in: STRING
  Product__W_in: STRING
  Product_H_in: STRING
  NET_WEIGHT_lbs: STRING
  Package_Length_L_in: STRING
  Package_Width_W_in: STRING
  Package_Height_H_in: STRING
  PACKAGE_NET_WEIGHT__lb_: STRING
  Master_Carton_L_in: FLOAT
  Master_Carton_W_in: STRING
  Master_Carton_H_in: STRING
  CBFT_CTN_ft3: STRING
  Master_CTN_GROSS_WEIGHT_lbs: FLOAT
  Pallet_L_in: FLOAT
  Pallet_W_in: FLOAT
  Pallet_H_in: FLOAT
  CBFT_PLT_ft3: FLOAT
  PLT_GROSS_WEIGHT_lbs: FLOAT
  CLOTHING_: BOOLEAN
  CONTAINS_BATTERY_: BOOLEAN
  HAZARD__: BOOLEAN
  NPN: STRING

AAA_General_Core_Tables.recontour_template_datebrandcountrychannelsku:
  Year_US_Week: INTEGER
  US_Week: INTEGER
  start_of_week: DATE
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  sku: STRING

AAA_General_Core_Tables.sales_fcast_ALL_brands:
  account: STRING
  brand: STRING
  country: STRING
  channel: STRING
  asin: STRING
  sku: STRING
  month: DATE
  forecast_units: FLOAT
  forecast_asp: FLOAT
  forecast_gross_sales: FLOAT

AAA_General_Core_Tables.sales_fcast_ALL_brands_daily:
  month: DATE
  Year_US_Week: INTEGER
  US_Week: INTEGER
  start_of_week: DATE
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  sku: STRING
  daily_fcastsales: FLOAT
  daily_fcastunits: FLOAT

AAA_General_Core_Tables.sales_fcast_ALL_brands_table_2023:
  account: STRING
  brand: STRING
  country: STRING
  channel: STRING
  asin: STRING
  sku: STRING
  month: DATE
  forecast_units: FLOAT
  forecast_asp: FLOAT
  forecast_gross_sales: FLOAT

AAA_General_Core_Tables.sales_fcast_ALL_brands_table_2023_daily:
  month: DATE
  Year_US_Week: INTEGER
  US_Week: INTEGER
  start_of_week: DATE
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  sku: STRING
  daily_fcastsales: FLOAT
  daily_fcastunits: FLOAT

AAA_General_Core_Tables.sellerboard_per_month:
  month: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  metric: STRING
  value: FLOAT

AAA_General_Core_Tables.units_fcast_ALL_brands_2023:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKU: STRING
  January_2023: INTEGER
  February_2023: INTEGER
  March_2023: INTEGER
  April_2023: FLOAT
  May_2023: FLOAT
  June_2023: FLOAT
  July_2023: FLOAT
  August_2023: FLOAT
  September_2023: FLOAT
  October_2023: FLOAT
  November_2023: FLOAT
  December_2023: FLOAT

AAA_General_Core_Tables.units_fcast_ALL_brands_2024:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKU: STRING
  January_2024: INTEGER
  February_2024: INTEGER
  March_2024: INTEGER
  April_2024: INTEGER
  May_2024: INTEGER
  June_2024: INTEGER
  July_2024: INTEGER
  August_2024: INTEGER
  September_2024: INTEGER
  October_2024: INTEGER
  November_2024: INTEGER
  December_2024: INTEGER

AAA_General_Core_Tables.units_fcast_ALL_brands_2025:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKU: STRING
  January_2025: INTEGER
  February_2025: INTEGER
  March_2025: INTEGER
  April_2025: INTEGER
  May_2025: INTEGER
  June_2025: INTEGER
  July_2025: INTEGER
  August_2025: INTEGER
  September_2025: INTEGER
  October_2025: INTEGER
  November_2025: INTEGER
  December_2025: INTEGER

AAA_General_Core_Tables.us_week_number:
  Day: DATE
  US_Week_Number: INTEGER
  Year_US_Week_Number: INTEGER

AAB_Finals.availability_listings:
  start_of_week: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  active_listings: INTEGER
  active_oos_listings: INTEGER
  inactive_listings: INTEGER
  inactive_oos_listings: INTEGER
  inactive_is_listings: INTEGER

AAB_Finals.daily_monitoring_dashboard_bsr:
  date: DATE
  account: STRING
  brand: STRING
  country: STRING
  title: STRING
  ReferenceASIN: STRING
  rank: INTEGER

AAB_Finals.interim_channels_inventory:
  start_of_week: DATE
  date: DATE
  account: STRING
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  channel_identifier: STRING
  on_hand: NUMERIC

AAB_Finals.ondemand_sostocked_inventory_days:
  week: DATE
  brand: STRING
  country: STRING
  type_of_location: STRING
  official_sku: STRING
  init_ava_n_os_qty_POS: FLOAT
  days_in_inventory_sostocked: INTEGER

AAB_Finals.salestraffic_month_currentyear-2:
  Year: INTEGER
  Month: INTEGER
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  sales: FLOAT
  units: INTEGER
  order_items: INTEGER
  sessions: INTEGER
  number_orders: INTEGER

AAB_Finals.salestraffic_week_currentyear-2:
  Year_US_Week: INTEGER
  US_Week: INTEGER
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  sales: FLOAT
  units: INTEGER
  order_items: INTEGER
  sessions: INTEGER
  number_orders: INTEGER
  filter_year: STRING

AAB_Finals.scheduled_activelistings_byasin:
  start_of_week: DATE
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  channel_identifier: STRING
  official_sku: STRING
  oh_i: NUMERIC
  status: STRING

AAB_Finals.scheduled_amz_ads_complete_sku_level:
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  Spend: FLOAT
  PPC_Sales: FLOAT
  Clicks: FLOAT
  Impressions: FLOAT
  Number_of_Orders: FLOAT

AAB_Finals.scheduled_amz_numberorders_week:
  Year_US_Week: INTEGER
  Month: INTEGER
  US_Week: INTEGER
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  ordered_quantity: INTEGER

AAB_Finals.scheduled_amz_unitssold_week:
  Year_US_Week: INTEGER
  Month: INTEGER
  US_Week: INTEGER
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  ordered_quantity: INTEGER

AAB_Finals.scheduled_cust_service_gsheets:
  Year: INTEGER
  Year_US_Week: INTEGER
  Month: INTEGER
  US_Week: INTEGER
  brand: STRING
  country: STRING
  channel: STRING
  number_messages: INTEGER
  messages_not_in_time: INTEGER
  resolved_tickets: INTEGER
  unresolved_tickets: INTEGER
  rft_tickets: INTEGER
  avg_first_response_time_h: FLOAT
  avg_resol_time_h: FLOAT
  stars: FLOAT
  feedbackReceived: INTEGER
  negativeFeedbackReceived: INTEGER
  unitsOrdered: NUMERIC
  number_orders: INTEGER
  return_quantity: NUMERIC

AAB_Finals.scheduled_customer_reviews:
  Year: INTEGER
  Year_US_Week: INTEGER
  Month: INTEGER
  US_Week: INTEGER
  brand: STRING
  country: STRING
  channel: STRING
  stars: NUMERIC
  number_reviews: NUMERIC
  number_negat_reviews: INTEGER

AAB_Finals.scheduled_daily_monit_bsr:
  date: DATE
  account: STRING
  brand: STRING
  country: STRING
  category: STRING
  category_classification: STRING
  ReferenceASIN: STRING
  rank: INTEGER

AAB_Finals.scheduled_daily_monitoring_gsheets:
  Year: INTEGER
  Year_US_Week: INTEGER
  Month: INTEGER
  US_Week: INTEGER
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  week_day_number: INTEGER
  sales: FLOAT
  units: NUMERIC
  sessions: INTEGER
  number_orders: INTEGER
  year_filter: STRING

AAB_Finals.scheduled_daily_monitoring_numberorders_gsheets:
  Year: INTEGER
  Year_US_Week: INTEGER
  Month: INTEGER
  US_Week: INTEGER
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  week_day_number: INTEGER
  number_orders: INTEGER
  year_filter: STRING

AAB_Finals.scheduled_inventory_stages:
  month: DATE
  location_status: STRING
  inventory_stage_correct_name: STRING
  inventory_stage_order: INTEGER
  brand: STRING
  country: STRING
  official_sku: STRING
  location_detail: STRING
  sku_type: STRING
  units: FLOAT

AAB_Finals.scheduled_inventoryavailability_byasin:
  start_of_week: DATE
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  channel_identifier: STRING
  on_hand: NUMERIC

AAB_Finals.scheduled_operations_gsheets_month:
  year: INTEGER
  month: DATE
  account: STRING
  brand: STRING
  country: STRING
  official_sku: STRING
  asin: STRING
  sku: STRING
  date: DATE
  estimated_excess_quantity: INTEGER
  inv_age_91_to_180_days: INTEGER
  inv_age_180plus: INTEGER
  sell_through: NUMERIC
  units_shipped_t90: INTEGER
  available: INTEGER
  stranded_inventory_qty: INTEGER
  inbound_quantity: INTEGER
  days_of_supply: INTEGER
  inv_age_0_to_90_days: INTEGER
  inv_age_181_to_270_days: INTEGER
  inv_age_271_to_365_days: INTEGER
  inv_age_365_plus_days: INTEGER
  quantity_to_be_charged_ais_181_210_days: INTEGER
  estimated_ais_181_210_days: NUMERIC
  quantity_to_be_charged_ais_211_240_days: INTEGER
  estimated_ais_211_240_days: NUMERIC
  quantity_to_be_charged_ais_241_270_days: INTEGER
  estimated_ais_241_270_days: NUMERIC
  quantity_to_be_charged_ais_271_300_days: INTEGER
  estimated_ais_271_300_days: NUMERIC
  quantity_to_be_charged_ais_301_330_days: INTEGER
  estimated_ais_301_330_days: NUMERIC
  quantity_to_be_charged_ais_331_365_days: INTEGER
  estimated_ais_331_365_days: NUMERIC
  quantity_to_be_charged_ais_365_PLUS_days: INTEGER
  estimated_ais_365_plus_days: NUMERIC
  storage_type: STRING
  storage_volume: NUMERIC
  volume_unit_measurement: STRING
  item_volume: NUMERIC

AAB_Finals.scheduled_operations_gsheets_week:
  Year_US_Week: INTEGER
  US_Week: INTEGER
  account: STRING
  brand: STRING
  country: STRING
  official_sku: STRING
  asin: STRING
  sku: STRING
  date: DATE
  estimated_excess_quantity: INTEGER
  inv_age_91_to_180_days: INTEGER
  inv_age_180plus: INTEGER
  sell_through: NUMERIC
  units_shipped_t90: INTEGER
  available: INTEGER
  stranded_inventory_qty: INTEGER
  inbound_quantity: INTEGER
  days_of_supply: INTEGER
  inv_age_0_to_90_days: INTEGER
  inv_age_181_to_270_days: INTEGER
  inv_age_271_to_365_days: INTEGER
  inv_age_365_plus_days: INTEGER
  quantity_to_be_charged_ais_181_210_days: INTEGER
  estimated_ais_181_210_days: NUMERIC
  quantity_to_be_charged_ais_211_240_days: INTEGER
  estimated_ais_211_240_days: NUMERIC
  quantity_to_be_charged_ais_241_270_days: INTEGER
  estimated_ais_241_270_days: NUMERIC
  quantity_to_be_charged_ais_271_300_days: INTEGER
  estimated_ais_271_300_days: NUMERIC
  quantity_to_be_charged_ais_301_330_days: INTEGER
  estimated_ais_301_330_days: NUMERIC
  quantity_to_be_charged_ais_331_365_days: INTEGER
  estimated_ais_331_365_days: NUMERIC
  quantity_to_be_charged_ais_365_PLUS_days: INTEGER
  estimated_ais_365_plus_days: NUMERIC
  storage_type: STRING
  storage_volume: NUMERIC
  volume_unit_measurement: STRING

AAB_Finals.scheduled_pnl:
  date: DATE
  account: STRING
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  pnl_account: STRING
  pnl_account_order: INTEGER
  pnl_subaccount1: STRING
  pnl_subaccount1_order: INTEGER
  pnl_subaccount2: STRING
  pnl_subaccount2_order: INTEGER
  pnl_subaccount3: STRING
  pnl_subaccount3_order: INTEGER
  consolidated_transaction: STRING
  ordered_quantity: NUMERIC
  refund_quantity: NUMERIC
  amount: FLOAT

 AAB_Finals.scheduled_ppc_daily_monitoring:
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  spend: FLOAT
  ppc_sales: FLOAT
  clicks: FLOAT
  impressions: FLOAT
  number_of_orders: FLOAT

 AAB_Finals.scheduled_ppc_metrics_all_channels:
  Year_US_Week: INTEGER
  US_Week: INTEGER
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  ppc_spend: FLOAT
  ppc_sales: FLOAT
  ppc_clicks: FLOAT
  ppc_impressions: FLOAT
  ppc_orders: FLOAT
  filter_year: STRING

 AAB_Finals.scheduled_ppc_metrics_all_channels_month:
  Year: INTEGER
  Month: INTEGER
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  ppc_spend: FLOAT
  ppc_sales: FLOAT
  ppc_clicks: FLOAT
  ppc_impressions: FLOAT
  ppc_orders: FLOAT

 AAB_Finals.scheduled_ppc_metrics_allchannels_intermediary:
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  spend: FLOAT
  ppc_sales: FLOAT
  clicks: FLOAT
  impressions: FLOAT
  number_of_orders: FLOAT

 AAB_Finals.scheduled_replyco_tickets:
  Year: INTEGER
  Year_US_Week: INTEGER
  Month: INTEGER
  US_Week: INTEGER
  brand: STRING
  country: STRING
  channel: STRING
  number_messages: INTEGER
  messages_not_in_time: INTEGER
  resolved_tickets: INTEGER
  unresolved_tickets: INTEGER
  rft_tickets: INTEGER
  avg_first_response_time_h: FLOAT
  avg_resol_time_h: FLOAT

 AAB_Finals.scheduled_returns_report_week:
  Year_US_Week: INTEGER
  Month: INTEGER
  US_Week: INTEGER
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  detailed_disposition: STRING
  return_category: STRING
  reason: STRING
  status: STRING
  customer_comments: STRING
  return_orders: INTEGER
  return_quantity: INTEGER
  avg_days_to_return: FLOAT

 AAB_Finals.scheduled_shopify_sales:
  process_date: DATE
  country: STRING
  channel: STRING
  brand: STRING
  official_sku: STRING
  ordered_quantity: INTEGER
  gross_sales: FLOAT
  number_orders: INTEGER
  refund_quantity: INTEGER
  refund_amount: FLOAT
  number_items: INTEGER
  Year: INTEGER
  US_Week: INTEGER

 AAB_Finals.scheduled_sku_count:
  level: STRING
  brand: STRING
  country: STRING
  channel: STRING
  sku: STRING
  _12_31_2023: INTEGER
  _1_7_2024: INTEGER
  _1_14_2024: INTEGER
  _1_21_2024: INTEGER
  _1_28_2024: INTEGER
  _2_4_2024: INTEGER
  _2_11_2024: INTEGER
  _2_18_2024: INTEGER
  _2_25_2024: INTEGER
  _3_3_2024: INTEGER
  _3_10_2024: INTEGER
  _3_17_2024: INTEGER
  _3_24_2024: INTEGER
  _3_31_2024: INTEGER
  _4_7_2024: INTEGER
  _4_14_2024: INTEGER
  _4_21_2024: INTEGER
  _4_28_2024: INTEGER
  _5_5_2024: INTEGER
  _5_12_2024: INTEGER
  _5_19_2024: INTEGER
  _5_26_2024: INTEGER
  _6_2_2024: INTEGER
  _6_9_2024: INTEGER
  _6_16_2024: INTEGER
  _6_23_2024: INTEGER
  _6_30_2024: INTEGER
  _7_7_2024: INTEGER
  _7_14_2024: INTEGER
  _7_21_2024: INTEGER
  _7_28_2024: INTEGER
  _8_4_2024: INTEGER
  _8_11_2024: INTEGER
  _8_18_2024: INTEGER
  _8_25_2024: INTEGER
  _9_1_2024: INTEGER
  _9_8_2024: INTEGER
  _9_15_2024: INTEGER
  _9_22_2024: INTEGER
  _9_29_2024: INTEGER
  _10_6_2024: INTEGER
  _10_13_2024: INTEGER
  _10_20_2024: INTEGER
  _10_27_2024: INTEGER
  _11_3_2024: INTEGER
  _11_10_2024: INTEGER
  _11_17_2024: INTEGER
  _11_24_2024: INTEGER
  _12_1_2024: INTEGER
  _12_8_2024: INTEGER
  _12_15_2024: INTEGER
  _12_22_2024: INTEGER

 AAB_Finals.scheduled_walmart_sales:
  date: DATE
  country: STRING
  channel: STRING
  sku: STRING
  number_orders: INTEGER
  order_items: INTEGER
  brand: STRING
  gross_sales: NUMERIC
  ordered_quantity: INTEGER
  refund_quantity: NUMERIC
  refund_amount: NUMERIC
  Year: INTEGER
  US_Week: INTEGER

 AAB_Finals.scheduled_wbr_all_channels_intermediary:
  Year: INTEGER
  Year_US_Week: INTEGER
  Month: INTEGER
  US_Week: INTEGER
  start_of_week: DATE
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  sales: FLOAT
  units: NUMERIC
  order_items: INTEGER
  sessions: INTEGER
  number_orders: INTEGER
  sales_net_of_tax: FLOAT

 AAB_Finals.scheduled_wbr_brandlevelorders_month:
  Year: INTEGER
  Month: INTEGER
  brand: STRING
  country: STRING
  channel: STRING
  number_orders: INTEGER

 AAB_Finals.scheduled_wbr_brandlevelorders_week:
  Year_US_Week: INTEGER
  US_Week: INTEGER
  brand: STRING
  country: STRING
  channel: STRING
  number_orders: INTEGER
  filter_year: STRING

 AAB_Finals.scheduled_wbrallchannels_intermidiary_numberorders:
  Year: INTEGER
  Year_US_Week: INTEGER
  Month: INTEGER
  US_Week: INTEGER
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  number_orders: INTEGER

 AAB_Finals.scheduled_wbrsales_gsheets_month:
  Year: INTEGER
  Month: INTEGER
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  sales: FLOAT
  units: NUMERIC
  order_items: INTEGER
  sessions: INTEGER
  number_orders: INTEGER
  sales_net_of_tax: FLOAT

 AAB_Finals.scheduled_wbrsales_gsheets_week:
  Year_US_Week: INTEGER
  US_Week: INTEGER
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  sales: FLOAT
  units: NUMERIC
  order_items: INTEGER
  sessions: INTEGER
  number_orders: INTEGER
  sales_net_of_tax: FLOAT
  filter_year: STRING

 AAB_Finals.wbr_all_channels_intermediary_numberorders:
  Year: INTEGER
  Year_US_Week: INTEGER
  Month: INTEGER
  US_Week: INTEGER
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  number_orders: INTEGER

 AAB_Finals.wbr_allchanninterm_gb_month:
  month: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  units: NUMERIC

 AAB_Finals.wbr_sales_all_channels:
  Year: INTEGER
  Year_US_Week: INTEGER
  Month: INTEGER
  US_Week: INTEGER
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  sales: FLOAT
  units: INTEGER
  order_items: INTEGER
  sessions: INTEGER
  number_orders: INTEGER

 AACC_inventoryadjustment.brands_amazonorders:
  month: DATE
  account: STRING
  brand: STRING
  country: STRING
  channel: STRING
  sku: STRING
  official_sku: STRING
  fulfillment_channel: STRING
  sales_channel: STRING
  order_status: STRING
  item_status: STRING
  amazon_order_id: STRING
  ordered_quantity: INTEGER
  ordered_sales: FLOAT

 AACC_inventoryadjustment.brands_amazonreturns:
  month: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  detailed_disposition: STRING
  reason: STRING
  status: STRING
  return_quantity: INTEGER

 AACC_inventoryadjustment.brands_netstockmovements:
  months: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  branch: STRING
  shipped_quantity: NUMERIC
  shipped_sales: FLOAT
  returned_quantity: NUMERIC
  returned_amount: FLOAT
  net_shipped_quantity: NUMERIC
  net_shipped_sales: FLOAT

 AACC_inventoryadjustment.sagercreek_amazonorders:
  month: DATE
  account: STRING
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  fulfillment_channel: STRING
  sales_channel: STRING
  order_status: STRING
  item_status: STRING
  ordered_quantity: INTEGER

 AACC_inventoryadjustment.sagercreek_amazonreturns:
  month: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  detailed_disposition: STRING
  reason: STRING
  status: STRING
  return_quantity: INTEGER

 AACC_inventoryadjustment.sagercreek_netstockmovements:
  months: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  branch: STRING
  shipped_quantity: INTEGER
  returned_quantity: NUMERIC
  net_shipped_quantity: NUMERIC

 AACC_inventoryadjustment.sgc_rll_amazonorders:
  month: DATE
  account: STRING
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  fulfillment_channel: STRING
  sales_channel: STRING
  order_status: STRING
  item_status: STRING
  ordered_quantity: INTEGER

 AACC_inventoryadjustment.sgc_rll_amazonreturns:
  month: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  detailed_disposition: STRING
  reason: STRING
  status: STRING
  return_quantity: INTEGER

 AACC_inventoryadjustment.sgc_rll_netstockmovements:
  months: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  branch: STRING
  shipped_quantity: NUMERIC
  returned_quantity: NUMERIC
  net_shipped_quantity: NUMERIC

 AAC_TopLevelTables_Finals.inventory_turnover_cogs_month:
  month: DATE
  brand: STRING
  country: STRING
  COGS: FLOAT
  val_SOH_bom: FLOAT
  val_HOL_bom: FLOAT
  val_INC_bom: FLOAT
  val_OPS_bom: FLOAT
  val_SOH_eom: FLOAT
  val_HOL_eom: FLOAT
  val_INC_eom: FLOAT
  val_OPS_eom: FLOAT

 AAC_TopLevelTables_Finals.inventoryactualsfcast_month:
  month: DATE
  brand: STRING
  country: STRING
  official_sku: STRING
  sku_type: STRING
  available_plus_transit_plus_opensales_qty_POS: FLOAT
  sales_veloc_adjusted_8Mact_4Mfcast: FLOAT

 AAC_TopLevelTables_Finals.inventoryvalue_month:
  month: DATE
  brand: STRING
  country: STRING
  official_sku: STRING
  sku_type: STRING
  stock_qty: FLOAT
  sales_veloc_adjusted_8Mact_4Mfcast: FLOAT
  sales_veloc_adjusted_12Mfcast: FLOAT

 AAC_TopLevelTables_Finals.po_fcast:
  month: DATE
  brand: STRING
  country: STRING
  official_sku: STRING
  qty_SOH: INTEGER
  units_sold: FLOAT
  ending_inventory: FLOAT

 AAC_TopLevelTables_Finals.ppc_salesunits_month:
  month: DATE
  brand: STRING
  country: STRING
  channel: STRING
  ppc_sales: FLOAT
  ppc_spend: FLOAT

 AAC_TopLevelTables_Finals.ppc_salesunits_week:
  start_of_week: DATE
  brand: STRING
  country: STRING
  channel: STRING
  ppc_sales: FLOAT
  ppc_spend: FLOAT

 AAC_TopLevelTables_Finals.scheduled_pnl_without_calculations:
  date: DATE
  account: STRING
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  pnl_account: STRING
  pnl_account_order: INTEGER
  pnl_subaccount1: STRING
  pnl_subaccount1_order: INTEGER
  pnl_subaccount2: STRING
  pnl_subaccount2_order: INTEGER
  pnl_subaccount3: STRING
  pnl_subaccount3_order: INTEGER
  consolidated_transaction: STRING
  ordered_quantity: NUMERIC
  refund_quantity: NUMERIC
  amount: FLOAT

 AAC_TopLevelTables_Finals.sku_salesunits_month_blend_fcastactuals:
  month: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  sales: FLOAT
  units: FLOAT
  data_type: STRING

 AAC_TopLevelTables_Finals.total_salesunits_month:
  month: DATE
  brand: STRING
  country: STRING
  channel: STRING
  sales: FLOAT
  units: FLOAT
  data_type: STRING

 AAC_TopLevelTables_Finals.total_salesunits_week:
  start_of_week: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  sales: FLOAT
  units: FLOAT
  data_type: STRING

 B2B_business.B2B_BKG_LGB_faire:
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  invoicenumber: STRING
  units: NUMERIC
  sales: FLOAT
  salespromotion: FLOAT
  salesshipping: FLOAT
  refund_quantity: NUMERIC
  refunds: FLOAT
  refundpromotion: NUMERIC
  refundshipping: NUMERIC
  faire_fee: FLOAT
  number_orders: INTEGER
  order_items: INTEGER
  bkg_b2b_commission: FLOAT

 B2B_business.B2B_BKG_LGB_faire_gsheets_support:
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  order_number: STRING
  units: INTEGER
  sales: FLOAT
  number_orders: INTEGER
  order_items: INTEGER
  refund_amount: FLOAT
  sales_promotion: FLOAT
  commission_amount: FLOAT
  platform_costs_amount: FLOAT
  sales_shipping: FLOAT
  bkg_b2b_commission: FLOAT

 B2B_business.B2B_BKG_shopify:
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  sales: FLOAT
  units: NUMERIC
  order_items: INTEGER
  sessions: INTEGER
  number_orders: INTEGER
  shipping_amount: FLOAT
  promo_amount: FLOAT
  transac_amount: FLOAT
  transac_fee: FLOAT
  bkg_b2b_commission: FLOAT

 B2B_business.B2B_BKG_xero:
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  sku: STRING
  invoicenumber: STRING
  bkg_b2b_commission: FLOAT
  number_orders: INTEGER
  order_items: INTEGER
  sales_quantity: NUMERIC
  sales: FLOAT
  salespromotion: NUMERIC
  salesshipping: NUMERIC
  refund_quantity: NUMERIC
  refunds: FLOAT
  refundpromotion: NUMERIC
  refundshipping: NUMERIC

 B2B_business.B2B_Wayfair:
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  invoicenumber: STRING
  units: NUMERIC
  sales: FLOAT
  salespromotion: NUMERIC
  salesshipping: NUMERIC
  wayfair_fee: FLOAT
  number_orders: INTEGER
  order_items: INTEGER

 B2B_business.BKG_B2B_POs:
  Agency: STRING
  Buyer: STRING
  PO_month: DATE
  PO_Date: STRING
  PO__: STRING
  PO_Items_Payment_Received: FLOAT
  PO_Items_Total: FLOAT
  Shipping_Price: FLOAT
  PO_Total: FLOAT
  Commission_Total: FLOAT
  PO_Beneficiary: STRING
  PO_Comments: STRING

 B2B_business.BKG_B2B_POsItems:
  PO__: STRING
  Invoice__: STRING
  Month_Invoice: STRING
  Invoice_Date: STRING
  Paid: BOOLEAN
  Month_Payment: STRING
  Payment_Date: STRING
  Requested_Shipment_Date: STRING
  Shipment_Date: STRING
  Item: STRING
  Quantity: INTEGER
  Item_Price: FLOAT
  Items_Subtotal: INTEGER
  Items_Discount: FLOAT
  Items_Total: FLOAT
  Commission__: FLOAT
  Commission_Amount: FLOAT
  Invoice_Comments: STRING
  string_field_18: STRING
  string_field_19: STRING

 B2B_business.BKG_Orders_Faire:
  Order_Date: DATE
  Order_Number: STRING
  Retailer_Name: STRING
  Address_1: STRING
  Address_2: STRING
  City: STRING
  State: STRING
  Zip_Code: INTEGER
  Country: STRING
  Product_Name: STRING
  Option_Name: STRING
  SKU: STRING
  Status: STRING
  Quantity: INTEGER
  Wholesale_Price: FLOAT
  Retail_Price: FLOAT
  Ship_Date: DATE
  Scheduled_Order_Date: STRING

 B2B_business.BKG_Payouts_Faire:
  Payout_Date: DATE
  Payout_Amount: FLOAT
  Order_Number: STRING
  Retailer_Name: STRING
  Order_Date: DATE
  Order_Total: FLOAT
  Currency: STRING
  Damaged_Or_Missing: FLOAT
  Promotions: FLOAT
  Commission____: INTEGER
  Commission: FLOAT
  Placement_Fee: INTEGER
  Taxes: INTEGER
  Shipping_Costs: FLOAT
  ACH_Next_Day_Fee____: INTEGER
  ACH_Next_Day_Fee: INTEGER

 B2B_business.LGB_Orders_Faire:
  Order_Date: DATE
  Order_Number: STRING
  Retailer_Name: STRING
  Address_1: STRING
  Address_2: STRING
  City: STRING
  State: STRING
  Zip_Code: INTEGER
  Country: STRING
  Product_Name: STRING
  Option_Name: STRING
  SKU: STRING
  Status: STRING
  Quantity: INTEGER
  Wholesale_Price: FLOAT
  Retail_Price: FLOAT
  Ship_Date: DATE
  Scheduled_Order_Date: STRING

 B2B_business.LGB_Payouts_Faire:
  Payout_Date: DATE
  Payout_Amount: FLOAT
  Order_Number: STRING
  Retailer_Name: STRING
  Order_Date: DATE
  Order_Total: FLOAT
  Currency: STRING
  Damaged_Or_Missing: FLOAT
  Promotions: INTEGER
  Commission____: INTEGER
  Commission: FLOAT
  Placement_Fee: INTEGER
  Taxes: INTEGER
  Shipping_Costs: FLOAT
  ACH_Next_Day_Fee____: INTEGER
  ACH_Next_Day_Fee: INTEGER

 COGS.BCK_CA:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKUs: STRING
  Start_of_Month: DATE
  Year: INTEGER
  FOB_Costs: STRING
  Costs_to_Landed: STRING

 COGS.BCK_US:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKUs: STRING
  Start_of_Month: DATE
  Year: INTEGER
  FOB_Costs: FLOAT
  Costs_to_Landed: FLOAT

 COGS.BKG_MX:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKUs: STRING
  Start_of_Month: DATE
  Year: INTEGER
  FOB_Costs: FLOAT
  Costs_to_Landed: FLOAT

 COGS.BKG_US:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKUs: STRING
  Start_of_Month: DATE
  Year: INTEGER
  FOB_Costs: FLOAT
  Costs_to_Landed: FLOAT

 COGS.DUA_US:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKUs: STRING
  Start_of_Month: DATE
  Year: INTEGER
  FOB_Costs: FLOAT
  Costs_to_Landed: INTEGER

 COGS.LGB_CA:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKUs: STRING
  Start_of_Month: DATE
  Year: INTEGER
  FOB_Costs: FLOAT
  Costs_to_Landed: FLOAT

 COGS.LGB_US:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKUs: STRING
  Start_of_Month: DATE
  Year: INTEGER
  FOB_Costs: FLOAT
  Costs_to_Landed: FLOAT

 COGS.RLL_CA:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKUs: STRING
  Start_of_Month: DATE
  Year: INTEGER
  FOB_Costs: FLOAT
  Costs_to_Landed: FLOAT

 COGS.RLL_FR:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKUs: STRING
  Start_of_Month: DATE
  Year: INTEGER
  FOB_Costs: FLOAT
  Costs_to_Landed: FLOAT

 COGS.RLL_GE:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKUs: STRING
  Start_of_Month: DATE
  Year: INTEGER
  FOB_Costs: FLOAT
  Costs_to_Landed: FLOAT

 COGS.RLL_IT:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKUs: STRING
  Start_of_Month: DATE
  Year: INTEGER
  FOB_Costs: FLOAT
  Costs_to_Landed: FLOAT

 COGS.RLL_SPA:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKUs: STRING
  Start_of_Month: DATE
  Year: INTEGER
  FOB_Costs: FLOAT
  Costs_to_Landed: FLOAT

 COGS.RLL_US:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKUs: STRING
  Start_of_Month: DATE
  Year: INTEGER
  FOB_Costs: FLOAT
  Costs_to_Landed: FLOAT

 COGS.SGC_CA:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKUs: STRING
  Start_of_Month: DATE
  Year: INTEGER
  FOB_Costs: STRING
  Costs_to_Landed: STRING

 COGS.SGC_FR:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKUs: STRING
  Start_of_Month: DATE
  Year: INTEGER
  FOB_Costs: FLOAT
  Costs_to_Landed: FLOAT

 COGS.SGC_GE:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKUs: STRING
  Start_of_Month: DATE
  Year: INTEGER
  FOB_Costs: FLOAT
  Costs_to_Landed: FLOAT

 COGS.SGC_IT:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKUs: STRING
  Start_of_Month: DATE
  Year: INTEGER
  FOB_Costs: FLOAT
  Costs_to_Landed: FLOAT

 COGS.SGC_SPA:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKUs: STRING
  Start_of_Month: DATE
  Year: INTEGER
  FOB_Costs: FLOAT
  Costs_to_Landed: FLOAT

 COGS.SGC_US:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKUs: STRING
  Start_of_Month: DATE
  Year: INTEGER
  FOB_Costs: STRING
  Costs_to_Landed: STRING

 COGS.SHK_US:
  Brand: STRING
  Country: STRING
  Channel: STRING
  SKUs: STRING
  Start_of_Month: DATE
  Year: INTEGER
  FOB_Costs: FLOAT
  Costs_to_Landed: FLOAT

 COGS.cin7_stockvaluation_cogs_2022:
  Month: DATE
  Category: STRING
  Product_Name: STRING
  Code: STRING
  Branch: STRING
  Stock_Value: FLOAT
  SOH: INTEGER

 COGS.cin7_stockvaluation_cogs_2023:
  Date: DATE
  Category: STRING
  Product_Name: STRING
  Code: STRING
  Branch: STRING
  Stock_Value: FLOAT
  SOH: INTEGER

 COGS.cin7_stockvaluation_cogs_2024:
  Date: DATE
  Category: STRING
  Product_Name: STRING
  Code: STRING
  Branch: STRING
  Stock_Value: FLOAT
  SOH: INTEGER

 COGS.cin7_stockvaluation_cogs_output:
  months_year: DATE
  brand: STRING
  official_sku: STRING
  country: STRING
  cogs: FLOAT

 COGS.cogs_all_brands:
  brand: STRING
  country: STRING
  channel: STRING
  skus: STRING
  start_of_month: DATE
  fob_costs: FLOAT
  costs_to_landed: FLOAT

 COGS.cogs_sellable_returns:
  return_date: DATE
  brand: STRING
  channel: STRING
  country: STRING
  official_sku: STRING
  return_quantity: NUMERIC
  returned_cogs: FLOAT

 COGS.cost_master_file_interimcogs:
  Month: DATE
  Brand: STRING
  SKU: STRING
  Country: STRING
  Interim_COGS: FLOAT

 COGS.costs_sku_invadj:
  Year: INTEGER
  Brand: STRING
  SKU: STRING
  PO_Code: STRING
  Country: STRING
  Unit_Cost: FLOAT

 COGS.inventory_value_month_cin7:
  month: DATE
  brand: STRING
  inventory_value_bomonth: FLOAT
  inventory_value_eomonth: FLOAT
  avg_inv_value_month: FLOAT
  soh_bomonth: INTEGER
  soh_eomonth: INTEGER
  avg_soh_month: FLOAT

 COGS.landed_cogs_masterfile:
  month: DATE
  brand: STRING
  official_sku: STRING
  country: STRING
  cogs_fixed: FLOAT

 COGS.port_landedcost_masterfile_landedskus:
  string_field_0: STRING
  string_field_1: STRING
  string_field_2: STRING
  string_field_3: STRING
  string_field_4: STRING
  string_field_5: STRING
  string_field_6: STRING
  string_field_7: STRING
  string_field_8: STRING
  string_field_9: STRING
  string_field_10: STRING
  string_field_11: STRING
  string_field_12: STRING
  string_field_13: STRING
  string_field_14: STRING
  string_field_15: STRING

 COGS.sellable_returns:
  order_date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  return_quantity: NUMERIC

 COGS.sostocked_pos_2024_2025:
  ASIN: STRING
  SKU_MARKETPLACE: STRING
  SKU: STRING
  MARKETPLACE: STRING
  January_2024: INTEGER
  February_2024: INTEGER
  March_2024: INTEGER
  April_2024: INTEGER
  May_2024: INTEGER
  June_2024: INTEGER
  July_2024: INTEGER
  August_2024: INTEGER
  September_2024: INTEGER
  October_2024: INTEGER
  November_2024: INTEGER
  December_2024: INTEGER
  January_2025: INTEGER
  February_2025: INTEGER
  March_2025: INTEGER
  April_2025: INTEGER
  May_2025: INTEGER
  June_2025: INTEGER
  July_2025: INTEGER
  August_2025: INTEGER
  September_2025: INTEGER
  October_2025: INTEGER
  November_2025: INTEGER
  December_2025: INTEGER

 COGS.sostocked_pos_2024_2025_view:
  month: DATE
  brand: STRING
  official_sku: STRING
  country: STRING
  sostocked_units_sold_fcast: INTEGER
  cogs: FLOAT
  total_cogs: FLOAT

 Ebay.eBay-promoted-listing-advanced_BCK_2022:
  Start_date: STRING
  End_date: STRING
  Date: DATE
  Campaign_name: STRING
  Campaign_ID: STRING
  Campaign_start_date: STRING
  Campaign_end_date: STRING
  Impressions: INTEGER
  Clicks: INTEGER
  CTR: STRING
  Sold_quantity: INTEGER
  Ad_fees: FLOAT
  Sales: FLOAT

 Ebay.eBay-promoted-listing-standard_BCK_2022:
  Campaign_name: STRING
  Campaign_ID: FLOAT
  Campaign_start_date: DATE
  Campaign_end_date: STRING
  Date: DATE
  Item_ID: FLOAT
  Title: STRING
  Price__Current_or_Last_Price_: FLOAT
  Quantity_available: INTEGER
  Listing_start_date: STRING
  Listing_end_date: STRING
  Promoted_Listings_Impressions__via_eBay_Placements_: INTEGER
  Total_Promoted_Listings_Clicks: INTEGER
  Total_Promoted_Listings_Sold_quantity: INTEGER
  Organic_Sold_Quantity: INTEGER
  Total_Quantity_Sold: INTEGER
  Promoted_Listings_Conversion_rate__Promoted_Listings_Sold_quantity_Promoted_Listings_Clicks_: FLOAT
  Promoted_Listings_Contribution__Promoted_Listings_Sold_quantity_Total_Quantity_Sold_: FLOAT
  Total_Promoted_Listings_Sales: FLOAT
  Ad_fees: FLOAT
  Return_on_Ad_spend__Sales_Ad_fees_: INTEGER
  Average_cost_per_sale: INTEGER
  Promoted_Listings_Clicks__via_eBay_placements_: INTEGER
  Promoted_Listings_Clicks__via_external_placements_: INTEGER
  Promoted_Listings_Sold_Quantity__via_eBay_placements_: INTEGER
  Promoted_Listings_Sold_Quantity__via_external_placements_: INTEGER
  Promoted_Listings_Sales__via_eBay_placements_: INTEGER
  Promoted_Listings_Sales__via_external_placements_: INTEGER
  Ad_fees__via_eBay_placements_: INTEGER
  Ad_fees__via_external_placements_: INTEGER
  Promoted_Listings_Conversion_Rate__via_eBay_placements_: FLOAT
  Promoted_Listings_Conversion_Rate__via_external_placements_: FLOAT
  Organic_Clicks: INTEGER
  Organic_Impressions: INTEGER

 Ebay.eBay-promoted-listing-standard_BCK_2023:
  Campaign_name: STRING
  Campaign_ID: INTEGER
  Campaign_start_date: DATE
  Campaign_end_date: STRING
  Date: DATE
  Item_ID: FLOAT
  Title: STRING
  Price__Current_or_Last_Price_: FLOAT
  Quantity_available: INTEGER
  Listing_start_date: DATE
  Listing_end_date: DATE
  Promoted_Listings_Impressions__via_eBay_Placements_: INTEGER
  Total_Promoted_Listings_Clicks: INTEGER
  Total_Promoted_Listings_Sold_quantity: INTEGER
  Organic_Sold_Quantity: INTEGER
  Total_Quantity_Sold: INTEGER
  Promoted_Listings_Conversion_rate__Promoted_Listings_Sold_quantity_Promoted_Listings_Clicks_: FLOAT
  Promoted_Listings_Contribution__Promoted_Listings_Sold_quantity_Total_Quantity_Sold_: FLOAT
  Total_Promoted_Listings_Sales: INTEGER
  Ad_fees: INTEGER
  Return_on_Ad_spend__Sales_Ad_fees_: INTEGER
  Average_cost_per_sale: INTEGER
  Promoted_Listings_Clicks__via_eBay_placements_: INTEGER
  Promoted_Listings_Clicks__via_external_placements_: INTEGER
  Promoted_Listings_Sold_Quantity__via_eBay_placements_: INTEGER
  Promoted_Listings_Sold_Quantity__via_external_placements_: STRING
  Promoted_Listings_Sales__via_eBay_placements_: INTEGER
  Promoted_Listings_Sales__via_external_placements_: STRING
  Ad_fees__via_eBay_placements_: INTEGER
  Ad_fees__via_external_placements_: STRING
  Promoted_Listings_Conversion_Rate__via_eBay_placements_: FLOAT
  Promoted_Listings_Conversion_Rate__via_external_placements_: FLOAT
  Organic_Clicks: INTEGER
  Organic_Impressions: INTEGER

 Ebay.eBay-promoted-listing-standard_BKG_2022:
  Campaign_name: STRING
  Campaign_ID: FLOAT
  Campaign_start_date: DATE
  Campaign_end_date: STRING
  Date: DATE
  Item_ID: FLOAT
  Title: STRING
  Price__Current_or_Last_Price_: FLOAT
  Quantity_available: INTEGER
  Listing_start_date: STRING
  Listing_end_date: STRING
  Promoted_Listings_Impressions__via_eBay_Placements_: INTEGER
  Total_Promoted_Listings_Clicks: INTEGER
  Total_Promoted_Listings_Sold_quantity: INTEGER
  Organic_Sold_Quantity: INTEGER
  Total_Quantity_Sold: INTEGER
  Promoted_Listings_Conversion_rate__Promoted_Listings_Sold_quantity_Promoted_Listings_Clicks_: FLOAT
  Promoted_Listings_Contribution__Promoted_Listings_Sold_quantity_Total_Quantity_Sold_: FLOAT
  Total_Promoted_Listings_Sales: INTEGER
  Ad_fees: INTEGER
  Return_on_Ad_spend__Sales_Ad_fees_: INTEGER
  Average_cost_per_sale: INTEGER
  Promoted_Listings_Clicks__via_eBay_placements_: INTEGER
  Promoted_Listings_Clicks__via_external_placements_: INTEGER
  Promoted_Listings_Sold_Quantity__via_eBay_placements_: INTEGER
  Promoted_Listings_Sold_Quantity__via_external_placements_: STRING
  Promoted_Listings_Sales__via_eBay_placements_: INTEGER
  Promoted_Listings_Sales__via_external_placements_: STRING
  Ad_fees__via_eBay_placements_: INTEGER
  Ad_fees__via_external_placements_: STRING
  Promoted_Listings_Conversion_Rate__via_eBay_placements_: FLOAT
  Promoted_Listings_Conversion_Rate__via_external_placements_: FLOAT
  Organic_Clicks: INTEGER
  Organic_Impressions: INTEGER

 Ebay.eBay-promoted-listing-standard_BKG_2023:
  Campaign_name: STRING
  Campaign_ID: INTEGER
  Campaign_start_date: DATE
  Campaign_end_date: STRING
  Date: DATE
  Item_ID: FLOAT
  Title: STRING
  Price__Current_or_Last_Price_: FLOAT
  Quantity_available: INTEGER
  Listing_start_date: DATE
  Listing_end_date: DATE
  Promoted_Listings_Impressions__via_eBay_Placements_: INTEGER
  Total_Promoted_Listings_Clicks: INTEGER
  Total_Promoted_Listings_Sold_quantity: INTEGER
  Organic_Sold_Quantity: INTEGER
  Total_Quantity_Sold: INTEGER
  Promoted_Listings_Conversion_rate__Promoted_Listings_Sold_quantity_Promoted_Listings_Clicks_: FLOAT
  Promoted_Listings_Contribution__Promoted_Listings_Sold_quantity_Total_Quantity_Sold_: FLOAT
  Total_Promoted_Listings_Sales: INTEGER
  Ad_fees: INTEGER
  Return_on_Ad_spend__Sales_Ad_fees_: INTEGER
  Average_cost_per_sale: INTEGER
  Promoted_Listings_Clicks__via_eBay_placements_: INTEGER
  Promoted_Listings_Clicks__via_external_placements_: INTEGER
  Promoted_Listings_Sold_Quantity__via_eBay_placements_: INTEGER
  Promoted_Listings_Sold_Quantity__via_external_placements_: STRING
  Promoted_Listings_Sales__via_eBay_placements_: INTEGER
  Promoted_Listings_Sales__via_external_placements_: STRING
  Ad_fees__via_eBay_placements_: INTEGER
  Ad_fees__via_external_placements_: STRING
  Promoted_Listings_Conversion_Rate__via_eBay_placements_: FLOAT
  Promoted_Listings_Conversion_Rate__via_external_placements_: FLOAT
  Organic_Clicks: INTEGER
  Organic_Impressions: INTEGER

 Ebay.ebay_ActiveListingsTraffic_BCK_2022:
  Week: DATE
  Listing_title: STRING
  eBay_item_ID: FLOAT
  Current_promoted_listings_status: STRING
  Quantity_available: INTEGER
  Total_impressions_on_eBay_site: INTEGER
  Top_20_search_slot_impressions_from_promoted_listings: INTEGER
  __change_in_top_20_search_slot_impressions_from_promoted_listings: FLOAT
  Top_20_search_slot_organic_impressions: INTEGER
  __change_in_top_20_search_slot_impressions: FLOAT
  Rest_of_search_slot_impressions: INTEGER
  Non_search_promoted_listings_impressions: INTEGER
  __Change_in_non_search_promoted_listings_impressions: STRING
  Non_search_organic_impressions: INTEGER
  __Change_in_non_search_organic_impressions: STRING
  Total_promoted_listings_impressions__applies_to_eBay_site_only_: INTEGER
  Total_organic_impressions_on_eBay_site: INTEGER
  Total_page_views: INTEGER
  Page_views_via_promoted_listings_impressions_on_eBay_site: INTEGER
  Page_views_via_promoted_listings_Impressions_from_outside_eBay__search_engines__affilliates_: INTEGER
  Page_views_via_organic_impressions_on_eBay_site: INTEGER
  Page_views_from_organic_impressions_outside_eBay__Includes_page_views_from_search_engines_: INTEGER
  Click_through_rate___Page_views_from_eBay_site_Total_impressions: FLOAT
  Quantity_sold: INTEGER
  Sales_conversion_rate___Quantity_sold_Total_page_views: FLOAT

 Ebay.ebay_ActiveListingsTraffic_BCK_2023:
  Week: DATE
  Listing_title: STRING
  eBay_item_ID: FLOAT
  Current_promoted_listings_status: STRING
  Quantity_available: INTEGER
  Total_impressions_on_eBay_site: STRING
  Top_20_search_slot_impressions_from_promoted_listings: STRING
  __change_in_top_20_search_slot_impressions_from_promoted_listings: STRING
  Top_20_search_slot_organic_impressions: STRING
  __change_in_top_20_search_slot_impressions: STRING
  Rest_of_search_slot_impressions: STRING
  Non_search_promoted_listings_impressions: STRING
  __Change_in_non_search_promoted_listings_impressions: STRING
  Non_search_organic_impressions: STRING
  __Change_in_non_search_organic_impressions: STRING
  Total_promoted_listings_impressions__applies_to_eBay_site_only_: STRING
  Total_organic_impressions_on_eBay_site: STRING
  Total_page_views: STRING
  Page_views_via_promoted_listings_impressions_on_eBay_site: STRING
  Page_views_via_promoted_listings_Impressions_from_outside_eBay__search_engines__affilliates_: STRING
  Page_views_via_organic_impressions_on_eBay_site: STRING
  Page_views_from_organic_impressions_outside_eBay__Includes_page_views_from_search_engines_: STRING
  Click_through_rate___Page_views_from_eBay_site_Total_impressions: STRING
  Quantity_sold: INTEGER
  Sales_conversion_rate___Quantity_sold_Total_page_views: STRING

 Ebay.ebay_ActiveListingsTraffic_BCK_2024:
  Week: DATE
  Listing_title: STRING
  eBay_item_ID: FLOAT
  Current_promoted_listings_status: STRING
  Quantity_available: INTEGER
  Total_impressions_on_eBay_site: INTEGER
  Total_page_views: INTEGER

 Ebay.ebay_ActiveListingsTraffic_BKG_2022:
  Week: DATE
  Listing_title: STRING
  eBay_item_ID: FLOAT
  Current_promoted_listings_status: STRING
  Quantity_available: INTEGER
  Total_impressions_on_eBay_site: INTEGER
  Top_20_search_slot_impressions_from_promoted_listings: INTEGER
  __change_in_top_20_search_slot_impressions_from_promoted_listings: FLOAT
  Top_20_search_slot_organic_impressions: INTEGER
  __change_in_top_20_search_slot_impressions: FLOAT
  Rest_of_search_slot_impressions: INTEGER
  Non_search_promoted_listings_impressions: INTEGER
  __Change_in_non_search_promoted_listings_impressions: FLOAT
  Non_search_organic_impressions: INTEGER
  __Change_in_non_search_organic_impressions: FLOAT
  Total_promoted_listings_impressions__applies_to_eBay_site_only_: INTEGER
  Total_organic_impressions_on_eBay_site: INTEGER
  Total_page_views: INTEGER
  Page_views_via_promoted_listings_impressions_on_eBay_site: INTEGER
  Page_views_via_promoted_listings_Impressions_from_outside_eBay__search_engines__affilliates_: INTEGER
  Page_views_via_organic_impressions_on_eBay_site: INTEGER
  Page_views_from_organic_impressions_outside_eBay__Includes_page_views_from_search_engines_: INTEGER
  Click_through_rate___Page_views_from_eBay_site_Total_impressions: FLOAT
  Quantity_sold: INTEGER
  Sales_conversion_rate___Quantity_sold_Total_page_views: FLOAT

 Ebay.ebay_ActiveListingsTraffic_BKG_2023:
  Week: DATE
  Listing_title: STRING
  eBay_item_ID: FLOAT
  Current_promoted_listings_status: STRING
  Quantity_available: INTEGER
  Total_impressions_on_eBay_site: INTEGER
  Top_20_search_slot_impressions_from_promoted_listings: INTEGER
  __change_in_top_20_search_slot_impressions_from_promoted_listings: STRING
  Top_20_search_slot_organic_impressions: INTEGER
  __change_in_top_20_search_slot_impressions: FLOAT
  Rest_of_search_slot_impressions: INTEGER
  Non_search_promoted_listings_impressions: INTEGER
  __Change_in_non_search_promoted_listings_impressions: STRING
  Non_search_organic_impressions: INTEGER
  __Change_in_non_search_organic_impressions: FLOAT
  Total_promoted_listings_impressions__applies_to_eBay_site_only_: INTEGER
  Total_organic_impressions_on_eBay_site: INTEGER
  Total_page_views: INTEGER
  Page_views_via_promoted_listings_impressions_on_eBay_site: INTEGER
  Page_views_via_promoted_listings_Impressions_from_outside_eBay__search_engines__affilliates_: INTEGER
  Page_views_via_organic_impressions_on_eBay_site: INTEGER
  Page_views_from_organic_impressions_outside_eBay__Includes_page_views_from_search_engines_: INTEGER
  Click_through_rate___Page_views_from_eBay_site_Total_impressions: FLOAT
  Quantity_sold: INTEGER
  Sales_conversion_rate___Quantity_sold_Total_page_views: STRING

 Ebay.ebay_ActiveListingsTraffic_BKG_2024:
  Week: DATE
  Listing_title: STRING
  eBay_item_ID: FLOAT
  Current_promoted_listings_status: STRING
  Quantity_available: INTEGER
  Total_impressions_on_eBay_site: INTEGER
  Total_page_views: INTEGER

 Ebay.ebay_ppc_metrics:
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  spend: FLOAT
  ppc_sales: FLOAT
  clicks: INTEGER
  impressions: INTEGER
  number_of_orders: INTEGER

 Ebay.ebay_sales:
  date: DATE
  brand: STRING
  Item_title: STRING
  Custom_label: STRING
  order_number: STRING
  sales: FLOAT
  units: INTEGER
  order_items: INTEGER
  number_orders: INTEGER

 Ebay.ebay_sessions:
  date: DATE
  Item_title: STRING
  custom_label: STRING
  sessions: INTEGER

 Ebay.ebay_transactionsreport_BCK_2022:
  Transaction_creation_date: DATE
  Type: STRING
  Order_number: STRING
  Legacy_order_ID: STRING
  Buyer_username: STRING
  Buyer_name: STRING
  Ship_to_city: STRING
  Ship_to_province_region_state: STRING
  Ship_to_zip: STRING
  Ship_to_country: STRING
  Net_amount: STRING
  Payout_currency: STRING
  Payout_date: STRING
  Payout_ID: INTEGER
  Payout_method: STRING
  Payout_status: STRING
  Reason_for_hold: STRING
  Item_ID: STRING
  Transaction_ID: STRING
  Item_title: STRING
  Custom_label: STRING
  Quantity: STRING
  Item_subtotal: STRING
  Shipping_and_handling: STRING
  Seller_collected_tax: STRING
  eBay_collected_tax: STRING
  Final_Value_Fee___fixed: STRING
  Final_Value_Fee___variable: STRING
  Very_high__item_not_as_described__fee: STRING
  Below_standard_performance_fee: STRING
  International_fee: STRING
  Deposit_processing_fee: STRING
  Gross_transaction_amount: STRING
  Transaction_currency: STRING
  Exchange_rate: STRING
  Reference_ID: STRING
  Description: STRING

 Ebay.ebay_transactionsreport_BCK_2023:
  Transaction_creation_date: DATE
  Type: STRING
  Order_number: STRING
  Legacy_order_ID: STRING
  Buyer_username: STRING
  Buyer_name: STRING
  Ship_to_city: STRING
  Ship_to_province_region_state: STRING
  Ship_to_zip: STRING
  Ship_to_country: STRING
  Net_amount: FLOAT
  Payout_currency: STRING
  Payout_date: STRING
  Payout_ID: FLOAT
  Payout_method: STRING
  Payout_status: STRING
  Reason_for_hold: STRING
  Item_ID: STRING
  Transaction_ID: STRING
  Item_title: STRING
  Custom_label: STRING
  Quantity: STRING
  Item_subtotal: STRING
  Shipping_and_handling: STRING
  Seller_collected_tax: STRING
  eBay_collected_tax: STRING
  Final_Value_Fee___fixed: STRING
  Final_Value_Fee___variable: STRING
  Very_high__item_not_as_described__fee: STRING
  Below_standard_performance_fee: STRING
  International_fee: STRING
  Deposit_processing_fee: STRING
  Gross_transaction_amount: FLOAT
  Transaction_currency: STRING
  Exchange_rate: STRING
  Reference_ID: STRING
  Description: STRING

 Ebay.ebay_transactionsreport_BCK_2024:
  Transaction_creation_date: DATE
  Type: STRING
  Order_number: STRING
  Legacy_order_ID: STRING
  Buyer_username: STRING
  Buyer_name: STRING
  Ship_to_city: STRING
  Ship_to_province_region_state: STRING
  Ship_to_zip: STRING
  Ship_to_country: STRING
  Net_amount: FLOAT
  Payout_currency: STRING
  Payout_date: STRING
  Payout_ID: FLOAT
  Payout_method: STRING
  Payout_status: STRING
  Reason_for_hold: STRING
  Item_ID: STRING
  Transaction_ID: STRING
  Item_title: STRING
  Custom_label: STRING
  Quantity: STRING
  Item_subtotal: STRING
  Shipping_and_handling: STRING
  Seller_collected_tax: STRING
  eBay_collected_tax: STRING
  Final_Value_Fee___fixed: STRING
  Final_Value_Fee___variable: STRING
  Very_high__item_not_as_described__fee: STRING
  Below_standard_performance_fee: STRING
  International_fee: STRING
  Deposit_processing_fee: STRING
  other_fee: STRING
  Gross_transaction_amount: FLOAT
  Transaction_currency: STRING
  Exchange_rate: STRING
  Reference_ID: STRING
  Description: STRING

 Ebay.ebay_transactionsreport_BKG_2022:
  Transaction_creation_date: DATE
  Type: STRING
  Order_number: STRING
  Legacy_order_ID: STRING
  Buyer_username: STRING
  Buyer_name: STRING
  Ship_to_city: STRING
  Ship_to_province_region_state: STRING
  Ship_to_zip: STRING
  Ship_to_country: STRING
  Net_amount: FLOAT
  Payout_currency: STRING
  Payout_date: STRING
  Payout_ID: INTEGER
  Payout_method: STRING
  Payout_status: STRING
  Reason_for_hold: STRING
  Item_ID: STRING
  Transaction_ID: STRING
  Item_title: STRING
  Custom_label: STRING
  Quantity: STRING
  Item_subtotal: STRING
  Shipping_and_handling: STRING
  Seller_collected_tax: STRING
  eBay_collected_tax: STRING
  Final_Value_Fee___fixed: STRING
  Final_Value_Fee___variable: STRING
  Very_high__item_not_as_described__fee: STRING
  Below_standard_performance_fee: STRING
  International_fee: STRING
  Deposit_processing_fee: STRING
  Gross_transaction_amount: FLOAT
  Transaction_currency: STRING
  Exchange_rate: STRING
  Reference_ID: STRING
  Description: STRING

 Ebay.ebay_transactionsreport_BKG_2023:
  Transaction_creation_date: DATE
  Type: STRING
  Order_number: STRING
  Legacy_order_ID: STRING
  Buyer_username: STRING
  Buyer_name: STRING
  Ship_to_city: STRING
  Ship_to_province_region_state: STRING
  Ship_to_zip: STRING
  Ship_to_country: STRING
  Net_amount: FLOAT
  Payout_currency: STRING
  Payout_date: STRING
  Payout_ID: INTEGER
  Payout_method: STRING
  Payout_status: STRING
  Reason_for_hold: STRING
  Item_ID: STRING
  Transaction_ID: STRING
  Item_title: STRING
  Custom_label: STRING
  Quantity: STRING
  Item_subtotal: STRING
  Shipping_and_handling: STRING
  Seller_collected_tax: STRING
  eBay_collected_tax: STRING
  Final_Value_Fee___fixed: STRING
  Final_Value_Fee___variable: STRING
  Very_high__item_not_as_described__fee: STRING
  Below_standard_performance_fee: STRING
  International_fee: STRING
  Deposit_processing_fee: STRING
  Gross_transaction_amount: FLOAT
  Transaction_currency: STRING
  Exchange_rate: STRING
  Reference_ID: STRING
  Description: STRING

 Ebay.ebay_transactionsreport_BKG_2024:
  Transaction_creation_date: DATE
  Type: STRING
  Order_number: STRING
  Legacy_order_ID: STRING
  Buyer_username: STRING
  Buyer_name: STRING
  Ship_to_city: STRING
  Ship_to_province_region_state: STRING
  Ship_to_zip: STRING
  Ship_to_country: STRING
  Net_amount: FLOAT
  Payout_currency: STRING
  Payout_date: STRING
  Payout_ID: STRING
  Payout_method: STRING
  Payout_status: STRING
  Reason_for_hold: STRING
  Item_ID: FLOAT
  Transaction_ID: STRING
  Item_title: STRING
  Custom_label: STRING
  Quantity: STRING
  Item_subtotal: STRING
  Shipping_and_handling: STRING
  Seller_collected_tax: STRING
  eBay_collected_tax: STRING
  Final_Value_Fee___fixed: STRING
  Final_Value_Fee___variable: STRING
  Very_high__item_not_as_described__fee: STRING
  Below_standard_performance_fee: STRING
  International_fee: STRING
  Deposit_processing_fee: STRING
  other_fee: STRING
  Gross_transaction_amount: FLOAT
  Transaction_currency: STRING
  Exchange_rate: STRING
  Reference_ID: STRING
  Description: STRING

 Ebay.ebay_wbr_sales:
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  sales: FLOAT
  units: INTEGER
  order_items: INTEGER
  sessions: INTEGER
  number_orders: INTEGER

 Etsy.daton_metadata:
  table_name: STRING
  daton_source_name: STRING
  daton_table_name: STRING
  column_name: STRING
  daton_column_name: STRING
  in_use: BOOLEAN
  created: INTEGER
  updated: INTEGER

 Etsy.etsy_ListingsByShop:
  _daton_user_id: NUMERIC
  _daton_batch_runtime: NUMERIC
  _daton_batch_id: NUMERIC
  price: RECORD
  ListingImages: RECORD
  ListingInventory: RECORD
  listing_id: INTEGER
  user_id: INTEGER
  shop_id: INTEGER
  title: STRING
  description: STRING
  state: STRING
  creation_timestamp: INTEGER
  created_timestamp: INTEGER
  ending_timestamp: INTEGER
  original_creation_timestamp: INTEGER
  last_modified_timestamp: INTEGER
  updated_timestamp: INTEGER
  state_timestamp: INTEGER
  quantity: INTEGER
  shop_section_id: INTEGER
  featured_rank: INTEGER
  url: STRING
  num_favorers: INTEGER
  non_taxable: BOOLEAN
  is_taxable: BOOLEAN
  is_customizable: BOOLEAN
  is_personalizable: BOOLEAN
  personalization_is_required: BOOLEAN
  listing_type: STRING
  tags: STRING
  materials: STRING
  shipping_profile_id: NUMERIC
  processing_min: INTEGER
  processing_max: INTEGER
  who_made: STRING
  when_made: STRING
  is_supply: BOOLEAN
  is_private: BOOLEAN
  file_data: STRING
  has_variations: BOOLEAN
  should_auto_renew: BOOLEAN
  language: STRING
  taxonomy_id: INTEGER
  skus: STRING
  item_weight: INTEGER
  item_weight_unit: STRING
  item_length: INTEGER
  item_width: INTEGER
  item_height: INTEGER
  item_dimensions_unit: STRING
  views: INTEGER
  return_policy_id: NUMERIC

 Etsy.etsy_Receipts:
  grandtotal: RECORD
  subtotal: RECORD
  total_price: RECORD
  total_shipping_cost: RECORD
  total_tax_cost: RECORD
  total_vat_cost: RECORD
  discount_amt: RECORD
  gift_wrap_price: RECORD
  transactions: RECORD
  receipt_id: NUMERIC
  receipt_type: INTEGER
  seller_user_id: INTEGER
  seller_email: STRING
  buyer_user_id: INTEGER
  buyer_email: STRING
  name: STRING
  first_line: STRING
  second_line: STRING
  city: STRING
  state: STRING
  zip: STRING
  status: STRING
  formatted_address: STRING
  country_iso: STRING
  payment_method: STRING
  payment_email: STRING
  message_from_buyer: STRING
  is_shipped: BOOLEAN
  is_paid: BOOLEAN
  create_timestamp: INTEGER
  created_timestamp: INTEGER
  update_timestamp: INTEGER
  updated_timestamp: INTEGER
  is_gift: BOOLEAN
  gift_message: STRING
  shipments: RECORD
  receipt_id_in: INTEGER
  refunds: RECORD
  _daton_user_id: NUMERIC
  _daton_batch_runtime: NUMERIC
  _daton_batch_id: NUMERIC
  message_from_seller: STRING

 Etsy.etsy_Reviews:
  _daton_user_id: NUMERIC
  _daton_batch_runtime: NUMERIC
  _daton_batch_id: NUMERIC
  shop_id: INTEGER
  listing_id: INTEGER
  transaction_id: NUMERIC
  buyer_user_id: INTEGER
  rating: INTEGER
  review: STRING
  language: STRING
  create_timestamp: INTEGER
  created_timestamp: INTEGER
  update_timestamp: INTEGER
  updated_timestamp: INTEGER
  image_url_fullxfull: STRING
  transaction_id_in: INTEGER

 Etsy.etsy_Transactions:
  price: RECORD
  shipping_cost: RECORD
  transaction_id: NUMERIC
  title: STRING
  description: STRING
  seller_user_id: INTEGER
  buyer_user_id: INTEGER
  create_timestamp: INTEGER
  created_timestamp: INTEGER
  paid_timestamp: INTEGER
  quantity: INTEGER
  listing_image_id: NUMERIC
  receipt_id: NUMERIC
  is_digital: BOOLEAN
  file_data: STRING
  listing_id: INTEGER
  sku: STRING
  product_id: NUMERIC
  transaction_type: STRING
  shipping_profile_id: NUMERIC
  min_processing_days: INTEGER
  max_processing_days: INTEGER
  expected_ship_date: INTEGER
  buyer_coupon: INTEGER
  shop_coupon: INTEGER
  variations: RECORD
  product_data: RECORD
  shipped_timestamp: INTEGER
  buyer_coupon_nu: NUMERIC
  shop_coupon_nu: NUMERIC
  listing_image_id_in: INTEGER
  product_id_in: INTEGER
  receipt_id_in: INTEGER
  transaction_id_in: INTEGER
  _daton_user_id: NUMERIC
  _daton_batch_runtime: NUMERIC
  _daton_batch_id: NUMERIC

 Etsy.etsy_ads_2021:
  Date: DATE
  Spend: FLOAT
  Sales: FLOAT
  Clicks: INTEGER
  Impressions: INTEGER
  Number_of_Orders: INTEGER

 Etsy.etsy_ads_2022:
  Date: DATE
  Spend: FLOAT
  Sales: FLOAT
  Clicks: INTEGER
  Impressions: INTEGER
  Number_of_Orders: INTEGER

 Etsy.etsy_ads_2023:
  Date: DATE
  Spend: FLOAT
  Sales: INTEGER
  Clicks: INTEGER
  Impressions: INTEGER
  Number_of_Orders: INTEGER

 Etsy.etsy_ads_2024:
  Date: DATE
  Spend: FLOAT
  Sales: INTEGER
  Clicks: INTEGER
  Impressions: INTEGER
  Number_of_Orders: INTEGER

 Etsy.etsy_ppc_metrics:
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  official_sku: STRING
  spend: FLOAT
  ppc_sales: FLOAT
  clicks: INTEGER
  impressions: INTEGER
  number_of_orders: INTEGER

 Etsy.etsy_sales:
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  sku: STRING
  receipt_id: NUMERIC
  sales: FLOAT
  quantity: INTEGER
  order_items: INTEGER
  number_orders: INTEGER

 Etsy.etsy_visits:
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  weighted_visits: INTEGER

 Etsy.etsy_visits_2021:
  Date: DATE
  Visits: INTEGER

 Etsy.etsy_visits_2022:
  Date: DATE
  Visits: INTEGER

 Etsy.etsy_visits_2023:
  Date: DATE
  Visits: INTEGER

 Etsy.etsy_visits_2024:
  Date: DATE
  Visits: INTEGER

 Etsy.etsy_wbr_sales:
  date: DATE
  brand: STRING
  country: STRING
  channel: STRING
  sku: STRING
  sales: FLOAT
  units: INTEGER
  order_items: INTEGER
  sessions: INTEGER
  number_orders: INTEGER
