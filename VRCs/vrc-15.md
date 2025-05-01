| VRC | Title | Status | Type | Author | Created |
|-----|--------|--------|------|---------|----------|
| VRC-15 | Data Access Architecture | Draft | Technical | Kahtaf, Anna | 2025-03-20 |

## Abstract

This VRC proposes the Vana Data Access Architecture, a secure framework for enabling application builders to query and use data from Data Liquidity Pools (DLPs) in a privacy-preserving manner. The architecture introduces a data refinement process, secure query execution within Trusted Execution Environments (TEEs), and a permission and payment system for accessing data. This proposal ensures that data remains private, secure, and accessible while creating a sustainable economic model with fees from data access benefiting data contributors, DLP owners, and the broader Vana ecosystem. 

## Motivation

As the Vana ecosystem grows, there's an increasing need for applications to programmatically access and utilize the data collected by DLPs. However, this access must be balanced with strong privacy protections, security measures, and economic incentives. The current system lacks:
1. A standardised way for applications to query data across multiple DLPs, connecting cross-platform data by user. In particular, AI application builders who want access to data from multiple DLPs have expressed a need for this cross-DLP data access. 
2. A secure compute environment for data processing for any task run on data, including AI training jobs. While this is supported in part by the Satya validators running proof of contribution and through other ecosystem collaborations, a standardized approach is needed for more general jobs like AI training that take place across DLPs. 
3. A unified permission and payment system for data access. Currently, DLPs manually approve access to their data and may not use the same format, making it hard for self-serve data consumers to understand how to access data in the ecosystem. 

The Data Access Architecture addresses these needs by establishing a framework that enables secure, privacy-preserving data access alongside payments and onchain permissions for the data, ensuring attribution and sustainable economics.  

## Specification

### Architecture Overview
The Data Access Architecture consists of the following core components:
1. **Data Refinement**: A process for DLPs to transform raw data into a queryable, structured format
2. **Data Refiner Registry**: A smart contract that maintains refinement definitions and data schemas
3. **Query Engine**: A secure TEE-based system for executing queries against refined data
4. **Compute Engine**: A secure environment for running verified compute jobs that can interact with the Query Engine
5. **Permission and Payment Contracts**: Smart contracts for managing data access permissions and payments

### Data Refinement
Each DLP must implement a data refinement process (that runs during Proof of Contribution) which:
1. Maps raw data contributions to a standardized libSQL file format
2. Encrypts and uploads the refined data, and adds it to the Data Registry
3. Permissions the file with a DLP-specific public key so the Query Engine can index the data point
4. Sets pricing (negotiated between the buyer and DLP offchain) according to the amount of data accessed

As a prerequisite, DLPs must create a schema definition to which all of their data refinements adhere, and add it to the Data Refiner Registry.

### Data Refiner Registry
A new smart contract that maintains all refinement definitions, including:
1. An SQL-compatible schema that all refinements must adhere to
2. A URL to a publicly available refinement process that can be audited

### Query Engine
The Query Engine provides a secure environment for executing SQL queries against refined data. It can only be accessed from the Compute Engine and is not directly accessible. It is responsible for:
1. Indexing all refined data from all DLPs
2. Authenticating and validating onchain permissions before running a query
3. Executing queries within a TEE
4. Distributing and executing payments to DLPs for data access

DLPs can grant application builders fine-grained permissions onchain. The permission structure allows DLPs to specify table and column names, and price for data access, along with compute jobs that can be run on the result. 

### Compute Engine
The Compute Engine runs predefined jobs that can interact with the Query Engine:
1. Runs various compute jobs (ETL, AI model training, inference, RAG, etc) submitted by data accessors or application builders
2. Processes compute jobs asynchronously and stores results as artifacts
3. Runs in a secure compute environment (TEE) and includes support for GPUs
4. Has usage-based pricing to pay for compute

Application builders can define arbitrary compute jobs, that once audited and approved by a DLP, will execute that compute to interface with a DLP’s data. For example, an AI researcher can write a training job that runs on the DLP’s data, get approval from the DLP, and run the job to train their AI model. 

## Permissions and Payment Contracts

The Query Engine contract handles fine-grained permissions and defining pricing for data access. It allows a DLP to grant access to specific schemas, tables and columns to a specific user for a pre-negotiated price. 

Payments will be in $VANA. 20% of the data access fees will be distributed back to TEE stakers as yield and to TEE operators to cover operational costs. This ratio may be adjusted over time and may eventually involve a dynamic pricing mechanism. The remaining 80% will go to the DLP treasury in v0. Starting in v1, it'll be used to buy and burn DLP tokens. The 20% rate is deliberately set on the higher side initially, as it's preferable to start higher and reduce if needed, rather than starting too low and having to introduce unexpected increases later.

The Job Registry contract manages secure compute jobs and allows application builders to pay for compute. Here, an application builder can point DLPs to the compute they want to run on a DLP’s data, and the DLP can approve or deny the request. This allows a DLP to grant access to a builder to train an AI model or run an operation on the DLP’s data without the builder ever having to see the underlying data.

## Rationale 

### Design Decisions
1. **LibSQL format for refinements**: A modern fork of the popular SQLite format, provides a standardized queryable format that is lightweight and well-suited for SQL operations.
2. **IPFS for Refinement Storage**: 
   - Decentralized storage ensures availability and transparency
   - DLPs maintain IPFS pinning control for GDPR compliance (ability to stop pinning for right to be forgotten)
3. **TEEs for Query and Compute Engines**: 
   - Ensures secure execution in a trusted environment
   - Prevents unauthorized access to data and query results
   - Provides attestation to ensure code is unmodified
4. **Permission and Payment System**: 
   - Enables clear consent and control for data access
   - Creates sustainable economic incentives for the ecosystem
   - Allows granular permissions at schema, table, or column level

## Security & Privacy Considerations
The data access architecture prioritizes security and privacy through multiple safeguards. Security is maintained through trusted execution environments that protect against tampering. Smart contract permissions ensure only authorized access, and comprehensive encryption protecting data both at rest and in transit. Requiring payment for data access upfront discourages spamming and replay attacks. DLPs are kept in the loop for both permissioning their data and signing off on the compute that runs against their data.

## Implementation
### Phase 1 (First half of Epoch 6)
- Query and Compute engine supporting basic SQL queries
- Accept $VANA payment for data access only and a deterministic pricing model. 20% kept by the query engine treasury, 80% distributed back to the DLP treasury.
- Permission layer for DLP owners to approve data access and sign off on compute tasks
- Only new data from DLPs will be indexed by the Query Engine

### Phase 2 (Second half of Epoch 6)
- Payment flow encompassing usage-based compute and data access. All paid in $VANA, 20% kept by query engine treasury, 80% used to buy and burn DLP tokens.
- Migrate all DLP data collected before the refinement rollout, leveraging support from the ecosystem

### Requirements for DLPs
- Create a Dockerized refinement process that will be run during their proof-of-contribution
  - Optionally, remove or mask information they do not want accessed during refinement
- Add schema and refinement definitions to the Data Refiner Registry
- Manually approve data access permissions and set prices for data access
- Manually approve compute tasks that are allowed to run against a DLP’s dataset

## Copyright

Copyright and related rights waived via CC0.

