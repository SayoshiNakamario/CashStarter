# CashStarter (Alpha Testing)

##What is CashStarter?
A decentralized crowdfunding system built on BitcoinCash. It is a set of UTXO smart contracts written with [CashScript](https://cashscript.org/) that work together to provide a fundraising experience similar to Kickstarter or Flipstarter. 

The system is divided up into 6 contracts:

**CashStarterManager:** lets users create a new campaignUTXO and sends it to the CashStarter contract.
**CashStarter:** holds all campaignUTXO's and allows users to pledge to an existing campaignUTXO. Pledgers receive a pledgeNFT that records the campaignID and pledge amount in its commitment.
**Refund:** combined with a campaignUTXO and a pledgeNFT, allows the pledgeNFT owner to refund their pledge.
**Stop:** combined with a campaignUTXO, this contract allows * *anyone* * to cause a campaign to stop accepting pledges after the campaign deadline has been reached.
**Cancel:** combined with a campaignUTXO, this contract allows the campaign creator to stop accepting pledges even before the campaign deadline has been reached.
**Claim:** combined with a campaignUTXO, this contract allows the campaign creator to claim the pledged BCH if the campaigns fundraise amount is met or exceeded.

##Incentivized Front-Ends
Front-ends (websites, wallets, etc.) that interact with the CashStarter contracts (specifically, initialize() and claim()) can charge the user an 'interaction fee' from a minimum of 0.00001 BCH (1000sats) up to a maximum of 0.01 BCH (1,000,000 sats). This provides an anti-spam measure, as well as a financial incentive for websites and apps to provide the front-end interactions to users.

The first implementation is [FundMe.Cash](https://fundme.cash)

##Campaign Data
The BCH is handled by the CashStarter contracts, but the campaign data is hosted outside the blockchain. Currently FundMe.Cash hosts the campaign data itself.
* *Open to ways of sharing this data between apps* *  

##CashStarter Limits
* Maximum campaigns: 1,099,511,627,774 
* Maximum BCH you can fundraise: 2,814,749
* Maximum BCH you can pledge: 2,814,849
* Latest campaign ending block: 499,999,999 (year ~11521)
