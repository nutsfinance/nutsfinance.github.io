# Protobuf Solidity Generator

NUTS Platform supports financial instruments with properties and parameters of various types, including complex struct. In order to address this requirements, NUTS Platform introduces a generic serialization/deserialization tools where instrument developers can use Protocol Buffer to define custom data structure, and the tool generates serialization/deserialization stubs that converts the custom data structure from and to bytes.

NUTS Platform is also designed to be forward compatible and should support upgrade. Even though NUTS Platform logic can be upgraded using Proxy, data format upgrade is more trickier. Protocol Buffer is extensible and works well in data structure upgrade.

For more information about our Protocol Buffer Solidity Generator, please refer to the [repo](https://github.com/nutsfinance/solidity-protobuf).

