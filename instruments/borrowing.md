# Borrowing

The borrowing instrument allows makers to deposit collaterals, borrow digital assets and pay interest. Takers can deposit borrowing assets and expect interest as return.

Currently, the borrow instrument is 1 to 1 only, which means one borrowing issuance can be engaged by only one taker.

## Borrowing Lifecycle

The image below shows the lifecycle of borrowing issuance and engagement.

![](../.gitbook/assets/borrowing.jpg)

* When a borrowing issuance is created and the collateral token is deposited, the borrowing issuance becomes Engageable;
* When a taker engages the borrowing issuance, a borrowing engagement is created and the borrowing issuance becomes Complete with a completion ratio of 10000;
* When maker cancels an Engageable borrowing issuance, the borrowing issuance becomes Cancelled and the deposited collateral token is returned;
* When taker deposits the principal token, the engagement is Active and the principal token is transferred to maker;
* When the borrowing engagement is due or maker repays in full\(principal + interest\), the engagement becomes Complete. Borrowing issuance defines a borrowing-specific engagement property to determine whether it's Complete as it's due or repaid.

## Borrowing Issuance Maker Parameters

The borrowing issuance defines a set of maker parameters which allows makers to customize the borrowing issuance:

* Borrowing token address
* Borrowing amount
* Collateral token address
* Collateral ratio: The ratio of collateral to principal. Should between 50% and 200%;
* Tenor: The duration of the borrowing engagement. Should between 2 to 90 days;
* Interest rate: The per day interest rate to pay in principal. Should between 0.0001% to 0.0010%.

## Borrowing Issuance Custom Property

The borrowing issuance defines a set of custom property. It includes all the maker parameters shown in the previous section with the following additional fields:

* Collateral amount:  The actual collateral amount deposited. For borrowing engagement, the actual collateral value is computed at the time of issuance creation using the price oracle. Therefore, it's part of the borrowing issuance property.
* Interest amount: The computed interest amount to pay

## Borrowing Engagement Custom Property

The borrowing engagement also defines a set of custom properties.

* Loan state: The state of the loan. Could be Unpaid/Repaid/Delinquent. It's useful to identify whether a borrowing issuance is Complete because it's due or repaid.

