# Timer Oracle

Timer Oracle is a standardized Oracle solution provided by NUTS Platform.

Issuance state update can be driven by issuance participant operations. For example, a repay in full action will complete the borrowing issuance, paying principals and interest to taker and returning collateral to maker.

Issuance state update can be also driven by time. For example, an issuance will be transitioned into Complete state once it's due and is not Complete prematurely. However, since there is no "automatic" method invocation mechanism in Ethereum, someone must be present to tell the issuance that it's due. That's what Timer Oracle comes for.

Issuances can define their time-driven events using the following Solidity events:

* EventTimeScheduled, which schedules an event after a specific timestamp;
* EventBlockScheduled, which schedules an event after a specific block number.

Both events specify the target issuance ID and engagement ID. If a scheduled event is targeted at the issuance, the engagement ID will be 0.

Timer Oracle monitors all issuance instances and keeps track of the emitted scheduled events. Once an event is due, it will notify NUTS Platform which in turn delegates the actual processing to the issuance instance. It's up to the issuance to ensure that:

* The event is indeed notifier after the desired timestamp/block number;
* The event is not handled multiple times.

Please note that there is no Timer Oracle role on NUTS Platform. The Timer Oracle can be treated as a normal user to NUTS Platform. Therefore, anyone could notify the scheduled event. The purpose of the Timer Oracle is to remove the need of FSP/maker/taker to implement their own monitors.

