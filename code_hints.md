Date last edited: 9/29/2024 at 2:55PM

# Successful Code Logics

### Analyze the order history to identify customers with consistently increasing spending
```
import json
from datetime import datetime

result = {}
data_copy = data.copy() if isinstance(data, dict) else json.loads(data)

# Access the appropriate key
customer_orders = data.get("KEY", {})

for email, customer_data in customer_orders.items():
    if not isinstance(customer_data, dict):
        continue

    orders = customer_data.get("orders", [])
    if not isinstance(orders, list) or len(orders) < 2:
        continue

    # Extract order dates and total prices
    order_dates_prices = []
    for order in orders:
        processed_at = order.get("processed_at")
        total_price = order.get("total_price")
        if processed_at and total_price:
            try:
                date = datetime.strptime(processed_at, "%Y-%m-%dT%H:%M:%SZ")
                price = float(total_price)
                order_dates_prices.append((date, price))
            except (ValueError, TypeError):
                continue

    # Sort by date and check for consistently increasing spending
    order_dates_prices.sort(key=lambda x: x[0])
    if len(order_dates_prices) >= 2:
        increasing = all(order_dates_prices[i][1] < order_dates_prices[i + 1][1] for i in range(len(order_dates_prices) - 1))
        if increasing:
            result[email] = {
                "order_count": len(orders),
                "orders": [(date.strftime("%Y-%m-%dT%H:%M:%SZ"), price) for date, price in order_dates_prices]
            }
```

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
```
orders_data = data["key"]
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
```
Define the cutoff date for 3 months ago (timezone-aware): 
cutoff_date = datetime.now(timezone.utc) - timedelta(days=90)
Filter customers who haven't made a purchase in the last 3 months:
```
result = []
# Access the appropriate key
customers_data = data["key"]
for customer in customers_data:
    email = customer.get("email")
    if email and (email not in last_purchase_date or last_purchase_date[email] < cutoff_date):
        result.append({
            "customerID": customer.get("id"),
            "email": customer.get("email)
        })
```
### Filter customers who have made multiple orders
```
def safe_get(obj, key, default=None):
    if isinstance(obj, dict):
        return obj.get(key, default)
    return default

data = parse_json(data)
result = []

# Access the keys
for key in data:
    customers_str = safe_get(data, key, "[]")
    customers = parse_json(customers_str)
    
    if not isinstance(customers, list):
        continue
    
    for customer in customers:
        if not isinstance(customer, dict):
            continue
        
        orders = safe_get(customer, "orders", [])
        if isinstance(orders, list) and len(orders) > 1:
            result.append({
                "id": safe_get(customer, "id"),
                "email": safe_get(customer, "email"),
                "firstName": safe_get(customer, "firstName"),
                "lastName": safe_get(customer, "lastName"),
                "order_count": len(orders)
            })
```
### Count Orders by Customer Emails 
```
import json
from collections import defaultdict

def count_emails(file_path):

    result = defaultdict(int)
    # Access the appropriate key
    orders_data = data["key"]
    
    # Iterate directly over the list of orders
    for order in orders_data:
        if isinstance(order, dict):
            email = order.get("email")
            if email:
                result[email] += 1

    # Convert defaultdict to a regular dictionary for the final result
    return dict(result)
```

### Filter orders for customers who made a purchase 20+ days ago and have not made a new purchase since then

```
import json
from datetime import datetime, timedelta

# Load the orders data
with open('orders.json') as f:
    orders_data = json.load(f)

# Convert orders into a more manageable format
orders = orders_data["results"]

# Get the current date
current_date = datetime.now()

# Set the threshold for "20+ days ago"
threshold_date = current_date - timedelta(days=20)

# Dictionary to store the last order date for each customer
customer_last_order = {}

# Iterate over each order and store the latest order date for each customer
for order in orders:
    email = order.get('email')
    processed_at = order.get('processedAt')

    # Skip orders without email
    if email:
        order_date = datetime.strptime(processed_at, "%Y-%m-%dT%H:%M:%SZ")

        # If customer is already in the dictionary, check if this order is more recent
        if email in customer_last_order:
            if order_date > customer_last_order[email]:
                customer_last_order[email] = order_date
        else:
            customer_last_order[email] = order_date

# Filter customers who made their last purchase more than 20 days ago
inactive_customers = [email for email, last_order_date in customer_last_order.items() if last_order_date < threshold_date]

# Output inactive customers
print("Customers who haven't made a purchase in the last 20 days:")
for customer in inactive_customers:
    print(customer)


```


### Filter Orders to Customers with decreasing purchasing frequency
```
import json
from collections import defaultdict
from datetime import datetime

def identify_decreasing_frequency(file_path, threshold_days=30):
    
    purchase_dates = defaultdict(list)

    # Access the appropriate key
    orders_data = data["key"]
    for order in orders_data:
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
```

### Filter Orders by Purchase Time
```
import json
from collections import defaultdict
from datetime import datetime

# Access the appropriate key
orders_data = data["key"]
orders = orders_data["results"]

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
```
### Get customer information for those who purchased gift cards
```
import json
from datetime import datetime

def get_nested_value(data, keys):
    for key in keys:
        if isinstance(data, dict):
            data = data.get(key)
        elif isinstance(data, list) and isinstance(key, int):
            data = data[key] if 0 <= key < len(data) else None
        else:
            return None
        if data is None:
            return None
    return data

def parse_json_if_string(value):
    if isinstance(value, str):
        try:
            return json.loads(value)
        except json.JSONDecodeError:
            return value
    return value

# Assume data_copy is already created and contains the necessary data
orders_data = parse_json_if_string(data_copy.get('KEY', '[]'))
customers_data = parse_json_if_string(data_copy.get('customers', '{}'))

# Step 1: Identify orders that include gift cards (assuming this is already done)
gift_card_emails = set(order['email'] for order in orders_data if 'gift_card_title' in order)

# Step 2: Get customer information for those who purchased gift cards
gift_card_customers = []

for customer in get_nested_value(customers_data, ['results']) or []:
    if customer.get('email') in gift_card_emails:
        gift_card_customers.append({
            'id': customer.get('id'),
            'email': customer.get('email'),
            'firstName': customer.get('firstName'),
            'lastName': customer.get('lastName'),
            'tags': customer.get('tags', []),
            'createdAt': customer.get('createdAt'),
            'updatedAt': customer.get('updatedAt')
        })

result = {
    "metadata": {
        "processedAt": datetime.utcnow().isoformat() + "Z",
        "dataSource": "orders and customers",
        "recordsProcessed": len(gift_card_customers)
    },
    "data": gift_card_customers
}
```

### Show a graph/chart
FUCKING NAME YOUR FILE `query_visualization.png`
```
import matplotlib
matplotlib.use('Agg')  # Use non-interactive Agg backend for PNG file generation
import matplotlib.pyplot as plt
import mplcyberpunk
plt.style.use("cyberpunk")

<write code here to prepare data for plotting>

# Plot the data
plt.figure(figsize=(<INSERT APPROPRIATE SIZES HERE>))
plt.plot(x_data, y_data, marker='o', linestyle='-', color='b')
plt.xlabel(x_label)
plt.ylabel(y_label)
plt.title(title)
plt.grid(True)
plt.xticks(rotation=45)
plt.tight_layout()
mplcyberpunk.add_glow_effects()

# Save the plot to a file named 'query_visualization.png'
plt.savefig('query_visualization.png')

# Store the result
result = {
    "return_data": result_data,
    "plot_file": "query_visualization.png"
}
```
Instead of add_glow_effects, you can add the line glow and underglow effects separately:
```
mplcyberpunk.make_lines_glow()
mplcyberpunk.add_underglow()
```
You can also add the effect to a specific axis object explicitly:
```
fig, ax = plt.subplots()
...
mplcyberpunk.make_lines_glow(ax)
```

For plotting with the cyberpunk style, you can also add these effects:
Gradient underglow effect can be added with
```
mplcyberpunk.add_glow_effects(gradient_fill=True)
```
or independently of line glow with
```
mplcyberpunk.add_gradient_fill(alpha_gradientglow=0.5)
```
Glow effect can be added to scatter plots via ```mplcyberpunk.make_scatter_glow()```:
