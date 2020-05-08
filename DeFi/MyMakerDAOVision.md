# MakerDAO Long-term Value Proposition

I'm writing this because I'm tired of seeing stuttering ETH-maxis post about how a $DAI that was only backed by $ETH would be vastly superior to the current system. It is becoming increasingly clear that these people are largely unfamiliar with MakerDAO's system and simply want to increase the price of Ether by having newbs lock it up in highly risky, capital-inefficient margin positions.


### MakerDAO as a margin trading platform
As a tool for margin trading, the MakerDAO is incredibly limited, these are the current parameters:
    - 150% Liquidation Ratio
    - 3x Leverage
    - 1 Hour Margin Call Time

If you're a trader/business looking to get leveraged exposure to ETH (read as capital efficient exposure), MCD (Multi-Collateral DAI) is a horrific system to do this with. The only redeeming quality of this system is that you get up to 1-hour to react to significant market movements or systemic failures within the system. Everything else about the platform is suboptimal for margin trading ETH.

Yet despite all this, there are people on twitter lecturing me about how this embarrassment of a margin trading system will somehow scale to bank all the un-banked of the world and provide a trustless stablecoin liquidity for all of humanity. If MakerDAO insists on staying with only highly-liquid, trustless collaterals, it will be outcompeted on the lending side by solutions that are much more capital efficient.

The current peg crisis ($DAI trading above 1 USD) is because there is not enough demand for ETH-based Vaults but there is a lot of demand for $DAI. Letting people use previously illiquid assets as collateral is a great way to build up greater demand for Vaults and balance the supply and demand of $DAI. MakerDAO's unique edge on other protocols is its governance and the ability to mint $MKR to cover bad debt. These two mechanisms mean MakerDAO is the only synthetic protocol (today) that can safely use real-world assets as collateral AND remain 100% decentralized, trustless, etc.

### Competition for fiat synths & margin-trading
We are already seeing lots of emerging competition for Maker in the two core areas it currently caters to:
 - Margin Trading (Vaults)
 - Synthetic Assets ($DAI)

For margin trading (I'm including derivatives) we have:
 - Tonnes of margin protocols
 - FutureSwap
 - Options
 - UMA (margin shorting)

For synthetics we have:
 - UMA
 - Others, probably

If MakerDAO were ETH-only they would need to greatly re-architect (faster oracles, for starter) and take risks in other areas (lower collateralization), in order to effectively compete with the upcoming alternatives. I think the safest on-chain margin system will be built on top of a "priceless oracle" (see Augur & UMA for ideas), which MakerDAO currently is not.

I am not saying MakerDAO can't become a high leverage, capital-efficient margin facility. I am saying it currently is not and was never advertised as such.

### MakerDAO USP & $MKR Economics
I touched briefly on this up above but the current vision for MakerDAO's USP (Unique Selling Point), is that MakerDAO will act us the risk management protocol (decentralized bank) for a wide range of collateralized loans. For this to work $MKR will provide a backstop for any poor parameter choices on behalf of MakerDAO governance. However, there is little reason to pay stability fees to MakerDAO governance if all MakerDAO is, is a set of $ETH margin trading parameters and an oracle (there are many ways to do this in a more efficient manner).

Now on to economics, why do we pay stability fees to $MKR holders? Why not just fork to a version without stability fees and "system rent"?

The answer to this question is that $MKR holders are paid to take on risk in the form of dilution when collateral blows up in their faces. For $MKR holders to be willing to bailout the system when it messes up, we will need to incentivize them with future earnings (stability fees). This economic design is also MakerDAO's biggest opportunity to build a moat, if $MKR becomes the most liquid, dilutable asset on the market, it will be hard to launch a competing version of MakerDAO because liquidity and market caps cannot be forked.

For the ETH thought leaders that need it in dot point format to understand:
 - $MKR holders carry dilution risk
 - You can't use $ETH as a back-stop because you can't print $ETH out of thin air to cover bad debt
 - The more valuable $MKR becomes, the safer $DAI becomes
 - $MKR market cap and liquidity becomes a moat that cannot be forked
 - Yes, you can make a high-leverage version of ETH-only MakerDAO but that needs to outperform derivatives, which it definitely will not
    - Also, an ETH-only system is far more fragile than a $MKR system due to no backstop/lenders of last resort.