# Protobuf Solidity Generator

NUTS Platform has an in-house solution to generate Solidity stubs from protocol buffer message definitions. The generator code repo is [here](https://github.com/nutsfinance/solidity-protobuf).

NUTS Platform has being using protocol buffer since its beginning. NUTS Platform v1 uses protocol buffer to reduce the storage cost since protocol buffer gives an optimal data compression. Both NUTS Platform v1 and v2 use protocol transfer to serialize complicated method parameters and return values, such as array of structs. However, as ABIEncoderV2 is adopted by more and more protocols, we migrate to ABIEncoderV2 in NUTS Platform v2.5 as well.

The main usage of protocol buffer in NUTS Platform v2.5 is export standardized and formatted issuance data. As stated in section [Design Principal](../architecture-overview/design-principles.md#auditability), the key to enhance issuance auditability is the ability to replicate its internal state off-chain. Protocol buffer provides the following benefits:

* It makes defining and serializing issuance and engagement properties easy. Financial instrument developers can simply define their own issuance and engagement properties with protocol buffer. Our generator will generate their Solidity stubs so that the custom properties can be serialized with ease. What's more, protocol buffer is much more flexible in defining complicated structures. Those complicated structure data can still be serialized and read out using a single method getIssuanceProperty\(\).
* It makes reading and analyzing issuance and engagement properties easy. Once the data is read out using getIssuanceProperty\(\), the financial instrument analyzer can parse it using any language as protocol buffer has a list of well-designed generators in different languages.

Since the generated protocol buffer stub is used in reading method only, it does not increase the gas usage for makers and takers. However, it does increase the contract code size. This is not a big deal in creating issuance as we use proxy solution to create new issuance instance.

