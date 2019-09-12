# NUTS Finance - Issuance

## Use Case Description

The system allows sellers to create new issuances of selected financial instruments, using the financial instruments implemented by FSPs as an initial instrument template.

## Actors

* Seller, creator of a specific financial instrument issuance. For example, a seller can create a unique instance of a loan instrument underwritten by Financial Service Provider; 
* Buyer, engager of the financial instrument issuance created by the Sellers. For instance, a buyer can engage a specific loan instance created by the seller;

## Preconditions

* Financial Service Providers have created selected financial instruments using the NUTS Technology Platform;

## Process Flow

## Open Questions

1. How does the seller select the financial instruments?
   1. How to select: Off-chain first
   2. Condition: FSP sets eligible sellers  --&gt; API in financial instrument - white list/black list/...
2. How does the buyer search the financial issuance?
   1. How to search: Off-chain first
   2. Condition: Sellers have right to set the eligible buyers
3. How will the seller and buyer interacts with the issuance?
   1. Interactions are done in the NUTS platform directly
4. OTC

