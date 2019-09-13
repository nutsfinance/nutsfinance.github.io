# Instrument Escrow

The Instrument Escrow is created along with the instrument management domain to keep user assets that are not yet locked by issuance.

In order to deposit assets to individual issuance, users should deposit assets to Instrument Escrow first, and then invokes NUTS Platform API to transfer assets from Instrument Escrow to Issuance Escrow.

The following functionalities, in addition to the shared functionalities between instrument escrow and issuance escrow, are supported for any account:

* Deposit ETH for their own account
* Withdraw ETH for their own account
* Deposit ERC20 token for their own account
* Withdraw ERC20 token for their own account

