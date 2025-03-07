| VRC | Title | Status | Type | Author | Created |
|-----|--------|--------|------|---------|----------|
| VRC-12 | Partial Unstaking | Final | Technical | Chris R, Tim N, Anatoly S | 2025-02-21 |

## Abstract

The current staking mechanism requires users to fully unstake their tokens if they wish to withdraw, leading to unnecessary rigidity.

This VRC introduces **partial unstaking**, allowing stakers to withdraw a portion of their stake while keeping the rest staked. This improvement enhances **staking flexibility** without compromising long-term incentives.

## Motivation

The existing staking model has a key limitation:

- **Full unstaking requirement** – Users must remove their entire stake to access liquidity, reducing flexibility and discouraging long-term participation.

Partial unstaking addresses this issue by enabling gradual withdrawals, ensuring that users retain both liquidity and staking benefits.

## Specification

- Stakers can withdraw a portion of their staked amount instead of the full balance.
- How it works:
  - Users specify the percentage of stake to withdraw.
  - The remaining stake continues earning rewards.
  - Withdrawn amount is sent to the user's wallet.

## Rationale

- **Improved flexibility** – Users can access liquidity without unstaking their entire balance.
- **Better staking incentives** – Long-term staking remains attractive as rewards continue on the remaining stake.
- **Reduced friction** – No longer an all-or-nothing decision.

## Security & Privacy Considerations

- **Security**: Smart contract updates will undergo audits before launch.
- **Privacy**: No changes—data contributor privacy remains protected.

## Implementation Plan

Epoch 5:
- Deploy partial unstaking functionality.
- Monitor adoption and gather feedback for potential refinements.

## Copyright

**CC0 – No rights reserved.**
