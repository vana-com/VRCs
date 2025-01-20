| VRC | Title | Status | Type | Author | Created |
|-----|--------|--------|------|---------|----------|
| 8 | Time-Weight Rewards | Final | Technical  | Dylan H - contact@vanatensor.io, Anatoly S - anatoly@opendatalabs.xyz | 2025-01-17 |

## Abstract

Time-weighted rewards ensure that Vana tokens are distributed fairly to both DLP creators and stakers. 

For stakers, rewards are adjusted only for stakes lasting fewer than 21 days. For DLPs, the total staked metric in the scoring formula is also adjusted for stakes under 21 days. 

This approach mitigates exploitative behavior, promotes consistent participation, and rewards continuous contributions.

## Motivation

The current system allows exploitative behaviors, such as staking large amounts near the end of an epoch to maximize rewards, leading to:

1. Ecosystem volatility and instability.
2. Incentives for short-term campaigns rather than sustained performance throughout an epoch.
3. In order to further promote long-term alignment, the staking duration required to achieve the maximum multiplier is extended by an additional epoch.

While the system includes a 7-day unlock period, which requires participants to stake for at least 7 days to exploit rewards, instability persists due to the lack of proportional rewards. Adopting time-weighted rewards addresses these issues by ensuring rewards are distributed in proportion to contributions over time, aligning with industry standards and increasing system predictability.

## Specification

Time-weighted rewards are implemented via changes to the existing multiplier logic:

1. **Staker Rewards:**
    - For stakes with fewer than 21 days, the multiplier is calculated as:
      **(X days staked) / 21**
    - After 21 days, the previous multiplier formula applies:
      - Day 42: Multiplier = 1.5x
      - Day 63: Multiplier = 2.75x
      - Day 84: Multiplier = 3x
    - Example:
      - Day 1: Multiplier = (1/21)x
      - Day 10: Multiplier = (10/21)x
      - Day 21: Multiplier = 1x 

2. **DLP Rewards:**
    - Total staked in the DLP Scoring is still measured as the sum of stakers’ stakes at the last epoch block.
    - However, if a staker has staked for fewer than 21 days, their stake is adjusted with the new multiplier
    - Example:
      If a staker adds 1M VANA at the last days, the effective contribution to the DLP’s score is: **1M / 21 days**

This ensures that last-minute staking has minimal impact on DLP rewards and incentivizes consistent performance throughout the epoch.

## Rationale

- **Adjustments for Stakers and DLPs:** Rewards are adjusted for stakes lasting fewer than 21 days, ensuring fairness and discouraging exploitative behaviors.
- **Exploit Mitigation:** Time-weighting reduces the impact of short-term staking, promoting consistent contributions over time.
- **Aligned with Standards:** This approach follows best practices in staking protocols, increasing user trust and transparency.

## Security & Privacy Considerations

- **Security:** Time-weighted rewards reduce the economic incentives for last-minute staking and the effects of potential exploits. Exploits affecting rewards over a short period have diminished impact due to proportional weighting.
- **Privacy:** Unchanged from the current system.

## Implementation

The changes are live starting Day 1 of Epoch 3. Adjustments include:

1. **Multiplier Logic:**
    - New time-weighting is applied to stakes only for durations under 21 days.
    - Epoch 1 and Epoch 2 stakers retain multipliers based on the old formula.

2. **DLP Scoring:**
    - The total staked metric in the scoring system now time-weights individual stakes under 21 days.

## Copyright

Copyright and related rights waived via CC0.
