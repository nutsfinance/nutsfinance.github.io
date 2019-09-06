# Design Principles

The following design principles serve as general practice to address both functional and non-functional requirements of NUTS Platform.

## Instrument-Centered

The goal of NUTS Platform is to serve FSPs and help them build marketplace that serves makers and takers. Each marketplace is built on top of one financial instrument, so NUTS Platform should be centered on financial instrument.

* Each financial instrument should form an isolated management domain.
  * All data and assets of one financial instrument are kept and managed in its domain;
  * No cross-domain operation\(if any\) should be allowed without going through NUTS Platform;
  * Each domain might evolve into an autonomous zone in the future; 
* The NUTS Platform, minus the isolated domain for individual financial instrument,  should be thin and flexible.
  * NUTS Platform should not hold any financial instrument assets;
  * NUTS Platform should hold minimum data about financial instrument;
  * NUTS Platform should be a registry for financial instrument and its issuances;
  * NUTS Platform should manage NUTS token.

## Isolation

Between financial instruments,

* All financial instruments are isolated;
* Cross-instrument operation, if any, should go though NUTS platform.

Inside financial instruments,

* The data of individual issuance should be isolated;
* The asset of individual issuance should be isolated;
* Cross-issuance operation, such as data or asset migration, are allowed within one financial instrument if it's supported by the instrument.

## Reliability

All data and assert mutation in NUTS Platform should be either of the following cases:

* Triggered by users through NUTS Platform API;
* Triggered by Oracle through NUTS Platform API.

In a word, no mutation is allowed without going through NUTS Platform API.

## Forward Compatible

NUTS Platform should be upgradeable in order to both fix bugs and address additional feature requirements.

* Existing financial instrument management domain should be upgradeable;
* NUTS Platform, minus the instrument management domain, should also be upgradeable;
* NUTS Platform should be able to introduce new implementation of financial instrument management domain.



