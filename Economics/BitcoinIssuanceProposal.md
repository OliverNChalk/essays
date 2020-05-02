# Proposed Solution to Bitcoin's Broken Issuance

While Bitcoin represents a breakthrough in technology, Satoshi was bound to not get everything 100% perfect on the first release. However, to improve social coordination and scalability, Bitcoin's base layer has largely ossified and the only way to adopt new changes is via soft-fork. Leaving aside the soft-fork vs hard-fork argument, here is a proposal for how to soft-fork an alternative issuance model onto Bitcoin.

### Thesis
---
I believe that the current Bitcoin issuance and miner compensation model is long-term flawed. Ideally, there would be small perpetual issuance that would strive to be off-set by burning a portion of transaction fees. Things like active UTXO rent could also help properly [internalize externalities](https://www.quora.com/What-does-internalizing-the-externality-mean) and further fix incentives in the Bitcoin system.

At a high-level, I propose the soft-forking the following changes:
 - Change `block_reward` to be `1/N * remaining_issuance`
 - Charge transactions a `protocol_fee` that will be fed back into `remaining issuance`
 - Charge an `N satoshi` fee per day on UTXOs smaller than `Y BTC`

These changes would have the following benefits:
 - Once 21M coins are issued, miner revenue will be less volatile than a pure transaction fee model. This is because `protocol_fee` will be distributed slowly to future miners.
 - The storage requirement of full nodes will go down because [dust UTXOs](https://cointelegraph.com/news/understanding-litecoins-dusting-attack-what-happened-and-why) can eventually be safely removed from the active UTXO set.
 - This proposal requires no trusted third-parties and still preserves the 21M Bitcoin supply cap.

#### Example implementation model:
I am not extremely familiar with the technical intricacies of Bitcoin but I imagine the proposed changes could be implemented in the following manner:
 - Miners only consider a block valid if it includes a `0 satoshis` transaction from the miner of the previous block.
 - This `0 satoshi` transaction will be used to forward the accumulated `protocol_fee` and future issuance to the next miner.
 - Each miner will subtract their designated `block_reward` and add in the `protocl_fee`s collected from transactions (minus the portion the protocol allows them to keep).
 - Miners will thus be able to enforce a new issuance and transaction fee model via majority hash rate.

It could also be implemented by having miners agree on a public address that controls the future issuance. If the private key of this address was publicly known, all miners could sign and receive transactions on behalf of this address.

#### Credit & Caveat
The idea of a `protocol_fee` as a way to fund perpetual issuance and the associated benefits was taken from Ethereum's EIP1559 proposal. This is simply an adaptation of that proposal that could be implemented on top of Bitcoin.

Because this is soft-forked onto Bitcoin, malicious miners could collude to steal the future issuance that is being forwarded from miner to miner.