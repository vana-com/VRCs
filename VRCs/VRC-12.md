| VRC | Title | Status | Type | Author | Created |
|-----|--------|--------|------|---------|----------|
| VRC-12 | veVANA Staking & Flexible Staking Features | Final | Technical | Chris R, Tim N | 2025-02-21 |

## Abstract

This VRC introduces **three major upgrades** to the DLP rewards system:

1. **veVANA Staking** – DLP rewards will be distributed in **veVANA (vote-escrowed VANA)** instead of VANA tokens, starting in Epoch 5. This introduces and clarifies **programmatic staking lockups, voting power, and automatic restaking** to reward long-term commitment.
2. **Partial Unstaking** – Stakers will be able to **withdraw a portion of their stake** instead of being forced to remove the entire amount.
3. **Stake Mobility** – Users can **move their veVANA stake between DLPs** without losing their existing multiplier.

These changes ensure **greater flexibility for stakers while maintaining strong incentives for long-term participation.**

## Motivation

The current staking model has **several limitations**:
- **Rigid lockups** – Users must **unstake everything at once**, reducing flexibility.
- **Lost multipliers** – If a staker wants to switch DLPs, they must unstake and **reset their rewards multiplier**.
- **No governance power** – Staked tokens do not currently provide voting rights.

By introducing **veVANA staking**, **partial unstaking**, and **stake mobility**, we give stakers **more control over their positions while maintaining incentives for long-term commitment.**

## Specification

### 1. **veVANA Staking (Epoch 5 Onward)**
- Users stake **$VANA → veVANA** (vote-escrowed VANA).
- **What is veVANA?** A **locked version of VANA** that gives:
  - **Voting power** in governance.
  - **Boosted rewards** based on staking duration.
  - **Automatic restaking** (unless withdrawn early).
- **Lock-up period required** – The longer the stake duration, the higher the rewards.
- **Early withdrawals have penalties** to discourage quick exits.

### 2. **Partial Unstaking**
- **Stakers can withdraw a portion of their stake** without removing the entire amount.
- **How it works:**
  - Users can **unstake X% of their veVANA** while keeping the rest staked.
  - **Unstaked amounts follow the standard withdrawal penalty curve.**
  - **Remaining veVANA retains its multiplier and continues earning rewards.**
- **Why this matters:**  
  ✅ More flexibility for users who need liquidity.  
  ✅ Encourages long-term staking by **reducing all-or-nothing decisions**.

### 3. **Stake Mobility Between DLPs**
- **Users can move their veVANA stake between DLPs** **without losing their staking multiplier.**
- **How it works:**
  - Instead of unstaking and restaking (resetting the multiplier), users can **reallocate their stake directly**.
  - The **original staking duration is preserved**, ensuring that stakers **don’t lose rewards progress** when switching DLPs.
- **Why this matters:**  
  ✅ Encourages active participation in the ecosystem.  
  ✅ Allows stakers to **support different DLPs over time without penalties**.  
  ✅ Strengthens the DLP landscape by **enabling stake flow between pools**.

## Rationale

These updates ensure:  
✅ **Long-term staking rewards** – Encourages real commitment while allowing flexibility.  
✅ **Better user experience** – Partial unstaking + stake mobility makes staking more attractive.  
✅ **Stronger ecosystem alignment** – Fairer incentives for both stakers and DLPs.  

## Security & Privacy Considerations

- **Security**: Smart contract updates will undergo audits before launch.
- **Privacy**: No changes—data contributor privacy remains protected.

## Implementation Plan

- **Epoch 5**:  
  - Switch from VANA rewards to veVANA staking.  
  - Enable **partial unstaking**.  
  - Introduce **stake mobility between DLPs** (may be deferred to Epoch 6).
- **Epoch 6+**:  
  - Refine staking logic based on ecosystem feedback.  

## Copyright

**CC0 – No rights reserved.**
