| VRC | Title | Status | Type | Author | Created |
|-----|--------|--------|------|---------|----------|
| 8 | Time-Weight Rewards | Draft | Technical  | Dylan H - contact@vanatensor.io | 2025-01-07 |

## Abstract

Time-weighted rewards means that Vana would be distributed based on continuous performance of DLPs and stakers, rather than based on a single snapshot at the end of each epoch.
It can be achieved by once a day logging current scores for stakers and DLPs, and accumulating them over the 21 day epoch, and finally distribute the rewards at the end of the tokens.

## Motivation

Currently there is minimal incentive for investors to stake until the end of an epoch, and investors can buy tokens the day before the epoch end, and then unstake the day after and sell with about a 10% increase in tokens.
This causes massive volatility and instability in the ecosystem, making it hard for participants to plan ahead. Metrics such as APY and estimated DLP rewards currently can be highly misleading since at the last second of an epoch, someone can add massive stake to a DLP and drastically change the rewards for people that may have been staked for weeks.
Further, having time-weighted rewards incentivizes DLPs to consistently perform well, rather than being incentivized to do massive campaigns at the end of each epoch, in order to win stake.
Lastly, time-weighted rewards are the standard for all major protocols with staking, and adopting this best practice will likely raise fewer questions and decrease confusion amongst users than the current system

## Specification

We suggest that stakers and DLPs accrue rewards daily, based on a snapchat of that specific day.
Since 400000 Vana are distributed per epoch, about 19048 Vana would be rewarded, but not claimable, each day.
On the final day of the epoch, a final snapshot is made, and the rewards are paid to DLPs, and stakers can get their rewards gradually unlocked.

## Rationale

- Daily Time-Weighted Rewards
Calculating rewards once a day means rewards are in practice mostly continuous from participants perspective, while minimizing load on the chain compared to more frequent reward calculations.
- Continuous Accruing
Continuously accruing rewards, even if inaccessible until epoch end, leads to a simpler calculation on the final day, than storing 21 non-accured snapshots and averaging.

## Security & Privacy Considerations

Time-Weighted Rewards decreases the incentives for, and effects of exploitative reward tactic. In the current system a DLP or staker could right before an epoch end use a potential exploit, and get highly rewarded for it. If rewards were time weighted, their rewards would only be one 21th as high, assuming the exploit can be addressed within one day.
Privacy is unaffected.

## Implementation

The functionality could likely be developed, tested and implemented well in time for epoch four.
Time-weighted reward is the standard for protocols with rewards for participants, and thus documentation and other resources are well established.

## Copyright

Copyright and related rights waived via CC0.
