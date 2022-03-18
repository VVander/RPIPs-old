---
rpip: 2
title: Rocket Pool Design Specification
status: Draft
type: Informational
author: Mike Leach (@Wander) <mike@bamboofin.tech>
discussions-to: https://dao.rocketpool.net/t/rpip-2-formalizing-protocol-changes/367
created: 2022-03-17
---



# Rocket Pool Project

The Rocket Pool project includes:
- protocol smart contracts 
- other smart contracts, such as the standards and reference contracts created via RPRCs
- the Smart Node CLI
- documentation such as RPIPs

## Protocol

The Rocket Pool core protocol is the set of smart contracts which are necessary for running a Rocket Pool node or swapping ETH for rETH via the deposit pool:

- [insert list of contracts and their addresses]

## Other Contracts

Standards and reference smart contracts which utilize the protocol are proposed via RPRCs and are not considered part of the core protocol:

- [SaaS SC 0x1234]

## Smart Node CLI

The smart node is a reference client, written in golang, for interacting with the Rocket Pool protocol: 

- https://github.com/rocket-pool/smartnode-install
- https://github.com/rocket-pool/smartnode

## RPIPs

Rocket Pool Improvement Proposals RPIPs) are the mechanism for documenting and proposing changes to the protocol. See [EIP-1](./eip-1.md) for more details.
