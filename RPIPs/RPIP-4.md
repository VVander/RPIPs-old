---
rpip: 4
title: Community Resolutions and Voting
author: Mike Leach (@VVander) <mike@bamboofin.tech>
discussions-to: https://dao.rocketpool.net/t/snapshot-voting/400
status: Draft
type: Meta
created: 2022-03-21
---

## Abstract
The Rocket Pool community at large agrees to use RPL token quadratic voting for governance proposals via the snapshot.org platform. Snapshot votes which pass mean their proposals are immediately adopted and the RP DAO will endeavor to enact them as soon as reasonably possible. This proposal suggests using a quadratic RPL vote for off-chain governance. This proposal is not related to the protocol DAO (pDAO), which refers to a planned on-chain protocol governance mechanism.

## Motivation
Governance in Rocket Pool is currently ad hoc, and there is no way for the community to adopt proposals. We must adopt a governance mechanism, even if imperfect, before any governance actions can be taken legitimately, such as but not limited to spending pDAO funds.

## Implementation
  
All Rocket Pool governance proposals must first be posted as a new topic on the governance forums at dao.rocketpool.net. Topics should include a poll with the following format:

```
[poll type=regular results=always chartType=bar]
* Support
* Oppose
[/poll]
```
A favorable forum poll which is live for at least [7] days and a corresponding RPIP document are necessary for snapshot voting to be scheduled. Once the requirements have been met, the following parties will create a snapshot vote and publicize it:

- Darren Langley AKA langers (General Manager - Rocket Pool Pty Ltd)
- Mike Leach AKA Wander (RPIP Editor, Founder - Bamboo Financial Technologies)
- [others]

The snapshot vote will run for [14] days and requires a [50.1%] majority to be successful.

### Snapshot Vote Strategy

The snapshot vote must utilize a custom strategy to accurately capture community sentiment. 

All votes are recorded into a `results` map which utilizes an Ethereum address as the index (`address`). The `result` map's values include a boolean `vote`, with `true` indicating support for the proposal and `false` indicating opposition, and an integer `power` which contains the ultimate voting power of that address. 

`power` for an address is determined in two steps. First, the address is compared to the list of withdrawal addresses for all nodes, and any nodes which use `address` as their withdrawal address will have their contained RPL (staked or otherwise) summed with the amount of RPL contained in the address. Next, `power` is determined in accordance with the following equation for quadratic voting: 

`power = √rpl`, with the result truncated into an integer.

*Note that to include staked RPL in calculations, if a voter is a node operator, they must sign their vote message from the node withdrawal address so staked RPL is included.*

The strategy sums all `power` values from the `results` map into two integers, `yea` and `nay`. If `yea` is greater than `nay`, the proposal passes. Otherwise, it fails.


## Rationale

### Quadratic Voting

Quadratic voting is widely used with sybil-resistant platforms as the most fair way of capturing community sentiment. This method lessens the effects of vote buying on outcomes while being relatively simple to understand and engineer.

### Snapshot.org

Snapshot.org is a web3-native platform for token voting and provides several pre-strategies for accomplishing this, such as 1-to-1 voting and qudratic voting. This platform also provides the capability to create custom voting strategies, which is necessary for Rocket Pool to include staked RPL, for example. The Snapshot.org platform is widely used and does not require fees.

### Strategy

This proposal notably does not include vote weighting, rETH participation, or staked ETH participation. The rationale behind this is to create a process which can be implemented and utilized as quickly as possible, as Rocket Pool currently has no formal mechanism for gauging community sentiment and taking legitmate governance action. In the future, other, more complex voting mechanisms can be proposed to replace this one if necessary.

## Security Considerations
As with any token-based voting mechanism, even quadratic voting allows large actors to influence the outcome of votes. Although this risk is significantly lower with quadratic voting vs 1-to-1 token votes, it is possible that a large actor may create a proposal which harms the security of the protocol and force it to be adopted via this mechanism.

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
