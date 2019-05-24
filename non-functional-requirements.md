---
description: This page lists the key non functional requirements for the system.
---

# Non Functional Requirements

## Security

## Upgradability

The system can be divided into two layers: The NUTS protocol, and the financial instruments implemented with the NUTS protocols.

For the NUTS protocols, it should be able to upgrade without affecting any financial issuance created on top of it. Due to the nature of the NUTS protocol \(central portal to all financial issuance and accessible to the underlying properties\), it is expected that the NUTS protocol will be upgraded periodically to enhance security or implement new functionalities. After each upgrade, all existing financial issuances will be status quo in terms of accessibility and functionality.

For financial instruments created using the NUTS protocol, they are immutable so that once a financial issuance is created with the target financial instrument, the functionality of this financial issuance will remain unchanged. In cases when the Financial Service Provider needs to upgrade an existing financial instrument, the upgraded financial instrument is treated as a new instrument without affecting existing issuance.

