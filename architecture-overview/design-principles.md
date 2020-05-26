# Design Principles

The following principles guides the design and implementation of NUTS Platform.

## Security

For all DeFi projects, security is paramount and is often the deciding factor of the project' success. Blockchain technologies make financial data visible and verifiable to public but make its vulnerability open as well. The most recent attack on dForce shows that anyone can study and exploit the vulnerability of a DeFi project.

In order to serve as a DeFi platform to host extensive financial instruments, NUTS Platform must treat security as the topmost concern. The following principals are applied to ensure security of NUTS Platform:

* Assets in different financial instruments are strictly isolated. Each financial instrument has its own asset domain and asset domains are isolated from each other. If one financial instrument is broken\(e.g. due to instrument code vulnerability or Service Provider key loss\), users' assets in other instruments or they own wallet should not be impacted.
* Assets in different issuances of the same financial instruments are relatively isolated. In one asset domain, assets from different issuances are isolated. Participants of one issuance cannot operate on the assets of another issuance of the same instrument.
* Users' assets should not be transferred into an asset domain without explicit user action. Users must manually deposit their assets in order to participate in the financial instrument. NUTS Platform should not touch any asset outside individual asset domains.
* Users' assets in a financial instrument's asset domain can be operated only through NUTS Platform services. If NUTS Platform services are proven to be secure, all assets locked in its asset domains are secure as well.

## Auditability

The ability to perform a comprehensive examination on the financial status is critical in enhancing transparency and security of financial instruments. Existing DeFi products are mostly difficult to audit due to the following reasons:

* Each DeFi protocol tends to define their own financial domain concepts tailored to its specific need. For example, DEX and lending protocols tend to have different domain models, while liquidation pool-based and order book-based DEX protocols can also differ greatly. The lack of a common domain model makes it difficult to reason about DeFi protocols using a common framework.
* For most DeFi protocols, it's hard to read out their internal data directly from their smart contracts. In order to comprehensively audit a DeFi protocol, the first step is to precisely replicate its internal state off-chain. This could be either via smart contract events or reading methods. However, neither approach can provide a complete view of a smart contract's internal data due to Ethereum's API limitation. 

NUTS Platform aims at providing a generic domain model for financial instruments and facilitates retrieval and examination of instrument status. Users of NUTS Platform should be able to view and analyze the instrument status with ease.

## Extensibility

As a DeFi instrument platform, NUTS Platform should be flexible and extensible in order to meet the new and varying financial market requirements. The following principals should be applied:

* Financial instrument developers should be able to implement new instruments with ease. Therefore, the domain model must be able to cover both current and future instrument requirement.
* NUTS Platform developers should be able to add new platform functionalities with ease. This requires NUTS Platform architecture to be flexible for future enhancement without migrating to a new platform unless it's essential.

## Efficiency

Blockchain operations come with cost as miners are paid to maintain the integrity and liveness of the blockchain. As users need to pay for their transactions in NUTS Platform, NUTS Platform should be gas efficient to reduce user friction.

