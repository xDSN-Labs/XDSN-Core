## 6. Testnet-to-Mainnet Migration

This chapter outlines how testnet participants can convert their earned `tXDSN` tokens into real `XDSN` tokens upon mainnet launch. The migration process is designed to reward meaningful contributions while maintaining token supply integrity and economic sustainability.

---

## 🧪 About tXDSN

`tXDSN` is a testnet token deployed on the Sepolia Ethereum testnet. It is used to simulate staking, governance, and node operations during the testnet phase. While `tXDSN` itself holds no intrinsic value, **rewards earned through verified participation will be redeemable for `XDSN` on mainnet** via a one-time swap mechanism.

- **Network:** Sepolia (Ethereum Testnet)
- **Supply:** 50,000,000 tXDSN
- **Purpose:** Node rewards, governance simulation, staking trials
- **Swap Eligibility:** Based on performance and participation tiers

---

## 🔄 Conversion Tiers

| **Tier**                | **Criteria**                                               | **Conversion Rate** | **Notes**                                      |
| ----------------------- | ---------------------------------------------------------- | ------------------- | ---------------------------------------------- |
| **Tier 1: Pioneer**     | ≥ 95% uptime, full archival node, governance participation | 1 tXDSN = 1.5 XDSN  | Bonus multiplier for top contributors          |
| **Tier 2: Sustainer**   | ≥ 80% uptime, full node, consistent data serving           | 1 tXDSN = 1.2 XDSN  | Solid performance, slightly boosted conversion |
| **Tier 3: Contributor** | ≥ 60% uptime, light node, occasional governance input      | 1 tXDSN = 1 XDSN    | Standard conversion                            |
| **Tier 4: Observer**    | < 60% uptime, minimal participation                        | 1 tXDSN = 0.5 XDSN  | Reduced conversion due to low engagement       |

---

## 🧮 Cap Total Conversion

To prevent inflation and preserve token value, a hard cap is enforced:

- **Maximum Conversion Supply:** 5% of total XDSN supply
- **Smart Contract Enforcement:** Conversion logic is capped programmatically
- **Tier Allocation:** Fixed percentages per tier to ensure fairness
- **Transparency:** Cap details published and auditable

---

## 📊 Audit Logs

Node performance is verified using a combination of on-chain and off-chain logs:

- **On-Chain:** Governance votes, staking events
- **Off-Chain:** Uptime, data served via Prometheus/Grafana
- **Immutable Storage:** Logs stored on IPFS or WORM formats
- **Review Process:** Automated analysis with public summaries

---

## ⏳ Claim Window

Participants must claim their converted tokens within a defined window:

- **Duration:** 90 days post-mainnet launch
- **Grace Period:** 30-day extension for verified contributors
- **Unclaimed Tokens:** Redirected to community treasury
- **Smart Contract Logic:** Claims disabled after window closes

---

## 🧠 Summary

The migration process ensures that early contributors are rewarded fairly, while maintaining economic sustainability and transparent governance. By simulating real-world participation on Sepolia and offering a structured swap to mainnet, XDSN builds a foundation of trust and performance-based incentives.
