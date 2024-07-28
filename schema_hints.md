Date last edited: 7/28/2024 at 12:43AM
ASSUME MAX N IS 200 AND ASSUME N IS 200 UNLESS OTHERWISE MENTIONED 


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


Additional info for customer: 
## sortKey =

- `CREATED_AT`
  - Sort by the `created_at` value.

- `ID`
  - Sort by the `id` value.

- `LAST_ORDER_DATE`
  - Sort by the `last_order_date` value.

- `LOCATION`
  - Sort by the `location` value.

- `NAME`
  - Sort by the `name` value.

- `ORDERS_COUNT`
  - Sort by the `orders_count` value.

- `RELEVANCE`
  - Sort by relevance to the search terms when the `query` parameter is specified on the connection.
  - Do not use this sort key when no search query is specified.

- `TOTAL_SPENT`
  - Sort by the `total_spent` value.

- `UPDATED_AT`
  - Sort by the `updated_at` value.


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

First N customers (MAX N = 250)
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

### Access Requirements
- **Recent Orders**: Last 60 days' worth of orders.
- **Access to Older Orders**: Request `read_all_orders` scope.
- **Private Apps**: Automatically granted access.

### Fields

#### Hidden Fields
- `availablePublicationsCount`: `Count`

#### Visible Fields
- `category`: `TaxonomyCategory`
- `compareAtPriceRange`: `ProductCompareAtPriceRange`
- `contextualPricing`: `ProductContextualPricing!`
- `createdAt`: `DateTime!`
- `defaultCursor`: `String!`
- `description`: `String!`
- `descriptionHtml`: `HTML!`
- `featuredImage`: `Image`
- `featuredMedia`: `Media`
- `feedback`: `ResourceFeedback`
- `giftCardTemplateSuffix`: `String`
- `handle`: `String!`
- `hasOnlyDefaultVariant`: `Boolean!`
- `hasOutOfStockVariants`: `Boolean!`
- `hasVariantsThatRequiresComponents`: `Boolean!`
- `id`: `ID!`
- `inCollection`: `Boolean!`
- `isGiftCard`: `Boolean!`
- `legacyResourceId`: `UnsignedInt64!`
- `mediaCount`: `Count`
- `metafield`: `Metafield`
- `onlineStorePreviewUrl`: `URL`
- `onlineStoreUrl`: `URL`
- `options`: `[ProductOption!]!`
- `priceRangeV2`: `ProductPriceRangeV2!`
- `productType`: `String!`
- `publishedAt`: `DateTime`
- `publishedInContext`: `Boolean!`
- `publishedOnCurrentPublication`: `Boolean!`
- `publishedOnPublication`: `Boolean!`
- `requiresSellingPlan`: `Boolean!`
- `resourcePublicationOnCurrentPublication`: `ResourcePublicationV2`
- `resourcePublicationsCount`: `Count`
- `sellingPlanGroupsCount`: `Count`
- `seo`: `SEO!`
- `status`: `ProductStatus!`
- `tags`: `[String!]!`
- `templateSuffix`: `String`
- `title`: `String!`
- `totalInventory`: `Int!`
- `tracksInventory`: `Boolean!`
- `translations`: `[Translation!]!`
- `updatedAt`: `DateTime!`
- `variantsCount`: `Count`
- `vendor`: `String!`



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

Order Fields: 
### Access Requirements
- **Recent Orders**: Last 60 days' worth of orders.
- **Access to Older Orders**: Request `read_all_orders` scope.
- **Private Apps**: Automatically granted access.

### Fields

#### Hidden Fields
- `additionalFees`: `[AdditionalFee!]!`

#### Visible Fields
- `alerts`: `[ResourceAlert!]!`
- `app`: `OrderApp`
- `billingAddress`: `MailingAddress`
- `billingAddressMatchesShippingAddress`: `Boolean!`
- `canMarkAsPaid`: `Boolean!`
- `canNotifyCustomer`: `Boolean!`
- `cancelReason`: `OrderCancelReason`
- `cancellation`: `OrderCancellation`
- `cancelledAt`: `DateTime`
- `capturable`: `Boolean!`
- `cartDiscountAmountSet`: `MoneyBag`
- `channelInformation`: `ChannelInformation`
- `clientIp`: `String`
- `closed`: `Boolean!`
- `closedAt`: `DateTime`
- `confirmationNumber`: `String`
- `confirmed`: `Boolean!`
- `createdAt`: `DateTime!`
- `currencyCode`: `CurrencyCode!`
- `currentCartDiscountAmountSet`: `MoneyBag!`
- `currentSubtotalLineItemsQuantity`: `Int!`
- `currentSubtotalPriceSet`: `MoneyBag!`
- `currentTaxLines`: `[TaxLine!]!`
- `currentTotalAdditionalFeesSet`: `MoneyBag`
- `currentTotalDiscountsSet`: `MoneyBag!`
- `currentTotalDutiesSet`: `MoneyBag`
- `currentTotalPriceSet`: `MoneyBag!`
- `currentTotalTaxSet`: `MoneyBag!`
- `currentTotalWeight`: `UnsignedInt64!`
- `customAttributes`: `[Attribute!]!`
- `customer`: `Customer`
- `customerAcceptsMarketing`: `Boolean!`
- `customerJourneySummary`: `CustomerJourneySummary`
- `customerLocale`: `String`
- `discountCode`: `String`
- `discountCodes`: `[String!]!`
- `displayAddress`: `MailingAddress`
- `displayFinancialStatus`: `OrderDisplayFinancialStatus`
- `displayFulfillmentStatus`: `OrderDisplayFulfillmentStatus!`
- `disputes`: `[OrderDisputeSummary!]!`
- `edited`: `Boolean!`
- `email`: `String`
- `estimatedTaxes`: `Boolean!`
- `fulfillable`: `Boolean!`
- `fulfillments`: `[Fulfillment!]!`
- `fullyPaid`: `Boolean!`
- `hasTimelineComment`: `Boolean!`
- `id`: `ID!`
- `legacyResourceId`: `UnsignedInt64!`
- `merchantEditable`: `Boolean!`
- `merchantEditableErrors`: `[String!]!`
- `merchantOfRecordApp`: `OrderApp`
- `metafield`: `Metafield`
- `name`: `String!`
- `netPaymentSet`: `MoneyBag!`
- `note`: `String`
- `originalTotalAdditionalFeesSet`: `MoneyBag`
- `originalTotalDutiesSet`: `MoneyBag`
- `originalTotalPriceSet`: `MoneyBag!`
- `paymentCollectionDetails`: `OrderPaymentCollectionDetails!`
- `paymentGatewayNames`: `[String!]!`
- `paymentTerms`: `PaymentTerms`
- `phone`: `String`
- `poNumber`: `String`
- `presentmentCurrencyCode`: `CurrencyCode!`
- `processedAt`: `DateTime!`
- `publication`: `Publication`
- `purchasingEntity`: `PurchasingEntity`
- `refundDiscrepancySet`: `MoneyBag!`
- `refundable`: `Boolean!`
- `refunds`: `[Refund!]!`
- `registeredSourceUrl`: `URL`
- `requiresShipping`: `Boolean!`
- `restockable`: `Boolean!`
- `returnStatus`: `OrderReturnStatus!`
- `risk`: `OrderRiskSummary!`
- `shippingAddress`: `MailingAddress`
- `shippingLine`: `ShippingLine`
- `shopifyProtect`: `ShopifyProtectOrderSummary`
- `sourceIdentifier`: `String`
- `subtotalLineItemsQuantity`: `Int!`
- `subtotalPriceSet`: `MoneyBag`
- `suggestedRefund`: `SuggestedRefund`
- `tags`: `[String!]!`
- `taxExempt`: `Boolean!`
- `taxLines`: `[TaxLine!]!`
- `taxesIncluded`: `Boolean!`
- `test`: `Boolean!`
- `totalCapturableSet`: `MoneyBag!`
- `totalDiscountsSet`: `MoneyBag`
- `totalOutstandingSet`: `MoneyBag!`
- `totalPriceSet`: `MoneyBag!`
- `totalReceivedSet`: `MoneyBag!`
- `totalRefundedSet`: `MoneyBag!`
- `totalRefundedShippingSet`: `MoneyBag!`
- `totalShippingPriceSet`: `MoneyBag!`
- `totalTaxSet`: `MoneyBag`
- `totalTipReceivedSet`: `MoneyBag!`
- `totalWeight`: `UnsignedInt64`
- `transactions`: `[OrderTransaction!]!`
- `unpaid`: `Boolean!`
- `updatedAt`: `DateTime!`

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
