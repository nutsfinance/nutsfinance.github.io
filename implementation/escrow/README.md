# Escrow

NUTS Platform, minus instrument management domain, does not keep any asset except NUTS token. All instrument assets are kept locally in their corresponding domain using escrow.

Each instrument management domain provides two kinds of escrows: Instrument Escrow, which serves as the asset portal of this instrument, and Issuance Escrow, which manages assets for individual issuance. They are all created by Instrument Manager, which is the owner of these escrows.

![Escrow Model](../../.gitbook/assets/escrow-model.jpg)

|  | Instrument Escrow | Issuance Escrow |
| :--- | :--- | :--- |
| Creation | Created when instrument is created | Created when issuance is created |
| Access by user | Deposit/Withdraw from their own account | Read-only |
| Access by instrument manager | Deposit/Withdraw from any account | Deposit/Withdraw from any account |
| Access by issuance | Read-only | Read-only |



