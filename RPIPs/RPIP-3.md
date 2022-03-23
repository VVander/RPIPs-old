---
rpip: 3
title: SaaS Provider Standard
status: Draft
type: Protocol
category: RPRC
author: Mike Leach (@Wander) <mike@bamboofin.tech>
discussions-to: https://discord.com/channels/405159462932971535/937053845610180628/956263874733174884
created: 2022-03-19
---
# Staking as a Service Provider Standard

## Simple Summary

A standard interface for staking as a service (SaaS) providers.

## Abstract

The following provides a standard API for Rocket Pool SaaS provider contracts. RPRC-3 allows clients to stake ETH and requires providers to supply RPL collateral.

## Motivation

An on-chain accounting standard for SaaS providers has benefits for both providers and users. Providers benefit from streamlined operations and increased interoperability, and users have increased visibility into their provider's operations, allowing them to verify fees and other expenses are accounted for correctly.

## Specification

A multi-signature scheme for controlling the withdrawal and node wallets is RECOMMENDED.

### Node Withdrawal Wallet Contract Specification

#### Fields

##### ethRewardFee

Fee percentage assessed on ETH rewards.

##### exit

Array of addresses. When the admin wallet calls `processValidatorExit(n)`, addresses in the `exit` array will be credited with their balance.

##### admin

Address with administrative privileges.

#### Functions

##### processValidatorExit

When the node operator exits validators, they may call this method from the admin address to distribute assets.

``` js
function processValidatorExit(uint256 numValidators) public view
```

##### balanceOf

Gets the balance of ETH for an address.

``` js
function rplBalanceOf(address owner) public view returns (uint256)
```

##### depositFor

Deposits ETH and credits it to an address.

``` js
function ethDepositFor(address owner) public view
```

##### exit

Adds the address to the exit queue.

``` js
function exit(address owner) public view
```

### Node Wallet Specification

[can this be the same as a normal RP node wallet?]
