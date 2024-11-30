Date last edited: 11/29/2024 at 7:15pm PT
Max N is 250.  

## Successful Plans

### Find optimal customers for re-engagement. Find customers most likely to order again.
```json
{
  "Plan": {
    "1": {
      "Request": "Calculate Recency, Frequency, and Monetary (RFM) scores for each customer using orders data.",
      "DataNeeded": "orders",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A dataset containing customer IDs and their calculated RFM scores (Recency, Frequency, Monetary values)."
    },
    "2": {
      "Request": "Calculate Customer Lifetime Value (CLV) for each customer using orders data.",
      "DataNeeded": "orders",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A dataset containing customer IDs and their calculated CLV values."
    },
    "3": {
      "Request": "Analyze purchase frequency trends to identify customers with declining activity.",
      "DataNeeded": "orders",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A list of customer IDs identified as having declining purchase frequency over time."
    },
    "4": {
      "Request": "Calculate the time since the last purchase for each customer.",
      "DataNeeded": "orders",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A dataset containing customer IDs and the number of days since their last purchase."
    },
    "5": {
      "Request": "Combine RFM scores, CLV, purchase trends, and time since last purchase to rank customers who haven't ordered in last N days.",
      "DataNeeded": "1, 2, 3, 4",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A ranked list of customer IDs who haven't ordered in the last N days, including their combined analysis scores."
    },
    "6": {
      "Request": "Identify and rank the top S customers for re-engagement based on the combined analysis.",
      "DataNeeded": "5",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A final ranked list of the top S customer IDs suitable for re-engagement."
    }
  }
}
```

### Segment customers based on their preferred shopping time (morning, afternoon, evening) and day of the week.
```json
{
  "Plan": {
    "1": {
      "Request": "Extract customer IDs and order timestamps from the orders data.",
      "DataNeeded": "orders",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A dataset containing customer IDs and their order timestamps."
    },
    "2": {
      "Request": "Determine the preferred shopping time (morning, afternoon, evening) and day of the week for each customer based on their order timestamps.",
      "DataNeeded": "1",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A dataset with customer IDs and their preferred shopping times and days of the week."
    },
    "3": {
      "Request": "Segment customers into groups based on their preferred shopping time and day of the week.",
      "DataNeeded": "2",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "Groups of customer IDs segmented by preferred shopping time and day."
    }
  }
}
```

### Find customers with high order volumes in the past
```json
{
  "Plan": {
    "1": {
      "Request": "Count the number of orders for each customer using orders data.",
      "DataNeeded": "orders",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A dataset with customer IDs and their total number of orders."
    },
    "2": {
      "Request": "Identify customers with high order volumes based on the counts.",
      "DataNeeded": "1",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A list of customer IDs who have high order volumes, exceeding a defined threshold."
    }
  }
}
```

### Filter this product list down to products most similar to X
```json
{
  "Plan": {
    "1": {
      "Request": "Filter the product list to find products most similar to product X.",
      "DataNeeded": "products, prompt",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A list of product IDs and names that are similar to product X."
    }
  }
}
```

### Find customers who made a purchase _+ days ago with no new purchase since then who are good fits for re-engagement. Select 10 likely to repurchase and generate a personalized email based on a given template:
```json
{
  "Plan": {
    "1": {
      "Request": "Identify customers who haven't made a purchase in the last N days, including their last order date and total number of orders.",
      "DataNeeded": "orders, customers",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A list of customer IDs who haven't ordered in the last N days, with their last order date and total orders."
    },
    "2": {
      "Request": "Select the top 10 customers most likely to repurchase based on past behavior.",
      "DataNeeded": "1",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A list of the top 10 customer IDs with high likelihood to repurchase."
    }
  }
}
```

### Select a cohort of customers that are highly likely to repurchase an item and haven't purchased recently, then sub-segment them into similar users, then personalize an email to each.
```json
{
  "Plan": {
    "1": {
      "Request": "Get a list of customers who haven't made a purchase in the last 3 months.",
      "DataNeeded": "orders",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A list of customer IDs who haven't purchased in the last 3 months."
    },
    "2": {
      "Request": "From the list in step 1, select customers with multiple past orders.",
      "DataNeeded": "1, orders",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A refined list of customer IDs with multiple past purchases."
    },
    "3": {
      "Request": "Compile a list of products purchased by each customer in the refined list.",
      "DataNeeded": "2, orders",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A mapping of customer IDs to their purchased products."
    },
    "4": {
      "Request": "Sub-segment the customers into groups based on similar purchase histories.",
      "DataNeeded": "3",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "Segments of customers grouped by similar product interests."
    }
  }
}
```

### Identify which customers are most likely to purchase product X
```json
{
  "Plan": {
    "1": {
      "Request": "Create a list of all product names and IDs.",
      "DataNeeded": "products",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A dataset of product IDs and names."
    },
    "2": {
      "Request": "Filter the product list to find products similar to product X.",
      "DataNeeded": "1, prompt",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A list of product IDs and names similar to product X."
    },
    "3": {
      "Request": "Identify customers who have purchased any products from the similar products list.",
      "DataNeeded": "2, orders",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A list of customer IDs who purchased similar products."
    },
    "4": {
      "Request": "Retrieve detailed information on the customers identified in step 3.",
      "DataNeeded": "3, customers",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "Customer details (e.g., name, email) for targeted marketing."
    }
  }
}
```

### Find Customers who purchased product X and also product Y
```json
{
  "Plan": {
    "1": {
      "Request": "Identify customers who purchased both product X and product Y.",
      "DataNeeded": "orders, prompt",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A list of customer IDs who purchased both products."
    },
    "2": {
      "Request": "Retrieve detailed information on these customers.",
      "DataNeeded": "1, customers",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "Customer details for those who purchased both products."
    }
  }
}
```

### Analyze top-selling products
```json
{
  "Plan": {
    "1": {
      "Request": "Create a list of products sorted by their number of sales.",
      "DataNeeded": "orders",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A ranked list of product IDs and names based on sales volume."
    }
  }
}
```

### Get Customers with Specific Tag
```json
{
  "Plan": {
    "1": {
      "Request": "Filter customers who have the specific tag provided in the prompt.",
      "DataNeeded": "customers, prompt",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A list of customer IDs and details who have the specific tag."
    }
  }
}
```

### Top 10% of customers by total spend in the last 6 months
```json
{
  "Plan": {
    "1": {
      "Request": "Calculate total spend for each customer in the last 6 months.",
      "DataNeeded": "orders",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A dataset with customer IDs and their total spend in the last 6 months."
    },
    "2": {
      "Request": "Identify the top 10% of customers based on total spend.",
      "DataNeeded": "1",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A list of top 10% customer IDs and their spend amounts."
    }
  }
}
```

### Customers who haven't made a purchase in the last 3 months but were active before that
```json
{
  "Plan": {
    "1": {
      "Request": "Identify customers who haven't made a purchase in the last 3 months.",
      "DataNeeded": "orders",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A list of customer IDs inactive in the last 3 months."
    },
    "2": {
      "Request": "From the above list, filter customers who have multiple past orders.",
      "DataNeeded": "1, orders",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A list of customer IDs who were previously active."
    }
  }
}
```

### Get Customer By Name
```json
{
  "Plan": {
    "1": {
      "Request": "Search for customers whose names match or partially match the provided name.",
      "DataNeeded": "customers, prompt",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "Customer details for matching names."
    }
  }
}
```

### List all orders
```json
{
  "Plan": {
    "1": {
      "Request": "Compile a list of all orders.",
      "DataNeeded": "orders",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A comprehensive list of all orders with details."
    }
  }
}
```

### Retrieve order history for this list of customers: [...]
```json
{
  "Plan": {
    "1": {
      "Request": "Filter orders placed by the customers provided in the prompt.",
      "DataNeeded": "orders, prompt",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "Order history for the specified customers."
    }
  }
}
```

### Find customers who have consistently increased their spending over multiple orders
```json
{
  "Plan": {
    "1": {
      "Request": "Identify customers with multiple orders.",
      "DataNeeded": "orders",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A list of customer IDs with multiple orders."
    },
    "2": {
      "Request": "Analyze spending patterns to find customers with increasing order amounts.",
      "DataNeeded": "1, orders",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A list of customer IDs showing consistent spending increases."
    }
  }
}
```

### Given date_sent for each user, report if the user ordered within 60 days of date_sent, as well as how much the order value was.
```json
{
  "Plan": {
    "1": {
      "Request": "For each user, identify orders placed within 60 days after their date_sent.",
      "DataNeeded": "orders, prompt",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A list of users with orders within 60 days, including order dates and values."
    },
    "2": {
      "Request": "Extract order value and date for each relevant order.",
      "DataNeeded": "1",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "Detailed order values and dates for each user."
    }
  }
}
```

### Analyze the top-selling products for the last month
```json
{
  "Plan": {
    "1": {
      "Request": "List products and their sales counts for the last month.",
      "DataNeeded": "orders",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A ranked list of products sold in the last month with sales counts."
    }
  }
}
```

### Create a cohort of customers who have purchased complementary products and might be interested in a new bundle offer.
```json
{
  "Plan": {
    "1": {
      "Request": "Identify customers who have purchased complementary products.",
      "DataNeeded": "orders, prompt",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A list of customer IDs who purchased complementary products."
    },
    "2": {
      "Request": "Retrieve detailed information on these customers.",
      "DataNeeded": "1, customers",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "Customer details for targeted bundle offers."
    }
  }
}
```

### Show a chart of the SKU with the highest order volume.
```json
{
  "Plan": {
    "1": {
      "Request": "Identify the SKU with the highest order volume.",
      "DataNeeded": "orders",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "The SKU with the highest sales volume and its sales data over time."
    },
    "2": {
      "Request": "Generate a chart showing the performance of this top SKU over the current year.",
      "DataNeeded": "1",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A time-series chart depicting monthly sales of the top SKU."
    }
  }
}
```

### Show a chart of sales of multiple products
```json
{
  "Plan": {
    "1": {
      "Request": "Filter orders to find those containing the specified products.",
      "DataNeeded": "orders, prompt",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "Sales data over time for the specified products."
    },
    "2": {
      "Request": "Create a time-series dataset for each product.",
      "DataNeeded": "1",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "Time-series data for each product's sales."
    },
    "3": {
      "Request": "Generate a line chart showing sales trends for each product over time.",
      "DataNeeded": "2",
      "RequiresCode": "True",
      "RequiresQuery": "False",
      "DesiredOutput": "A multi-line chart comparing sales of the specified products."
    }
  }
}
```
