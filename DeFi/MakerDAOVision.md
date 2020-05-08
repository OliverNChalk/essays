# MakerDAO - Multi Collateral vs. ETH Only

I'm writing this short explainer because I'm tired of seeing stuttering ETH-maxis post about how a $DAI that was backed only by $ETH would be vastly superior to the current system. It is becoming increasingly clear that these people are largely unfamiliar with MakerDAO's system and simply want to increase the price of their Ether by having newbs lock it up in highly risky, capital-inefficient margin positions.


### MakerDAO as a margin trading platform
As a tool for margin trading, MakerDAO is incredibly limited, these are the current parameters:
    - 150% Liquidation Ratio
    - 3x Leverage
    - 1 Hour Margin Call Time

If you're a trader/business looking to get leveraged exposure to ETH (read as capital efficient exposure), MCD (Multi-Collateral DAI) is a terrible system to do this with. The only redeeming quality of this system is that you get up to 1-hour to react to significant market movements or systemic failures within the system. Everything else about the platform is suboptimal for margin trading ETH.

Yet despite all this, there are people on twitter lecturing me about how this embarrassment of a margin trading system will somehow scale to bank all the un-banked of the world and provide trustless stablecoin access to all of humanity. If MakerDAO insists on staying with only highly-liquid, trustless collaterals, it will be outcompeted on the lending (leverage) side by solutions that are much more capital efficient.

The current peg crisis ($DAI trading above 1 USD) is because there is not enough demand for ETH-based Vaults but there is a lot of demand for $DAI. Letting people use previously illiquid assets as collateral is a great way to build up greater demand for Vaults and balance the supply and demand of $DAI. MakerDAO's unique edge over other protocols is its governance system and its ability to mint $MKR to cover bad debt. These two mechanisms mean MakerDAO is the only synthetic protocol (today) that can safely use real-world assets as collateral AND remain 100% decentralized, trustless, etc. (note, there is no such thing as a zero-risk synthetic)

### Competition for fiat synths & margin-trading
We are already seeing lots of emerging competition for Maker in the two core areas it currently caters to:
 - Margin Trading (Vaults)
 - Synthetic Assets ($DAI)

For margin trading (I'm including derivatives) we have:
 - Numerous of margin protocols
 - FutureSwap
 - Options
 - UMA (lerveraged shorting)

For synthetics we have:
 - UMA
 - Others, probably

If MakerDAO were to go ETH-only they would need to greatly re-architect (faster oracles, for starter) and take risks in other areas (lower collateralization ratios), in order to effectively compete with the upcoming alternatives. I think the safest on-chain margin system will be built on top of a "priceless oracle" (see Augur & UMA for ideas), which MakerDAO currently is not.

I am not saying MakerDAO can't become a high leverage, capital-efficient margin facility. I am saying it currently is not and was never intended as such.

### MakerDAO USP & $MKR Economics
I touched briefly on this up above but the current vision for MakerDAO's USP (Unique Selling Point), is that MakerDAO will act as the risk management protocol (decentralized bank) for a wide range of collateralized loans. For this to work $MKR will provide a backstop for any poor parameter choices made by MakerDAO governance. However, there is little reason to pay stability fees to MakerDAO governance if all MakerDAO is, is a set of $ETH margin trading parameters and an oracle (there are many ways to do this in a more efficient manner).

Now on to economics, why do we pay stability fees to $MKR holders? Why not just fork to a version without stability fees, sometimes called "system rent"?

The answer to this question is two-fold, the first is that the stability fee, when paired with the DSR, acts as a form of funding to balance longs and shorts effectively. However, for this to work we need to build support for a negative DSR and negative stability fees (to properly balance longs and shorts). This would break the social contract that 1 $DAI = 1USD.

The second reason, is that $MKR holders are paid to take on risk in the form of dilution when collateral blows up in their faces. For $MKR holders to be willing to bailout the system when it messes up, we will need to incentivize them with future earnings (stability fees). This economic design is also MakerDAO's biggest opportunity to build a moat, if $MKR becomes the most liquid, dilutable asset on the market, it will be hard to launch a competing version of MakerDAO because liquidity and market caps cannot be forked.

A dotpoint summary for the ETH thought leaders to digest:
 - You can't use $ETH as a back-stop because you can't print $ETH out of thin air to cover bad debt
 - $MKR holders carry dilution risk of centralized assets
 - The more valuable $MKR becomes, the safer $DAI becomes
 - $MKR's market cap and liquidity becomes a moat that cannot be forked
 - Yes, you can make a high-leverage version of ETH-only MakerDAO but that will need to compete with all the other derivative platforms
  - Also, the $MKR token and by extension, governance are necessary to provide a backstop (buyer of last resort) in extreme events