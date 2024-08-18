Date last edited: 8/17/2024 at 10:03PM

## Request: Determine the product IDs for product X and product Y
Data provided: dictionary of product information
Code logic: 
Loop through dictionary of products edges and, for each node, check if the "title" matches any part of the product X name given in the request. If so, add the "id" into a list. Return this list of IDs.

## Request: Determine which customers purchased both product X and product Y
Data provided: dictionary of order information
Code logic: 
Create an empty dictionary that will map customer emails to a list of booleans of whether or not they ordered Product X and Product Y. 
Loop through the edges and, for each node, add the customer's email to the dictionary. If their name is available, add that instead. Go into the node's lineItems edges and, for each node, if any part of the title matches product X or product Y, update that boolean. 
Add all customer emails who ordered both products into a result list. If the result list is empty, return a string "No customers ordered both Product X and Product Y"

## Request: Get complete information on customers given incomplete information
Data provided: dictionary of custoemr information, a list of 1 or 2 data points on each customer (ie, a list of customer emails)
Code logic:
Convert the list of emails into a set.
Loop through the dictionary of customer information and for each edge, check if the email is in the set. If so, add that node to a result data structure.
