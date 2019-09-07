# Timer Oracle

Issuance state changes are mostly triggered by participant actions. For example, collateral deposits from borrower makes borrow tokens available to borrowers. Sometimes issuance state changes are also driven by time. For example, if there is no collateral deposited within some period, the issuance should be delinquent. Therefore, an Oracle is needed to provide timing information to issuance.

Currently Instrument supports two times of scheduled events:

* Events that are scheduled to happen after some timestamp
* Events that are scheduled to happen after specific block

In order to scheduled these events, issuances emit events that contains information including timing\(timestamp or block\), event name and event payload. A Timer Oracle notifies issuance once the scheduled time has passed.

Note that one scheduled event might be notifies multiple times. Therefore, it's up to the Instrument to make sure that the same event is not processed multiple times.

