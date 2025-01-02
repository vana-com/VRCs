# VRC-4: Variable Staking Split

| VRC   | Title                  | Status | Type      | Authors    | Created    |
|-------|------------------------|--------|-----------|------------|------------|
| VRC-4 | Quadratic DLP Rewards Distribution | Draft  | Technical | @annakaz, @tnunamak, @art-vana, @dumedco | 2025-01-02 |

## Abstract

This VRC proposes implementing a polynomial reward distribution system for DLP treasury rewards while maintaining linear rewards for stakers. Under this model, staker rewards remain proportional to their staked amount, while DLP treasury rewards follow a quadratic distribution curve. This approach aims to promote network decentralization by making it easier for new DLPs to establish themselves while preventing excessive reward concentration among the largest DLPs. 

## Motivation

The current linear reward distribution system can lead to concentration of rewards among the largest DLPs, creating high barriers to entry for new DLPs. This concentration risk could result in concentration of rewards among existing top DLPs, reduced network decentralization as smaller DLPs struggle to compete, and fewer new DLPs due to high barriers to entry. This is based on observed behavior in Epoch 1, where the top DLP has nearly 100x more stake than lower ranking DLPs still in the top 16. 

A polynomial distribution system for DLP treasury rewards addresses these concerns while maintaining predictability for stakers.

## Specification

```
Staker Rewards (Linear):
SR = (Individual Stake / Total Network Stake) * Total Staker Rewards

DLP Treasury Rewards (Quadratic):
TR = (sqrt(DLP Total Stake) / sum(sqrt(All DLP Stakes))) * Total Treasury Rewards
```
This takes into account VRC-3, which introduces variable staking split between stakers and DLPs. 

## Rationale

Design Decisions
- Maintaining linear staker rewards ensures predictable APY for participants
- Quadratic distribution balances network decentralization with the need to appropriately reward larger DLPs for their security contributions
- Separation of staker and treasury reward calculations allows for independent optimization of each
- Implementation supports future parameter adjustments based on network evolution and governance

## Security, Privacy and Economic Considerations

- Large DLPs could still accumulate significant stake by staking their treasury rewards on themselves. However, this risk exists in the current system and is not exacerbated by the polynomial distribution.
- The quadratic formula makes economic attacks more expensive as rewards scale sub-linearly with stake.
- Encourages creation of more DLPs.

## Implementation

This change will take effect for rewards distributed in Epoch 2, which will be paid to DLP treasuries at the end of Epoch 2.

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
