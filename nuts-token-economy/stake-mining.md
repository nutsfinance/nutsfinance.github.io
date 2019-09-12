# Escrow as Stake Mining

NUTS stake mining is performed on a mining pool which consists of assets in NUTS Platform. An asset, which can be ETH or any ERC20 tokens, is considered as assets in NUTS Platform as long as it is in one of the Escrows, including both Instrument Escrows and Issuance Escrows. This means that any account could participant in NUTS stake mining once he deposits assets into Instrument Escrow until they withdraw all their assets.

Not all tokens are eligible to be part of the mining pool. NUTS Platform determines the list of ERC20 tokens supported and the list can be updated by NUTS Platform.The value of ERC20 tokens is converted into ETH in stake mining calculation.

The stake mining calculation is perform off-chain. As the number of NUTS tokens minted is constant for each Ethereum block, the number of NUTS token minted for individual account is proportional to its current balance in NUTS Platform for all supported tokens. The stake mining Oracle calculates the number of tokens minted to each account and then mint them on NUTS token.

