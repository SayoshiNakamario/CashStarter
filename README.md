# CashStarter (FundMe.Cash)

## What is CashStarter?
A decentralized crowdfunding system built on BitcoinCash. It is a set of UTXO smart contracts written with [CashScript](https://cashscript.org/) that work together to provide a fundraising experience similar to Kickstarter or Flipstarter. 

The system is divided up into 6 contracts:

1. **CashStarterManager:** lets users create a new campaignUTXO and sends it to the CashStarter contract.

2. **CashStarter:** holds all campaignUTXO's and allows users to pledge to an existing campaignUTXO. Pledgers receive a pledgeNFT that records the campaignID and pledge amount in its commitment.

3. **Refund:** combined with a campaignUTXO and a pledgeNFT, allows the pledgeNFT owner to refund their pledge.

4. **Stop:** combined with a campaignUTXO, this contract allows * *anyone* * to cause a campaign to stop accepting pledges after the campaign deadline has been reached.

5. **Cancel:** combined with a campaignUTXO, this contract allows the campaign creator to stop accepting pledges even before the campaign deadline has been reached.

6. **Claim:** combined with a campaignUTXO, this contract allows the campaign creator to claim the pledged BCH if the campaigns fundraise amount is met or exceeded.

## Incentivized Front-Ends
Front-ends (websites, wallets, etc.) that interact with the CashStarter contracts (specifically, initialize()) can charge the user an 'interaction fee' from a minimum of 0.00001 BCH (1000sats) up to a maximum of 0.01 BCH (1,000,000 sats). The claim() function also allows the front-end to charge up to a maximum of 1.5% of the campaigns raised funds. These provide an anti-spam measure, as well as a financial incentive for websites and apps to provide the front-end interactions to users.

The first implementation is [FundMe.Cash](https://fundme.cash)

## Campaign Data
The BCH is handled by the CashStarter contracts, but the campaign data is hosted outside the blockchain. Currently FundMe.Cash hosts the campaign data itself.
*Open to ways of sharing this data between apps* 

## CashStarter Limits
* Maximum campaigns: 549,755,813,887 
* Maximum BCH you can fundraise: 1,407,374
* Maximum BCH you can pledge: 1,407,374
* Latest campaign ending block: 499,999,999 (year ~11521)
