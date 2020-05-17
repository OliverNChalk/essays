# What is MakerDAO
A lot of MakerDAO's supporters and critics think it is simply a stablecoin protocol. In this article, I go over the core MakerDAO components, the $MKR token, and why MakerDAO is not primarily a stablecoin but rather a decentralized credit system.

### MakerDAO System Overview
There are a few core components in the MCD (Multi-Collateral DAI) system:
 - Vaults: Borrowers can access $DAI loans by posting collateral
 - $MKR: Governance & buyers of last resort
 - $DAI: Synthetic USD

And we also have some core actors:
 - Vault owners, access liquidity against worthy collateral
 - $MKR Holders
   - Take on systemic risk (risk of MKR dilution)
   - Recipients of system earnings
   - Right to govern risk parameters
 - $DAI Holders
   - Seek USD exposure
   - Potentially paid to hold $DAI (via the DSR: Dai Savings Rate)

Most people only see a stablecoin when they look at $DAI but the real innovations here is the credit protocol that lets businesses and individuals access liquidity against their assets (liquid or illiquid). This system has the potential to scale massively as a credit enabling protocol, not so much as a stablecoin.

### What is MakerDAO Not For?
MakerDAO is not a capital-efficient protocol for the leveraged trading of liquid assets, this should be obvious from the various design choices in the system:
 - Slow oracle & liquidations
 - Conservative collateral requirement (150%)
 - Slow, auction-based liquidations (generally used for illiquid assets)

If you're looking to take a USD loan against your ETH, you're much better off taking a leveraged position and selling the remaining 80% of your ETH on spot. Using a protocol with much lower collateral requirements, you can achieve much safer and cost-effective loans:
 - Low liquidation risk (if you took the same size loan)
 - Higher max loan amount
   - 95% of Collateral (FutureSwap)
   - 33% of Collateral (MakerDAO)
 - Lower liquidation penalty
   - \> 13% MakerDAO (ETHDAI)
   - < 5% FutureSwap (ETHDAI)
   - 0.80% BitMEX (ETHUSD)

I use FutureSwap as an example but there will undoubtedly be more, potentially better designed, leveraged trading protocols launching on Ethereum (especially once we see more layer 2 activity).

### What is MakerDAO For?
So if MakerDAO currently sucks as a protocol for leverage, what is it good for? To answer this we need to understand one of MakerDAO's key advantages over other protocols: the $MKR token!

The $MKR token is the mechanism by which the protocol offloads collateral risk onto speculators (the $MKR holders). $MKR holders are rewarded via the stability fees the system charges, however, they are required to bail the system out of it accumulates a deficit, usually via poor collateral choice and management. Thanks to the backstop provided by the $MKR token, the system could see the value of one of its collaterals set to zero and still remain 100% solvent. In fact, given the right parameters, there is no limit to how risky the added collateral can be.

This is perhaps MakerDAO's only advantage over other leverage protocols - it's breadth of assets & ability to avoid insolvency even if liquidations fail. When competing leverage protocols are adding only the top 10 most liquid assets on Ethereum, MakerDAO will be comfortably listing any asset the market shows demand for.

### Scaling MakerDAO
Beyond helping guarantee solvency within the system, the $MKR token has the added advantage of ensuring all issued $DAI are 100% fungible with each other. This is because despite which collateral the $DAI was originally drawn against, all $DAIs are backed by the same $MKR token and enjoy the same guarantees.

So now that we have a fungible unit of account for lenders to take loans in, all that remains is to scale the protocol to solve real-world problems. To do this, $MKR holders should be looking to list as many collaterals as possible, while limiting their risk exposure. While discussing risk management is out of the scope of this article, there definitely are ways to safely add centralized assets but diversifying and limiting risk will be key.

$MKR holders need to be acutely aware of the risks they are underwriting in the system. They are incentivized to maximize $DAI creation and minimize collateral blow-up, such that the system burns more $MKR in stability fees than it issues in bailing out bad debt.

### Are DAI Holders Necessary?
MakerDAO is 100% functional with **zero natural DAI holders**, that is there is technically zero need for any demand for DAI's stablecoin. Maker has the DSR which acts as a global funding rate that CDP holders (or MKR holders) pay DAI holders in exchange for DAI holders propping up the price of DAI. Rational actors will purchase DAI @ <= $1USD, as long as the DSR covers their cost of capital. And as we move into a negative interest rate world, the cost of capital is drastically going down.

So MKR holders need to focus on correctly pricing risk in their system while leveraging the DSR to ensure there is enough incentive for rational actors to absorb newly minted DAI. In fact, it is better to think of natural DAI stablecoin holders as simply saving MKR holders some money they would have otherwise needed to pay to rational actors. So it is definitely nice to have this saving in the form of a lower DSR, however, it is absolutely not critical to the health and growth of the Maker system.

### Strategy & Misc
In my opinion, for every collateral application, I would want to see a good explanation NOT to list it at all. Every collateral that has a non-zero value can be listed with the appropriate parameters (risk fee & debt ceiling). Despite this, Multi-Collateral DAI only has 4 types of collateral in its system. What's even worse, is the most recently added collateral (WBTC) started with a debt ceiling of 10M DAI, when the token itself only had a market capitalization of 10M DAI. Thankfully, the community is now discussing reducing the debt ceiling but this incident showed much of the community still does not properly understand the system they are attempting to govern (or the [reasoning](../Finance/TheOptionProblem.md#maker-dao-option) behind certain parameters).

