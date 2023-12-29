# tbSell

## Terms

### Product Categories
To help locate different order categories, every seller has a set of high-level 
product categories listed in their DID-DOC

### tbSell DID-DOC 
A tbSell DID-Document is a Web5 DID-DOC with at least one service starting with tbSell.
Following the tbSell are the product categories provided separated by a collin.
```
{
    ...
    "services": [
      {
        "name": "tbsell:food:bank-data:etc"
        "URI": "URI to service"
      }
    ]
}
```

### tbSell Order
Orders are JSON objects that must contain at least a price, product name, and 
the entire product category. Communication between the buyer is not specified by this protocol but is supported:
```
{
  "price": 1000
  "product-name": "chase-payment-vc"
  "product-category": "bank-data:payment-vcs"
}
```

## tbSell Seller

### Abstract

A Seller is a service that hosts a list of orders discoverable on the tbSell network. 

### Joining the network
To join the network, a seller must publish their DID-DHT key via TBBandwidth. The more bandwidth they have, the more orders they can host.

### Hosting an Order
All orders are hosted route "tbsell" as a JSON Array of tbSell Orders.

## tbSell Node

### Abstract
A tbSell node gathers a list of all the available order categories and orders.

### Discovering tbSell Sellers
The tbSell node will query a tbPUB node for a list of all the Seller DIDs.

### Accepting an Offer
Accepting offers and Communication between the Buyer and Seller is not specified by this protocol but is supported.
