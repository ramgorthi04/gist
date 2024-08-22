Date last edited: 8/17/2024 at 10:03 PM

# Successful Code Logics

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
