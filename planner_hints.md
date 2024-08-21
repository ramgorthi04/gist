Date last edited: 8/20/2024 a 8:59PM. 
Max N is 250. 
# Successful Plans

Reasoning tasks can be performed without code. "Filter the product list down to products most similar to X" does not require code and can be done using reasoning.
### Identify which customers are most likely to purchase product X 
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
            "RequiresCode": "False" (**NOTE**: This does not require code because it is a REASONING task)
            "RequiresQuery": "False"
        },
        "3": {
            "Request": "Determine which customers purchased any of the products in the similar products list"
            "DataNeeded": "2, orders"
            "PaginationNeeded": "False",
            "RequiresCode": "True"
            "RequiresQuery": "False"
        },
        "4": {
            "Request": "Get information on the customers found in step 3",
            "DataNeeded": 3, customers",
            "PaginationNeeded": "False",
            "RequiresCode": True"
            "RequiresQuery": "False"
        }
    }
}

### Find Customers who purchased product X and also product Y
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
            "DataNeeded": 1, customers",
            "PaginationNeeded": "False",
            "RequiresCode": True",
            "RequiresQuery": "False"
        }
    }
}

### Analyze top-selling products
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

## Cohort Selection
Examples of cohort selection queries and data collection plans:
### Top 10% of customers by total spend in the last 6 months
Plan:
Step 1: Sort customers by total spend. RequiresCode: True, DataNeeded: customers
### Customers who haven't made a purchase in the last 3 months but were active before that
Plan:
Step 1: Get a list of customers who haven't made a purchase in the last 3 months. RequiresCode: True, DataNeeded: customers
Step 2: For customers who haven't purchased in 3 months, filter down to customers who have multiple orders. RequiresCode: True, DataNeeded: Step 1
