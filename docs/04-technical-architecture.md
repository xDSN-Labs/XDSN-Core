## 4. Technical Architecture 🏗️

### 🌐 Overview

XDSN is a modular, decentralized storage network optimized for both hot and cold data. It harnesses IPFS for content addressing and peer-to-peer distribution, augmented by on-demand retrieval, tiered storage, and token-driven incentives. The architecture scales across devices—from mobile to VPS—ensuring resilience and broad participation.

---

### 🧩 Core Components

- **Node Types**

  - **Hot Nodes**: SSD-backed, low-latency, serve frequent requests.
  - **Warm Nodes**: HDD-backed, balance cost and performance.
  - **Cold Nodes**: Leverage home NAS and cloud servers for archival storage.

- **Storage Tiers**

  1. **Tier 1 (Hot)**: High-availability SSD pools.
  2. **Tier 2 (Warm)**: Cost-efficient HDD arrays.
  3. **Tier 3 (Cold)**: Hybrid NAS + cloud servers.

- **Stub File System**

  - Local metadata files (“stubs”) hold content references (e.g. IPFS CIDs), file metadata, and retrieval instructions.
  - On-demand fetch via CLI triggers actual data transfer when accessed.

- **Protocol Stack**

  | Layer      | Purpose                                           |
  | ---------- | ------------------------------------------------- |
  | Transport  | IPFS DHT for peer discovery & content exchange    |
  | Storage    | Local disk, NAS devices, cloud-integrated storage |
  | Retrieval  | CLI workflows for just-in-time data access        |
  | Incentives | Polygon-based XDSN token rewards & staking        |
  | Security   | Client-side encryption, reputation, audit trails  |

---

### 🕸️ Network Topology & Node Interactions

- **Decentralized Mesh**  
  Nodes connect via IPFS’s DHT, exchanging peer lists and content advertisements.

- **Dynamic Role Assignment**  
  Nodes declare or shift roles (hot, warm, cold) according to resource availability and network demand.

- **Replication Strategy**

  - Hot content: replicated widely across hot nodes.
  - Archival content: distributed sparsely across cold nodes to minimize cost.

- **Coordination Protocols**  
  Lightweight signaling handles cache invalidation, tier promotions, and request routing.

---

### 🗃️ Caching & Storage Mechanisms

- **Local Caching**  
  Frequently accessed files persist in local cache to reduce fetch latency.

- **Tier Promotion**  
  Access-driven promotions move data from cold → warm → hot tiers when thresholds are exceeded.

- **Stub-Driven Retrieval**  
  Placeholders trigger automated fetch workflows; actual chunks arrive only on access.

- **Deduplication & Integrity**  
  Content hashing ensures unique storage and automatic deduplication network-wide.

---

### 🏛️ Governance Architecture

- **Dual-Purpose XDSN Token**  
  Deployed on Polygon, XDSN serves as both utility (staking, access fees) and governance token.

- **On-Chain Voting**  
  Token holders vote on protocol upgrades, incentive parameters, and tier definitions via smart contracts.

- **Proposal System (XIPs)**  
  Any node or user can submit an XDSN Improvement Proposal; community feedback and voting follow.

- **Reputation-Weighted Influence**  
  Voting power factors in stake, node uptime, and historical contributions.

- **Multi-Sig Treasury Management**  
  Core protocol funds and upgrade execution are held in multi-signature wallets requiring multiple authorized signers.

---

### 📜 Smart Contract Flows

- **Node Registration**

  - Nodes stake XDSN tokens on Polygon to register identity and declare tier.
  - A minimum stake is required to join the network and become eligible for node rewards; this stake remains locked during operation.
  - Registration smart contract issues a unique node certificate.

- **Incentive Distribution**

  - Uptime, bandwidth, and storage contributions are measured off-chain and verified on-chain.
  - Rewards paid out in XDSN according to pre-defined epochs.
  - Node operators can view real-time reward accrual via the NodeJS CLI or web Dashboard.

- **Access Control**

  - File requests validated via token-gated smart contracts.
  - Optional usage- or time-based expiry enforced on-chain.

- **Governance Execution**
  - Approved votes trigger automated contract upgrades and parameter adjustments.
  - Multi-sig wallet threshold signatures govern the upgrade transactions to ensure secure deployment.

---

### 🛡️ Security Considerations

- **Client-Side Encryption**  
  End-users encrypt data prior to upload; nodes only handle ciphertext.

- **Content Integrity**  
  Chunk hashing and CID verification prevent tampering and ensure authenticity.

- **Reputation & Slashing**  
  Malicious or underperforming nodes risk token slashing or exclusion from reward pools.

- **Access Tokens**  
  Cryptographic tokens manage fine-grained permissions and time-locked access.

- **Multi-Sig Wallets**  
  Treasury, governance funds, and reward distribution contracts reside in multi-signature wallets requiring several key-holders to approve sensitive transactions.

- **High Availability**  
  Multi-path retrieval and redundant replicas guard against node failures.

---

### ⚙️ Node Lifecycle

1. **Onboarding**

   - Docker containers bundle all dependencies for hot, warm, and cold node deployments.
   - CLI tool initializes node identity, tier selection, and Polygon wallet integration.
   - Dockerized images enable one-command deployment across platforms.

2. **Heartbeat & Metrics**

   - Nodes emit uptime, latency, and storage usage to monitoring oracles.
   - Oracles feed data into on-chain reward calculations.

3. **File Distribution**

   - Files encrypted, chunked, hashed, and distributed.
   - Replication factors adapt per tier and file popularity.

4. **Retrieval & Rehydration**
   - Stub file access triggers data fetch.
   - Retrieved data cached locally; hot-tier promotion if reuse detected.

---

### 📈 Scalability & Resilience

- **Horizontal Scaling**  
  New nodes join seamlessly; DHT automatically redistributes routing tables.

- **Fault Tolerance**  
  Multiple replicas and alternative fetch paths guarantee availability even under network partitions.

- **Adaptive Tiering**  
  Automated heuristics balance cost, performance, and redundancy by relocating data across tiers based on usage patterns.

---
