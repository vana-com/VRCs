| VRC | Title | Status | Type | Author | Created |
|-----|--------|--------|------|---------|----------|
| VRC-14 | Aligning DLP Incentives with DataFi | Draft | Technical | Anna, Art, Colin, Francis, Tim | 2025-03-20 |

## Abstract

This VRC proposes a major upgrade to the DLP (Data Liquidity Pool) reward mechanism to create a sustainable DataFi ecosystem. The current approach of direct VANA emissions to top-performing DLPs is replaced with a market-driven model where rewards flow into liquidity pools for DLP tokens, creating deeper markets for data assets.

### Key Changes:

1. **Removing the artificial top 16 constraint** to support all qualifying DLPs.
2. **Extending epochs from 3 weeks to 3 months** for long-term planning.
3. **Introducing Data Validator staking** to support data access infrastructure.
4. **Aligning incentives with actual data utility** through a balanced scoring system:
   - Trading volume: **30%**
   - Unique contributors: **20%**
   - Data access fees: **50%**

This update establishes DLP tokens as first-class assets in the DataFi ecosystem, with market-driven price discovery that properly values data contributions while ensuring sufficient liquidity for both providers and consumers.

## Motivation

The current DLP reward system, while effective in the early phase of ecosystem development, has reached its natural evolution point and presents several limitations:

- Direct VANA rewards to DLP creators don't necessarily translate to ecosystem liquidity or benefit data contributors.
- The **top 16 constraint** creates artificial competition rather than fostering collaborative ecosystem growth.
- **Short epochs (3 weeks)** create volatility and short-term optimization at the expense of sustainable development.
- The system lacks direct alignment with **data access functionality and utility**.

As Vana evolves into a comprehensive DataFi ecosystem, **data tokens must function as liquid assets** with sufficient market depth to support actual usage. The health of data tokens is an important metric to track as it reflects data usage and the market price for a given dataset. 

To support the next phase of growth, the DLP incentive system should:

- Reward DLPs based on **data access fees**.
- Align incentives across **contributors, DLP creators, and data consumers**.
- Create **sustainable liquidity for data markets**, enabling a trading ecosystem with data as the underlying asset.
- Support **specialized data ecosystems** across various domains.

## Infrastructure Support

Alongside this proposal, the **Open Data Labs** team has developed **programmatic data access infrastructure**, enabling cross-DLP data access with detailed on-chain tracking, making it possible to directly track data access fees. This infrastructure **directly links data tokens with DLP incentives**, creating an economic model where **data token value reflects actual data usage**.

## Specification

### Walkthrough of how new DLP incentives work:

1. **At the close of the Epoch**, **TDVL (Total Data Value Locked)** is measured.  
   - The **annual rewards pool** is **0.5%**, plus **0.5%** for every **$500M** of TDVL on Vana, up to a cap of **5% per year**.
   - The **annual rewards pool** is **divided by four** for **quarterly epochs**.
   - **Example**:  
     - If **TDVL = $600M**, then **annual DLP incentives pool** = **1%**  
     - **Epoch rewards pool = 1% / 4 = 0.25% = 300,000 VANA**
     - If **TDVL < $500M**, the **rewards pool** remains at **0.5%**.
   - **Goal**: Scaling **rewards with TDVL** to grow the **incentive pool** alongside **ecosystem success**.

2. **TDVL (Total Data Value Locked) includes**:
   - **DEX liquidity pools**
   - **Lending protocols**
   - **Other applications built on Vana**
   - Similar to **Total Value Locked (TVL)** on other chains.

3. **No more "Top 16"**:  
   - Any **DLP** that **meets eligibility requirements** can **qualify** for incentives.  
   - **Example**: If **30 DLPs** meet the criteria, all **30 are eligible**.

4. **Eligibility criteria**:
   - Must **meet VRC-5 requirements**.
   - Must **migrate to the new data access architecture**.
   - Must have a **VRC-20 compliant token**.

### **Example: DLP Incentives Pool Distribution**

For this example, assume the **DLP incentives pool is 300,000 VANA** for the epoch, and **30 DLPs are eligible**. The split of rewards is determined at the **end of the epoch** based on the following **three performance metrics**, measured as averages across the epoch:

#### **1. DLP Token Trading Volume (30% of score)**

- Measured as the **trading volume of VANA/DLP token** throughout the epoch.
- This metric is used as a **proxy for the economic health** of the DLP.
- **Example:** If a DLP is selling a lot of data, or if many companies are planning to access data and have purchased the data token in advance, this would be **captured in DLP token trading volume**.
- **TensorSource**, an ecosystem company, will **actively participate** in DLP token markets by **building positions** in datasets it plans to buy access to.

#### **2. Unique Data Contributors (20% of score)**

- Measured by the **number of unique wallets contributing data**.
- This captures how much data the **DLP has aggregated**, even if it is not yet being used.
- Acts as a **leading indicator of a DLP’s potential success**.
- **Anti-gaming measures**:
  - DLPs are **discouraged from artificially inflating** data contributor numbers by creating an **intentionally weak proof of contribution**.
  - This would also **violate VRC-5**, making a **DLP ineligible for rewards**.
  - With data access now in place, the **Vana Foundation may investigate** unusual behavior through **data audits** and **disqualify any DLPs** who are **not acting in the best interests** of aggregating a valuable dataset.

#### **3. Data Access Fees (50% of score)**

- Measured in the **value of data access fees paid in DLP token and VANA** over the course of the epoch.
- Captures how much the **dataset is actually being used** to:
  - **Train AI models**
  - **Run other operations**
  - **Create products based on the data**
- **Vana Foundation audits**:
  - The **Vana Foundation may ask for documentation** on who is accessing data and why it is being accessed.
  - Ensures that **data access represents legitimate usage** rather than **data wash trading for mining rewards**.

#### **Score Normalization**

Scores for each category are **normalized across DLPs**:
**DLP Score** = 0.30 * (DLP token trading volume / total DLP token trading volume) + 0.20 * (DLP unique data contributors / total unique data contributors) + 0.50 * (DLP data access fees / total data access fees)
- Throughout the epoch, **monitoring will be in place** to detect anomalies.
- **Example:** If one DLP has **1,000 times as much data access** as any other DLP, there may be an **update proposed to add a polynomial** to slightly normalize the scores.
- **These changes will be proactively communicated** to DLPs and follow principles of:
  - **Ensuring high data quality** in the ecosystem.
  - **Avoiding excessive concentration of rewards**.

### **Reward Distribution Example**

- Suppose a **DLP is eligible for 10,000 VANA** in **DLP incentives** at the **close of Epoch 6**.
- This allocation is **split into the number of days** in the Epoch (**91 days**). 10,000 VANA / 91 days = 110 VANA (approximately)

- The **DLP incentives allocated in Epoch 6** will be **deployed linearly throughout Epoch 7**.
- Each day, the **proportionate amount of rewards (110 VANA)** is used to:
  - **Buy the DLP’s token**.
  - **Add it to the DEX liquidity pool** alongside **an equal amount of VANA**.

#### **Liquidity Pool Example**

- **55 VANA is used to buy the DLP token**, resulting in **550 of the DLP token** *(assuming a price of 0.1 VANA per token)*.
- This **550 DLP token is added to the DEX liquidity pool** alongside the remaining **55 VANA**.

#### **Slippage Protection**

- The **purchase of the DLP token** will **not exceed** a value that causes **more than 2% slippage**.
- **Example:**
  - If the **DEX liquidity pool for VANA/DLP token** can only handle **buying 10 VANA worth of the token**, then:
    - The remaining **45 VANA** **would not buy** the DLP token.
    - Instead, it would be **rolled into the DLP’s rewards pool** for the **following epoch**.

- If in the **following epoch**, the **DLP still does not have sufficient liquidity** *(measured by whether the protocol can deploy rewards without exceeding 2% slippage)*, the **DLP would lose this incentive**, and it **would be returned to the overall incentive pool**.

### **Liquidity Pool Monitoring**

- The **VANA and DLP token** are added as **liquidity in a full-range liquidity pool**.
- The **liquidity pool will be monitored** for any **unusual selling pressure** that **moves price below 15% of the reference price** when the liquidity was deployed.
- The **reference price** is tracked as a **moving average** based on the protocol’s DLP token purchases **throughout the epoch**.

#### **Automated Buying & Market Protection**

- The automatic buying process is repeated **daily**, with **randomized timing** to prevent traders from **gaming the system**.
- If **DLP tokens fall below 15% of the reference price**, the lowest price at which liquidity was deployed in a given epoch, a **review will be placed** as to why they are receiving negative price action to determine the **next steps** for their **participation in the incentives program**.

### **Epoch Structure Update**

- Epochs are **extended from 3 weeks to 3 months** given the **new incentives system**.
- Now that DLP rewards **are not based on stake**, DLP staking is replaced with **Data Validator staking**.
- **Stakers can stake with the Data Validator Pool** to:
  - **Directly support the data access infrastructure**.
  - **Tie yield to data access**.

### **Summary of Requirements for DLPs**

- DLPs must meet all requirements specified in VRC-5.
- DLPs must have a token conforming to the **VRC-20** DAT Token standard with **sufficient liquidity** to qualify for **DLP incentives**.
- **DLPs who already have a token** can work with the **Vana Foundation** to ensure compliance or find a migration path.
  - **DLPs without tokens** must launch a token during **Epoch 6 (Q2)** to qualify for rewards.
- **DLPs who do not plan to launch a token** during Epoch 6 can work with the Vana Foundation on **find alternate support** until they are **ready to launch**
- **DLPs must support the standardized data access interface*.

### **Major Changes**

- **All DLPs must have a DLP token** to be eligible for incentives.
- DLP incentives now go directly to **buying the DLP token** and adding it **as liquidity to the DEX pool**, rather than to the **DLP treasury**.
- **DLP incentives are now based on**:
  - **DLP token trading volume (30%)**.
  - **Unique data contributors (20%)**.
  - **Data access fees (50%)**.
- **No more Top 16** – any **DLP that meets the eligibility criteria** can **earn incentives**.
- **Epochs are now 3 months** rather than 3 weeks.

## **Rationale**

### **Shift to Liquidity-Based Incentives**

- **Direct VANA emissions** to DLP creators **created misaligned incentives**, where projects optimized for gaming the reward system rather than building sustainable data ecosystems and **driving value to their DLP token**.
- By redirecting incentives to liquidity pools, we **create natural price discovery** through **liquid markets** that enable efficient pricing of data assets.
- This approach also **ensures ecosystem alignment** so that **data token holders**, including **data contributors**, all benefit from DLP incentives rather than concentrating rewards with DLP operators.

### **Requiring Token Launches**

- **Requiring the launch of a data token** that follows the **VRC-20 standard** is a **significant change**.
- This could be **an issue for DLPs** that:
  - **Already have a token** that does **not** follow the standard. *(The Vana Foundation can work with DLPs on a migration path.)*
  - **Do not want to issue a data token**.
- However, it was determined that a **data token is ultimately required** to allow for the **tokenization of a dataset**.
- **DLP tokens create a direct economic link** between:
  - **Data contributors**
  - **DLP operators**
  - **Data consumers**
- This **aligns incentives across all stakeholders**.
- Additionally, the data token price provides **real-time feedback** on the **perceived value and utility** of each dataset, creating a **market-driven** quality assessment mechanism.
- **If a DLP is not yet ready to launch a token**, they can be **supported through other programs outside of DLP incentives**.

### **Performance Metric Alignment**

- **Tying performance metrics** to:
  - **Data access (50%)**
  - **Contributor growth (20%)**
  - **Token liquidity (30%)**
- Creates a **balanced approach** that:
  - **Rewards actual data usage**.
  - **Supports ecosystem development**.
- The **50% weight on data access fees** prioritizes **DLPs that generate real utility** through **active data consumption** for **AI training and consumer insights**.
- The **20% weight on unique contributors** encourages **growth of data contributors**.
- The **30% weight on trading volume** acts as a **proxy for the health of the DataFi ecosystem** and can **capture demand and interest** in a dataset.

### **Removal of Top 16**

- Eliminating the **"Top 16" limitation** and **extending epochs to quarterly cycles** promotes **collaboration over competition**.
- DLPs can focus on **their unique value proposition** rather than **competing for limited slots** in the **top 16 ranking system**.
- **Quarterly epochs** allow DLPs to:
  - **Implement more sophisticated strategies**.
  - **Reduce short-term optimization** that might **sacrifice long-term sustainability**.
- The **removal of the Top 16** also allows for **specialized DLPs** serving **various domains** (from **robotics** to **healthcare**) to **thrive in parallel**.

## **Security & Privacy Considerations**

### **Market Manipulation Risks**

- Because **DLP incentives go directly into buying the DLP token**, there are risks that a DLP could **manipulate its token price** to game the system.
- **Example of manipulation**:
  - A DLP could **artificially inflate the token price** before rewards are deployed.
  - The DLP could then **sell its own token at a high price**, effectively **extracting incentives unfairly**.
  
#### **Mitigation Strategies:**

1. **Gradual Buying Over the Epoch**  
   - The system buys the DLP token and deploys liquidity over a long period (3 months).
   - This makes it harder for a DLP to manipulate price in the short term.

2. **Slippage Limits**  
   - The protocol **limits buying pressure** to what the DEX liquidity pool **can handle**.
   - Buys are only executed if slippage is ≤2%.

3. **Liquidity Deployment Restrictions**  
   - Adding liquidity within a **specific price range** ensures that DLPs who experience significant price drops no longer have access to the liquidity.

4. **Standardized Token Requirements**  
   - DLP tokens must follow the **VRC-20 standard**.
   - This prevents **hyperinflationary token designs** that could create excessive sell pressure.

5. **Monitoring and Detection**  
   - New DLPs must ensure **healthy liquidity at launch**. There are initiatives in the ecosystem making it easy to use a **bonding curve** for new DLPs.
   - The ecosystem will introduce tools to detect **suspicious trading activity** in DLP token pairs.

### **Gaming Performance Metrics**

- DLPs could weaken their proof of contribution to show higher unique data contributor counts.
- This would **trade off against data access fees**, as companies and researchers would be **less interested in using this data**.
- The Vana Foundation will monitor for unusual behavior.
- DLPs violating **VRC-5** will be **disqualified from rewards**.

2. **Preventing Data Wash Trading**  
   - **DLPs could provide kickbacks** to companies and researchers paying fees to access their data, or convince users to run jobs and pay fees with other goals.
   - The Foundation will investigate unusual access patterns to ensure that **fees represent legitimate data consumption**.
   - DLPs may be asked to provide **commercial justifications** for data access usage.

## **Implementation**

### **Epoch 5: Transition Period**

- **Release all related VRCs** for public comment, including:
  - **Data Access VRC**
  - **Data Token Standard VRC**
  - **DLP Rewards Alignment VRC**
- Continue the **existing reward distribution mechanism** for the remainder of Epoch 5.

### **Close of Epoch 5 → Epoch 6: System Migration**

- **Introduce Data Validator staking infrastructure** to replace DLP staking.
- **Begin migration for existing DLPs**, assisting them in:
  - **Launching their tokens**.
  - **Preparing for the data access standard**.
- **DLPs do not need to complete migration** before Epoch 6, but they must finalize it **during the epoch**.

### **Epoch 6: First Full Cycle with New Rules**

- Switch from **3-week** epochs to **3-mont**h epochs.
- **Start enforcement of**:
  - Token standards (VRC-20 compliance)
  - Data access migration for eligibility.

### **Epoch 7: Incentive Distribution Begins**

- DLP incentives from **Epoch 6 rewards** will be deployed **throughout Epoch 7**.

For detailed roll-out timelines related to data token standards or data access functionality, refer to the respective VRCs.

## Copyright
Copyright and related rights waived via CC0.
