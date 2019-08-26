---
description: This page lists the key non functional requirements for the system.
---

# Non Functional Requirements

## Security

As a DeFi enabler, NUTS Technology Platform should treat security as the top-most requirements. It should provide strong guarantee that the data and assets on the NUTS Technology Platform are temper-proof.

* Users of NUTS Technology Platform are not able to access data and asserts without using the NUTS Technology Platform APIs;
* NUTS Technology Platform should not expose any security weakness itself;
* NUTS Technology Platform should be able to address the potential security weakness of the instruments running on the NUTS Technology Platform.

## Upgradability

The upgradeability requirements are shared by NUTS Technology Platform and the financial instruments running on the NUTS Technology Platform.

* For the NUTS Technology Platform, it should be able to upgrade without affecting any financial issuance created on top of it. Due to the nature of the NUTS Technology Platform \(central portal to all financial issuance and accessible to the underlying properties\), it is expected that the NUTS Technology Platform will be upgraded periodically to enhance security or implement new functionalities. After each upgrade, all existing financial issuances will be status quo in terms of accessibility and functionality.
* For financial instruments created using the NUTS Technology Platform, they are immutable once deployed. If new functionalities are desired, they should be created as new instruments without impacting the existing issuances.

## Flexibility

NUTS Technology Platform should provide an easy-to-user framework for instrument developers to implement their own instruments.

* The instruments model provided by NUTS Technology Platform should be generic and works well with most financial instruments;
* The instrument developers should be able to access and manipulate instrument data and assets with ease.

