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
The Rocket Pool community at large agrees to use RPL token quadratic voting for governance proposals via the snapshot.org platform. Snapshot votes which pass mean their proposals are immediately adopted and the protocol DAO will endeavor to enact them as soon as reasonably possible.

## Motivation
Governance in Rocket Pool is currently ad hoc. There is no way for the community to adopt proposals or legitimately request or pay for work. We must adopt a governance mechanism, even if imperfect, before any governance actions can be taken legitimately, such as but not limited to spending pDAO funds.
  
Snapshot.org is a web3-native platform for token voting and provides several strategies for accomplishing this, such as 1-to-1 voting and qudratic voting.

## Implementation
  
All Rocket Pool governance proposals must first be posted as a new topic on the governance forums at dao.rocketpool.net. Topics should include a poll with the following format:

```
[poll type=regular results=always chartType=bar]
* Support
* Oppose
[/poll]
```
A favorable forum poll which is live for at least 7 days and a corresponding RPIP document are necessary for snapshot voting to be scheduled. Once the requirements have been met, the following parties will create a quadratic RPL snapshot vote and publicize it:

- Darren Langley AKA langers (General Manager - Rocket Pool Pty Ltd)
- Mike Leach AKA Wander (RPIP Editor, Founder - Bamboo Financial Technologies)
- [others]

The snapshot vote will run for [14] days and requires a [50.1%] majority to be successful.

## Security Considerations
As with any token-based voting mechanism, even quadratic voting allows large actors to influence the outcome of votes. Although this risk is significantly lower with quadratic voting vs 1-to-1 token votes, it is possible that a large actor may create a proposal which harms the security of the protocol and force it to be adopted via this mechanism.

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
