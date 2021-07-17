1. Introduction
1. Motivation
1. Governance
1. Technical implementation
1. Applications
1. References

### Introduction

When Bitcoin launched in 2009, Satoshi proved that value could be stored and transmitted securely without intermediaries. The subsequent release of Ethereum proved that a Turing complete, distributed computer meant that arbitrary state and computation could be put on chain, enabling smart contracts that define complex relationships and agreements between people. 

The impact and reach of blockchain technology is largely confined to the digital sphere. Some novel experiments like [Unisocks](https://unisocks.exchange/) have tokenized real world assets, in this case giving owners a physical pair of socks in exchange for burning a SOCKS token. Unfortunately, the exchange of real-world assets usually relies on centralized trustees - in this case the Uniswap employee sending socks when a token is burned. A rogue sock distributor could simply not send the socks, and the blockchain would never know.

Perhaps socks will never be fully on chain, but fortunately ownership of real estate is a matter of deed.  Deeds are documents that can be held by LLCs, individuals and banks.

Wyoming's [DAO Law](https://www.wyoleg.gov/2021/Introduced/SF0038.pdf) opens the door to forming LLC entities and recognizing the rights and decisions of members as legally binding decisions that will be recognized in a court of law:

> Management of a decentralized autonomous organization shall be vested in its members, if member managed, or the smart contract, if algorithmically managed, unless otherwise provided in the articles of organization or operating agreement (p. 11)

Since LLCs can hold real estate deeds, this means a DAO can hold, manage, and make decisions regarding land owned.

### Motivation

Digitizing physical assets can increase accessibility, improve liquidity, and bring interoperability.

As a case study, compare the difference between converting $100 USD to EUR and converting $100 of ETH to $100 of USDC. The blockchain-native, digital conversion is instant, accessible, transparent, and has lower fees.

Currently, real estate is largely offline and transactions require intermediaries, large sums of capital, and extensive legal paperwork. What Satoshi and Buterin did for value and compute, we propose to do for real estate.

### Previous Examples

As of today, there are several existing projects which put real estate assets on chain. A notable examples is [RealT](https://realt.co/), which is using blockchain technology to innovate on the legacy methods of real estate ownership.  

### Governance

**Trustee model**

The most primitive way to link physical objects to on chain ones is to rely on a trusted third party.For example, a deed to land or a house is tokenized and held by a trustee who signs a binding agreement to execute actions that a smart contract dictates. Much like Unisocks, this is vulnerable to a malicious trustee, who could steal the deed to the house.

Using Wyoming's new DAO law, however, using trustees is more feasible because there is legal recourse and recognition of the DAO LLC. Since the actions of the DAO LLC have legal standing in Wyoming, this would violate the law, the DAO could recover the land. For interfacing with some institutions, the DAO shall assign trustees who take actions on behalf of members. 

### Technical implementation

Land parcels will be ERC-721 tokens (also known as NFTs). Initial parcels will be collectively owned by the DAO, but some parcels may be sold to individuals in the DAO or externally.  

Parcels may be fractionally owned by issuing an ERC-20 governance token over that specific parcel.

The CityDAO governance token will be an ERC-20 token. Holders will vote on proposals that will pass with a 50% + 1 vote majority.

[in discussion]

### Applications

[in discussion]

### References and Further reading

