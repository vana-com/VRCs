| VRC | Title | Status | Type | Author | Created |  
|-----|--------|--------|------|---------|----------|  
| VRC-20 | DAT Token Standard | Draft | Technical | Tim, Francis, Anatoly, Anna | 2025-03-20 |

## Abstract

This VRC establishes core design principles and minimum requirements for Data Asset Tokens (DATs) within the Vana ecosystem. As data tokenomics emerges as a critical component of DataFi, these standards provide a framework for creating tokens that effectively represent dataset value, govern access permissions, and incentivize data contributions.

Beginning in Epoch 6, as outlined in VRC-14, DLP rewards will transition from direct VANA distributions to liquidity support for qualifying DLP tokens. This VRC defines the essential token characteristics required to participate in this new incentive model while ensuring tokens serve their intended purpose in the DataFi ecosystem. The standard balances necessary protections for liquidity provision with sufficient flexibility for DLPs to design tokens appropriate to their specific data markets and communities.

## Motivation

Data tokenomics is an emerging field within the Vana ecosystem, with standardization playing a critical role in the success of any market. As the Vana ecosystem evolves toward a comprehensive DataFi framework, DLP tokens will play an increasingly central role in representing data value, access rights, and contributor incentives.

The new reward mechanism outlined in VRC-14 will direct VANA tokens to provide liquidity for DLP tokens in full-range positions rather than distributing VANA directly to DLP operators. This fundamental shift in the incentive structure elevates the importance of well-designed data tokens.

This change lays out baseline standards that:
1. Protect the protocol's liquidity provision
2. Ensure tokens function as genuine data assets with utility tied to their underlying dataset
3. Align incentives for data contributors and consumers
4. Enable a vibrant token ecosystem with appropriate flexibility
5. Establish consistent design principles for the tokenization of data

## Specification

### 1. Token Implementation

1.1 DAT tokens must implement the ERC-20 standard.

1.2 The token implementation must pass a Vana Foundation approved security review.

### 2. Supply Policy

2.1 The token must have one of the following supply policies:
  - A fixed maximum supply that cannot be changed
  - A transparent and predictable emission schedule that is enforced through smart contracts or, at minimum, publicly documented with clear accountability measures

2.2 The token must not implement automatic supply adjustments (rebasing) that could affect liquidity pool accounting.

### 3. Team Allocation and Vesting

3.1 Team, founder, and early contributor allocations must be subject to a vesting schedule of at least 6 months, followed by linear vesting for the remainder.

### 4. Transfer Limitations

4.1 If the token implements transfer fees or taxes, these must not exceed 3% per transaction.

4.2 The token must not implement selective transfer restrictions that could be used to trap liquidity.

### 5. Critical Function Protection

5.1 Any functions that can materially change the token's economic properties must be subject to a timelock of at least 48 hours. Critical functions include but are not limited to:
  - Minting capabilities
  - Fee structure changes
  - Transfer restriction modifications
  - Contract upgrade functions
  - Parameter adjustments that impact token value or liquidity

### 6. Data Utility Requirements

6.1 The token must serve multiple data utility functions including:
   - Distribution to data contributors based on successful proof of contribution, as defined by previous VRCs
   - Governance over dataset access permissions and refinement policies
   - Required medium of exchange for data access, as described in VRC-15

6.2 The DLP operator must document the token's role in their data ecosystem, including:
   - Specific mechanisms for how tokens are earned by or distributed to data contributors
   - Implementation details for how the token enables or governs data access
   - Integration with the Data Access Architecture described in VRC-15

### 7. Source Code Verification

7.1 The token's source code must be verified on the relevant block explorer.

7.2 All related contracts that interact with the token must also have verified source code.

### 8. Compliance and Enforcement

8.1 Failure to comply with any of these requirements will result in immediate disqualification of the DLP for rewards.

## Rationale

This proposal focuses on the minimum requirements needed to protect liquidity while ensuring tokens serve their intended purpose in the DataFi ecosystem:

**ERC-20 Compatibility**: Ensures technical compatibility with DEXs and wallets.

**Defined Supply Policy**: Prevents unexpected dilution of liquidity through hidden or unlimited minting capabilities. A clear supply policy ensures that liquidity providers can accurately assess the current and future token supply, preventing situations where value is extracted through unexpected inflation.

**Team Vesting Requirements**: Aligns team incentives with the long term success of the token.

**Transfer Fee Limitations**: Prevents excessive value extraction through transaction taxes.

**Critical Function Protection**: Provides transparency and reaction time if potentially harmful changes are proposed.

**Data Utility Requirements**: Ensures that tokens receiving liquidity support actually serve a genuine purpose within the DataFi ecosystem by incentivizing data contribution, governing access, and enabling dataset queries. This prevents liquidity support from being directed to tokens without meaningful data utility.


**Source Code Verification**: Verified source code allows the VF and the community to audit the actual implementation rather than relying solely on team-provided documentation.


## Security Considerations

These requirements address the most common economic attack vectors against liquidity pools. The Vana Foundation will deploy liquidity in full-range positions, which provides some protection against targeted price manipulation but still requires these baseline protections.

## Implementation

These standards will take effect at the beginning of Epoch 6. DLPs must ensure their tokens meet these requirements to maintain eligibility for liquidity support.

## Copyright

Copyright and related rights waived via CC0.
