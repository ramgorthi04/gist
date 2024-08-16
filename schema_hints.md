Date last edited: 8/16/2024 at 4:20PM
ASSUME MAX N IS 250 AND ASSUME N IS 250 UNLESS OTHERWISE MENTIONED 

# Queries
NEVER get all orders, or get all customers, or get all products. This data has already been collected and the plan should never include that step.
## pagination
If you need to 'get all' pages of a query, use pagination: In the plan, collect all this data in a single step with a step request like 'Get all ...'. ONLY do this if absolutely necessary. Otherwise, say FALSE for pagination.
The GraphQL query to get all products with pagination looks like this:
query getOrders($cursor: String) {
  orders(first: N, after: $cursor) {
        edges {
          cursor
          node {
            id
            lineItems(first: N) {
              edges {
                node {
                  variant {
                    product {
                      id
                    }
                  }
                }
              }
            }
            customer {
              id
              displayName
              email
            }
          }
        }
        pageInfo {
          hasNextPage
        }
      }
    }
ALWAYS include the `cursor` field in `edges` (this is separate from the `endCursor` field. 
For the operation definition in pagination queries, do NOT do this:
query getAllCustomers($first: Int = 1, $after: String)
Do THIS instead:
query getAllCustomers($cursor: String)


## customer
Customer by ID
query {
  customer(id: $CUSTOMER_ID) {
    id
    firstName
    lastName
    email
    phone
    numberOfOrders
    amountSpent {
      amount
      currencyCode
    }
    createdAt
    updatedAt
    note
    verifiedEmail
    validEmailAddress
    tags
    lifetimeDuration
    defaultAddress {
      formattedArea
      address1
    }
    addresses {
      address1
    }
    image {
      src
    }
    canDelete
  }
}

Get customers and their orders with high orders and not updated before 2024: 

query GetHighOrderCountCustomers {
  customers(first: 100, query: "orders_count:>5 AND NOT updated_at:>2024-01-01") {
    edges {
      node {
        id
        displayName
        email
        numberOfOrders
        orders(first: 10, sortKey: CREATED_AT, reverse: true) {
          edges {
            node {
              id
              name
              createdAt
            }
          }
        }
      }
    }
  }
}

Given a list of customer IDs, you can get the email, name, and account creation date of multiple specific customers using a GraphQL Inline Fragment with a Connection Field. 
query {
  customers: nodes(ids: [$CUSTOMER_ID1, $CUSTOMER_ID2, $CUSTOMER_ID3]) {
    ... on Customer {
      id
      numberOfOrders
      lastOrder {
        processedAt
      }
    }
  }
}

First N line items of customers order

query {
  customer(id: $CUSTOMER_ID) {
    lastOrder {
      lineItems(first: N) {
        edges {
          node {
            name
            quantity
          }
        }
      }
    }
  }
}

First N customers
query {
  customers(first: N) {
    edges {
      node {
        id
      }
    }
  }
}

Display name and spend of first N customers with more than X orders 

query {
  customers(first: N, query: "orders_count:>X") {
    edges {
      node {
        displayName
        amountSpent {
          amount
          currencyCode
        }
      }
    }
  }
}

First N customers in COUNTRY:
query {
  customers(first: N, query: "country:$COUNTRY") {
    edges {
      node {
        id
      }
    }
  }
}

Segment customer id: 
{
  segment(id) {
    # Segment fields
  }
}

Get details about specific inventory item: 
query {
  inventoryItem(id: $INVENTORY_ID) {
    id
    tracked
    sku
  }
}

Get details on first N inventory items: 
query {
  inventoryItems(first: N) {
    edges {
      node {
        id
        tracked
        sku
      }
    }
  }
}

Inventory properties for a shop: 
query inventoryProperties {
  inventoryProperties {
    quantityNames {
      belongsTo
      comprises
      displayName
      isInUse
      name
    }
  }
}

Title, description, and url of product: 
query {
  product(id: $PRODUCT_ID) {
    title
    description
    onlineStoreUrl
  }
}

Total Inventory of Product: 
query {
  product(id: $PRODUCT_ID) {
    title
    totalInventory
  }
}

Get data on products tagged as complementary:
**Note: 'sku' is not a valid field for node in this query**
query {
  products(first: 200, query: "tag:complementary") {
    edges {
      node {
        id
        title
        handle
        totalInventory
        variants(first: 1) {
          edges {
            node {
              compareAtPrice
              price
            }
          }
        }
      }
    }
  }
}


N recently created products: 
query {
  products(first: N, reverse: true) {
    edges {
      node {
        id
        title
        handle
        resourcePublicationOnCurrentPublication {
          publication {
            name
            id
          }
          publishDate
          isPublished
        }
      }
    }
  }
}

First N products updated after date: 
query {
  products(first: N, query: "updated_at:>$DATE") {
    edges {
      node {
        id
        updatedAt
      }
    }
  }
}

First N products on sale:
query {
  products(first: 200) {
    edges {
      node {
        id
        title
        handle
        variants(first: 1) {
          edges {
            node {
              compareAtPrice
              price
            }
          }
        }
      }
    }
  }
}

Get Order by ID: 
query {
  order(id: $ORDER_ID) {
    name
  }
}
Get Line Items per Order using order ID
query GetOrderLineItems {
  order(id: $ID) {
    lineItems(first: 10) {
      edges {
        node {
          title
          quantity
        }
      }
    }
  }
}

Order Fields: 
### Access Requirements
- **Recent Orders**: Last 60 days' worth of orders.
- **Access to Older Orders**: Request `read_all_orders` scope.
- **Private Apps**: Automatically granted access.


First N orders after specific date: 
query {
  orders(first: N, query: "updated_at:>$DATE") {
    edges {
      node {
        id
        updatedAt
      }
    }
  }
}



Pending Orders
{
  pendingOrdersCount {
    # Count fields
  }
}

## Fields that are in-accessible:
'relatedProducts' doesn't exist on type 'Product'
'products' field does not exist on type 'Product'

Be aware of the maximum query 'cost' of 1,000:
For example, the cost of this query is 4754 and will not work:
query getOrders($cursor: String) {
  orders(first: 250, after: $cursor) {
    edges { cursor 
      cursor
      node {
        id
        lineItems(first: 250) {
          edges { cursor 
            node {
              title
              variant {
                title
                image {
                  src
                }
                product {
                  title
                  onlineStoreUrl
                  variants(first: 250) {
                    edges { cursor 
                      node {
                        title
                        image {
                          src
                        }
                        product {
                          title
                          onlineStoreUrl
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    pageInfo {
      hasNextPage
    }
  }
}

This query does work:
query getOrders($cursor: String) {
  orders(first: 250, after: $cursor) {
    edges {
      cursor
      node {
        id
        lineItems(first: 10) {
          edges {
            node {
              title
              variant {
                title
                image {
                  src
                }
                product {
                  title
                  onlineStoreUrl
                  variants(first: 10) {
                    edges {
                      node {
                        title
                        image {
                          src
                        }
                        product {
                          title
                          onlineStoreUrl
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    pageInfo {
      hasNextPage
    }
  }
}

# Successful Plans

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
### Customers who purchased product X and also product Y
Plan:
Step 1: Determine the product IDs for product X and product Y. RequiresCode: True, DataNeeded: products
Step 2: Determine which customers purchased product X and product Y. RequiresCode: True, DataNeeded: customers
### Top 10% of customers by total spend in the last 6 months
Plan:
Step 1: Sort customers by total spend. RequiresCode: True, DataNeeded: customers
### Customers who haven't made a purchase in the last 3 months but were active before that
Plan:
Step 1: Get a list of customers who haven't made a purchase in the last 3 months. RequiresCode: True, DataNeeded: customers
Step 2: For customers who haven't purchased in 3 months, filter down to customers who have multiple orders. RequiresCode: True, DataNeeded: Step 1
