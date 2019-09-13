# Issuance Escrow

The Issuance Escrow is created along with individual issuance to keep assets locked by issuance.

Users/Issuances cannot deposit directly to/withdraw directly from Issuance Escrow; only Instrument Manager can do that. In short, instruments tells Instrument Manager what is the expected transfer to apply, then Instrument Manager complete the transfer on behalf of instrument.

For example, assume that an issuance wants to transfer 5 ETH of account A from Issuance Escrow to Instrument Escrow. In its return value, Instrument tells Instrument Manager this desired transfer action to take for the current issuance. Instrument Manager first withdraws 5 ETH from the corresponding Issuance Escrow, and then deposits this 5 ETH into Instrument Escrow. After this transfer, this 5 ETH is under account A's balance in Instrument Escrow, which means account A can withdraw it any time.

![](../../.gitbook/assets/escrow-interaction.jpg)

This transfer mechanism allows Instrument to perform asset transfers without taking direct actions to Issuance Escrow. While it's still Instrument's responsibility to ensure the desired transfer is legit, NUTS Platform ensures that Issuance Escrow is tempered with by Instruments.

As a summary, the following functionalities, in addition to the shared functionalities between instrument escrow and issuance escrow, are supported for Instrument Manager:

* Migrate ETH balance from one account to another
* Migrate ERC20 token balance from one account to another

The later allows Instrument Manager to change the ownership of an asset within an Issuance Escrow.

