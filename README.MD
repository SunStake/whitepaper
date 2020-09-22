# SunStake White Paper

**Last Update Time**: September 22nd, 2020

> NOTE
>
> This is a living document that will be updated as needed to reflect design changes over time. No infomation shall be considered final until mainnet launch.

## Introduction

Since the blockchain (aka. distributed ledger) technology was first [introduced](https://bitcoin.org/bitcoin.pdf), a community of crypto enthusiasts emerged and has been growing rapidly. Blockchains are so different and isolated from the rest of the world that almost everything, even something as simple as running a trivial application, needs to be re-invented. With Bitcoin being the first ever blockchain-native asset (i.e. cryptoasset), the community has witnessed numerous others created in the process. As the ecosystem continues to mature, the diversity of cryptoassets is expected to grow further.

However, the inherent isolation from the "outside world" also means that only assets that were created on blockchains in the first place can be transferred, used, and exchanged on-chain, which has essentially blocked access to a wide variety of valuable traditional assets such as gold and oil. In addition, despite growing in types and valuation, most cryptoassets are found to be highly co-related with Bitcoin after all, making the exposure to different kinds of cryptoassets less meaningful than desired.

Bringing off-chain assets on-chain, or even just bringing cryptoassets _cross_-chain, is a rather complicated process that's not as intuitive as one might think, which has resulted in further isolation not just between blockchains and the non-blockchain world, but also between different blockchains. For example, one cannot trade Bitcoins on Ethereum, or vice versa.

While truely taking assets cross-chain remains an unsolved puzzle, with the current blockchain infrastructure built and maintained by the marvelous community, the SunStake project sets out to bridge the aforementioned gap by enabling synthetic assets to be created and exchanged on-chain, without relying on any centralized party.

## Existing Alternative

Gaining exposure to non-crypto assets as well as assets from another blockchain is nothing new. There have been a number of different solutions around the problem, with the most popular one being the use of hard peg with centralized bridges.

Such a solution relies on a centralized party to keep a reserve of the underlying asset, and to issue a blockchain token representing that particular asset. The most famous example of this is probably [Tether](http://tether.to/), the issuer of multiple widely used such hard-pegged tokens as Tether USD (USDT) and Tether Gold (XAUt).

The main issue of such approach is the need for trust and transparency, which are difficult to establish. For the Tether example above, there have been constant concerns and allegations from the crypto community that the popular USDT token issuer isn't keeping enough reserve in its treasury, or has been dishonestly using it for investment to boost earnings. The fear and uncertainty around the trust-worthiness of Tether has historically caused significant USDT value deviation from 1 US dollar multiple times.

**The need for trust with the hard-pegging solution defeats the very purpose of blockchains**. Even if a service provider has an established track record, there's still no guarantee that it will continue to be well behaved.

## What is the SunStake Protocol

Inspired by [Synthetix](https://www.synthetix.io/), the team is proposing the SunStake protocol, a brand new synthetic asset issuance and trading protocol, as an attempt to bring exposure to non-crypto assets to the blockchain users.

### What are Synthetic Assets?

For the formal definition, according to [Investopedia](https://www.investopedia.com/terms/s/synthetic.asp), synthetics are "_financial instruments that are engineered to simulate other instruments_". Simply put, if one holds a synthetic of an underlying asset in his/her portfolio, he/she will then be exposed to (almost) the same price movements of that underlying asset. Synthetics are nothing specific to blockchains, and have existed long before the technology came along. For example, a long stock position can be simulated by purchasing a call option and a put option of that particular stock at the same time, in which case the combination of the two options can be referred to as a synthetic of the long stock.

In the context of SunStake, synthetic assets are TRC20 tokens that track price movements of other blockchain/non-blockchain assets in such a way that holding these tokens is (almost) financially the same as actually holding those assets. For instance, if a user were to buy and hold sGOLD (synthetic gold) tokens with USDT tokens, when gold appreciates against the US dollar, the user can sell his/her sGOLD tokens back to more USDT tokens than he/she started with. In fact, USDT in this example is also a synthetic, except it's controlled by a centralized party, and thus vulnerable to single point of failure.

### Built for the SUN community

The project name "SunStake" is quite self-explanatory. The protocol will allow SUN community members (i.e. SUN token holders) to create synthetic assets by staking, and earn passive income in the process.

One of the aspects that set SunStake apart is the use of SUN token as collateral. Unlike many existing synthetic asset networks, SunStake does not attempt to force its own token, SSK, into its users' hands. Instead, SunStake builds its services around the established SUN community. Building and maintaining a new community is hard, and hopefully the decision to leverage an existing robust community will increase the project's chance of success.

### Why Tron?

The reasons for building the platform on the Tron blockchain are mostly around its desirable transaction speed and fee model.

Originally established by [BitShares](https://bitshares.org/), the [delegated proof of stake (DPOS)](https://how.bitshares.works/en/master/technology/dpos.html) consensus algorithm used by the Tron blockchain guarantees a fast and predictable block time, which results in a much better user experience compared to proof-of-work (POW) blockchains like Ethereum, while still maintaining a high degree of decentralization that helps keep the network secure and censorship-resistent.

The fee model of Tron is a combination of fee-based and stake-based models, which uses resources obtained from staking by default, and falls back to taking fees from account balance if there aren't enough resources from staking to be used. This model allows for free usage of the blockchain for long-time TRX holders, while not compromising the blockchain's usability for one-off users or those who would not bother learning about the staking process.

The SunStake team believes that these desirable properties of the Tron blockchain will enable a smooth user experience of the platform.

## Using the SunStake Protocol

Using the SunStake network mainly involves the process of the minting, exchanging, and burning of sythetics.

### Minting Synthetics

In the SunStake protocol, users create sUSD, the syntheic US dollar, by excessively collateralizing with SUN tokens. As opposed to being backed by real US dollars in a reserve controlled by a centralized third party, sUSD tokens are backed by SUN tokens locked up via staking in an open-source smart contract.

Unlike a hard-pegged token, the price of the backing asset (i.e. SUN tokens) for sUSD is potentially highly volatile. Thus, a high collateralization ratio must be maintained for the system to properly function. The SunStake team will set the initial collateralization ratio to `1000%`, which can be changed later through a decentralized governance process.

The protocol incentivizes staking and collateralization ratio maintanance with financial rewards. When a user stakes SUN and mints sUSD (and maintains the required ratio), he/she receives:

- exchange fees paid in SSK

- staking rewards in SSK

Exchange fees are paid by users who use the SunStake Exchange to exchange between different synthetic assets, and shared 50/50 between SUN token stakers for providing the service, and [SSK token stakers](#Staking) for managing and evolving the network.

Note that since staking SUN tokens and minting sUSD puts the funds locked into a [debt pool](#The-Debt-Pool), there's a risk (and, of course, rewards) involved for doing so. Stakers are advised to fully understand the risk before participating.

### Exchanging Synthetics

Synthetic asset holders can exchange between different types of synthetics supported by the protocol through the use of the SunStake Exchange. Exchange trades are executed directly based on the exchange rate between the two assets involved. So no counter-party is required for a trade to happen.

For example, if a user wants to convert `1,000` sUSD to sBTC (Bitcoin synthetic), and the real-time price of sBTC is `10,000` sUSD, the user will receive `0.1` sBTC (without considering fees for illustration purposes), without slippages at all.

The reason SunStake Exchange is able to convert between synthetic assets directly without a counter-party is that the risk from different asset types is part of the commitment of all pool participants (i.e. SUN stakers) anyways, and all the pool cares about is the total amount of debt, which doesn't change in the event of asset exchange.

### Burning Synthetics

Once a SUN holder stakes his/her SUN tokens and mints synthetics, the part of SUN tokens used to fulfill the `1000%`
collateralization ratio will be locked and not available for transfers. These SUN tokens will only be released when they're no longer being used for the ratio maintanance, which is when the debt (from minting synthetics) of the user decreases, and a user's debt decreases when:

- the overall value of all synthetic assets in existence decreases; or

- the user burns synthetic assets he/she holds.

Therefore, to exit the pool and free up the locked SUN tokens, a user must burn the same amount of synthetic assets as his/her debt. Doing so is essentially "paying off" the debt (imagine the user taking a loan in synthetics when minting) to free up the collateral (i.e. SUN tokens).

Due to price movements (both in SUN and in synthetics) it's possible that a user's collateralization ratio will fall below the required level of `1000%`, thus disqualifying him/her from receiving rewards. In this case, the user can increase the ratio by either adding more SUN tokens, or by burning synthetics.

## Oracles

For the system to function properly, it's vital to keep the synthetic peg accurate and reliable, namely, to keep 1 sUSD = 1 US dollar. Since blockchains are isolated from the outside world, the SunStake network cannot possibly know the value of any assets that's not being traded on the same blockchain. Even for those already being traded on the Tron blockchain (e.g. on [Justswap](https://justswap.io/)), they're typically manipulation-prone due to their small volumes compared to large centralized exchanges.

Thus, an oracle system must be used to continuously feed price data onto the blockchain via a smart contract. Initially, the network will use an oracle run by the SunStake team, but will eventually migrate to community-elected oracles.

### Oracle Contract

An oracle contract will be developed and deployed to the Tron blockchain. It will be created as a public good that any other smart contracts can use. External contracts can retrieve price data simply by calling a method on the oracle contract, without building and maintaining the entire oracle network themselves. No fees will be charged by the oracle contract except, of course, the energy needed for calling the contract by the Tron blockchain itself.

### SunStake Oracles

The SunStake team will develop and open-source an oracle that can be later used by the community. The oracle program will pull data from multiple sources and push measurements into the oracle contract.

To speed up development and upgrades, in the early phase of the SunStake network the team will simply be running an oracle itself, but will eventually migrate to community-run oracles for better decentralization and censorship-resistence.

### Migration to Community Oracles

As mentioned above, the SunStake network will eventually evolve to using oracles run by the community for getting price data. These oracles will be elected through a decentralized voting process by SSK holders.

## The Debt Pool

The debt pool is one of the core components of the protocol. This section serves to explain what it is, and to give examples regarding some of the calculations involved.

### What is the Debt Pool

Whenever someone stakes SUN tokens and mints sUSD, he/she incurs a "debt". It's called "debt" because by minting, the user is essentially borrowing sUSD tokens from the system, and the SUN tokens are the collateral. It's like borrowing money from a bank, and collateralizing it with one's house.

What's different from borrowing money from a bank is that in SunStake, one's debt is pooled and dynamically adjusted.

Debts are pooled. To exit the system, one does _not_ pay the amount that's originally minted. Instead, the user's share of the pool is paid (i.e. burned). For example, if a user joins the pool by minting 100 sUSD, taking up 50% of the pool, when he/she exits the pool, asumming no new participants joined, he/she would need to pay 50% of whatever the entire pool is worth at the point of exit, and the amount has little to do with what's originally minted (100 sUSD).

The reason for the pool value change is that the following invariant always holds:

    Debt Pool Value == Total Value of All Synthetics

Since prices of synthetics change over time (unless only sUSD exists), the debt pool is constantly adjusted to match the aggregate value of all synthetic assets.

### Debt Pool Examples

For illustration purposes, exchange fees are ignored in this discussion.

As an example, let's say 4 users are currently in the pool:

| User    | Minted Value |
| ------- | ------------ |
| Alice   | 100 sUSD     |
| Bob     | 200 sUSD     |
| Charlie | 300 sUSD     |
| David   | 400 sUSD     |

Total amount of debts in the system is `1,000 sUSD`.

With a current exchange price of `1 sETH = 200 sUSD`, Bob swaps his `200` sUSD holdings into sETH. He will receive exactly `1` sETH because there's no slippage/spread.

Now everyone's position becomes:

| User    | sUSD | sETH | Total Value |
| ------- | ---- | ---- | ----------- |
| Alice   | 100  | -    | 100 sUSD    |
| Bob     | -    | 1    | 200 sUSD    |
| Charlie | 300  | -    | 300 sUSD    |
| David   | 400  | -    | 400 sUSD    |

The debt pool value is still `1,000 sUSD` at this point, and everyone except Bob can just burn the sUSD they're holding and leave the system. Bob can also convert his `1` sETH back to sUSD and burn them to leave.

Assuming no one joined or left, after a while, ETH depreciates in value and the new exchange rate becomes `1 sETH = 100 sUSD`.

After this price change everyone's position becomes:

| User    | sUSD | sETH | Total Value |
| ------- | ---- | ---- | ----------- |
| Alice   | 100  | -    | 100 sUSD    |
| Bob     | -    | 1    | 100 sUSD    |
| Charlie | 300  | -    | 300 sUSD    |
| David   | 400  | -    | 400 sUSD    |

Total amount of debts in the system drops to `900 sUSD`.

To calculate the amount of sUSD needed to be burnt to exit the system:

| User    | Pool Share | Need to Burn |
| ------- | ---------- | ------------ |
| Alice   | 10%        | 90 sUSD      |
| Bob     | 20%        | 180 sUSD     |
| Charlie | 30%        | 270 sUSD     |
| David   | 40%        | 360 sUSD     |

Everyone except Bob now has some sUSD left even after burning enough sUSD to leave the pool. Bob is losing money and it makes perfect sense as he was holding an asset that dropped in value.

## SSK Token

Like most other blockchain projects, SunStake issues its own token: SSK. The SSK token is at the core of the SunStake protocol, and mostly used for incentivization and governance.

### Token Value

The value of the SSK token derives from:

- the right to receive 50% of exchange fees when staked; and

- the right to make decision regarding the network (governance) when staked

### Staking

Similar to how SUN tokens can be staked to mint synthetics, SSK tokens can also be staked, but no synthetics can be minted from staked SSK tokens.

The staking of SSK tokens is essentially a proof-of-commitment type of stake. Once staked, tokens are frozen and the staker starts to enjoy the right to receive exchange fees and to vote for proposals. However, once an unstake request is initiated:

- the right to earn fees and vote is lost immediately; and

- tokens will be sent back to the staker only after 72 hours.

So, to earn exchange fees one must commit to holding SSK tokens for at least 3 days. This delay is intentionally designed to reward commitment to the SunStake community.

### Governance

In the early stage of the network, development and decision making will be mostly done by the team directly, trading decentralization for development speed. As the network matures, however, everything should be gradually handed over to the community, transforming into a true decentralized autonomous organization (DAO).

After the transformation, all improvements and changes to the network will be done via proposals, which will be approved by voting from SSK stakers.

### Distribution

Inheriting the philosophy of the SUN community, SunStake strives to maximize decentralization. There're no token sales. A total of 10 million SSK tokens will be issued:

- 3 million (30%) SSK tokens will be minted and deposited into a Justswap exchange. The team will also deposit 1 million TRX upfront into the pool for providing initial liquidity.

  Note that the team may withdraw from the pool if enough liquidity is provided by the community. In this case, the SSK tokens withdrawn from the pool will be destroyed.

- 500,000 (5%) SSK tokens will be airdropped to existing SUN token holders.

- 1 million (10%) SSK tokens are reserved for the team. This portion will only be minted after platform launch on Tron mainnet, and will be released gradually.

- 5.5 million (55%) SSK tokens are reserved for incentivization purposes.

  Like the team portion, these tokens will only be minted after mainnet launch. The token contract will be locked so that minting is not possible before that.
