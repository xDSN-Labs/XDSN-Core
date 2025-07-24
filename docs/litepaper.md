# litepaper

Version 1.0 • July 2025

***

## 1. Introduction

Today’s cloud storage locks us into high fees, non-transparent pricing, single points of failure, and ever-expanding privacy risks. The xDSN network shatters that model by delivering global, encrypted cloud hot and cold storage at a fraction of the cost—with built-in token rewards for every node operator, whether running on a smartphone, cloud VPS, or home server.

At its core, xDSN is built on the IPFS protocol and functions as a permissionless, incentivized, encrypted block-storage mesh network. It uses audits and automated redundancy to guarantee data integrity. Node operators earn xDSN tokens for uptime, data replication, geographic dispersion, and secure storage practices, while users enjoy low-cost, highly durable hot and cold storage without vendor lock-in or privacy compromises.



***

## 2. Problem Statement

Centralized cloud storage dominates today’s market, but at significant cost:

* High fees and non-transparent pricing lock users into expensive plans
* Single points of failure increase risk of outages and data loss
* Vendor lock-in restricts flexibility and portability
* Limited privacy controls leave data exposed to breaches, surveillance, and misuse

Meanwhile, purely decentralized networks still fall short:

* Incentive models remain fragmented across platforms, limiting overall scale
* Consumer devices (smartphones, home servers) sit idle, wasting potential capacity

xDSN tackles both sides by uniting encrypted storage resources into one permissionless, tokenized mesh that aligns incentives, lowers cost, maximizes resilience, and restores data privacy through client-side encryption and shard-and-disperse architecture.

***

## 3. Solution Overview

xDSN is built on the IPFS protocol and delivers a multi-layered, token-aligned storage mesh network. Each client-side encrypted data block is redundantly distributed across hot and cold tiers. Mobile devices, VPS nodes, and home storage nodes earn economic incentives for securing and replicating the network.

### Key Mechanics

* Incentivized Node Roles (hot & cold tiers)
* Decentralized Encryption & Sharding\
  • All data is encrypted before leaving the client and split into shards, each stored on different nodes—no single node ever holds a complete file or plaintext.
* Validator Nodes (lite & full)\
  • Stake xDSN tokens to run consensus duties, maintain the DHT, and provide uptime proofs
* Storage Nodes (lite & full)\
  • Pin encrypted shards in the hot tier or import and archive snapshots in the cold tier
* Full Storage Nodes\
  • Combine validator and storage responsibilities for premium xDSN token rewards

All participants earn xDSN tokens based on uptime, data replication, storage proofs, geographic dispersion, and adherence to encryption best practices.
