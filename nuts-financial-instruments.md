# NUTS Finance - Financial Instruments

## Use Case Description

The NUTS Technology Platform will allow Financial Service Providers to easily create new financial instruments and deactivate existing financial instruments in a trustless and transparent fashion.

## Actors

* Financial Service Providers \(FSPs\), who are the underwriters of financial instruments. Usually Underwriters of specialized financial instruments or Blockchain Foundation;
* Timer Oracle, who is an external timer service provider that provides timing triggers to NUTS Technology Platform.

## Precondition

FSP implements a new financial instruments according to the selected instrument interface, and then deploy the financial instruments smart contract on Ethereum.

## Process Flow

### Create Financial Instruments

* FSP creates a new financial instruments using the NUTS Technology Platform;
* The newly created financial instrument can have an optional expiration so that no one can create new issuance of a financial issuance once it expires.
* FSP needs to deposit NUTS tokens in creating new financial instruments.

### Deactivate Financial Instruments

* FSP can prematurely deactivate a financial instrument so that no one can create new issuance of this financial instrument.
* NUTS tokens are returned to FSP during deactivation;
* For expired financial instruments, manual deactivation is required in order to get the deposited NUTS tokens back.

