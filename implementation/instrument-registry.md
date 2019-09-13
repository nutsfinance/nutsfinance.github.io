# Instrument Registry

Instrument Registry serves as the registry for instruments. It's designed to be a light-weight registry that contains minimum information required for instruments and manages NUTS token deposited in activating instruments.

Below are the main functionalities of Instrument Registry.

### Activate Financial Instruments

Each financial instrument is a standalone smart contract in Ethereum. After deploying the financial instrument, FSPs need to activate this financial instrument on NUTS Platform.

A certain amount of NUTS token, called instrument deposit, is needed in activating financial instrument.

In activating financial instruments, Instrument Registry delegates Instrument Manager Factory to create a new instrument management domain for each instrument. One instrument can only be activated once in NUTS Platform.

### Deactivate Financial Instruments

FSPs can deactivate a financial instrument activated by themselves. After deactivating, a financial instrument can no create any new issuance, and the deposited NUTS token is returned to FSP.

### Lookup Financial Instruments

Instrument Registry supports looking up instrument management domain by financial instrument. Each instrument management domain has two entries points:

* Instrument Manager Interface, which serves as the portal for issuance operation;
* Instrument Escrow Interface, which serves as the portal for instrument assets.

As each financial instrument can be activated in NUTS Platform for at most once, Instrument Registry supports address lookup for both Instrument Manager Interface and Instrument Escrow Interface using financial instrument address.

