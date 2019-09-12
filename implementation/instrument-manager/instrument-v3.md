# Instrument V3

Instrument V3 adopts Proxy contracts to keep issuance data. While traditional Proxy pattern uses Proxy contract to separate logic and storage, Instrument V3 uses Proxy pattern to separate Issuance data.

![](../../.gitbook/assets/instrument-v3-1.jpg)

When invoking Instrument methods, Instrument Manager does that through the Proxy contracts which delegates calls to Instrument. Each issuance has a dedicated Proxy which keeps data for that issuance.

Instrument V3 allows any Instrument data layout and is thus more flexible than Instrument V2. In order to enforce access control, only Instrument Manager can invoke methods on Proxy contracts. It's also subject to reentrancy attack and thus suitable for trusted FSPs.

