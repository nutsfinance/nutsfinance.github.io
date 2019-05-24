# Unit Test Plan

This document lists the unit test coverage for all smart contracts and libraries of NUTS platform. Unit tests are mostly written in Solidity.

### Property.sol

* TestPropertyValue.sol: Test setting and getting values for the following data types, especially after serialization and deserialization.
  * bytes
  * string
  * uint
  * int
  * address
  * bool
* TestPropertyArray.sol: Test adding and reading array elements for the following data types. especially after serialization and deserialization.
  * bytes
  * string
  * uint
  * int
  * address
  * bool

### Balance.sol

* TestBalance.sol: Test setting and getting balance of both Ether and any ERC20 tokens, especially after serialization and deserialization.

### Transfer.sol

* TestTransfer.sol: Test setting and getting transfer information\(token type, token address, amount\) for both Ether and any ERC20 tokens, especially after serialization and deserialization.

### UnifiedStorage.sol

* unifiedStorage.js: Testing setting, updating and getting values with key in JavaScript;
* TestUnifiedStorage.sol: Test setting, updating and getting values in Solidity;

### NutsEscrow.sol

* nutsEscrow.js
  * Test anyone should be able to deposit and withdraw Ether;
  * Test anyone should be able to deposit and withdraw ERC20 tokens;
  * Test issuance should be able to hold Ethers;
  * Test issuance should be able to hold ERC20 tokens;

### InstrumentRegistry.sol

* TestInstrumentRegistry.sol: Test instrument registration, deactivation and validation;

### Loan.sol

* TestLoan.sol: The test cases should be comprehensive and complete enough to cover all possible state transitions between any state.
  * Initiated
  * Engageable
  * Active
  * Unfunded
  * Complete not engaged
  * Complete engaged
  * Delinquent

