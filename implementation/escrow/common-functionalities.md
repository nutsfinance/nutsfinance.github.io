# Common Functionalities

The following functionalities are shared between Instrument Escrow and Issuance Escrow.

![](../../.gitbook/assets/escrow-common-functionalities.jpg)

For any account, they can:

* Get ETH balance of individual user
* Get ERC20 token balance of individual user
* Get the list of ERC20 tokens deposited of individual user

This means everyone can view the balance information of any other users in both Instrument Escrows and Issuance Escrows.

For the escrow owner\(Instrument Manager\), it can:

* Withdraw ETH for any account
* Deposit ETH for any account
* Withdraw ERC20 token for any account
* Deposit ERC20 token for any account

Instrument Manager can deposit/withdraw assets for any account so that it could implement the following functionalities:

* Transfer assets from Instrument Escrow to Issuance Escrow
* Transfer assets from Issuance Escrow to Instrument Escrow
* Transfer assets between Issuance Escrows, e.g in issuance renewal

