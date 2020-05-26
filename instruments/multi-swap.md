# Multi-Swap

The Multi-Swap instrument allows makers to post their intend for a token exchange. Taker can engage the issuance and complete the exchange.

The Multi-Swap instrument is similar to Swap but it allows multiple engagements to the same issuance. Maker defines the expected input token amount and output amount. When a taker engages with output token less than the expected output amount, the proportional amount of input token is swapped.

## Multi-Swap lifecycle

The image below shows the lifecycle of Multi-Swap issuance and engagement.

![](../.gitbook/assets/multiswap.jpg)

* When a multi-swap issuance is created and the input token is deposited, the multi-swap issuance becomes Engageable;
* When a taker engages the multi-swap issuance and deposits the output token
  * If there is enough input token remaining, the multi-swap engagement is created and Complete with input token transferred to taker and output token transferred to maker
  * If there is not enough input token remaining, the engagement transaction will fail
  * If there is no input token left after this engagement, the multi-swap issuance is Complete
* When maker cancels an Engageable multi-swap issuance and there is no engagement, the multi-swap issuance becomes Cancelled and the deposited input token is returned;
* When the multi-swap issuance is due, the multi-swap is Complete and remaining input tokens are returned.

## Multi-Swap Issuance Maker Parameters

The multi-swap issuance defines a set of maker parameters which allows makers to customize the multi-swap issuance:

* Input token address
* Input amount
* Output token address
* Output amount
* Duration: The duration of the swap issuance. Should between 2 to 90 days

## Multi-Swap Issuance Custom Property

The multi-swap issuance defines a set of custom property. It includes all the maker parameters shown in the previous section with the addition of one field:

* Remaining input token: The amount of input token remaining in the Issuance Escrow

## Multi-Swap Engagement Custom Property

The multi-swap engagement defines the following custom property:

* Output amount: The amount of output token deposited in this engagement.



