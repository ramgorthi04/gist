Date last edited: 10/20/2024 at 6:03PM

# Successful Code Logics

### Calculate Recency, Frequency, and Monetary (RFM) scores for each customer using orders data.
```
# Create a copy of the input data dictionary
data_copy = data.copy()

# Function to safely parse JSON
def parse_json_if_string(value):
    return json.loads(value) if isinstance(value, str) else value

# Safely access 'orders' data using the key from the data dictionary
orders_data = parse_json_if_string(data_copy.get('orders', '{}'))

# Ensure 'results' is in orders_data and contains the list of orders
orders_list = orders_data.get('results', [])

# Process orders to calculate RFM metrics
for order in orders_list:  # Loop through orders_list instead of orders_data
    try:
        # Access email, processedAt, and totalPriceSet safely
        email = order.get('email', None)
        processed_at = order.get('processedAt', None)
        total_price = float(order.get('totalPriceSet', {}).get('shopMoney', {}).get('amount', 0))

        # Ensure email and processedAt are present
        if email and processed_at:
            # Parse the date
            order_date = datetime.strptime(processed_at, "%Y-%m-%dT%H:%M:%SZ")
            
            # Calculate recency
            days_since_order = (current_date - order_date).days
            if email not in recency or days_since_order < recency[email]:
                recency[email] = days_since_order
            
            # Calculate frequency
            frequency[email] += 1
            
            # Calculate monetary value
            monetary[email] += total_price
    except Exception as e:
        # Catch and print any errors during parsing
        print(f"Error processing order: {e}")

# Combine RFM scores into a single dictionary
rfm_scores = {}
for email in set(recency.keys()).union(frequency.keys()).union(monetary.keys()):
    rfm_scores[email] = {
        'recency': recency.get(email, float('inf')),
        'frequency': frequency.get(email, 0),
        'monetary': monetary.get(email, 0.0)
    }

# Store the final result
result = {
    "rfm_scores": rfm_scores
}
```



### Get all previous order items for a list of customers (given their emails)
```
# Create a copy of the input data dictionary
data_copy = data.copy()

# Parse the orders JSON data
orders_data = parse_json_if_string(data_copy['orders'])

# List of specified email addresses to filter
specified_emails = [...]

# Create a set for faster lookup
specified_emails_set = set(specified_emails)

# Initialize dictionaries to store data
last_orders = {}
order_counts = defaultdict(int)
all_line_items = defaultdict(list)

# Process orders to find the last order, count orders, and collect all line items
for order in orders_data.get('results', []):
    try:
        email = order.get('email', None)
        if email in specified_emails_set:
            processed_at = order.get('processedAt', None)
            if processed_at:
                # Convert processedAt to a datetime object
                processed_at_dt = datetime.fromisoformat(processed_at.replace('Z', '+00:00'))
                if email not in last_orders or processed_at_dt > last_orders[email]['processed_at_dt']:
                    # Update the last order for this email
                    last_orders[email] = {
                        'order': order,
                        'processed_at_dt': processed_at_dt
                    }
            # Increment the order count for this email
            order_counts[email] += 1
            # Collect line items from this order
            line_items = order.get('lineItems', {}).get('edges', [])
            for item_edge in line_items:
                item = item_edge.get('node', {})
                title = item.get('title', 'Unknown Title')
                quantity = item.get('quantity', 0)
                all_line_items[email].append({'title': title, 'quantity': quantity})
    except Exception as e:
        print(f"Error processing order: {e}")

# Prepare the final result
result = {
    "last_orders": {
        email: data['order'] for email, data in last_orders.items()
    },
    "order_counts": dict(order_counts),
    "all_line_items": dict(all_line_items)
}
```
### Calculate the time since the last interaction (purchase or abandoned cart) for each customer.
```
import json
from datetime import datetime
from collections import defaultdict

# Function to safely parse JSON
def parse_json_if_string(value):
    return json.loads(value) if isinstance(value, str) else value

# Create a copy of the input data dictionary
data_copy = data.copy()

# Safely access 'orders' and 'abandonedCheckouts' data using their respective keys from the data dictionary. In this data, the key for abandoned checkout data is '1' and the key for orders is 'orders'
orders_data = parse_json_if_string(data_copy.get('orders', []))
abandoned_checkouts_data = parse_json_if_string(data_copy.get('1', {}).get('edges', []))

# Initialize dictionary to track customer interactions (date and type)
customer_interactions = defaultdict(list)

# Process orders to build customer interactions
for order in orders_data:
    try:
        # Access email and processedAt safely
        email = order.get('email', None)
        processed_at = order.get('processedAt', None)
        
        # Ensure both email and processedAt are present
        if email and processed_at:
            # Parse the date and store the interaction as a tuple (date, 'purchase')
            date = datetime.strptime(processed_at, "%Y-%m-%dT%H:%M:%SZ")
            customer_interactions[email].append((date, 'purchase'))
    except Exception as e:
        # Catch and print any errors during parsing
        print(f"Error processing order: {e}")

# Process abandoned checkouts to build customer interactions
for checkout in abandoned_checkouts_data:
    try:
        # Access nested customer email and updatedAt fields safely
        customer_info = checkout.get('node', {}).get('customer', {})
        email = customer_info.get('email', None)
        updated_at = checkout.get('node', {}).get('updatedAt', None)
        
        # Ensure both email and updatedAt are present
        if email and updated_at:
            # Parse the date and store the interaction as a tuple (date, 'abandoned_cart')
            date = datetime.strptime(updated_at, "%Y-%m-%dT%H:%M:%SZ")
            customer_interactions[email].append((date, 'abandoned_cart'))
    except Exception as e:
        # Catch and print any errors during parsing
        print(f"Error processing abandoned checkout: {e}")

# Calculate time since last interaction and its type for each customer
time_since_last_interaction = {}

# Get current UTC time
current_time = datetime.utcnow()

# Process the interaction dates to find the last interaction for each customer
for email, interactions in customer_interactions.items():
    if interactions:
        # Get the most recent interaction (based on date)
        last_interaction = max(interactions, key=lambda x: x[0])
        last_interaction_date, interaction_type = last_interaction
        
        # Calculate the time difference in days
        time_diff = current_time - last_interaction_date
        
        # Store the time difference and the interaction type
        time_since_last_interaction[email] = {
            'days_since_last_interaction': time_diff.days,
            'interaction_type': interaction_type
        }
    else:
        # If no interactions, set to None or a default value
        time_since_last_interaction[email] = {
            'days_since_last_interaction': None,
            'interaction_type': None
        }

# Store the final result
result = {
    "time_since_last_interaction": time_since_last_interaction
}
```


### Analyze purchase frequency trends to identify customers with declining activity
```
import json
from collections import defaultdict
from datetime import datetime
import numpy as np

# Function to safely parse JSON
def parse_json_if_string(value):
    return json.loads(value) if isinstance(value, str) else value

# Create a copy of the input data dictionary
data_copy = data.copy()

# Safely access 'orders' key from the data dictionary
orders_data = parse_json_if_string(data_copy.get('orders', '[]')).get('results', [])

# Initialize dictionaries to track customer orders and activity
customer_orders = defaultdict(list)
customer_activity = {}

# Build customer purchase history
for order in orders_data:
    try:
        # Access email and processedAt safely
        email = order.get('email', None)
        processed_at = order.get('processedAt', None)
        
        # Ensure both email and processedAt are present
        if email and processed_at:
            # Parse the date
            date = datetime.strptime(processed_at, "%Y-%m-%dT%H:%M:%SZ")
            customer_orders[email].append(date)
    
    except Exception as e:
        # Catch and print any errors during parsing
        print(f"Error processing order: {e}")

# For each customer, count purchases per month
for email, dates in customer_orders.items():
    monthly_activity = defaultdict(int)
    
    for date in dates:
        month_year = date.strftime("%Y-%m")  # Extract year-month
        monthly_activity[month_year] += 1  # Count purchases per month
    
    customer_activity[email] = dict(monthly_activity)  # Store activity for each customer

# Identify customers with declining activity
declining_customers = []

for email, activity in customer_activity.items():
    months = sorted(activity.keys())  # Sort the months
    counts = []
    for month in months:
        counts.append(activity[month])  # Get purchase counts

    if len(counts) > 1:  # Only consider customers with data for multiple months
        try:
            # Use numpy to calculate linear regression slope
            x = np.arange(len(months))  # x-axis: time (months)
            y = counts  # y-axis: purchase counts
            slope, intercept = np.polyfit(x, y, 1)  # Perform regression

            # If the slope is negative, the activity is declining
            if slope < 0:
                declining_customers.append({
                    'email': email,
                    'months': months,
                    'counts': counts,
                    'slope': slope
                })
        
        except Exception as e:
            # Catch and print any errors during regression calculation
            print(f"Error calculating trend for {email}: {e}")

# Store the final result
result = {
    "declining_customers": declining_customers
}
```

### Determine the next likely product order for each customer in a list
```
# Given:
# List of target customer emails
# orders data

# Build a mapping from customer email to their orders
customer_orders = {}
for order in orders:
    email = order['email']
    if email not in customer_orders:
        customer_orders[email] = []
    customer_orders[email].append(order)

# Build a mapping from customer email to products they've purchased
customer_products = {}
for email, orders_list in customer_orders.items():
    products = set()
    for order in orders_list:
        for item_edge in order['lineItems']['edges']:
            product_title = item_edge['node']['title']
            products.add(product_title)
    customer_products[email] = products

# Step 2 and 3: Identify Similar Customers and Analyze Product Popularity

# We will store the predicted next product for each target customer
predicted_products = []

for email in target_customers:
    products_bought = customer_products.get(email, set())
    
    # Find similar customers among all customers
    similar_customers = set()
    for other_email, other_products in customer_products.items():
        if other_email == email:
            continue
        if products_bought & other_products:
            similar_customers.add(other_email)
    
    # Compile products purchased by similar customers, excluding already purchased products
    product_frequency = {}
    for similar_email in similar_customers:
        other_products = customer_products[similar_email]
        for product in other_products:
            if product not in products_bought:
                product_frequency[product] = product_frequency.get(product, 0) + 1
    
    # Rank the products
    sorted_products = sorted(product_frequency.items(), key=lambda x: x[1], reverse=True)
    
    # Predict the next product
    if sorted_products:
        next_likely_product = sorted_products[0][0]
    else:
        next_likely_product = "No prediction available"
    
    # Add to the result list
    predicted_products.append({
        "email": email,
        "next_likely_product": next_likely_product
    })

# Store the predictions
result = {}
for prediction in predicted_products:
    result[prediction['email'] = prediction['next_likely_product']
```

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

### Determine if a list of customers ordered within _ days
Data provided: list of customers to filter and orders data
```
import json
from datetime import datetime, timedelta, timezone

# Function to parse JSON if the input is a string
def parse_json_if_string(value):
    return json.loads(value) if isinstance(value, str) else value

# Copy the data dictionary
data_copy = {}
# Read the data from the JSON file orders.json
with open("orders.json", "r") as f:
    data_copy['orders'] = json.load(f)

# Parse the orders JSON data
orders_json_string = data_copy.get('orders', '{}')
orders_data = parse_json_if_string(orders_json_string)

# List of specified email addresses to filter
specified_emails = [
    "anonymous-8651470169255@example.com",
    ...
]

# Create a set for faster lookup
specified_emails_set = set(specified_emails)

# Calculate the date 30 days ago from today with timezone awareness
thirty_days_ago = datetime.now(timezone.utc) - timedelta(days=30)

# Initialize a list to store filtered orders
filtered_orders = []

# Process orders to find those placed by specified customers within the last 30 days
for order in orders_data.get('results', []):
    try:
        email = order.get('email', None)
        if email in specified_emails_set:
            processed_at = order.get('processedAt', None)
            if processed_at:
                # Convert processedAt to a datetime object
                processed_at_dt = datetime.fromisoformat(processed_at.replace('Z', '+00:00'))
                # Check if the order was placed within the last 30 days
                if processed_at_dt >= thirty_days_ago:
                    filtered_orders.append(order)
    except Exception as e:
        print(f"Error processing order: {e}")

# Check if the result is empty and set an appropriate message if so
if not filtered_orders:
    result = "No orders found for specified customers within the last 30 days."
else:
    result = filtered_orders

print(result)
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
result = [email for email, last_order_date in customer_last_order.items() if last_order_date < threshold_date]
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
Note that mdates expects datetime objects, not strings. Instead of using strftime to convert dates to strings, keep the dates as datetime objects for proper handling by matplotlib. Make sure the final result JSON is serializable.
FUCKING NAME YOUR FILE `query_visualization.png`
```
import matplotlib
matplotlib.use('Agg')  # Use non-interactive Agg backend for PNG file generation
import matplotlib.pyplot as plt
import matplotlib.dates as mdates # If you need to plot dates
import mplcyberpunk
plt.style.use("cyberpunk")


<write code here to prepare data for plotting>

# Plot the data
plt.figure(figsize=(<INSERT APPROPRIATE SIZES HERE>)) # Increase the width of the figure if there's a lot of data
plt.plot(x_data, y_data, marker='o', linestyle='-', color='b')
plt.xlabel(x_label)
plt.ylabel(y_label)
plt.title(title)
plt.grid(True)

# Improve x-axis date formatting if applicable
plt.gca().xaxis.set_major_locator(mdates.MonthLocator())  # Set major ticks to months
plt.gca().xaxis.set_major_formatter(mdates.DateFormatter('%b %Y'))  # Format date as 'Month Year'

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

### Combine RFM scores, CLV, purchase trends, and time since last interaction to rank customers who haven't ordered in last n days
```
import json
from collections import defaultdict
from datetime import datetime, timedelta
import numpy as np

# Function to safely parse JSON
def parse_json_if_string(value):
    return json.loads(value) if isinstance(value, str) else value

# Create a copy of the input data dictionary
data_copy = data.copy()

# Safely access data using their respective keys from the data dictionary
rfm_data = parse_json_if_string(data_copy.get('1', '{}')).get('rfm_scores', {})
clv_data = parse_json_if_string(data_copy.get('2', '{}')).get('customer_lifetime_value', {})
declining_data = parse_json_if_string(data_copy.get('3', '[]'))
time_since_last_purchase_data = parse_json_if_string(data_copy.get('4', '{}')).get('time_since_last_purchase', {})

# Parameters
N = 30  # Number of days to consider for customers who haven't purchased

# Merge data into a single dictionary
customers = {}
for email in rfm_data:
    time_since_last = time_since_last_purchase_data.get(email)
    if time_since_last is None:
        time_since_last = float('inf')
    else:
        try:
            time_since_last = float(time_since_last)
        except ValueError:
            time_since_last = float('inf')

    customers[email] = {
        'recency': rfm_data[email]['recency'],
        'frequency': rfm_data[email]['frequency'],
        'monetary': rfm_data[email]['monetary'],
        'clv': clv_data.get(email, 0),
        'time_since_last_purchase': time_since_last
    }

# Filter customers who haven't purchased in the last N days
filtered_customers = {}
for email, data in customers.items():
    days_since = data['time_since_last_purchase']
    if days_since >= N:
        filtered_customers[email] = data

# Calculate weighted score
# Normalize RFM scores and CLV
if filtered_customers:
    max_recency = max([data['recency'] for data in filtered_customers.values()])
    max_frequency = max([data['frequency'] for data in filtered_customers.values()])
    max_monetary = max([data['monetary'] for data in filtered_customers.values()])
    max_clv = max([data['clv'] for data in filtered_customers.values()])
else:
    max_recency = max_frequency = max_monetary = max_clv = 1  # Avoid division by zero

for email, data in filtered_customers.items():
    # Normalize the scores
    recency_score = (max_recency - data['recency']) / max_recency  # Higher score for more recent customers
    frequency_score = data['frequency'] / max_frequency
    monetary_score = data['monetary'] / max_monetary
    clv_score = data['clv'] / max_clv

    # Weights (adjust these weights as needed)
    recency_weight = 0.3
    frequency_weight = 0.2
    monetary_weight = 0.3
    clv_weight = 0.2

    # Calculate weighted score
    total_score = (
        recency_weight * recency_score +
        frequency_weight * frequency_score +
        monetary_weight * monetary_score +
        clv_weight * clv_score
    )
    filtered_customers[email]['total_score'] = total_score

# Sort customers by total_score
top_customers = sorted(filtered_customers.items(), key=lambda x: x[1]['total_score'], reverse=True)

# Get the top 500 customers
result = top_customers[:500]
```

### Calculate profitability of a product given various data sources
```
import json

# Extract and parse the relevant data
amazon_data = parse_json_if_string(data_copy.get('2', '[]'))
walmart_data = parse_json_if_string(data_copy.get('3', '[]'))
shopify_data = parse_json_if_string(data_copy.get('6', '[]'))
cost_data = parse_json_if_string(data_copy.get('7', '[]'))

# Initialize variables to store total revenue, costs, and number of orders
total_revenue = 0.0
total_costs = 0.0
total_orders_revenue = 0  # To track the total number of orders for which revenue is calculated
total_orders_cost = 0     # To track the total number of orders for which costs are calculated

# Aggregate sales data from Shopify
for entry in shopify_data:
    try:
        if entry.get('official_sku') == 'SC-001-BRO':
            total_revenue += entry.get('gross_sales', 0.0)
            total_orders_revenue += entry.get('ordered_quantity', 0)  # Track total orders for revenue
    except Exception as e:
        print(f"Error processing transaction data: {e}")

# Aggregate sales data from Amazon, data is MISSING the price of each sale
amazon_selling_price = <INSERT PRICE>  # Assume an average selling price for Amazon based on the data

for entry in amazon_data:
    try:
        ordered_quantity = entry.get('ordered_quantity', 0)
        total_revenue += ordered_quantity * amazon_selling_price
        total_orders_revenue += ordered_quantity  # Track total orders for revenue
    except Exception as e:
        print(f"Error processing Amazon data: {e}")

# Aggregate sales data from Walmart
for entry in walmart_data:
    try:
        if entry.get('ordered_quantity') and entry.get('gross_sales'):
            total_revenue += entry.get('gross_sales', 0.0)
            total_orders_revenue += entry.get('ordered_quantity', 0)  # Track total orders for revenue
    except Exception as e:
        print(f"Error processing Walmart data: {e}")

# Aggregate cost data
for entry in cost_data:
    try:
        fob_costs = entry.get('fob_costs', 0.0)
        costs_to_landed = entry.get('costs_to_landed', 0.0)
        total_costs += fob_costs + costs_to_landed
        total_orders_cost += 1  # Assume each cost entry corresponds to 1 order
    except Exception as e:
        print(f"Error processing cost data: {e}")

# Adjust revenue and cost based on the difference between orders
if total_orders_revenue > total_orders_cost:
    # More orders with revenue than cost, adjust revenue downward
    adjustment_factor = total_orders_cost / total_orders_revenue
    adjusted_revenue = total_revenue * adjustment_factor
    print(f"Adjusting revenue downward by factor {adjustment_factor}")
else:
    adjusted_revenue = total_revenue

if total_orders_cost > total_orders_revenue:
    # More cost entries than revenue, adjust costs downward
    adjustment_factor = total_orders_revenue / total_orders_cost
    adjusted_costs = total_costs * adjustment_factor
    print(f"Adjusting costs downward by factor {adjustment_factor}")
else:
    adjusted_costs = total_costs

# Store the result in a dictionary
result = {
    "total_adjusted_revenue": adjusted_revenue,
    "total_adjusted_costs": adjusted_costs,
    "num_revenue_data_exists": total_orders_revenue,  # Total orders we calculated revenue for
    "num_cost_data_exists": total_orders_cost         # Total orders we calculated costs for
}

```


### Using orders data, get the next likely order for all customers with SVD
```
import pandas as pd
import numpy as np

def preprocess_data(orders):
    orders_list = []
    for order in orders:
        email = order['email']
        for item in order['lineItems']['edges']:
            product_title = item['node']['title']
            quantity = item['node']['quantity']
            orders_list.append({
                'email': email,
                'product_title': product_title,
                'quantity': quantity
            })
    return pd.DataFrame(orders_list)

def create_interaction_matrix(df):
    return df.pivot_table(
        index='email',
        columns='product_title',
        values='quantity',
        aggfunc='sum',
        fill_value=0
    )

def perform_svd(interaction_matrix, n_factors=50):
    # Convert to numpy array and ensure it's float type
    matrix = interaction_matrix.values.astype(float)

    # Perform SVD using NumPy's linalg.svd
    U, sigma, Vt = np.linalg.svd(matrix, full_matrices=False)

    # Keep only the top n_factors singular values
    U = U[:, :n_factors]
    sigma = np.diag(sigma[:n_factors])
    Vt = Vt[:n_factors, :]

    # Reconstruct the matrix
    predicted_ratings = pd.DataFrame(
        np.dot(np.dot(U, sigma), Vt),
        index=interaction_matrix.index,
        columns=interaction_matrix.columns
    )
    
    return predicted_ratings

def get_recommendations(email, predicted_ratings, interaction_matrix, n_recommendations=5):
    user_ratings = predicted_ratings.loc[email]
    user_purchases = interaction_matrix.loc[email]
    recommendations = user_ratings[user_purchases == 0]
    return recommendations.sort_values(ascending=False).head(n_recommendations).index.tolist()

# Preprocess data using the existing 'data_copy' variable
df = preprocess_data(data_copy['orders'])
interaction_matrix = create_interaction_matrix(df)

# Perform SVD
predicted_ratings = perform_svd(interaction_matrix)

# Generate recommendations for each customer
result = {}
for email in interaction_matrix.index:
    result[email] = get_recommendations(email, predicted_ratings, interaction_matrix)
```
