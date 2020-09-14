# SunStake White Paper

## Introduction

Since the blockchain (aka. distributed ledger) technology was first [introduced](https://bitcoin.org/bitcoin.pdf), a community of crypto enthusiasts emerged and has been growing rapidly. Blockchains are so different and isolated from the rest of the world that almost everything, even something as simple as running a trivial application, needs to be re-invented. With Bitcoin being the first ever blockchain-native asset (i.e. cryptoasset), the community has witnessed numerous others being created in the process. As the ecosystem continues to mature, the diversity of cryptoassets is expected to grow further.

However, the inherent isolation from the "outside world" also means that only assets that were created on blockchains in the first place can be transferred, used, and exchanged on-chain, which has essentially blocked access to a wide variety of valuable traditional assets such as gold and oil. In addition, despite growing in types and valuation, most cryptoassets are found to be highly co-related with Bitcoin after all, making the exposure to different kinds of cryptoassets less meaningful than desired.

Bringing off-chain assets on-chain, or even just bringing cryptoassets _cross_-chain, is a rather complicated process that's not as intuitive as one might think, which has resulted in further isolation not just between blockchains and the non-blockchain world, but also between different blockchains. For example, one cannot trade Bitcoins on Ethereum, or vice versa.

While truely taking assets cross-chain remains an unsolved puzzle, with the current blockchain infrastructure built and maintained by the marvelous community, the SunStake project sets out to bridge the aforementioned gap by enabling synthetic assets to be created and exchanged on-chain, without replying on any centralized party.

## Existing Alternative

Gaining exposure to non-crypto assets as well as assets from another blockchain is nothing new. There have been a number of different solutions around the problem, with the most popular one being the use of hard peg with centralized bridges.

Such a solution relies on a centralized party to keep a reserve of the underlying asset, and to issue a blockchain token representing that particular asset. The most famous example of this is probably [Tether](http://tether.to/), the issuer of multiple widely used such hard-pegged tokens as Tether USD (USDT) and Tether Gold (XAUt).

The main issue of such approach is the need for trust and transparency, which are difficult to establish. For the Tether example above, there have been constant concerns and allegations from the crypto community that the popular USDT token issuer isn't keeping enough reserve in its treasury, or has been dishonestly using it for investment to boost earnings. The fear and uncertainty around the trust-worthiness of Tether has historically caused significant USDT value deviation from 1 US dollar multiple times.

**The need for trust with the hard-pegging solution defeats the very purpose of blockchains**. Even if a service provider has an established track record, there's still no guarantee that it will continue to be well behaved.

## What is the SunStake Protocol

Inspired by [Synthetix](https://www.synthetix.io/), the team is proposing the SunStake protocol, a brand new synthetic asset issuance and trading protocol, as an attempt to bring exposure to non-crypto assets to the blockchain users.

### What are Synthetic Assets?

For the formal definition, according to [Investopedia](https://www.investopedia.com/terms/s/synthetic.asp), synthetics are "_financial instruments that are engineered to simulate other instruments_". Simply put, if one holds a synthetic of an underlying asset in his/her portfolio, he/she will then be exposed to (almost) the same price movements of that underlying asset. Synthetics are nothing specific to blockchains, and have existed long before the technology came along. For example, a long stock position can be simulated by purchasing a call option and a put option of that particular at the same time, in which case the combination of the two options can be referred to as a synthetic of the long stock.

In the context of SunStake, synthetic assets are TRC20 tokens that track price movements of other blockchain/non-blockchain assets in such a way that holding these tokens are (almost) financially the same as actually holding those assets. For instance, if a user were to buy and hold sGOLD (synthetic gold) tokens with USDT tokens, when gold appreciates against the US dollar, the user can sell his/her sGOLD tokens back to more USDT tokens than he/she started with. In fact, USDT in this example is also a synthetic, except it's controlled by a centralized party, and thus vulnerable to single point of failure.

### Built for the SUN community

The project name "SunStake" is quite self-explanatory. The protocol will allow SUN community holders (i.e. SUN token holders) to create synthetic assets by staking, and earn passive income in the process.

One of the aspects that set SunStake apart is the use of SUN token as collateral. Unlike many existing synthetic asset networks, SunStake does not attempt to force its own token, SSK, into its users' hands. Instead, SunStake builds its services around the established SUN community. Building and maintaining a new community is hard, and hopefully the decision to leverage an existing robust community will increase the project's chance of success.

### Why Tron?

The reasons for building the platform on the Tron blockchain are mostly around its desirable transaction speed and fee model.

Originally established by [BitShares](https://bitshares.org/), the [delegated proof of stake (DPOS)](https://how.bitshares.works/en/master/technology/dpos.html) consensus algorithm used by the Tron blockchain guarantees a fast and predictable block time, which results in a much better user experience compared to proof-of-work (POW) blockchains like Ethereum, while still maintaining a high degree of decentralization that helps keep the network secure and censorship-resistent.

The fee model of Tron is a combination of fee-based and stake-based models, which uses resources obtained from staking by default, and falls back to taking fees from account balance if there aren't enough resources from staking to be used. This model allows for free usage of the blockchain for long-time TRX holders, while not compromising the blockchain's usability for one-off users or those who would not bother learning about the staking process.

The SunStake team believes that these desirable properties of the Tron blockchain will enable a smooth user experience of the platform.
