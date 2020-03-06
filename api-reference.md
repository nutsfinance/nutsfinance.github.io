# API Reference

This page lists the APIs that are accessible to NUTS Platform users. For more information about the APIs that are used inside NUTS Platform or used only by NUTS Platform owner, please refer to the NUTS Platform smart contracts.

## InstrumentRegistry

### activateInstrument\(\)

A public function for FSPs to activate new financial instruments in NUTS Platform. 

#### Parameters

| Type | Name | Description |
| :--- | :--- | :--- |
| address | instrumentAddress | The address of the deployed financial instrument contract. A financial instrument contract can be shared by multiple activated financial instruments. |
| bytes | instrumentParameters | Custom [parameters](https://github.com/nutsfinance/nuts-platform-v2/blob/master/messages/InstrumentData.proto#L8) about the instrument. |

#### Return Values

| Type | Name | Description |
| :--- | :--- | :--- |
| uint256 | instrumentId | ID of the activated financial instrument. |

### lookupInstrumentManager\(\)

A public function to query Instrument Manager contract address with Instrument ID.

#### Parameters

| Type | Name | Description |
| :--- | :--- | :--- |
| uint256 | instrumentId | ID of the activated financial instrument. |

#### Return Values

| Type | Name | Description |
| :--- | :--- | :--- |
| address | instrumentManagerAddress | Address of the Instrument Manager Contract. |

## InstrumentManager

### getInstrumentEscrowAddress\(\)

Get the address of the Instrument Escrow owned by the current Instrument Manager.

#### Parameters

None

#### Return Values

| Type | Name | Description |
| :--- | :--- | :--- |
| address | instrumentEscrowAddress | Address of the Instrument Escrow owned by the current Instrument Manager. |

### deactivate\(\)

Deactivate the activated financial instrument managed by the current Instrument Manager. Once deactivated, the financial instrument cannot create new issuance, but the existing issuances are not affected.

A financial instrument can be deactivated only once. It can only be deactivated by maker before the instrument override time. After that, anyone can deactivate this instrument.

#### Parameters

None

#### Return Values

None

### setMakerWhitelist\(\)

Update the maker whitelist.

#### Parameters

| Type | Name | Description |
| :--- | :--- | :--- |
| address | makerAddress | The address of the maker. |
| bool | allowed | Whether the maker is allowed to create new issuance. |

#### Return Values

None.

### setTakerWhitelist\(\)

Update the taker whitelist.

#### Parameters

| Type | Name | Description |
| :--- | :--- | :--- |
| address | takerAddress | The address of the taker. |
| bool | allowed | Whether the taker is allowed to engage existing issuance. |

#### Return Values

None.

### createIssuance\(\)

Create a new issuance of the financial instrument. Only whitelisted makers are allowed if maker whitelist is enabled.

#### Parameters

| Type | Name | Description |
| :--- | :--- | :--- |
| bytes | makerParameters | Custom parameters of the issuance. |

#### Return Values

| Type | Name | Description |
| :--- | :--- | :--- |
| uint256 | issuanceId | ID of the newly created issuance. |

### engageIssuance\(\)

Engage an existing issuance.. Only whitelisted takers are allowed if taker whitelist is enabled.

#### Parameters

| Type | Name | Description |
| :--- | :--- | :--- |
| uint256 | issuanceId | ID of the issuance to engage. |
| bytes | takerParameters | Custom parameters of the engagement. |

#### Return Values

None.

### depositToIssuance\(\)

Deposit from Instrument Escrow to issuance.

#### Parameters

| Type | Name | Description |
| :--- | :--- | :--- |
| uint256 | issuanceId | ID of the issuance to engage. |
| address | tokenAddress | Address of the token to deposit. ETH address is Constants.getEthAddress\(\). |
| uint256 | amount | Amount of token to deposit. |

#### Return Values

None.

### withdrawFromIssuance\(\)

Withdraw from issuance to Instrument Escrow.

#### Parameters

| Type | Name | Description |
| :--- | :--- | :--- |
| uint256 | issuanceId | ID of the issuance to engage. |
| address | tokenAddress | Address of the token to withdraw. ETH address is Constants.getEthAddress\(\). |
| uint256 | amount | Amount of token to withdraw. |

#### Return Values

None.

### notifyCustomEvent\(\)

Notify a custom event to the issuance.

#### Parameters

| Type | Name | Description |
| :--- | :--- | :--- |
| uint256 | issuanceId | ID of the issuance to engage. |
| bytes32 | eventName | Name of the custom event. |
| bytes | eventPayload | Payload of the custom event. |

#### Return Values

None.

### getCustomData\(\)

Get custom data from the issuance.

#### Parameters

| Type | Name | Description |
| :--- | :--- | :--- |
| uint256 | issuanceId | ID of the issuance to engage. |
| bytes32 | dataName | Name of the data to retrieve. |

#### 

#### Return Values

| Type | Name | Description |
| :--- | :--- | :--- |
| bytes | customData | The custom data to return. |

