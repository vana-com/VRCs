| VRC | Title | Status | Type | Author | Created |
|-----|--------|--------|------|---------|----------|
| VRC-14 | Aligning DLP Incentives with DataFi | Draft | Technical | Anna, Art, Colin, Francis, Tim | 2025-03-20 |

## Abstract

This VRC proposes a major upgrade to the DLP (Data Liquidity Pool) reward mechanism to create a sustainable DataFi ecosystem. The current approach of direct VANA emissions to top-performing DLPs is replaced with a market-driven model where rewards flow into liquidity pools for DLP tokens, creating deeper markets for data assets. 

Key changes include: 
- (1) removing the artificial top 16 constraint to support all qualifying DLPs, 
- (2) extending epochs from 3 weeks to 3 months for long-term planning,
- (3) introducing Data Validator staking to support data access infrastructure, and
- (4) aligning incentives with actual data utility through a balanced scoring system based on trading volume (30%), unique contributors (20%), and data access fees (50%). 

This update establishes DLP tokens as first-class assets in the DataFi ecosystem, with market-driven price discovery that properly values data contributions while ensuring sufficient liquidity for both providers and consumers.

## Motivation

The current DLP reward system, while effective in the early phase of ecosystem development, has reached its natural evolution point and presents several limitations:
- Direct VANA rewards to DLP creators don't necessarily translate to ecosystem liquidity or benefit data contributors
- The top 16 constraint creates artificial competition rather than collaborative ecosystem growth
- Short epochs (3 weeks) create volatility and short-term optimization at the expense of sustainable development
- The system lacks direct alignment with data access functionality and utility

As Vana evolves from initial data onboarding toward a comprehensive DataFi ecosystem, data tokens must function as liquid assets with sufficient market depth to support actual usage. The health of data tokens is an important metric to track as it reflects data usage and the market price for a given dataset. 

For the next chapter of growth for Vana, the DLP incentive system should:
- Reward DLPs based on data access fees
- Align incentives across all stakeholders (contributors, DLP creators, data consumers)
- Create sustainable liquidity for data markets, enabling a trading ecosystem to form with data as the underlying asset
- Support specialized data ecosystems across various domains

Alongside this proposal, the Open Data Labs team has developed programmatic data access infrastructure, allowing for cross-DLP access of data with detailed onchain tracking, making it possible to directly track data access fees. This infrastructure presents an opportunity to more tightly couple data tokens with DLP incentives, creating an economic model where data token value reflects actual data usage.

## Specification

Walkthrough of how new DLP incentives work: 
1. At the close of the Epoch, TDVL (Total Data Value Locked) is measured. The annual rewards pool is 0.5%, plus 0.5% for every $500M of TDVL on Vana, up to a cap of 5% per year. The annual rewards pool is divided by four for the quarterly epochs. For example, if there is $600M of TDVL on Vana, then the annual DLP incentives pool is 1%, so the Epoch rewards pool for the quarter is 1%/4 = .25% = 300,000 VANA. If there is less than $500M of TDVL on Vana, then the rewards pool is 0.5%. The goal of scaling rewards with TDVL is to grow the incentive pool alongside the ecosystem’s overall success. 
   - TDVL (Total Data Value Locked) is the sum of all assets locked in DataFi applications on Vana, including DEX liquidity pools, lending protocols, and other applications built on Vana. Total Data Value Locked is similar to Total Value Locked (TVL) on other chains. 
2) There is no longer a top 16, so any DLP which meets the eligibility requirement qualifies for incentives. For example, there could be 30 DLPs eligible for incentives. To be eligible, DLPs must meet all criteria of VRC-5, have migrated to the new data access architecture, and have a token compliant with the VRC-20 standard. 
3) For this example, assume the DLP incentives pool is 300,000 VANA for the epoch, and 30 DLPs are eligible. The split of rewards is determined at the end of the epoch based on the following three performance metrics: DLP token trading volume, unique data contributors, and data access, measured as averages across the epoch. 
   - DLP token trading volume (30% of score): measured as the trading volume of VANA / DLP token throughout the epoch. This metric is used as a proxy for the health of the DLP from an economic perspective. For example, if the DLP is selling a lot of data, or if many companies are planning to access data and have purchased the data token in advance, this would be captured in DLP token trading volume. TensorSource, an ecosystem company, will be actively participating in DLP token markets by building up positions in datasets it plans to buy access to. 
   - Unique data contributors (20% of score): unique wallets contributing data within the current epoch. Contributors who participated in previous epochs and contribute again in the current epoch still count as unique contributors for that epoch's scoring, encouraging regular contributions. This captures how much data the DLP has aggregated, even if it is not yet being used, and acts as a leading indicator of a DLP's potential success. DLPs are discouraged from artificially inflating data contributor numbers by for example creating an intentionally weak proof of contribution (this would also violate VRC-5, making a DLP ineligible for rewards). With data access now in place, the Vana Foundation may investigate unusual behavior through data audits and will disqualify any DLPs who are not acting in the best interests of aggregating a valuable dataset. 
   - Data access fees (50% of score): measured in the value of data access fees paid in DLP token and VANA over the course of the epoch. This captures how much the dataset is actually being used to train AI models and run other operations to create products based on the data. The Vana Foundation may ask for documentation on who is accessing data and why it is being accessed to ensure that data access represents legitimate use of the data, rather than data wash trading for the sake of mining rewards. 
   - Scores for each category are normalized across DLPs. DLP Score = 0.30 * (DLP token trading volume / total DLP token trading volume) + 0.20 * (DLP unique data contributors / total unique data contributors) + 0.50 * (DLP data access fees / total data access fees). 
   - Throughout the epoch, there will be monitoring in place to make note of any scores that need additional normalization. For example, if one DLP has 1,000 times as much data access as any other DLP, there may be an update proposed to add a polynomial to slightly normalize the scores. These changes will be proactively communicated to DLPs, and will follow principles of ensuring high data quality in the ecosystem while avoiding excessive concentration of rewards. 
4) Suppose a DLP is eligible for 10,000 VANA in DLP incentives at the close of Epoch 6. 
   - This allocation of the DLP incentives pool is split into the number of days in the Epoch (91 days). 10,000 VANA / 91 days = 110 VANA (approximately)
   - The DLP incentives allocated to a DLP in Epoch 6 will be deployed linearly throughout Epoch 7. Each day, the proportionate amount of rewards (110 VANA) is used to buy the DLP’s token and add it to the DEX liquidity pool alongside an equal amount of VANA. 
   - For example, around 55 VANA is used to buy the DLP token, resulting in 550 of the DLP token (assuming a price of 0.1 VANA). This 550 DLP token is added to the DEX liquidity pool alongside the remaining 55 VANA. 
     - The purchase of the DLP token will not exceed a value that would go above 2% slippage. 
     - For example, if the DEX liquidity pool for VANA / DLP token can only handle buying 10 VANA worth of the token, then the remaining 45 VANA would not buy the DLP token, and would be rolled into the DLP’s rewards pool for the following epoch. 
     - If in the following epoch the DLP still does not have sufficient liquidity (measured by whether or not the protocol can deploy rewards without more than 2% slippage), the DLP would lose this incentive and it would be returned to the overall incentive pool. 
     - The VANA and DLP token are added as liquidity in a full range liquidity pool. The liquidity pool will be monitored for any unusual selling pressure that moves price below 15% of the reference price when the liquidity was deployed. This reference price is tracked as a moving average based on the protocol’s DLP token purchases throughout the Epoch. 
   - The automatic buying process is repeated daily, +/- a random equal amount of time to prevent a trader from predictably trading against this reward. 
   - DLP tokens which fall below 15% of the reference price, the lowest price at which liquidity was deployed in a given epoch, will have a review placed as to why they are receiving negative price action to determine the next steps with their participation in the incentives program. 
  - Epochs are extended from 3 weeks to 3 months given the new incentives system. 
  - Now that DLP rewards are not based on stake, DLP staking is replaced with Data Validator staking, where stakers can stake with the Data Validator Pool to directly support the data access infrastructure and tie yield to data access. 

As a summary, the requirements for DLPs are:
- DLPs must meet all requirements specified in VRC-5
- DLPs must have a token conforming to the VRC-20 DAT Token standard with sufficient liquidity to qualify for DLP incentives. DLPs who already have a token can work with the Vana Foundation on ensuring they meet the standard or finding a migration path. DLPs without tokens must launch a token during Epoch 6 (Q2) to qualify for rewards. DLPs who do not plan to launch a token during Epoch 6 can work with the Vana Foundation on finding alternate support until they are ready to launch. (new)
- DLPs must support the standardized data access interface (new)

The major changes are: 
- All DLPs must have a DLP token to be eligible for incentives. 
- DLP incentives now go directly to buying the DLP token and adding it as liquidity to the DEX pool, rather than to the DLP treasury. 
- DLP incentives are based on: DLP token trading volume (30%), data contributors (20%), and data access fees (50%). 
- There is no more top 16 - any DLP that meets the eligibility criteria can earn incentives. 
- Epochs are now 3 months rather than 3 weeks. 

## Rationale

### Shift to Liquidity-Based Incentives
Direct VANA emissions to DLP creators created misaligned incentives where projects optimized for gaming the reward system rather than building sustainable data ecosystems and driving value to their DLP token. By redirecting incentives to liquidity pools, we create natural price discovery through liquid markets that enable efficient pricing of data assets. This approach also ensures ecosystem alignment so that data token holders, including data contributors, all benefit from DLP incentives rather than concentrating rewards with DLP operators.

### Requiring token launches
Requiring the launch of a data token that follows the VRC-20 standard is a significant change. This could be an issue for DLPs that already have a token that does not follow the standard (the Vana Foundation can work with DLPs on a migration path) or for DLPs who do not want to issue a data token. However, it was determined that a data token is ultimately required to allow for the tokenization of a dataset. DLP tokens create a direct economic link between data contributors, DLP operators, and data consumers, aligning incentives across all stakeholders. Also, data token price provides real-time feedback on the perceived value and utility of each dataset, creating a market-driven quality assessment mechanism. If a DLP is not yet ready to launch a token, they can be supported through other programs outside of DLP incentives. 

### Performance Metric Alignment
Tying performance metrics to data access, contributor growth, and token liquidity creates a balanced approach that rewards actual usage while supporting ecosystem development. The 50% weight on data access fees prioritizes DLPs that generate real utility through active data consumption for AI training and consumer insights. The 20% weight on unique contributors encourages the growth of data contributors. The 30% weight on trading volume acts as a proxy for the health of the dataDAOs datafi ecosystem and can capture demand and interest in their dataset.

### Removal of Top 16
Eliminating the "top 16" limitation and extending epochs to quarterly cycles promotes collaboration over competition. DLPs can focus on their unique value proposition rather than competing for limited slots in the top 16 ranking system. Quarterly epochs allow DLPs to implement more sophisticated strategies and reduce short-term optimization that might sacrifice long-term sustainability. The removal of the top 16 also allows for specialized DLPs serving various domains from robotics to healthcare to thrive in parallel. 

## Security & Privacy Considerations

### Market Manipulation Risks
- Because DLP incentives go directly into buying the DLP token, there are risks that a DLP could manipulate its DLP token price to game the system. For example, the DLP could try to get the rewards deployed in at a very high price and sell their own DLP token at this high price. 
- To mitigate this, the system buys the DLP token and deploys it as liquidity over a long period of time (the full 3 month epoch), making it harder for the DLP to manipulate price. The system also limits its buying pressure to the amount of liquidity the DEX pool can handle, and will only buy as much as it can with a maximum of 2% slippage. Finally, adding liquidity within a specific range means that DLPs who see the price of their DLP token drop significantly no longer have access to the liquidity. 
- DLP tokens are required to follow the VRC-20 standard, ensuring standardization across tokens and a healthy environment for the protocol to be able to deploy liquidity into. VRC-20 for example prevents hyperinflationary data tokens which could lead to unhealthy sell pressure on the DLP token. 
- It will be important for new DLPs to find ways to launch with healthy liquidity, and there are initiatives in the ecosystem making it easy to use a bonding curve for new DLPs. 
- Monitoring tools will also flag suspicious trading activity in DLP token pairs

### Gaming performance metrics
- DLPs could modify their proof of contribution to be intentionally weak to show high unique data contributor counts. This would trade off against data access fees, as companies and researchers would be less interested in using this data, but is still a risk. The Vana Foundation will monitor for unusual behavior and mark DLPs who violate VRC-5 as no longer eligible for rewards. 
- DLPs could provide kickbacks to companies and researchers paying fees to access their data, or convince random people to run jobs and pay fees without any goal in mind. The Vana Foundation will monitor for unusual activity and can ask questions about the commercial motivations behind data access to ensure it’s being used for a legitimate use case rather than simply to mine rewards. 

## Implementation

During Epoch 5:
- Release all related VRCs for public comment, including: Data Access VRC, Data Token Standard VRC, This DLP Rewards Alignment VRC, laying out the technical specifications for the transition
- Continue existing reward distribution mechanism for the remainder of the epoch

Close of Epoch 5 to Epoch 6:
- Introduce Data Validator staking infrastructure to replace DLP staking
- Begin migration process for existing DLPs, supporting them in their token launches and preparing for data access. DLPs do not need to complete the migration before Epoch 6, it can be completed during the epoch. 

Epoch 6
- First epoch on the 3-month cycle (formerly 3-week cycle)
- Begin enforcement of token standards and data access migration for eligibility

Epoch 7
- DLP incentives from Epoch 6 rewards go out

For detailed roll-out timelines related to data token standards or data access functionality, please refer to the respective VRCs.

## Copyright
Copyright and related rights waived via CC0.
