Date last edited: 8/16/2024 at 4:20PM. 
Max N is 250. 
# Successful Plans

### Find Customers who purchased product X and also product Y
{
    "Plan": {
        "1": {
            "Request": "Determine the product IDs for product X and product Y",
            "DataNeeded": "products",
            "PaginationNeeded": "False",
            "RequiresCode": "True"
        },
        "2": {
            "Request": "Determine which customers purchased product X and product Y",
            "DataNeeded": "1, customers",
            "PaginationNeeded": "False",
            "RequiresCode": "True"
        }
    },
    "Original user request": "Find Customers who purchased product X and also product Y"
}

### Analyze top-selling products
{
    "Plan": {
        "1": {
            "Request": "Create a list of products sorted by their number of sales",
            "DataNeeded": "orders",
            "PaginationNeeded": "True",
            "RequiresCode": "True"
        }
    },
    "Original user request": "Analyze top-selling products for the last month"
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
