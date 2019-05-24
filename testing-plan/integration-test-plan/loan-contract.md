# Loan Contract

This integration plan covers the use case of the [loan contract](../../use-cases/use-case-loan-contract.md). 

* Test set 1: Issuance creation\(the instrument must in Active state\)
  * ~~Test case 1: Sellers can create a new issuance of the selected instrument and then deposit Ethers to make the issuance into Engageable state;~~
  * ~~Test case 2: If any one of the following pre-conditions are not met, the issuance creation should fail.~~
    * ~~Collateral token address is not set;~~
    * ~~Collateral token amount is not set;~~
    * ~~Borrow amount is not set;~~
    * ~~Deposit due days is not set\(should we provide a reasonable default?\);~~
    * ~~Engagement due days is not set\(should we provide a reasonable default?\);~~
    * ~~Collateral due days is not set\(should we provide a reasonable default?\);~~
    * ~~Tenor days is not set\(should we provide a reasonable default?\);~~
    * ~~Tenor days is smaller than or equal to the collateral due days\(should we provide a reasonable default?\);~~
    * ~~Grace period is not set\(should we provide a reasonable default?\);~~
    * ~~Interest rate is not set\(should we provide a reasonable default?\)~~
  * ~~Test case 3: If deposit is due but no deposit is made, the issuance goes to Unfunded state;~~
  * ~~Test case 4: If deposit is due but the deposit amount is smaller than the borrow amount, the issuance goes to unfunded state and all deposited Ethers are returned to the seller;~~
  * Test case 5: If the seller tries to deposit more Ethers than the borrow amount, the deposit should fail.
  * Test case 6: If anyone other than the seller tries to deposit Ether, the deposit should fail;
  * Test case 7: If anyone\(including the seller\) tries to deposit any token, the deposit should fail;
* Test set 2: Issuance engagement\(the issuance is in Engageable state\)
  * Test case 1: Buyers can engage the issuance and then deposit the collateral token. This makes two changes:
    * The issuance is transitioned into Active state;
    * All Ethers are sent to the buyer so that the issuance Ether balance has reached zero;
  * Test case 2: If a buyer already engages the issuance\(no matter whether the collateral is fully deposited\), and a second buyer wants to engage, the engagement should fail;
  * Test case 3: If no one engages the issuance when engagement is due, the issuance is transitioned into Complete Not Engaged state;
  * Test case 4: If the collateral is due but no collateral payment is made, the issuance is transitioned into Delinquent state;
  * Test case 5: If the collateral is due but the collateral balance is smaller then the collateral amount, the issuance is transitioned into Delinquent state and the deposited collateral token is sent back to buyer;
  * Test case 6: During the collateral deposit phase, no one can deposit any Ethers;
  * Test case 7: During the collateral deposit phase, only the buyer can deposit the collateral token, otherwise the deposit should fail;
  * Test case 8: During the collateral deposit phase, if the buyer tries to deposit more than the collateral token ,the deposit should fail;
* Test set 3: Issuance repay\(the issuance is in Active state\)
  * Test case 1: Buyer can repay the Ether before the grace period is due. After repaying back the whole borrow amount, the following change happens:
    * The issuance is transitioned into Complete Engaged state;
    * All Ethers are sent back to seller;
    * The interest, which are calculated in the collateral tokens, are sent to seller;
    * The remaining collateral balance are sent back to buyer;
    * The issuance balance of both Ether and collateral tokens becomes zero;
  * Test case 2: If buyer fails to repay the whole borrow amount before the grace period is due, the following change happens:
    * The issuance is transitioned into Delinquent state;
    * All Ethers, if there are any, are sent to the sellers;
    * The interest, which is calculated in full period and in the collateral token, are sent to seller;
    * The remaining collateral tokens, if there are any, are sent back to buyer;
    * The issuance balance of both Ether and collateral tokens becomes zero;
  * Test case 3: No one can deposit any token in this period;
  * Test case 4: Only buyer can deposit Ether in this period;
  * Test case 5: If the buyer tries to deposit more Ethers than the borrow amount, the deposit should fail.

