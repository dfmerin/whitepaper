# A Decentralized Protocol for Land Ownership and Management


## Contents 

1. Introduction
1. Motivation
1. Fractionalized Ownership
1. Philosophy
1. Governance
1. Technical implementation
1. Applications
1. References

### Introduction

When Bitcoin launched in 2009, Satoshi proved that value can be stored and transmitted securely without intermediaries. The subsequent release of Ethereum proved that a arbitrary computation and state can be agreed upon in a trustless, peer-to-peer fashion. 

The impact and reach of blockchain technology is largely confined to the digital sphere. Some novel experiments like [Unisocks](https://unisocks.exchange/) have tokenized real world assets, in this case by issuing a token that can be burned in order to claim a physical pair of sockets. Unfortunately, the exchange of real-world assets usually relies on centralized trustees - in this case the Uniswap employee sending socks when a token is burned. A rogue sock distributor could simply not send the socks, and the blockchain would never know. 

Perhaps the socks on chain problem is intractable without a Proof of Shipping protocol, but fortunately ownership of real estate is easily accounted for by a ledger. Deeds are documents that can be held by LLCs, individuals and banks often held by county recorders. Leases are agreements executed between private parties. Zoning is how a city decides what can be built where. These agreements between parties are perfect for encoding in a public, transparent blockchain. 

Wyoming's [DAO Law](https://www.wyoleg.gov/2021/Introduced/SF0038.pdf) opens the door to forming DAO LLC entities and giving legal recognition to the DAO and its smart contracts:

> Management of a decentralized autonomous organization shall be vested in its members, if member managed, or the smart contract, if algorithmically managed, unless otherwise provided in the articles of organization or operating agreement (p. 11)

### Motivation

Cities are our interfaces for the world, accelerators for opportunity, and hubs for finding community, yet the mechanisms that govern land, property, and voting leave residents excluded from true ownership in their city.

For example, ownership of real estate is a privilege for the wealthiest people. Allocation of tax dollars is vested with a small group of politicians. Poor land use policies in places like the San Francisco Bay Area are causing displacement and homelessness.

Not all problems can be sovled by putting assets on chain, but our conviction is by fundamentally making city assets digitally legible, we can bolster accessibility, interoperability, and opportunity.

Attempts to radically rethink the City, like Google's Sidewalk Labs in Toronto have [had trouble getting community buy in](https://www.thestar.com/opinion/editorials/2020/05/07/sidewalk-labs-has-walked-away-thats-a-lost-opportunity-for-toronto.html) for a centralized project on privately owned land.

The current city is technology enhanced, but it is not technology defined. Initial considerations are things like real estate, tax collection and allocation, and voting. What Nakamoto and Buterin did for value and compute, we propose to do for the phyiscal world.

### Fractionalized Ownership

Currently, real estate is largely recorded offline and transactions require intermediaries, large sums of capital, and extensive legal paperwork. Fractionalized ownership is a method of dividing real estate, or any asset, into pieces or shares so that it can have multiple owners. Timeshares and companies like Fundrise and Roofstock are in essence ways of providing ownership of a single asset to many people. These versions however come with many restrictions regarding their use, transferability, duration of investment, and limits of legal ownership. 

Tokenization is fractional ownership represented on a blockchain, which increases liquidity, transparency, and accessibility of properties and their profits, and has been [a dream of members of the Ethereum community since it’s earliest days](https://blog.slock.it/decentralized-sharing-economy-to-be-revealed-at-leading-blockchain-conference-f419f15beb7f?gi=828f6c1a9ee1). [RealT](https://realt.co/) is one of the most successful companies to do this so far and has tokenized residential investment properties and sold fractions to individuals all over the world. Profits from these properties are also delivered on chain, increasing the speed in which investors receive cash flow from their investment.

[Countries have also worked to put title registries on chain](https://ethereumworldnews.com/uaes-capital-abu-dhabi-to-place-land-registry-on-blockchain-based-platform/), [and several teams](https://medium.com/meridio/meridio-the-new-standard-for-shared-ownership-of-physical-assets-ce6291050a38) [have tried putting shares of traditional real estate syndications on chain](https://www.coindesk.com/harbor-tokenizes-real-estate-funds-worth-100-million-on-ethereum), and yet none of these efforts have  achieved product market fit. Some reasons are the lack of interoperability between legacy systems with blockchain standards, and lack of regulatory clarity.

Since ownership of land is enforced at the jurisdictional level, a special purpose vehicle (a shell company) is typically created for the sole purpose of owning a parcel of land. This allows the name on the deed to remain the same, while the individuals that comprise the company can change. This is very common for commercial developers since it protects individuals from personal liability and cross-liabilty between properties under common ownership. This is also the way [RealT](https://realt.co/) has structured themselves, a series LLC is created for each property and then that LLC is split up into many pieces by using a legal agreement that dictates that holders of a token are the members of that LLC.

Most, if not all, of the effort to tokenize real estate has been from the perspective of passive investment. Little, or none, of the current examples have approached distributed ownership from the initial purchase decision to ongoing collective management.

### Philosophy

Coming soon....
### Governance

All decisions regarding land acquisition, use, rights, and policies will be decided by CityDAO. By purchasing land through the DAO, purchasers agree to follow the collective policies set by the DAO on land use, taxation, and rights.

The CityDAO governance token will be an ERC-20 token. Holders will vote on proposals that will pass with a 50% + 1 vote majority and the DAO itself may change hyperparameters like vote quorum thresholds and vote delegation rules.

**Smart contracts as legal documents**

Wyoming's DAO law gives legal recongition to the underlying claims of the smart contract, so the general powers of CityDAO are large in scope and only confined to the law of Wyoming and the USA. 

**Powers of the members of CityDAO**

The most primitive way to link physical objects to on chain ones is to rely on a trusted third party. For example, a deed to land or a house is tokenized and held by a trustee who signs a binding agreement to execute actions that a smart contract dictates. Much like Unisocks, this is vulnerable to a malicious trustee, who could steal the deed to the house.

Using Wyoming's new DAO law, however, using trustees is more feasible because there is legal recourse and recognition of the DAO LLC. Since the actions of the DAO LLC have legal standing in Wyoming, this would violate the law, the DAO could recover the land. For interfacing with some institutions, the DAO shall assign trustees who take actions on behalf of members. 

CityDAO may make any proposal that is congruent with Wyoming and US law, but here are some common responsiblities of the DAO:
- LAND MANAGEMENT: Purchasing new land, developing and/or using land, and selling land.
- CONFLICT RESOLUTION: Resolving conflicts between parties, for example boundaries, natural resources, and conflicts of land use.
- TAXATION: Setting tax on land ownership or transfer. 
- TRUSTEE DESIGNATION The intention of the project is to minimize interactions with non-digitally native institutions like banks, notaries, and county assessors, but we acknowledge that it may be be needed, for which we propose the DAO elect a Trustee. 

Since smart contracts may be amended, CityDAO members may vote to grant members additional powers.

**Trustee designation**

For interfacing with some institutions, the DAO shall assign trustees who take actions on behalf of members. Smart contracts will implement an `electTrustee` method who will be authorized to take an action with a purpose. Note, the trustee need not be a member of the DAO.

### Technical implementation

Land parcels will be ERC-721 tokens (also known as NFTs). Initial parcels will be collectively owned by the DAO, but some parcels may be sold to individuals in the DAO or externally.  

Parcels may be fractionally owned by issuing an ERC-20 governance token over that specific parcel.

Pursuant to the discussion on Powers of CityDAO, the governance contract shall implement the followng methods:

- join
- fund
- createProposal
- voteOnProposal
- assignTrustee
- openDispute
- setAnnualTaxRate
- setYearlyTaxRate

[in discussion]

## Land Use

The DAO may choose to hold land or use land with a vote. An example of the governance process. CityDAO votes to acquire a parcel of land proposed by Member A. CityDAO members vote to build a wind energy farm, and assign a Trustee to implement the use case.

**Community campground**
A campground can be established which members of the DAO may use freely. Communal ammenities could be funded through votes of the DAO.

**NFT parcels**
The DAO may designate a land area as individual plots and sell them to individuals.

**Bitcoin Mining**
Buy or Rent a warehouse. Buy ASICs. Make agreement with local utility to use wind energy. 

**Hunting/Fishing Resort**
Buy land along a river. Provide exclusive hunting and fishing access. (ie. elk hunting, flyfishing) Will need to hire someone to maintain the business.

**Land or camping rentals**
Use HipCamp or Airbnb to provide access to the property.

**Farming**
Buy land and make agreement with a local farmer. Note: This would require a member of the DAO to speak with farmer to make the agreement every season. The profit margins for the DAO would be low and seasonal.

**Housing**
Buy an apartment building. Hire a management company to collect rent and do repairs.
## Bibliography, References, and Further Reading

1. Wyoming DAO Law full text - https://www.wyoleg.gov/2021/Introduced/SF0038.pdf
1. RealT whitepaper - https://realt.co/wp-content/uploads/2019/05/RealToken_White_Paper_US_v03.pdf
1. How to Start A New City (Balaji) - https://twitter.com/balajis/status/1269178671086006273?s=20
1. How to Start a New Country (1729) - https://1729.com/how-to-start-a-new-country/
