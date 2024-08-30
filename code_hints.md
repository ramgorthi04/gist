Date last edited: 8/29/2024 at 10:38PM

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


### Parsing through Customer, Order, Product jsons
def parse_json(data):
    if isinstance(data, str):
        try:
            return json.loads(data)
        except json.JSONDecodeError:
            return data
    return data

data = parse_json(data)

result = []

for key in data:
    customers_str = data.get(key, "[]")
    customers = parse_json(customers_str)
    
    if not isinstance(customers, list):
        continue
    
    for customer in customers:
        if not isinstance(customer, dict):
            continue
        
        orders = customer.get("orders", [])
        if isinstance(orders, list) and len(orders) > 1:
            result.append({
                "id": customer.get("id"),
                "email": customer.get("email"),
                "firstName": customer.get("firstName"),
                "lastName": customer.get("lastName"),
                "order_count": len(orders)
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


### Filter Orders to Customers with decreasing purchasing frequency
import json
from collections import defaultdict
from datetime import datetime

def identify_decreasing_frequency(file_path, threshold_days=30):
    with open(file_path, 'r') as file:
        data = json.load(file)

    purchase_dates = defaultdict(list)

    for order in data:
        email = order.get('email')
        processed_at = order.get('processed_at')
        if email and processed_at:
            date = datetime.strptime(processed_at, "%Y-%m-%dT%H:%M:%SZ")
            purchase_dates[email].append(date)

    decreasing_frequency_customers = {}

    for email, dates in purchase_dates.items():
        if len(dates) > 2:
            sorted_dates = sorted(dates)
            time_diffs = [(sorted_dates[i] - sorted_dates[i-1]).days for i in range(1, len(sorted_dates))]
            
            # Check if the last time difference is significantly larger than the average of previous ones
            if len(time_diffs) > 1:
                avg_previous = sum(time_diffs[:-1]) / len(time_diffs[:-1])
                if time_diffs[-1] > avg_previous + threshold_days:
                    decreasing_frequency_customers[email] = {
                        'purchase_dates': sorted_dates,
                        'time_diffs': time_diffs,
                        'avg_previous': avg_previous,
                        'last_diff': time_diffs[-1]
                    }

    return decreasing_frequency_customers

file_path = 'otest.json'
decreasing_customers = identify_decreasing_frequency(file_path)

print("Customers with decreasing purchase frequency:")
for email, info in decreasing_customers.items():
    print(f"\nEmail: {email}")
    print(f"  Average time between previous purchases: {info['avg_previous']:.2f} days")
    print(f"  Time since last purchase: {info['last_diff']} days")
    print("  Purchase dates:")
    for date in info['purchase_dates']:
        print(f"    {date}")

### Filter Orders by Purchase Time
import json
from collections import defaultdict
from datetime import datetime

with open('otest.json', 'r') as file:
    orders = json.load(file)

if not isinstance(orders, list):
    raise ValueError("Expected a list of orders in the JSON file")

morning_customers = defaultdict(list)
afternoon_customers = defaultdict(list)
evening_customers = defaultdict(list)

morning_hours = list(range(6, 12))
afternoon_hours = list(range(12, 18))
evening_hours = list(range(18, 24)) + list(range(0, 6))

for order in orders:
    processed_at = order.get("processed_at")
    if processed_at:
        try:
            dt = datetime.strptime(processed_at, "%Y-%m-%dT%H:%M:%SZ")
            hour = dt.hour
            day_of_week = dt.strftime("%A")

            if hour in morning_hours:
                morning_customers[day_of_week].append(order)
            elif hour in afternoon_hours:
                afternoon_customers[day_of_week].append(order)
            elif hour in evening_hours:
                evening_customers[day_of_week].append(order)
        except ValueError:
            continue
result = {
    "morning_customers": dict(morning_customers),
    "afternoon_customers": dict(afternoon_customers),
    "evening_customers": dict(evening_customers)
}

print(result)
