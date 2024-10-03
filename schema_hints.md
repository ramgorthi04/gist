Date last edited: 8/16/2024 at 4:20PM
ASSUME MAX N IS 250 AND ASSUME N IS 250 UNLESS OTHERWISE MENTIONED 
# Shopify GraphQL Schema Hints

## General Notes
- **Date Last Edited**: 10/2/2024 at 3:13 PM
- **Pagination**: Use pagination when retrieving large datasets. Only collect all data if absolutely necessary. Otherwise, set pagination to `FALSE`.
- **Max N**: Assume `N` is 250 unless otherwise specified.
- **Query Cost**: Be aware of the maximum query cost of 1,000. Queries exceeding this will not work.
- **Data Collection**: NEVER get all orders, all customers, or all products; these data have already been collected.

## Customers

### Fetch all customers using pagination
        query ($cursor: String) {
          customers(first: 250, after: $cursor) {
            edges {
              node {
                id
                email
                firstName
                lastName
                tags
                createdAt
                updatedAt
                orders(first: 250) {
                  edges {
                    node {
                      totalPrice
                    }
                  }
                }
              }
            }
            pageInfo {
              hasNextPage
              endCursor
            }
          }
        }

### Get Customer by ID
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

### Get High Order Count Customers
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

### Get Multiple Specific Customers
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

### Get First N Customers
query {
  customers(first: N) {
    edges {
      node {
        id
      }
    }
  }
}

### Get Customers with High Order Count
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

### Get Customers by Country
query {
  customers(first: N, query: "country:$COUNTRY") {
    edges {
      node {
        id
      }
    }
  }
}

### First N Line Items of Customer's Last Order
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

## Products

### Fetch all products using pagination
        query ($cursor: String) {
          products(first: 250, after: $cursor) {
            edges {
              node {
                id
                title
                handle
                description
                productType
                vendor
                totalInventory
                priceRange {
                  minVariantPrice {
                    amount
                    currencyCode
                  }
                  maxVariantPrice {
                    amount
                    currencyCode
                  }
                }
                createdAt
                updatedAt
              }
            }
            pageInfo {
              hasNextPage
              endCursor
            }
          }
        }

### Get Product Details
query {
  product(id: $PRODUCT_ID) {
    title
    description
    onlineStoreUrl
  }
}

### Get Product Inventory
query {
  product(id: $PRODUCT_ID) {
    title
    totalInventory
  }
}

### Get Products with Specific Tag
**Note: 'sku' is not a valid field for `node` in this query**
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

### Get Recently Created Products
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

### Get Recently Updated Products
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

### Get Products on Sale
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

## Orders

### Fetch all orders using pagination
        query ($cursor: String) {
          orders(first: 250, after: $cursor) {
            edges {
              node {
                id
                name
                customer {
                    firstName
                    lastName
                }
                email
                totalPriceSet {
                  shopMoney {
                    amount
                    currencyCode
                  }
                }
                processedAt
                lineItems(first: 250) {
                  edges {
                    node {
                      title
                      quantity
                      originalTotalSet {
                        shopMoney {
                          amount
                          currencyCode
                        }
                      }
                    }
                  }
                }
              }
            }
            pageInfo {
              hasNextPage
              endCursor
            }
          }
        }

### Get Order by ID
query {
  order(id: $ORDER_ID) {
    name
  }
}

### Get Order Line Items by ID
query GetOrderLineItems {
  order(id: $ORDER_ID) {
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

### Get Orders Updated After Specific Date
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

### Get Orders with Pagination
**Remember to manage the query cost and use pagination properly.**
query getOrders($cursor: String) {
  orders(first: N, after: $cursor) {
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

## Inventory

### Get Inventory Item Details
query {
  inventoryItem(id: $INVENTORY_ID) {
    id
    tracked
    sku
  }
}

### Get Multiple Inventory Items
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

### Get Inventory Properties
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

## Miscellaneous

### Abandoned Cart
{
  abandonedCheckouts(first: 250, reverse: true) {
    edges {
      node {
        id
        abandonedCheckoutUrl
        lineItems(first: 20) {
          edges {
            node {
              title
              quantity
              product {
                id
                title
              }
            }
          }
        }
        customer {
          id
          displayName
          email
        }
        createdAt
        updatedAt
      }
    }
  }
}


### Get Segment Details
query {
  segment(id: $SEGMENT_ID) {
    # Segment fields
  }
}

### Get Pending Orders Count
{
  pendingOrdersCount {
    # Count fields
  }
}

### Fields that are Inaccessible
- `'relatedProducts'` does not exist on type `Product`.
- `'products'` field does not exist on type `Product`.
