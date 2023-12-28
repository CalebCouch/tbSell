# tbSell

## Description
tbSell is a protocol built on top of tbPUB and TBBandwidth that allows anyone to
publish orders without spam.

## Product Categories
To help locate different order categories, every seller has a set of high-level 
product categories listed in their DID-DOC: 
```
[
  {
    "name": "tbsell:food:bank-data:etc"
    "URI": "URI to service"
  }
]
```

## Orders

All orders are hosted by the seller at the route "tbsell".

```did-dht:key/tbsell```

Orders are JSON objects that must contain at least a price, product name, and 
the full product category:
```
{
  "price": 1000
  "product-name": "chase-payment-vc"
  "product-category": "bank-data:payment-vcs"
}
```

## tbSell Seller

### Description
A Seller is a hosted service that contains a list of orders for a set of product 
categories. To be a discoverable Seller, the Seller hosts their DID-DHT key via 
tbPUB. The bandwidth of their DID determines the number of orders that can be listed.

## tbSell Node

### Description
Runs a tbPUB node and gets a list of all the tbSeller did docs from TBBandwidth. 
From the did-docs, it assembles a list of all available product categories. 
When a product category is requested, it reaches out to all the tbSellers of that 
category and obtains a list of offers.

### Requirements
1. tbPUB Node
