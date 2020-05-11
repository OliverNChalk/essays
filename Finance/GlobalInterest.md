### NEEDS REVISING

# Interest Rates & Staking

In any asset that is freely traded in spot markets, there should be no divergence between the yield of that asset and any other asset. The reasoning behind this is that it is expected that any differences in yield would be arbitraged and the exchange rate risk would be hedged.

### Interest Rates in Efficient Markets

Assume there are two lending opportunities:

```
Microfinance Loan
 - Currency:      USD
 - Interest Rate: 10%
 - Default Rate:  1%

Ethereum Money Market
 - Currecy:       ETH
 - Interest Rate: 2%
 - Default Rate:  1%
```

Assume you were looking to attain yield on your ETH while you waited for staking to come online. Currently, you are lending it out to Compound, a popular money market on Ethereum, where you get paid 2% interest per annum and you assign it a default rate of 1%. This means you are currently earning a 1% per annum risk-adjusted return. However, over in the fiat world, you see numerous opportunities for higher yield but you don't want to hold any inflationary fiat currencies. Your solution is to hedge the exchange rate and arbitrage the difference in rates without exposing yourself to USD.

Here's your trade, assuming you started with 11 ETH:
 - Sell 11 ETH @ $100USD    (Physical)
 - Buy 11 ETH @ $100USD     (Futures)
 - Lend $1000USD to Microfinance project

When your loan yields $1100USD, you:
 - Close futures position
 - Use futures PNL + loan principal + interest to purchase ETH spot
 - You have earned 10% interest on your ETH, instead of 2%.

In reality, there are more costs to doing this trade than simply being able to fund the loan value and principle.