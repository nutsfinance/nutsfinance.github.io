# Deposit Escrow

Deposit Escrow is a special escrow for NUTS token only. It holds NUTS token that is:

* Deposited by FSPs in activating new financial instruments;
* Deposited by makers in creating new issuance.

Deposit Escrow is identical to Instrument Escrow except that:

* The owner is Instrument Registry instead of Instrument Manager;
* The account is Instrument Managers instead of any account.

### Deposit Token for New Instruments

When FSPs activate new financial instruments, the following steps are included:

1. FSP creates an allowance for Instrument Registry;
2. Instrument Registry invokes Instrument Manager Factory to create new Instrument Manager;
3. Instrument Registry transfers NUTS tokens from FSP, and then deposits into Deposit Escrow under new Instrument Manager's account.

### Deposit Token for New Issuance

When makers create new issuance, the following steps are included:

1. The NUTS token should be deposited into Instrument Escrow already;
2. Instrument Manager withdraws the NUTS token and then stores it into Deposit Escrow;

### Return Token

When a financial instrument is deactivated or an issuance is terminated, Instrument Managers retrieves the NUTS tokens from the Deposit Escrow and transfers it to FSP/maker.

