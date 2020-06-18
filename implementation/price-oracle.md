# Price Oracle

Many financial instruments rely on asset prices in order to function properly. For example, the [Lending](../instruments/lending.md) and [Borrowing](../instruments/borrowing.md) instruments calculate the required collateral based on the price of the principal and collateral tokens.

For the Lending and Borrowing instruments, it's the Service Providers' responsibility to provide price oracle to the underlying issuances. The Service Providers can choose to use a fixed value, to deploy a price oracle which are updated as needed, or to use well-known third-party price oracles. In order to reduce the user friction, NUTS Platform provides a reference price oracle contract which could be adopted by Service Providers.

## Price Data Sources

