# VRC-4: Sublinear DLP Rewards Distribution

| VRC   | Title                  | Status | Type      | Authors    | Created    |
|-------|------------------------|--------|-----------|------------|------------|
| VRC-4 | Sublinear DLP Rewards Distribution | Final  | Technical | @annakaz, @tnunamak, @art-vana, @dumedco | 2025-01-02 |

## Abstract

This VRC proposes implementing a sublinear reward distribution system for DLP treasury rewards while maintaining linear rewards for stakers. Under this model, staker rewards remain proportional to their staked amount, while DLP treasury rewards follow a polynomial distribution curve with an exponent between 0 and 1, starting with 0.5 (so effectively a square roote function). This approach aims to promote network decentralization by making it easier for new DLPs to establish themselves while preventing excessive reward concentration among the largest DLPs. 

## Motivation

The current linear reward distribution system can lead to concentration of rewards among the largest DLPs, creating high barriers to entry for new DLPs. This concentration risk could result in concentration of rewards among existing top DLPs, reduced network decentralization as smaller DLPs struggle to compete, and fewer new DLPs due to high barriers to entry. This is based on observed behavior in Epoch 1, where the top DLP has nearly 100x more stake than lower ranking DLPs still in the top 16. 

A polynomial reward distribution with parameter 0 < p < 1 addresses these concerns by dampening the relationship between stake and rewards. When p = 0.5, for example, doubling a DLP's stake increases their rewards by only ~41% rather than 100%, making the system more accessible to newer and smaller DLPs while still rewarding larger DLPs for their increased stake. This maintains predictability for stakers through linear staking rewards.

## Specification

The reward distribution system introduces two separate reward calculations:

1. Staker rewards remain proportional to stake (linear) to maintain predictable APY
2. DLP treasury rewards follow a polynomial transformation where rewards scale as stake^p, with parameter p between 0 and 1

The polynomial parameter p will initially be set to 0.5, meaning treasury rewards will scale with the square root of stake. For example, a DLP with 4x more stake than another would receive 2x (√4) more treasury rewards, rather than 4x under the current linear system.

Implementation must account for the interaction with:
- VRC-2: Performance metrics for DLPs may further adjust the base treasury rewards
- VRC-3: Variable staking splits between stakers and DLPs affect the total reward pool for each calculation

The parameter p can be adjusted to optimize the balance between rewarding larger DLPs and maintaining accessibility for newer participants. A higher p (closer to 1) approaches linear scaling, while a lower p creates a more gradual reward curve.

## Rationale

Design Decisions
- Maintaining linear staker rewards ensures predictable rewards for stakers
- Quadratic distribution balances network decentralization with the need to appropriately reward DLPs with more stake
- Separation of staker and treasury reward calculations allows for independent optimization of each
- Implementation supports future parameter adjustments based on network evolution and governance

## Security and Privacy Considerations

- Large DLPs could still accumulate significant stake by staking their treasury rewards on themselves. However, this risk exists in the current system and is not exacerbated by the polynomial distribution.
- The polynomial distribution makes economic attacks more expensive as rewards scale sub-linearly with stake.
- Encourages creation of more DLPs.

## Implementation

This change will take effect for rewards distributed in Epoch 2, which will be paid to DLP treasuries at the end of Epoch 2.

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
