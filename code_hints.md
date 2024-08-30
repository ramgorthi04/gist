Date last edited: 8/29/2024 at 10:21PM

# Successful Code Logics

### Filter the list from step N to only the customers with multiple orders
Data provided: shortened list of customer emails from step X, full dictionary of customer information
Code logic: 
Access the shortened list of customer emails keyed by "N" in the data dictionary. Add all the customer emails in that list to a dictionary of `relevant_customers` that maps each email to the order count for that customer. Loop through the full dictionary of customer information. If the customer's email is in `relevant_customers`, increment the order count. Finally, add customers from `relevant_customers` with over 1 order to a result list.

### Determine the product IDs for product X and product Y  
Data provided: dictionary of product information  
Code logic:  
Loop through the dictionary of product edges, and for each node, check if the "title" matches any part of the product X name given in the request. If so, add the "id" into a list. Return this list of IDs.

### Determine which customers purchased both product X and product Y  
Data provided: dictionary of order information  
Code logic:  
Create an empty dictionary that will map customer emails to a list of booleans, indicating whether they ordered Product X and Product Y.  
Loop through the edges, and for each node, add the customer's email to the dictionary. If their name is available, add that instead. Go into the node's `lineItems` edges, and for each node, if any part of the title matches Product X or Product Y, update that boolean.  
Add all customer emails who ordered both products into a result list. If the result list is empty, return the string "No customers ordered both Product X and Product Y."

### Get complete information on customers given incomplete information  
Data provided: dictionary of customer information, a list of 1 or 2 data points on each customer (e.g., a list of customer emails)  
Code logic:  
Convert the list of emails into a set.  
Loop through the dictionary of customer information, and for each edge, check if the email is in the set. If so, add that node to a result data structure.

### Filter down a given list of customers to those who haven't ordered in the past 3 months
Data provided: list of customers to filter and orders data
Code logic:
Create a dictionary to store the last purchase date for each customer
Process orders to find the last purchase date for each customer: 
for order in orders_data.get("results", []):
    email = order.get("email")
    processed_at = order.get("processedAt")
    if email and processed_at:
        try:
            processed_at_date = datetime.fromisoformat(processed_at.replace("Z", "+00:00"))
            if email not in last_purchase_date or processed_at_date > last_purchase_date[email]:
                last_purchase_date[email] = processed_at_date
        except ValueError:
            continue
Define the cutoff date for 3 months ago (timezone-aware): 
cutoff_date = datetime.now(timezone.utc) - timedelta(days=90)
Filter customers who haven't made a purchase in the last 3 months:
result = []
for customer in customers_data:
    email = customer.get("email")
    if email and (email not in last_purchase_date or last_purchase_date[email] < cutoff_date):
        result.append({
            "customerID": customer.get("id"),
            "email": customer.get("email)
        })

### Filter orders to find those placed by Customer firstName
import json

if isinstance(data, str):
    data = json.loads(data)

orders = data.get("orders")
if isinstance(orders, str):
    orders = json.loads(orders)

for order in orders.get("results", []):
    customer = order.get("customer", {})
    
    # Check that customer exists before accessing it
    if customer:
        first_name = customer.get("firstName")
        last_name = customer.get("lastName")
        
        if first_name == "Jackie":
            line_items = []
            for item in order.get("lineItems", {}).get("edges", []):
                node = item.get("node", {})
                line_items.append({
                    "title": node.get("title"),
                    "quantity": node.get("quantity"),
                    "price": node.get("originalTotalSet", {}).get("shopMoney", {}).get("amount"),
                    "currency": node.get("originalTotalSet", {}).get("shopMoney", {}).get("currencyCode")
                })
            
            result.append({
                "order_id": order.get("id"),
                "customer_first_name": first_name,
                "customer_last_name": last_name,
                "email": order.get("email"),
                "total_price": order.get("totalPriceSet", {}).get("shopMoney", {}).get("amount"),
                "currency": order.get("totalPriceSet", {}).get("shopMoney", {}).get("currencyCode"),
                "processed_at": order.get("processedAt"),
                "line_items": line_items
            })


### Count Orders by Customer Emails 
import json
from collections import defaultdict

def count_emails(file_path):
    # Read data from the file
    with open(file_path, 'r') as file:
        data = json.load(file)

    result = defaultdict(int)

    # Iterate directly over the list of orders
    for order in data:
        if isinstance(order, dict):
            email = order.get("email")
            if email:
                result[email] += 1

    # Convert defaultdict to a regular dictionary for the final result
    return dict(result)


file_path = 'otest.json'
email_counts = count_emails(file_path)

print("Email counts:")
for email, count in email_counts.items():
    print(f"{email}: {count}")
