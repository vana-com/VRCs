# VRC-5: DLP Launch Readiness Standards

| VRC   | Title                            | Status | Type      | Authors              | Created    |
|-------|----------------------------------|--------|-----------|---------------------|------------|
| VRC-5 | DLP Launch Readiness Standards | Final  | Technical | Anna, Colin, Anatoly  | 2025-01-02 |


## Abstract

This VRC proposes launch readiness standards for Data Liquidity Pools (DLPs) to be eligible for DLP rewards. The goal is to make DLP best practices clear as the network scales with new DLPs being built across the ecosystem. The requirements establish baseline expectations around web presence, community engagement, data contribution activity, and data schema documentation. These requirements support the growth of Vana by providing clear readiness standards for DLPs and enabling future data portability features.

## Motivation

As the Vana ecosystem expands, builders from all across the world are creating DLPs for data sources they care about. While early DLPs could ask questions directly to some of the core contributors Open Data Labs and the Vana Foundation, the network's growth requires standardized guidelines so DLPs anywhere can launch successfully. 

These standards are designed to:
- Enable new DLPs to launch with clear guidance on requirements
- Foster active data contributor communities
- Create a foundation for network-wide data interoperability

## Specification

For a DLP to meet launch readiness standards, they must have: 

1. Data Infrastructure and Documentation
- Minimum of 100 unique wallet data contributions onchain
- Data schema documentation on the format of data collected
- Accurate documentation of the DLP's robust proof of contribution requirements, or a link to the proof of contribution implementation if using the TEEs

2. User Access and Community Engagement
- Data contributor UI for users to contribute data. This can be a website, chrome extension, CLI, or some other way for data contributors to contribute data. 
- Website (can be the same as the data contributor UI if that is a website)
- Active social media presence with regular updates
- Public communication channel (Twitter, Discord or Telegram)

3. VRC Compliance
- Must comply with VRC-20 (Data Asset Token)
- Must comply with VRC-15 (Data Access)
- Must implement any future VRCs marked as mandatory within the specified implementation timeline

DLPs must actively maintain these launch readiness standards beyond initial registration. If a DLP no longer meets these standards, they would not be eligible for DLP rewards. 

## Rationale

These requirements ensure DLPs are launch ready while maintaining flexibility for the diverse range of data sources DLPs are being built around:
1. Data Infrastructure and Documentation
- Provides a central hub for contributors and stakeholders
- Maintains data schema documentation for data access requesters
- Documents proof of contribution requirements for potential data access requesters. This requirement is particularly important for data consumers as it provides transparency into how DLPs verify contributions.


2. User Access and Community Engagement
- Social media presence ensures timely updates and direct communication with contributors
- The minimum of 100 data contributors demonstrates viability without excessive barriers, keeping in mind that some data sources may have a smaller number of data contributors with higher value individual data points.

## Security & Privacy Considerations

Public data schemas and proof of contribution documentation provide essential transparency while supporting network-wide interoperability. These benefits outweigh any potential risks from information disclosure about the DLP.

The proof of contribution requirements ensure data integrity by establishing clear standards for verifying the quality and uniqueness of contributions from the minimum 100 data contributors.

Accurate proof of contribution documentation is important alongside VRC-15, which introduces data access for data consumers. DLPs must maintain robust proof of contribution implementations consistent with their documentation to remain eligible for rewards under these launch readiness standards.

Compliance with all mandatory VRCs is crucial for maintaining network standardization. Each VRC plays a specific role in ensuring the network can function as a cohesive ecosystem while maintaining individual DLP flexibility.

## Implementation

To be implemented during Epoch 2 and take effect for end-of-epoch rewards distribution:

- DataHub interface will display DLP launch readiness status
- DLPs that do not meet launch readiness standards will not be eligible for rewards
- DLPs that do not comply with mandatory VRCs before Epoch 7 will not be eligible for rewards.

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
