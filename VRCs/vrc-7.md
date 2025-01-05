# VRC-7: Universal Staker Rewards

| VRC   | Title                  | Status | Type      | Authors    | Created    |
|-------|------------------------|--------|-----------|------------|------------|
| VRC-7 | Universal Staker Rewards | Draft  | Technical | V from Finquarium | 2025-01-05 |

## Abstract

This VRC proposes extending staker rewards to all DLP stakers regardless of their DLP's ranking, while maintaining the current treasury reward structure for top-ranked DLPs only. 
This change aims to incentivize staking across a broader range of DLPs while preserving the competitive aspect of DLP treasury rewards.

## Motivation

The current reward system, where only stakers of top-ranked DLPs receive rewards, creates several challenges:

1. Limited incentive to stake with lower-ranked DLPs, even if they provide valuable data services
2. Difficulty for new DLPs to attract stake and climb rankings
3. Reduced network decentralization due to stake concentration in top DLPs
4. Misalignment between network growth goals and staking incentives

Extending staker rewards while maintaining DLP treasury reward restrictions would:
- Encourage stake distribution across more DLPs
- Support emerging DLPs with valuable data sources
- Enhance network decentralization
- Maintain competitive pressure on DLP performance

## Specification

The proposal modifies reward distribution mechanics:

1. Staker Rewards:
   - All stakers receive rewards proportional to their stake
   - Reward calculation includes all staked tokens network-wide
   - Maintains compatibility with VRC-3 variable staking splits

2. DLP Treasury Rewards:
   - Continue to be restricted to top-ranked DLPs
   - No changes to treasury reward calculation
   - Maintains compatibility with VRC-4 sublinear distribution
```

## Rationale

This design maintains network security while improving decentralization:

1. Universal Staker Rewards:
   - Encourages broader stake distribution
   - Supports emerging DLPs
   - Aligns with network growth goals

2. Restricted Treasury Rewards:
   - Maintains competitive pressure
   - Preserves incentives for operational excellence
   - Supports sustainable network economics

## Security & Privacy Considerations

Security implications:
- Potential for increased stake volatility
- More complex reward calculations
- Increased network state transitions

Mitigations:
- Maintain existing staking periods
- Optimize reward distribution computation
- Comprehensive testing of new distribution logic

## Implementation

Implementation Timeline:

Phase 1 (Pre-deployment):
- Smart contract updates
- Economic simulation and testing
- UI updates to reflect universal rewards

Phase 2:
- Deploy contract updates
- Monitor stake distribution changes
- Gather community feedback

Required Changes:
- Update reward distribution contracts
- Modify subgraph indexing
- Update UI to show reward eligibility
- Add new monitoring metrics

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
