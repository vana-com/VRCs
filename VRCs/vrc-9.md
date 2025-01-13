| VRC | Title | Status | Type | Author | Created |
|-----|--------|--------|------|---------|----------|
| VRC-9 | The Mufasa VRC -  Introducing a Points-Based Reward System for Fair Distribution of DLP Rewards to stimulate the Circle of Life | Proposed | Technical  | Roger Ying (r@dfusion.ai), Patrick de la Garza (p@dfusion.ai) | 2025-01-13 |

## Abstract

This proposal introduces a points-based reward model for Data Liquidity Pools (DLPs) in the Vana ecosystem. It shifts away from relying solely on staking amounts and contributor numbers by incorporating a multi-metric framework. This system aims to prevent gaming by dominant pools, encourage healthy competition, and promote decentralization, innovation, and community-driven contributions.

## Motivation

The current reward mechanism risks fostering a “winner-takes-all” scenario where a few dominant pools monopolize rewards. This could discourage smaller DLPs, stifle innovation, and concentrate power within the ecosystem.
A points-based reward system addresses these risks by:
	1.	Ensuring fairer reward distribution.
	2.	Incentivizing balanced growth across all DLPs.
	3.	Preventing centralization of power and rewards.
	4.	Strengthening the ecosystem’s resilience and decentralization.
 
## Specification

Proposed Metrics for Points-Based Rewards

We propose these criteria, but for the purpose of this VRC, these criteria will be used as an example and we can propose subsequent VRC’s on each criteria. 

1.	Stake Diversity (20% weight):
Rewards pools with diverse contributors rather than simply large stakes. Diversity Score = Unique Contributors / Total Contrbutors

2.	Data Contribution Quality (30% weight):
Rewards high-quality, validated, and unique data contributions based on peer reviews or validator feedback.

3.	Network Participation (20% weight):
Rewards active involvement in governance, discussions, or protocol development.

4.	Uptime and Performance (20% weight):
Measures reliability, uptime, and timeliness of data contributions using automated monitoring.

5.	Innovation and Impact (10% weight):
Recognizes pools that propose and implement impactful features, tools, or initiatives.

Reward Allocation Framework
	•	Points are earned based on performance across the metrics.
	•	Rewards are distributed proportionally to the total points accumulated by each DLP within an epoch.
	•	Metric weights are adjustable based on community feedback.

**Points Breakdown for Top 16 in Each Metric**

To encourage consistent performance, rewards are allocated to the top 16 DLPs in each category based on the following points system:


|Position | Points|
|---|---|
|1st | 25|
|2nd | 20|
|3rd | 18|
|4th | 16|
|5th | 14|
|6th | 12|
|7th | 10|
|8th | 8|
|9th | 6|
|10th | 5|
|11th | 4|
|12th | 3|
|13th | 2|
|14th | 1.5|
|15th | 1|
|16th | 0.5|



Integration Example
If DLP-X ranks as follows:

	•	Stake Diversity (20%): 2nd (20 points)
 
	•	Data Quality (30%): 5th (14 points)
 
	•	Network Participation (20%): 10th (5 points)
 
	•	Uptime and Performance (20%): 1st (25 points)
 
	•	Innovation and Impact (10%): 8th (8 points)
 

**Total Points for DLP-X = (20 x 0.2) + (14 x 0.3) + (5 x 0.2) + (25 x 0.2) + (8 x 0.1) = 15**

Rewards are then distributed proportionally based on the total points accumulated by all DLPs.

**Advantages of the Proposed System**

	1.	Incentivizes Broader Participation: Encourages all DLPs to compete across multiple metrics.
 
	2.	Prevents Dominance: Reduces reliance on a single metric, promoting fair competition.
 
	3.	Encourages Consistency: Rewards sustained performance across diverse areas.
 
	4.	Flexibility: Allows for metric adjustments to adapt to ecosystem needs.
 
 
## Rationale

The points-based system supports Vana’s vision of a decentralized and inclusive data economy by rewarding DLPs across diverse performance metrics. This approach ensures:

	•	Decentralized Participation: Smaller pools are encouraged to contribute without being overshadowed by larger ones.
 
	•	Metric Diversity: Rewards are based on multiple aspects like data quality, timeliness, and participation.
 
	•	Ecosystem Health: Reduces the likelihood of exploitation by single entities.
 
At this early stage of Vana’s ecosystem, preventing a concentration of power is critical to avoid creating an “insider’s game.” All DLP’s benefit from the $VANA token increasing in utility and valuation. 



## Implementation

Phase 1: Design and Testing
	•	Prototype the points-based system.
	•	Simulate the model with current Epoch’s criteria.

Phase 2: Community Feedback
	•	Gather input from DLP operators and stakeholders.
	•	Refine metrics and weights, categories can be rolled out at each new Epoch.

Phase 3: Rollout
	•	Deploy the system on next Epoch. 
	•	Monitor and evaluate performance for one quarter.

Phase 4: Iteration
	•	Launch on the mainnet with governance approval.
	•	Continuously refine based on feedback.

**Impact Evaluation**

	1.	Fairer Distribution: Reduces dominance by large DLPs, ensuring equity.
 
	2.	Decentralization: Encourages participation from smaller pools.
 
	3.	System Integrity: Mitigates risks of gaming or manipulation.
 
 	4.	Ecosystem Growth: Promotes innovation and high-quality contributions.
  

**Conclusion**

Adopting a points-based reward system will ensure a fairer, more resilient reward mechanism for DLPs in the Vana ecosystem. By incentivizing diverse contributions and decentralization, this approach guarantees long-term sustainability and equity while fostering innovation and competition.


## Copyright

Copyright and related rights waived via CC0.

---

## VRC Type Terms

- **Technical** - A VRC that proposes changes to Vana protocol specifications or implementations
