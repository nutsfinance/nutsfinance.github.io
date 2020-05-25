# Instrument Escrow

Instrument Escrow is the asset portal for an instrument domain. It's the place where users can deposit assets to or withdraw assets from the instrument domain. Since it's the only place where assets can be transferred out of the instrument domain, it provides a strong guarantee that no assets will be loss unless there is critical vulnerability in instrument business logic.

Users can deposit both ETH and ERC20 tokens into Instrument Escrow. When ETH is deposited, Instrument Escrow uses the Wrapped ETH contract which is global on NUTS Platform to convert ETH into Wrapper ETH token. This allows Instrument Escrow and Issuance Escrow to work on ERC20 tokens only.

Users can also withdraw both ETH and ERC20 tokens from Instrument Escrow. When ETH is withdrawn, Instrument Escrow converts Wrapper ETH token to ETH and sends out ETH.

