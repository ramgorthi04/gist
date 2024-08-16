Date last edited: 8/16/2024 at 7:00PM

## Request: Determine the product IDs for product X and product Y
Data provided: dictionary of product information
Code logic: 
Loop through dictionary of products edges and, for each node, check if the "title" matches any part of the product X name given in the request. If so, add the "id" into a list. Return this list of IDs.

## Request: Determine which customers purchased product X and product Y
Data provided: list of customer IDs and dictionary of customer information
Code logic: 
Initialize a set of customer_ids that stores all items of the given customer ID list. Loop through dictionary of customer edges and, for each node, check if the id matches an ID in the set. If so, add the node to a result dataset. 
