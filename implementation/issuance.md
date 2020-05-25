# Issuance

Issuance is where the instrument business logic is defined. Each time a maker tries to create a new issuance, they must do it via Instrument Manager as it is the portal of the instrument domain. Instrument Manager in turn invokes instrument contract to create a new issuance instance. Once the issuance instance is created, it's owned and managed by Instrument Manager. 

Issuance has a well-defined lifecycle as shown in section [Domain Model](../architecture-overview/domain-model-1.md#issuance-lifecycle). It could be engaged one or more times, depending on the issuance nature. Each engagement also has its own lifecycle, as discussed in section [Domain Model](../architecture-overview/domain-model-1.md#engagement-lifecycle). Issuance and engagement lifecycle are driven either user interaction or timed event. In either case, the caller cannot interact directly with the issuance instance. Instead, it must be done via Instrument Manager.

## Issuance Property

Issuance defines a set of standard properties:

* Issuance ID: ID of the issuance. Unique in the instrument domain.
* Instrument ID: ID of the instrument. The combination of instrument ID and issuance ID uniquely identifies an issuance on NUTS Platform.
* Maker address: Address of the maker who creates the issuance;
* Issuance creation timestamp: When the issuance is created;
* Issuance due timestamp: When the issuance is due. Issuance becomes Complete after this timestamp if it's not Complete prematurely;
* Issuance cancel timestamp: When the issuance is cancelled;
* Issuance complete timestamp: When the issuance becomes Complete
  * It's equal to issuance due timestamp if the issuance is Complete because it's due
  * It's smaller than issuance due timestamp if the issuance is Complete prematurely;
* Completion ratio: A number from 0 to 10000 denoting the current progress of the issuance. It's calculation is issuance-specific. 
* Issuance state: State of the issuance\(Initiated/Engageable/Cancelled/Complete\)
* Issuance custom property: Issuance-specific property of the issuance

## Engagement Property

Engagement also defines a set of standard properties:

* Engagement ID: ID of the engagement. Unique in the issuance;
* Taker address: Address of the taker who engages the issuance;
* Engagement creation timestamp: When the engagement is created;
* Engagement due timestamp: When the engagement is due. Engagement becomes Complete after this timestamp if it's not Complete prematurely;
* Engagement cancelled timestamp: When the engagement is cancelled;
* Engagement complete timestamp: When the engagement is Complete. 
  * It's equal to engagement due timestamp if the engagement is Complete because it's due
  * It's smaller than engagement due timestamp if the engagement is Complete prematurely;
* Engagement state: The state of the engagement\(Initiated/Active/Cancelled/Complete\);
* Engagement custom property: Issuance-specific property of the engagement.

## Payable

Issuance uses payable to track its accounting status. Issuance participants can determine how much they are expected to pay/receive in this issuance by checking the payable list of the issuance. Each payable entry is strictly related to one asset.

Payable defines the following properties:

* Payable ID: Each payable entry should have a unique ID;
* Engagement ID: The payable entry might be related to a specific engagement. 0 if the entry is issuance-wide and not related to any issuance;
* Obligator address: Who is expected to pay the asset;
* Claimor address: Who is expected to receive the asset'
* Token address: Address of the asset;
* Amount: The amount of token that should be paid/received;
* Due timestamp: When the payable is due

Payables are immutable once created. A payable entry also has its own lifecycle:

* If a payable is paid out, the payable becomes Paid and is removed from payable list
* If a payable is due, the payable becomes Due and is removed from the payable list
* If a payable is reinitiated by another payable, the payable becomes Reinitiated and is removed from payable list.

## Issuance API

Issuance defines the following standard APIs:

* initialize\(\): Initializes the issuance instance;
* engage\(\): Process a new engagement request to the issuance;
* processEvent\(\): Process a custom event to the issuance. Note that all custom operations, including issuance cancellation or issuance repay, can be defined as custom event;
* getIssuanceProperty\(\): A single method to read out all properties about the issuance and its engagements.

Issuances can also define customized read methods so that users can directly query the issuance instance for more information about the issuance.

## Timed Event

Issuance state changes can be triggered by either user interaction or time. For example, an issuance might be transitioned into Compete state once it's due. Since Ethereum does not have any "automatic" method, someone must tell the issuance that it's due. This is done by the [Timer Oracle](timer-oracle.md).

The general process is as following:

* The issuance defines the list of events that it should be notified after a specific timestamp using Solidity events;
* The Timer Oracle keeps the list of timed events and monitors whether there is any event due;
* Once the event is due, the Timer Oracle notifies the event to NUTS Platform;
* The timed event is dispatched to issuance for future processing.

