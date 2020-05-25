# Instrument Registry

Instrument Registry serves as the registry for instrument domains. It's a light-weight registry that maintains minimum information for instrument domain creation and lookup.

Instrument Registry has the following responsibilities:

### Activate Financial Instruments

As mentioned in section [Instrument](instrument.md), once the instrument contract is deployed, FSPs can activate this instrument on NUTS Platform in Instrument Registry. Below is the activation process:

1. Instrument Registry queries Config to get the Instrument Manager Factory;
2. Instrument Registry calls Instrument Manager Factory to create a new instrument domain for this instrument;
3. Instrument Registry assigns a new ID for the instrument.

During the activation process, FSPs might be required to deposit NUTS tokens which are burned when the instrument is deactivated. The amount of NUTS token to deposit is configured in the Config.

### Lookup Financial Instruments

Instrument Registry supports looking up instrument domain by instrument ID. Since the Instrument Manager is the portal for the instrument domain, the lookup method simply returns the address of the Instrument Manager.

