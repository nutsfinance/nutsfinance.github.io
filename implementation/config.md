# Config

Config is a central contract for NUTS Platform configurations. Currently, it can be only updated by NUTS Platform admins. A more community-driven solution might come in the future release.

Config provides the following configurations:

* Address of Wrapped ETH token
  * One Wrapped ETH token contract is deployed within NUTS Platform
  * All Instrument Escrows share the same Wrapped ETH token contract
  * Instrument Escrows convert ETH into Wrapped ETH token when user deposits ETH, and convert Wrapped ETH token into ETH when user withdraws ETH
  * The address of Wrapped ETH token is updateable, but it take effects in new instrument domains created after the update. Existing Instrument Managers keep a reference to the existing Wrapped ETH token contract and continue to use it.
* Address of Escrow Factory
  * One Escrow Factory contract is deployed within NUTS Platform;
  * All Instrument Managers share the same Escrow Factory to create Instrument Escrow and Issuance Escrow
  * The address of Escrow Factory is updateable, but it take effects in new instrument domains created after the update. Existing Instrument Managers keep a reference to the existing Escrow Factory and continue to use it.
* Address of NUTS token
  * NUTS token is deposited when an instrument is activated
  * The address of NUTS token is updateable but updating it is discouraged
* Amount of NUTS token to deposit when a new instrument is activated
  * If set to 0, no deposit is required
  * Deposited NUTS token is burned when the instrument is deactivated
  * The deposit is updateable
* The list of Instrument Manager Factories
  * Instrument Manager Factory is used to create new Instrument Managers
  * Multiple Instrument Manager Factories might coexists on NUTS Platform. Different Instrument Manager Factories are keyed by a byte32 version string.

