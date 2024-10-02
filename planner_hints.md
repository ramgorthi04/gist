Date last edited: 10/01/2024 at 7:57pm ET
Max N is 250.  

# Successful Plans

### RE-ENGAGEMENT DATA ANALYSIS
{
    "Plan": {
      "1": {
        "Request": "Collect all abandoned cart data sorted by recency.",
        "DataNeeded": "None",
        "PaginationNeeded": "True",
        "RequiresCode": "False",
        "RequiresQuery": "True"
      },
      "2": {
        "Request": "Calculate Recency, Frequency, and Monetary (RFM) scores for each customer using orders data.",
        "DataNeeded": "orders",
        "PaginationNeeded": "True",
        "RequiresCode": "True",
        "RequiresQuery": "False"
      },
        "3": {
          "Request": "Calculate Customer Lifetime Value (CLV) for each customer using orders data.",
          "DataNeeded": "orders",
          "PaginationNeeded": "False",
          "RequiresCode": "True",
          "RequiresQuery": "False"
        },
        "4": {
          "Request": "Analyze purchase frequency trends to identify customers with declining activity.",
          "DataNeeded": "orders",
          "PaginationNeeded": "False",
          "RequiresCode": "True",
          "RequiresQuery": "False"
        },
        "5": {
          "Request": "Calculate the time since the last interaction (purchase or abandoned cart) for each customer.",
          "DataNeeded": "orders, 1",
          "PaginationNeeded": "False",
          "RequiresCode": "True",
          "RequiresQuery": "False"
        },
        "6": {
          "Request": "Combine RFM scores, CLV, purchase trends, and time since last interaction to rank customers.",
          "DataNeeded": "1, 2, 3, 4, 5",
          "PaginationNeeded": "False",
          "RequiresCode": "True",
          "RequiresQuery": "False"
        },
        "7": {
          "Request": "Identify and rank the top N customers for re-engagement based on the combined analysis.",
          "DataNeeded": "7",
          "PaginationNeeded": "False",
          "RequiresCode": "True",
          "RequiresQuery": "False"
        }
      }
      


### Filter this product list down to products most similar to X
Does not require code or query  
Plan: given the product list, use reasoning to determine which products are similar to X and create a list

### Find customers who made a purchase _+ days ago with no ne purchase since then who are good fits for re-engagement. Select 10 likely to repurchase and generate a personalized email based on a given template:
**DO NOT FUCKING assign a step in the plan to filling in the email template. Leave it to the final analysis step.**
{
    "Plan": {
        "1": {
            "Request": "Filter customers who haven't ordered in _ days, fetch their last order ID and their total number of orders.",
            "DataNeeded": "customers",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        }
        "2": {
            "Request": "Pick the top 10 customers from the list returned by step 1 and get their past orders."
            "DataNeeded": "1, customers",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        }
    }
}

### Select a cohort of customers that are highly likely to repurchase an item and haven't purchased recently, then sub-segment them into similar users, then personalize an email to each.
Plan:  
{
    "Plan": {
        "1": {
            "Request": "Get a list of customers who haven't made a purchase in the last 3 months",
            "DataNeeded": "orders",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "2": {
            "Request": "Using the list from step 1, get only the customers with multiple orders in that list",
            "DataNeeded": "1, customers",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "3": {
            "Request": "Create a list of which products each customer in the list has purchased",
            "DataNeeded": "2, orders",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "4": {
            "Request": "Group customers into segments given their past purchases",
            "DataNeeded": "3",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "False"
        }
    }
}

### Identify which customers are most likely to purchase product X 
Plan:  
{
    "Plan": {
        "1": {
            "Request": "Create a list of the names and IDs of all products in your store",
            "DataNeeded": "products",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "2": {
            "Request": "Filter the product list down to the products most similar to product X, creating a similar products list",
            "DataNeeded": "1",
            "PaginationNeeded": "False",
            "RequiresCode": "False", 
            "RequiresQuery": "False"
        },
        "3": {
            "Request": "Determine which customers purchased any of the products in the similar products list",
            "DataNeeded": "2, orders",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "4": {
            "Request": "Get information on the customers found in step 3",
            "DataNeeded": "3, customers",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        }
    }
}

### Find Customers who purchased product X and also product Y
Plan:  
{
    "Plan": {
        "1": {
            "Request": "Determine which customers purchased product X and product Y, either in the same order or over multiple orders",
            "DataNeeded": "orders",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "2": {
            "Request": "Get information on the customers found in step 1",
            "DataNeeded": "1, customers",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        }
    }
}

### Analyze top-selling products
Plan:  
{
    "Plan": {
        "1": {
            "Request": "Create a list of products sorted by their number of sales",
            "DataNeeded": "orders",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        }
    }
}

### Get Customers with Specific Tag
Plan:  
Step 1: Loop through customers JSON and build list of customers with specific tag. RequiresCode: True, DataNeeded: customers

### Top 10% of customers by total spend in the last 6 months
Plan:  
Step 1: Sort customers by total spend. RequiresCode: True, DataNeeded: customers

### Customers who haven't made a purchase in the last 3 months but were active before that
Plan:  
Step 1: Get a list of customers who haven't made a purchase in the last 3 months. RequiresCode: True, DataNeeded: customers  
Step 2: For customers who haven't purchased in 3 months, filter down to customers who have multiple orders. RequiresCode: True, DataNeeded: Step 1

### Get Customer By Name
Plan:  
Step 1: Loop through list of all customers and check if any part of the name matches, and return the information on matches. RequiresCode: True, DataNeeded: customers


### List all orders
Plan: 
{
    "Plan": {
        "1": {
            "Request": "List all orders",
            "DataNeeded": "orders",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        }
    }
}


### Get all orders by Customer Name
{
    "Plan": {
        "1": {
            "Request": "Filter orders to find those placed by Customer Name",
            "DataNeeded": "orders",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        }
    }
}

### Find customers who have consistently increased their spending over multiple orders
{
    "Plan": {
        "1": {
            "Request": "Get a list of customers with multiple orders",
            "DataNeeded": "orders",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "2": {
            "Request": "For each customer from step 1, get their order history",
            "DataNeeded": "1, orders",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "3": {
            "Request": "Analyze the order history to identify customers with consistently increasing spending",
            "DataNeeded": "2",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "4": {
            "Request": "Create a list of customers identified in step 3 as candidates for a loyalty program upgrade",
            "DataNeeded": "3",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "False"
        }
    }
}

### Given date_sent for each user, report if the user ordered within 60 days of date_sent, as well as how much the order value was.
{
    "Plan": {
        "1": {
            "Request": "Get a list of all orders with dates for the given users",
            "DataNeeded": "orders",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "2": {
            "Request": "Filter orders to find those placed by customers within 60 days after their respective date_sent",
            "DataNeeded": "1",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "3": {
            "Request": "Extract order value, date placed, and customer name for each order",
            "DataNeeded": "2",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        }
    }
}

### Analyze the top-selling products for the last month
Plan:  
{
    "Plan": {
        "1": {
            "Request": "Create a list of products and the number of times they were ordered last month",
            "DataNeeded": "orders",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        }
    }
}

### Create a cohort of customers who have purchased complementary products and might be interested in a new bundle offer.
{
    "Plan": {
        "1": {
            "Request": "Identify customers who have purchased complementary products",
            "DataNeeded": "orders",
            "PaginationNeeded": "True",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "2": {
            "Request": "Get information on the customers found in step 1",
            "DataNeeded": "1, customers",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "3": {
            "Request": "Segment customers based on their purchase history of complementary products",
            "DataNeeded": "2",
            "PaginationNeeded": "False",
            "RequiresCode": "False",
            "RequiresQuery": "False"
        }
    }
}

### Show a chart of the SKU with the highest order volume.
{
    "Plan": {
        "1": {
            "Request": "Identify the SKU with the highest order volume",
            "DataNeeded": "orders",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "2": {
            "Request": "Generate a chart showing the performance of the top SKU this year",
            "DataNeeded": "2, orders",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        }
    }
}

### Show a chart of sales of multiple products
{
    "Plan": {
        "1": {
            "Request": "Filter orders to find those containing the specified products",
            "DataNeeded": "orders",
            "PaginationNeeded": "True",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "2": {
            "Request": "Create a time-series data structure for each product",
            "DataNeeded": "1",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        },
        "3": {
            "Request": "Generate a line chart with multiple lines showing sales of each product over time",
            "DataNeeded": "2",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        }
    }
}
