# Swap

The Swap instrument allows makers to post their intend for a token exchange. Taker can engage the issuance and complete the exchange.

The swap instrument is 1 to 1 only, which means one swap issuance can be engaged by only one taker.

## Swap lifecycle

The image below shows the lifecycle of swap issuance and engagement.

![](../.gitbook/assets/swap.jpg)

* When a swap issuance is created and the input token is deposited, the swap issuance becomes Engageable;
* When a taker engages the swap issuance and deposits the output token
  * The swap issuance is Complete with a completion ratio of 10000
  * The swap engagement is created and Complete;
  * The input token is transferred to taker and the output token is transferred to maker
* When maker cancels an Engageable swap issuance, the swap issuance becomes Cancelled and the deposited input token is returned.

## Swap Issuance Maker Parameters

The swap issuance defines a set of maker parameters which allows makers to customize the swap issuance:

* Input token address
* Input amount
* Output token address
* Output amount
* Duration: The duration of the swap issuance. Should between 2 to 90 days

## Swap Issuance Custom Property

The swap issuance defines a set of custom property. It includes all the maker parameters shown in the previous section.

## Swap Engagement Custom Property

The swap engagement does not define any custom property.



