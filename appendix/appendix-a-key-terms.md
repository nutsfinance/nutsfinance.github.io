# Glossary

<table>
  <thead>
    <tr>
      <th style="text-align:left"></th>
      <th style="text-align:left"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Active positions</td>
      <td style="text-align:left">Active Positions = Engageable Offers + Engaged Offers</td>
    </tr>
    <tr>
      <td style="text-align:left">Approval transaction</td>
      <td style="text-align:left">For security measures, users must first grant approval permission for
        dApp Toolkit to withdraw a defined quantity of ERC-20 tokens from the user&#x2019;s
        wallet. The Ethereum network will then verify the token transfer limit
        for each deposit transaction. Upon successful verification, users will
        be granted with &lt;=X amount of tokens transfer limit per transaction.
        Users can then deposit the tokens into the Instrument Account. If the next
        deposit amount exceeds X, the Ethereum network would require another approval
        for the increased amount</td>
    </tr>
    <tr>
      <td style="text-align:left">Borrowing instrument</td>
      <td style="text-align:left">Borrowing instrument is a form of loan where Borrowers create borrowing
        offers by depositing collateral initially. Borrowing offer provides flexibility
        for Borrowers to define the specific borrowing terms such as: principal
        amount, interest rate, collateral ratio and tenor</td>
    </tr>
    <tr>
      <td style="text-align:left">Canceled</td>
      <td style="text-align:left">Offer canceled by Maker</td>
    </tr>
    <tr>
      <td style="text-align:left">Collateral</td>
      <td style="text-align:left">A Borrower&apos;s pledge of assets to the Lender in order to secure the
        principal</td>
    </tr>
    <tr>
      <td style="text-align:left">Collateral ratio</td>
      <td style="text-align:left">Represents the required ratio between the value of pledged assets relative
        to the value of principal assets</td>
    </tr>
    <tr>
      <td style="text-align:left">Completed</td>
      <td style="text-align:left">Offer has completed its life cycle</td>
    </tr>
    <tr>
      <td style="text-align:left">Engageable</td>
      <td style="text-align:left">Offer available for engagement</td>
    </tr>
    <tr>
      <td style="text-align:left">Engaged</td>
      <td style="text-align:left">Offer engaged by Takers</td>
    </tr>
    <tr>
      <td style="text-align:left">Expired</td>
      <td style="text-align:left">Offer expired without any Takers</td>
    </tr>
    <tr>
      <td style="text-align:left">FSP</td>
      <td style="text-align:left">Financial Service Provider, underwriters of financial instruments and
        organizers of exchange markets</td>
    </tr>
    <tr>
      <td style="text-align:left">Inactive positions</td>
      <td style="text-align:left">Inactive Positions = Expired Offers + Canceled Offers + Completed Offers</td>
    </tr>
    <tr>
      <td style="text-align:left">Input token</td>
      <td style="text-align:left">The asset which the Maker is using for exchange</td>
    </tr>
    <tr>
      <td style="text-align:left">Instrument account balance</td>
      <td style="text-align:left">Represents the available balance for offer creation or offer engagement
        in a specific instrument market</td>
    </tr>
    <tr>
      <td style="text-align:left">Interest rate</td>
      <td style="text-align:left">In a lending position, interest rate is the borrowing cost charged by
        the Lender to the Borrower. In a borrowing position, interest rate is the
        borrowing cost paid by the Borrower to the Lender</td>
    </tr>
    <tr>
      <td style="text-align:left">Lending instrument</td>
      <td style="text-align:left">Lending instrument is a form of loan where Lenders create lending offers
        by depositing principal initially. Lending offer provides flexibility for
        Lenders to define the specific lending terms such as: principal amount,
        interest rate, collateral ratio and tenor</td>
    </tr>
    <tr>
      <td style="text-align:left">Liquidated</td>
      <td style="text-align:left">Offer liquidated by System</td>
    </tr>
    <tr>
      <td style="text-align:left">Liquidation alert</td>
      <td style="text-align:left">System will trigger a liquidation alert when the collateral ratio falls
        by 15% relative to the initial collateral ratio. Borrower is required to
        deposit additional collateral assets to increase the ratio back to its
        initial level to avoid liquidation</td>
    </tr>
    <tr>
      <td style="text-align:left">Liquidation event</td>
      <td style="text-align:left">A liquidation event will be automatically trigged when the collateral
        ratio falls by 20% or more relative to the initial collateral ratio. The
        system will automatically close out the loan position. Borrowers can no
        longer repay or deposit additional collateral assets to reactivate the
        loan position</td>
    </tr>
    <tr>
      <td style="text-align:left">Liquidation levels</td>
      <td style="text-align:left">Level 1: the collateral ratio falls by 15% relative to the initial collateral
        ratio Level 2: the collateral ratio falls by 20% or more relative to the
        initial collateral ratio</td>
    </tr>
    <tr>
      <td style="text-align:left">Maker</td>
      <td style="text-align:left">Creators of financial instrument offers. Also referred to as Liquidity
        Providers</td>
    </tr>
    <tr>
      <td style="text-align:left">Output token</td>
      <td style="text-align:left">The asset which the Maker is looking to exchange for</td>
    </tr>
    <tr>
      <td style="text-align:left">Overall account balance</td>
      <td style="text-align:left">
        <p>Overall account balance is the aggregated balance across all instrument
          markets.</p>
        <p>Overall Account Balance = Savings A/C Balance + Lending A/C Balance +
          Borrowing A/C Balance + Swap A/C Balance</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Payables</td>
      <td style="text-align:left">Represents a user&apos;s obligations to repay. Payables balance is the
        sum of assets owed by the user.</td>
    </tr>
    <tr>
      <td style="text-align:left">Position balance</td>
      <td style="text-align:left">Represents the aggregated assets escrowed in all active positions across
        instrument markets Position Balance = Receivables - Payables</td>
    </tr>
    <tr>
      <td style="text-align:left">Principal</td>
      <td style="text-align:left">In a lending position, principal is the asset which the Lender wishes
        to lend out. In a borrowing position, principal is the asset which the
        Borrower wishes to borrow</td>
    </tr>
    <tr>
      <td style="text-align:left">Receivables</td>
      <td style="text-align:left">Represents the assets owed to the user. Receivable balance is the sum
        of assets supplied by the user that is currently locked in engaged and
        engageable offers</td>
    </tr>
    <tr>
      <td style="text-align:left">Swap instrument</td>
      <td style="text-align:left">Swap instrument is a form of spot exchange function between two tokens
        specified by the Maker. Maker of a swap offer determines the exchange rate,
        exchange tokens and offer valid period</td>
    </tr>
    <tr>
      <td style="text-align:left">Taker</td>
      <td style="text-align:left">Engagers of financial instrument offers currently available on the market</td>
    </tr>
    <tr>
      <td style="text-align:left">Tenor</td>
      <td style="text-align:left">The length of time until a loan is due</td>
    </tr>
    <tr>
      <td style="text-align:left">Valid period</td>
      <td style="text-align:left">The length of time until the the swap offer expires</td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>