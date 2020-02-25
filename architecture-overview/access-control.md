# Access Control

The diagram below depicts the access control topology in NUTS Platform. In short, 

* NUTS Platform controls FSP's and maker's access via NUTS token;
* FSP controls maker's and taker's access via white list;
* Maker controls taker's access via custom logic in instrument.

![](../.gitbook/assets/access-control-4.jpg)

## NUTS Platform to FSP

NUTS Platform controls FSPs' access via NUTS token. When creating new financial instrument, FSPs are required to deposit certain amount of NUTS token. The deposited NUTS tokens are burned when the financial instruments are deactivated.

NUTS token is deposited in Instrument Registry and burned in Instrument Manager.

## NUTS Platform to Maker

NUTS Platform controls makers' access via NUTS token. When creating new issuance of existing financial instruments, makers are required to deposit certain amount of NUTS token. The deposited NUTS tokens are burned when the issuance enters INACTIVE state. No operation is allowed once an issuance enters INACTIVE state.

NUTS token is deposited and burned in Instrument Manager.

## FSP to Maker

FSP can determine who can create new issuance from the existing financial instrument. Instrument Manager provides a Maker Whitelist for FSPs so that they can set the list of eligible makers.

In activating new financial instrument on NUTS platform, FSPs need to set whether this instrument uses maker whitelist. Once set, FSP can add account to the maker whitelist or remove account from the maker whitelist. Maker whitelist must be enabled in activating new financial instrument and cannot be updated in the future.

## FSP to Taker

FSP can determine who can engage existing issuances. Instrument Manager provides a Taker Whitelist for FSPs so that they can set the list of eligible takers.

In activating new financial instrument on NUTS platform, FSPs need to set whether this instrument uses taker whitelist. Once set, FSP can add account to the taker whitelist or remove account from the taker whitelist. Taker whitelist must be enabled in activating new financial instrument and cannot be updated in the future.

## Maker to Taker

Whether makers can determine who can engage their created issuance depends on the financial instrument implementation. For example, FSPs could implement a white list mechanism in the instrument. When creating a new issuance, makers can provide the white listed takers as issuance parameters. FSPs can support white list update as one of the custom operations.

