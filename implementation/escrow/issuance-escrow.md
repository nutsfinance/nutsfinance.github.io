# Issuance Escrow

Issuance Escrow, which is one per issuance, helps manages the locked assets for individual issuance. Issuance Escrows only work on ERC20 tokens, as ETH is converted into Wrapped ETH token by Instrument Escrow.

Instrument can optionally define whether an Issuance Escrow is needed for this instrument. For example, an off-chain order book-based swap does not need an Issuance Escrow as the asset swap could be settled directly on Instrument Escrow. Instrument Escrows are required by default.

Instrument Manager is the only contract that could operate the assets in Issuance Escrows, while others can only check its balance information. When an asset transfer is needed, the issuance contract will tell Instrument Manager what are the desired asset transfer actions. Instrument Manager performs the actual asset transfer actions.

Instrument can optionally define whether issuance transaction is supported. If set to true, issuance instance is also granted the admin role of the Instrument Escrow, which means issuance instance can also operates on the assets in Issuance Escrow. This is useful for issuances that want to deposit its locked assets into third-party protocols such as Compound. However, this is only an experimental feature and is not used by existing financial instruments.

