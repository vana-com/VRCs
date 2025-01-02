# VRC-4: Quadratic DLP Rewards Distribution

| VRC   | Title                  | Status | Type      | Authors    | Created    |
|-------|------------------------|--------|-----------|------------|------------|
| VRC-4 | Quadratic DLP Rewards Distribution | Draft  | Technical | @annakaz, @tnunamak, @art-vana, @dumedco | 2025-01-02 |

## Abstract

This VRC proposes implementing a quadratic reward distribution system for DLP treasury rewards while maintaining linear rewards for stakers. Under this model, staker rewards remain proportional to their staked amount, while DLP treasury rewards follow a quadratic distribution curve. This approach aims to promote network decentralization by making it easier for new DLPs to establish themselves while preventing excessive reward concentration among the largest DLPs. 

## Motivation

The current linear reward distribution system can lead to concentration of rewards among the largest DLPs, creating high barriers to entry for new DLPs. This concentration risk could result in concentration of rewards among existing top DLPs, reduced network decentralization as smaller DLPs struggle to compete, and fewer new DLPs due to high barriers to entry. This is based on observed behavior in Epoch 1, where the top DLP has nearly 100x more stake than lower ranking DLPs still in the top 16. 

A quadratic distribution system for DLP treasury rewards addresses these concerns while maintaining predictability for stakers.

## Specification

The reward distribution system maintains linear rewards for stakers while applying a quadratic transformation to DLP treasury rewards. This creates a more equitable distribution while preserving predictable staking returns.

- Staker rewards remain linear to maintain predictable APY
- DLP treasury rewards apply a quadratic transformation to avoid too much concentration of rewards

Implementation must take into account both VRC-2, which introduces performance metrics for DLPs, and VRC-3, which introduces variable staking split between stakers and DLPs. The quadratic parameter X can be adjusted between 0 and 1, and will start at 0.5 (effectively a square root function).

## Rationale

Design Decisions
- Maintaining linear staker rewards ensures predictable rewards for stakers
- Quadratic distribution balances network decentralization with the need to appropriately reward DLPs with more stake
- Separation of staker and treasury reward calculations allows for independent optimization of each
- Implementation supports future parameter adjustments based on network evolution and governance

## Security and Privacy Considerations

- Large DLPs could still accumulate significant stake by staking their treasury rewards on themselves. However, this risk exists in the current system and is not exacerbated by the quadratic distribution.
- The quadratic distribution makes economic attacks more expensive as rewards scale sub-linearly with stake.
- Encourages creation of more DLPs.

## Implementation

This change will take effect for rewards distributed in Epoch 2, which will be paid to DLP treasuries at the end of Epoch 2.

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
