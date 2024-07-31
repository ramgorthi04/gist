# Shopify GraphQL Schema Hints

## Customers

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

## Products

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

### Get Order by ID
query {
  order(id: $ORDER_ID) {
    name
  }
}

### Get Order Line Items
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

### Get Recent Orders
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

### Get Segment Details
query {
  segment(id: $SEGMENT_ID) {
    # Segment fields
  }
}

### Get Pending Orders Count
query {
  pendingOrdersCount {
    # Count fields
  }
}
