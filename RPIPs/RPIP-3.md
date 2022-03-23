---
rpip: 3
title: SaaS Provider Standard
status: Draft
type: Protocol
category: RPRC
author: Mike Leach (@Wander) <mike@bamboofin.tech>
discussions-to: 
created: 2022-03-19
---
# Staking as a Service Provider Standard

## Simple Summary

A standard interface for staking as a service (SaaS) providers.

## Abstract

RPRC-3 is a standard which allows SaaS providers to transparently manage client funds and apply fees on-chain. 

## Motivation

An on-chain accounting standard for SaaS providers has benefits for both providers and users. Saaas providers benefit from streamlined operations and increased interoperability, and users have increased visibility into their provider's operations, allowing them to verify fees and other expenses are accounted for correctly.

## Specification

A multi-signature scheme for controlling the withdrawal and node wallets is RECOMMENDED.

### Node Withdrawal Wallet Contract Specification

#### Fields

##### ethRewardFee

Fee percentage assessed on ETH rewards.

##### rplRewardFee

Fee percentage assessed on RPL rewards.

##### exit

Array which uses addresses as an index. Keeps track of the priority of addresses to credit upon validator exit.

##### admin

Address with administrative privileges.

#### Functions

##### processValidatorExit

When the node operator manually exits validators, they must manually call this method from the admin address.

##### ethBalanceOf

Gets the balance of ETH for an address.

##### rplBalanceOf

Gets the balance of RPL for an address.

##### ethDepositFor

Deposits ETH and credits it to an address.

##### rplDepositFor

Deposits RPL and credits it to an address. MUST NOT succeed if the node wallet RPL balance exceeds 150% of the node wallet ETH balance.

##### rplRewardsWithdraw

Withdraws a specified amount of RPL rewards for an address.

##### exit

Adds the address to the exit queue.






### Node Wallet Specification
