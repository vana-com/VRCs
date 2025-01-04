# VRC-3: Variable Staking Split

| VRC   | Title                  | Status | Type      | Authors    | Created    |
|-------|------------------------|--------|-----------|------------|------------|
| VRC-3 | Variable Staking Split | Proposed  | Technical | Anna, Art  | 2025-01-01 |

## Abstract

This VRC proposes expanding the allowable range of staker reward percentages from the current fixed 50% to a variable range of 40-60%. Currently, the parameters of what goes to stakers are set at a maximum and minimum of 50%. This was to prevent a "race to the bottom" early on where DLPs could set higher and higher thresholds to go to their stakers, especially in Epoch 1 where the only performance metric was stake. With the introduction of DLP performance metrics in VRC-2, DLPs should have the flexibility to choose their staker reward percentages, now that staking rewards will be based on both performance metrics and the DLP's stake.

## Motivation

The current fixed 50% staking reward split was implemented as a protective measure during the network's first epoch to prevent a "race to the bottom" scenario where DLPs might compete solely on staking rewards. However, several factors now show the ecosystem is ready for a more flexible approach:
- The introduction of DLP performance metrics as part of VRC-2 provides additional criteria for staker selection beyond pure reward rates, reducing the risk of stake-based competition dominating DLP selection.
- DLPs with less stake who want to offer higher APY to their stakers to attract more stake are constrained by the fixed 50% reward based on the current parameters. Market dynamics have already led to off-protocol reward arrangements, suggesting that the current fixed split does not optimally serve network participants' needs. DLPs with less stake can still choose whatever approach is best for them: whether offering stakers a specific reward off-protocol, or by updating their staker reward percentage. 

## Specification

The proposal modifies the following parameters in the DLP reward distribution mechanism:
- Minimum staker reward percentage: 40% (decreased from 50%)
- Maximum staker reward percentage: 60% (increased from 50%)

## Rationale

The proposed bounds of 40-60% were selected based on several considerations: 

Competitive Dynamics: New DLPs face significant barriers to entry in attracting as much stake as large established DLPs. The expanded upper bound of 60% provides another tool in their toolkit to attract initial stake, similar to how new businesses might operate at lower margins initially to gain market share.

Market Demand: While DLPs can and do offer off-protocol rewards to their stakers, some may prefer to manage their reward distributions entirely on-protocol. The proposed range of 40-60% provides this flexibility while maintaining reasonable bounds on the protocol-level split.

Capping the upper bound at 60% and setting a lower bound of 40% provides flexibility while encouraging DLPs to compete based on the full range of factors including the performance metrics introduced in VRC-2, rather than solely on reward rates.

## Security & Privacy Considerations

From a protocol implementation perspective, this is a straightforward parameter change in the DLP Root contract.

From an economic perspective, one risk is a potential competitive environment where DLPs all offer higher and higher staker rewards to try to attract as much stake as possible. Maintaining a maximum staker reward percentage of 60% helps mitigate this risk.

## Implementation

Implementation requires the following changes:

Update the DLPRoot contract parameters:
- Set MIN_STAKER_PERCENTAGE to 40
- Set MAX_STAKER_PERCENTAGE to 60

DLP Requirements:
- DLPs must update their preferred percentage before the start of Epoch 2 if they wish to deviate from the current 50%
- No action is required from DLPs who wish to maintain the current 50% split

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
