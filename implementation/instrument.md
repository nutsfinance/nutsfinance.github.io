# Instrument

Instrument is the portal for FSPs. It's deployed on chain by FSP as an independent contract. Once the instrument is deployed, FSP could activate the instrument on NUTS Platform with the instrument address. The Instrument Registry with create a new instrument domain around the instrument and assign it with a unique instrument ID.

The interface for instrument contains only three methods:

* supportsIssuanceEscrow\(\): Returns whether issuances of this instrument need an Issuance Escrow. The default value is true;
* supportsIssuanceEscrow\(\): Returns whether issuances of this instrument can operate directly on the assets in its Issuance Escrow. This is an experimental feature and its default value is false;
* createIssuance\(\): Create a new issuance instance. Once created, the issuance instance is owned and operated by Instrument Manager. Instrument should not operate directly on the issuance instance.

Even though instrument cannot directly interact with issuances, it can hold instrument-wide configurations for all issuances. In fact, one of the critical role of instrument is to act as an Oracle for all issuances in the same instrument domain. By storing instrument address as a member variable, issuances can query instrument for instrument-wide configurations which could be updated by FSPs as needed. Below are some examples of using instrument as issuance Oracle:

* FSPs could maintain maker and taker whitelist in instrument. They could update the whitelist at any time as the whitelist changes. When a new issuance is initialized, it could query instrument to check whether the maker is whitelisted; when a new engagement is proposed, it could query instrument to check whether the taker is whitelisted. The whitelist update does not affect existing issuances and engagements.
* FSPs could set maker and taker fees in instruments. When a new issuance is initialized, it checks whether any maker fee is required; if so, the issuance transfers the maker fee from maker to the fee recipient. Similarly, when a new engagement is proposed, it checks whether any taker fee is required. If so, the issuance transfers the taker fee from taker to the fee recipient.
* FSPs could provide a price feed Oracle in instrument, which allows issuances to query asset prices;
* FSPs could set investment strategies in instrument, which allows issuances to invest accordingly.

