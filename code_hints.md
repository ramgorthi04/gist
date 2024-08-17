Date last edited: 8/16/2024 at 8:26PM

## Request: Determine the product IDs for product X and product Y
Data provided: dictionary of product information
Code logic: 
Loop through dictionary of products edges and, for each node, check if the "title" matches any part of the product X name given in the request. If so, add the "id" into a list. Return this list of IDs.

## Request: Determine which customers purchased product X and product Y
Data provided: dictionary of order information
Code logic: 
Create an empty dictionary that will map customer emails to a list of booleans of whether or not they ordered Product X and Product Y. 
Loop through the edges and, for each node, add the customer's email to the dictionary. Go into the node's lineItems edges and, for each node, if any part of the title matches product X or product Y, update that boolean. 
Add all customers who ordered both products into a result list. 
