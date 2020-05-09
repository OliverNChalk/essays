# The Option Problem
There is a cost to posting any resting order, this cost can be calculated the same way other options are calculated, using the Black-Scholes model. For Central Limit Order Books (CLOBs), the time variable in the equation is the one-way latency between the trader and the exchange. This latency can range from in the microseconds (collocated), to in the minutes (on-chain trading), all the way into the hours (cross-chain atomic swap trading).

Pricing resting orders as short-term at the money options lets market-makers and other pricing providers better quantify the cost/risk of their order. This model becomes more valuable the higher the latency is, and this is particularly relevant for DeFi protocol risk management.

### Option Problem: DEX
For completely on-chain DEXs (Etherdelta, Oasis), there is no good way to avoid the option problem. There will always be one party that is given the advantage of optionality on order execution. In the current protocols, this party is the taker and as such, they typically pay higher fees or a spread due to this.

This leads to perverse liquidity incentives, where "honest" traders are required to subsidize the losses market-makers incur to arbitrageurs. Typical traders will find themselves paying higher fees and spreads as volatility and arbitrage/front-running increases. This problem is further compounded by the fact that as fees and spread go up, trading volume declines, while the margins of arbitrageurs does not. This could lead to a scenario where only predatory traders trade on-chain and there are no typical traders trading to cover the costs of market-makers.

The cycle could look something like this:
1. Market-makers create an ETHUSD on-chain market with 20bp spread.
2. Arbitrage bots front-run market maker cancels each time price moves > 20bp
3. Market-makers raise spreads to 40bp give them a greater buffer to price moves.
4. Honest traders move to hybrid on-off-chain protocols (0x), MM profits drop
5. The ratio between toxic order flow (losing arbitrage trades) and "honest" trading volume increases
6. Market-makers are forced to further increase their spreads to buffer against price moves

<a name="option-pricing"></a>Option pricing tells us that there is no spread at which a market-maker is safe. As such, the better approach is to not trade on-chain unless they can get a sufficient flow of "honest" traders. An example of this could be liquidation events but all liquidations protocols use auctions to my knowledge (so they wouldn't be filling resting CLOB orders).

##### Reversing Optionality
It is possible to reverse optionality and turn orders into a three-phase process:

1. Maker places a resting limit order.
2. Taker fills the resting limit order.
3. Maker confirms or rejects the order.

This would naturally break a lot of UX and would swing the balance of power in favour of makers. However, it would allow for efficient, low spread arbitrage between centralized exchanges and on-chain exchanges. However, if you're going to break UX like this, it may be better to consider a hybrid model and moving order negotiation and matching off-chain.

### Option Problem: Oracles
Oracles are another class of actors that are subject to the option problem. If an oracle's price is used as the basis for a continuous market (perpetual future), then it is vulnerable to toxic order flow in the form of price arbitrage (sometimes referred to as front-running). There are two ways projects currently address this:
 - Implement a fee that provides sufficient buffer (flawed, [see above](#option-pricing))
   - Synthetix
 - Reverse optionality
   - Synthetix (recently added)
   - FutureSwap

##### Synthetix & FutureSwap
In Synthetix and FutureSwap there is a grace period after you perform a trade in which the oracle can change the execution price of your trade. This doesn't necessarily increase the trust assumption in these oracles but it does break certain things:
 - Positions may become illiquid during this "grace period"
 - It becomes harder to hedge positions because the execution price is unknown
  
For your average speculative trader, these are not major issues but they could pose barriers to the adoption of these derivatives by automated and more sophisticated trading strategies.

##### MakerDAO
<a name="maker-dao-option"></a>
MakerDAO only uses its oracle for collateralization purposes, instead of P&L calculations. This means that with a collateralization ratio of 150%, the price would need to drop 33% for arbitrageurs to be able to exploit the oracle for profit. However, as we know, options will have a price, no matter how far out of the money they are. As such, to limit the risk and cost of writing this option every hour, MakerDAO implements a `debt_ceiling` parameter, that provides a hard-cap (`debt_ceiling - current_debt`) on how much new debt can be minted at any one time.

If one wanted to price the cost Maker's 1 hour delayed oracle imposes on MKR holders, they could work out the price of writing the following option:

```
MakerDAO ETH-A Option
 - Strike: 2/3 * ETHUSD
 - Expiry: 1 Hour
 - Quantity: debt_ceiling - current_debt
```

Then the daily cost to MKR holders would be `24 * option_premium`.