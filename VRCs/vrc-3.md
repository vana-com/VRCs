# VRC-3: Variable Staking Split

| VRC   | Title                  | Status | Type      | Authors    | Created    |
|-------|------------------------|--------|-----------|------------|------------|
| VRC-3 | Variable Staking Split | Proposed  | Technical | Anna, Art  | 2025-01-01 |

## Abstract

This VRC proposes expanding the allowable range of staker reward percentages from the current fixed 50% to a variable range of 40-80%. Currently, the parameters of what goes to stakers are set at a max and minimum of 50%. This was to prevent a "race to the bottom" early on where DLPs could set higher and higher thresholds to go to their stakers, especially in Epoch 1 where the only performance metric was stake. With the introduction of DLP performance metrics in VRC-2 and based on observed market behavior where DLPs are providing additional off-protocol rewards, it makes sense to allow this range to change.

## Motivation

The current fixed 50% staking reward split was implemented as a protective measure during the network's first epoch to prevent a "race to the bottom" scenario where DLPs might compete solely on staking rewards. However, several factors now show the ecosystem is ready for a more flexible approach:
- The introduction of DLP performance metrics as part of VRC-2 provides additional criteria for staker selection beyond pure reward rates, reducing the risk of stake-based competition dominating DLP selection.
- New DLPs face significant challenges in attracting stake to compete with established providers, potentially limiting network growth and decentralization.
- Market dynamics have already led to off-protocol reward arrangements, suggesting that the current fixed split does not optimally serve network participants' needs.

## Specification

The proposal modifies the following parameters in the DLP reward distribution mechanism:
- Minimum staker reward percentage: 40% (decreased from 50%)
- Maximum staker reward percentage: 80% (increased from 50%)

## Rationale

The proposed bounds of 40-80% were selected based on several key observations from mainnet operation and market dynamics:

Market Demand: Early mainnet operation has demonstrated that DLPs are already creating off-protocol arrangements to effectively offer higher staking percentages, indicating that the current 50% cap is artificially constraining natural market behavior. The proposed 80% upper bound legitimizes these arrangements while keeping them on-protocol where they can be properly tracked and governed.

Competitive Dynamics: New DLPs face significant barriers to entry in competing with established providers. The expanded upper bound of 80% gives them a powerful tool to attract initial stake, similar to how new businesses might operate at lower margins initially to gain market share. This is particularly important now that performance metrics are being introduced, as it allows DLPs to attract sufficient stake to demonstrate their capabilities.

The 40% minimum ensures that stakers are rewarded as they align with DLPs.

## Security & Privacy Considerations

From a protocol implementation perspective, this is a straightforward parameter change in the DLP Root contract.

From an economic perspective, one risk is a potential competitive environment where DLPs all offer higher and higher staker rewards to try to attract as much stake as possible. Maintaining a maximum staker reward percentage of 80% helps mitigate this risk.

## Implementation

Implementation requires the following changes:

Update the DLPRoot contract parameters:
- Set MIN_STAKER_PERCENTAGE to 40
- Set MAX_STAKER_PERCENTAGE to 80

DLP Requirements:
- DLPs must update their preferred percentage before the start of Epoch 2 if they wish to deviate from the current 50%
- No action is required from DLPs who wish to maintain the current 50% split

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
