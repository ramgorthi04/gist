Date last edited: 8/22/2024 at 2:28 PM.  
Max N is 250.  

# Successful Plans

### Filter this product list down to products most similar to X
Does not require code or query  
Plan: given the product list, use reasoning to determine which products are similar to X and create a list

### Segment customers based on X
The basis for segmenting customers will usually be found in the customers data  
Plan: given a list of customers from a previous step, get 

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
            "Request": "Filter down the list from step 1 to only the customers with multiple orders",
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
            "PaginationNeeded": "True",
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


## List all orders
    "Plan": {
        "1": {
            "Request": "List all orders",
            "DataNeeded": "orders",
            "PaginationNeeded": "False",
            "RequiresCode": "True",
            "RequiresQuery": "False"
        }
    },
