# VRC-2: DLP Performance Metrics

| VRC   | Title                   | Status | Type      | Authors              | Created    |
|-------|-------------------------|--------|-----------|----------------------|------------|
| VRC-2 | DLP Performance Metrics | Proposed  | Technical | @annakaz, @kahtaf, @dumedco | 2025-01-01 |

## Abstract

This VRC proposes enhancing DLP rankings by combining existing staking metrics with performance metrics based on verified data contributions. The initial proposed split allocates 80% of a DLP's rating to their staked VANA amount and 20% to their unique wallet contributions with verified data. By incorporating contribution metrics alongside staking, the system incentivizes DLPs to both maintain strong financial commitment and cultivate an active, diverse contributor base. This change also incentivizes stakers to choose to stake with DLPs with better performance metrics. The change aims to strengthen network participation while preserving the economic security provided by staking requirements.

## Motivation

The current DLP ranking system relies solely on staked VANA amounts, which may not fully capture the health and activity of a DLP. By incorporating unique wallet contributions:

1. DLPs are incentivized to foster broader participation rather than depending on a few large stakeholders
2. Active data contribution and verification become key performance indicators
3. The system better reflects both financial commitment (staking) and operational activity (data contributions)
4. Stakers are incentivized to research and understand DLP performance to optimize rewards. 

## Specification

### Rating System
```
Total Rating = (Staking Rating * 0.8) + (Performance Rating * 0.2)

Where:
Staking Rating = (DLP Staked Amount / Total Network Staked Amount) * 100
Performance Rating = (DLP Unique Wallets With Verified Data This Epoch / Total Unique Wallets with Verified Data This Epoch) * 100
```

This rating system impacts the rewards that go to both stakers and DLPs. 

### Oracle Service
- Tracks unique wallet contributions via subgraph queries
- Updates ratings every 30 minutes
- Uploads final ratings to blockchain
- Implemented as an oracle to support future performance metrics beyond unique wallets with data contributions

### Smart Contract Updates
- Accepts authorized performance rating uploads
- Implements configurable weight parameters

## Rationale

### Design Decisions
- Off-chain calculation chosen for efficiency and flexibility
- 30-minute updates balance data freshness with resource usage
- Designed to support adding future metrics beyond unique wallets with verified data contributions. Future metrics could include: demand for data, measurements of data quality, and other metrics capturing the importance and quality of the DLP's dataset.

## Security & Privacy Considerations

This change encourages many unique wallets to contribute data to DLPs, which is generally aligned with having many users contributing data. However, one wallet does not always mean one user, so it is important that DLPs also have a strong proof of contribution implementation, verifying that the data is legitimate. Implementing this change alongside VRC-5, which ensures DLPs provide accurate documentation on their roboust proof of contribution, helps to mitigate this risk. 

## Implementation

Rolling out in Epoch 2.

The DataHub UI will also be updated to show each DLP's unique wallets with verified data contributions, providing stakers with information needed to make an informed decision. 

## Copyright

Copyright and related rights waived via CC0.
