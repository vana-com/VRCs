| VRC | Title | Status | Type | Author | Created |
|-----|--------|--------|------|---------|----------|
| VRC-15 | Data Access Architecture | Draft | Technical | Kahtaf, Anna | 2025-03-20 |

## **Abstract**

This VRC proposes the **Vana Data Access Architecture**, a secure framework for enabling application builders to query and use data from **Data Liquidity Pools (DLPs)** in a **privacy-preserving** manner. 

The architecture introduces:  
- A **data refinement process**  
- **Secure query execution** within **Trusted Execution Environments (TEEs)**  
- A **permission and payment system** for accessing data  

This ensures that data remains **private, secure, and accessible**, while creating a **sustainable economic model**, where **fees from data access** benefit:  
- Data contributors  
- DLP owners  
- The broader Vana ecosystem  

## Motivation

As the Vana ecosystem grows, there's an increasing need for applications to **programmatically access** and utilize the data collected by DLPs. However, this access must be balanced with strong **privacy protections, security measures, and economic incentives**.  

The current system lacks:  
- **A standardized way for applications to query data across multiple DLPs**, connecting cross-platform data by user.  
  - In particular, AI application builders who want access to data from multiple DLPs have expressed a need for this cross-DLP data access.  
- **A secure compute environment for data processing for any task run on data, including AI training jobs.**  
  - While this is supported in part by the Satya validators running proof of contribution and through other ecosystem collaborations, a standardized approach is needed for more general jobs like AI training that take place across DLPs.  
- **A unified permission and payment system for data access.**  
  - Currently, DLPs manually approve access to their data and may not use the same format, making it hard for self-serve data consumers to understand how to access data in the ecosystem.  

The Data Access Architecture addresses these needs by establishing a framework that enables **secure, privacy-preserving data access** alongside **payments** and **onchain permissions** for the data, ensuring attribution and sustainable economics. 
 
## Specification

### Architecture Overview

The Data Access Architecture consists of the following core components:
- **Data Refinement** – A process for DLPs to transform raw data into a queryable, structured format.  
- **Data Refiner Registry** – A smart contract that maintains refinement definitions and data schemas.  
- **Query Engine** – A secure TEE-based system for executing queries against refined data.  
- **Compute Engine** – A secure environment for running verified compute jobs that can interact with the Query Engine.  
- **Permission and Payment Contracts** – Smart contracts for managing data access permissions and payments.  

### Data Refinement

Each DLP must implement a data refinement process (that runs during Proof of Contribution), which:
- Maps raw data contributions to a standardized libSQL file format.  
- Encrypts and uploads the refined data and adds it to the Data Registry.  
- Permissions the file with a DLP-specific public key so the Query Engine can index the data point.  
- Sets pricing (negotiated between the buyer and DLP offchain) according to the amount of data accessed.  

As a prerequisite, DLPs must create a schema definition to which all of their data refinements adhere and add it to the Data Refiner Registry.  

### Data Refiner Registry

A new smart contract that maintains all refinement definitions, including:  
- An SQL-compatible schema that all refinements must adhere to.  
- A URL to a publicly available refinement process that can be audited.  

### Query Engine

The Query Engine provides a secure environment for executing SQL queries against refined data. It can only be accessed from the Compute Engine and is not directly accessible.  

#### Responsibilities:

- Indexing all refined data from all DLPs.  
- Authenticating and validating onchain permissions before running a query.  
- Executing queries within a TEE.  
- Distributing and executing payments to DLPs for data access.  

DLPs can grant application builders fine-grained permissions onchain. The permission structure allows DLPs to specify:  
- Table and column names.  
- Price for data access.  
- Compute jobs that can be run on the result.  

### Compute Engine

The Compute Engine runs predefined jobs that can interact with the Query Engine.

#### Capabilities:

- Runs various compute jobs (ETL, AI model training, inference, RAG, etc.) submitted by data accessors or application builders.  
- Processes compute jobs asynchronously and stores results as artifacts.  
- Runs in a secure compute environment (TEE) and includes support for GPUs.  
- Has usage-based pricing to pay for compute.  

Application builders can define arbitrary compute jobs that, once audited and approved by a DLP, will execute on a DLP’s data.  

For example, an AI researcher can write a training job that runs on the DLP’s data, get approval from the DLP, and run the job to train their AI model.  

### Permissions and Payment Contracts

The **Query Engine contract** handles fine-grained permissions and pricing for data access. It allows a DLP to grant access to specific schemas, tables, and columns to a specific user for a pre-negotiated price.
Initially, payment will be in **$VANA**, but eventually, it will support DLP-specific tokens.  

The **Job Registry contract** manages secure compute jobs and allows application builders to pay for compute. Here, an application builder can point DLPs to the compute they want to run on a DLP’s data, and the DLP can approve or deny the request.  

This allows a DLP to grant access to a builder to train an AI model or run an operation on the DLP’s data without the builder ever having to see the underlying data.  

## Rationale

### Design Decisions

- **LibSQL format for refinements**  
  - A modern fork of the popular SQLite format, providing a standardized queryable format that is lightweight and well-suited for SQL operations.  
- **IPFS for refinement storage**  
  - Decentralized storage ensures availability and transparency.  
  - DLPs maintain IPFS pinning control for GDPR compliance (ability to stop pinning for right to be forgotten).  
- **TEEs for Query and Compute Engines**  
  - Ensures secure execution in a trusted environment.  
  - Prevents unauthorized access to data and query results.  
  - Provides attestation to ensure code is unmodified.  
- **Permission and payment system**  
  - Enables clear consent and control for data access.  
  - Creates sustainable economic incentives for the ecosystem.  
  - Allows granular permissions at schema, table, or column level.  

## Security & Privacy Considerations

The **data access architecture** prioritizes **security and privacy** through multiple safeguards:
- **Security is maintained** through trusted execution environments that protect against tampering.  
- **Smart contract permissions** ensure only authorized access.  
- **Comprehensive encryption** protects data both at rest and in transit.  
- **Requiring payment for data access upfront** discourages spamming and replay attacks.  
- **DLPs remain in full control** of permissioning their data and approving compute tasks executed against their data.  

## Implementation Roadmap

### Phase 1 (First Half of Epoch 6)

- Query and Compute Engine supporting basic SQL queries.  
- Accept $VANA payments for data access only, with a deterministic pricing model.  
- Permission layer for DLP owners to approve data access and sign off on compute tasks.  
- Only new data from DLPs will be indexed by the Query Engine.  

### Phase 2 (Second Half of Epoch 6)

- Payment flow encompassing usage-based compute (paid in $VANA) and data access (paid in $VANA or DLP tokens once ready).  
- **Migrate all DLP data collected before the refinement rollout**, leveraging support from the ecosystem.  

## Requirements for DLPs

DLPs must:  
- **Create a Dockerized refinement process** that will be run during their proof-of-contribution.  
- **Optionally remove or mask sensitive information** before refinement.  
- **Add schema and refinement definitions** to the **Data Refiner Registry**.  
- **Manually approve**:  
  - Data access permissions.  
  - Prices for data access.  
  - Compute tasks that are allowed to run against a DLP’s dataset.  

## Copyright

Copyright and related rights waived via CC0. 



