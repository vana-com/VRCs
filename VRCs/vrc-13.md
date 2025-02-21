| VRC | Title | Status | Type | Author | Created |
|-----|--------|--------|------|---------|----------|
| VRC-13 | Tokenomics Roadmap: DLP rewards and programmatic data access | Draft | Technical | Chris R, Tim N | 2025-02-21 |

# Abstract
This document provides a high-level, preliminary overview of proposed changes to the Vana Data Liquidity Pool (DLP) ecosystem, intended to be rolled out over the coming months. These changes are designed to evolve Vana’s tokenomics, introduce staking and slashing mechanisms, and implement new performance metrics to incentivize participation of high-performing DLPs and high-quality data contributions to the Vana network.

The plan includes the introduction of vote-escrowed VANA (veVANA), dual reward structures, slashing penalties for malicious behavior, and data access metrics for reward allocation. As this is a preliminary proposal, the details will be refined over time and released in individual VRCs for comment before each phase is scheduled for implementation.

# Motivation
The purpose of this proposal is to outline a broad vision for enhancing the DLP ecosystem through rewards and incentives that increasingly align DLPs to promote verified, high-quality data contribution, as well as incentivize other necessary ecosystem parties such as liquidity providers, application builders, and individual data providers.

We are sharing this approach (which is still in development), in order to foster trust and transparency with the Vana community as we move towards the long-term vision where DLPs are incentivized to contribute valuable data and ensure the long-term sustainability of the ecosystem.

The intention is to drive meaningful alignment and participation across the Vana ecosystem: DLPs (DataDAOs), data application developers, data capital providers and individual data contributors.

This proposal offers a broad picture of the intended direction, and is subject to revision based on ongoing feedback and evolving needs. Each phase of the plan will be reviewed and refined as we move closer to execution.

# Specification
This proposal covers a series of planned changes that will be implemented over several months. The detailed mechanics of each phase are not finalized and will be the subject of separate, future VRCs, each released for comment in the epoch ahead of its planned release. This gives stakeholders the opportunity to review and influence the final structure of each change.

## Key Changes and Planned Rollout (Expected over the Coming Months):

### 1. Staking Mechanism:
VANA holders will stake tokens to receive veVANA (staking version of VANA, detailed more thoroughly in VRC 12), which can be staked with DLPs for rewards.  
**Tentative release**: Epoch 5.  
**VRC for comment** will be released in Epoch 4.

### 2. Slashing Penalties:
DLPs found in breach of a VRC will be subject to slashing penalties, including the loss of 10% of their stake for each breach, impacting both the DLP and user stakes.  
**Tentative release**: Epoch 6.  
**VRC for comment** will be released in Epoch 5.

### 3. Performance Metrics:
DLP rewards will be based on data access (compute usage) and data value, with rewards distributed in both DLP tokens and veVANA. The size of the rewards pool will also be conditioned on these performance metrics; we want to align incentives around building valuable datasets, and see these metrics as the most accurate indicator.  
**Tentative release**: Epoch 6.  
**VRC for comment** will be released in Epoch 5.

### 4. Dual Rewards Structure:
Once DLP tokenomics have been phased in, we aim to distribute DLP rewards using a mixture of buying DLP tokens and through veVANA.  
**Tentative first release**: Epoch 7  
**VRC for comment** will be released Epoch 6.

### 5. Tokenomics & Rewards Distribution:
A fixed, non-inflationary DLP token standard will be launched, which will include a bonding curve, with mechanisms for burning during data sales and access. This is necessary to ensure ecosystem value creation and proper use of DLP rewards.  
**Tentative release**: Epoch 7.  
**VRC for comment** will be released in Epoch 6.

### 6. Launch Process for DLP Tokens:
New DLP tokens will be registered and created via a bonding curve, and liquidity will become transferable once thresholds are met. There will be a portion of the stake which will be locked until data access minimums are met.  
**Tentative release**: Epoch 8.  
**VRC for comment** will be released in Epoch 7.

Each of these changes will be part of a broader evolutionary roadmap for the DLP ecosystem, subject to ongoing refinement based on feedback, simulations, and real-world testing. As each milestone approaches, separate VRCs will be released in the preceding epoch to gather comments and fine-tune the details.

# Rationale
This proposal is a high-level, preliminary vision that aims to set the direction for the DLP ecosystem's growth. As such, the details are subject to change, and much of the design will be refined over time. This roadmap provides a broad outline of potential changes to incentivize quality data contributions and create a more robust, sustainable system. The goal is to encourage active participation, while maintaining flexibility to adjust as the ecosystem matures.

- **Staking with veVANA**: This will encourage long-term involvement and provide governance rights, though the exact mechanisms will evolve.
- **Slashing Penalties**: These serve as a deterrent to malicious behavior but will be fine-tuned based on feedback and testing.
- **DLP Token Standards & Performance Metrics**: These are still under discussion and will be developed with input from the community, aiming to align the DLP token closely with the DLP’s dataset.
- **Data Access & Value Metrics**: These provide clear criteria for rewarding DLPs, but the mechanisms and thresholds will evolve over time.

# Security & Privacy Considerations
As with any large-scale change, security and privacy implications need to be carefully considered. Potential attack vectors will be monitored, including those related to staking mechanics and the burning process during data sales. Trust assumptions will also need to be managed, especially as slashing penalties and staking systems are introduced. Since this proposal is preliminary, the risk of attack or exploitation will be evaluated as each phase moves forward.

- **Attack Vectors**: Including slashing-related risks, malicious data manipulation, and DLP token manipulation during the staking and incentives process.
- **Trust Assumptions**: Trust in the DLPs' good faith and the staking process will be fundamental, with slashing mechanisms acting as a safeguard.
- **Privacy Implications**: Data sales and access will be designed to protect user privacy and ensure economic protection of the dataset.

# Implementation
The changes will be implemented incrementally, with each component rolled out in a phased manner. The final structure of each change will be shaped by community feedback received through VRCs released before each phase.

## Expected Timeline:
- **Epoch 4**: Initial VRC released for staking mechanism and veVANA.
- **Epoch 5**: Introduce veVANA staking and begin reward distribution.
- **Epoch 6**: Implement performance metrics and introduce DLP token purchases.
- **Epoch 7**: Launch tokenomics and reward burning mechanisms.
- **Epoch 8**: Begin DLP token launch process and liquidity transferability.

### Testing:
Each phase will undergo internal testing, with feedback incorporated to refine each step. Smart contracts will be audited and tokenomics have undergone a system design & review.

# Copyright
Copyright and related rights waived via CC0.
