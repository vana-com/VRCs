# VRC-6: Increase Active DLP Limit to 32

| VRC   | Title                  | Status | Type      | Authors    | Created    |
|-------|------------------------|--------|-----------|------------|------------|
| VRC-6 | Increase Active DLP Limit to 32 | Draft  | Technical | V from Finquarium | 2025-01-05 |

## Abstract

This VRC proposes increasing the number of active DLPs eligible for protocol rewards from 16 to 32. This change aims to enhance network decentralization by allowing more DLPs to participate actively in the network while maintaining economic security through existing staking requirements. The increase aligns with network growth and rising demand for diverse data sources.

## Motivation

The current limit of 16 active DLPs was established during the network's initial phase to ensure sufficient stake concentration and economic security. However, several factors now support expanding this limit:

1. Growing network participation and increased total stake
2. Rising demand for specialized data sources
3. Need for greater network decentralization
4. Current presence of capable DLPs operating below the top 16 threshold

This expansion would:
- Enable more diverse data sources to participate actively
- Reduce barriers to entry for new DLPs
- Increase network decentralization
- Support ecosystem growth

## Specification

The implementation requires updating the following parameters:

1. Update DLPRoot contract:
   - Modify MAX_ACTIVE_DLPS from 16 to 32

2. Update reward distribution calculations to accommodate 32 DLPs:
   - Adjust reward pool distribution mechanisms
   - Update related subgraph queries
   - Modify UI components displaying DLP rankings

This change maintains compatibility with:
- VRC-2: DLP Performance Metrics
- VRC-3: Variable Staking Split
- VRC-4: Sublinear DLP Rewards Distribution
- VRC-5: DLP Launch Readiness Standards

## Rationale

The selection of 32 DLPs balances several factors:

1. Network Security: The increase maintains sufficient stake concentration per DLP while allowing for greater participation
2. Technical Scalability: The network can efficiently support 32 active DLPs
3. Market Demand: Current participation indicates sufficient demand for additional DLP slots
4. Gradual Scaling: Doubling from 16 to 32 represents a measured increase that can be effectively monitored

## Security & Privacy Considerations

Security implications include:
- Slightly reduced stake concentration per DLP
- More distributed security model
- Increased validator resource requirements

Mitigations:
- Maintaining existing staking requirements
- No changes to individual DLP security requirements
- Progressive implementation timeline

## Implementation

The change will be implemented in phases:

Phase 1 (Epoch 3):
- Smart contract updates
- UI modifications
- Subgraph query updates

Phase 2 (Epoch 4):
- Monitor network performance
- Gather feedback from DLPs and stakers
- Assess impact on network decentralization

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
