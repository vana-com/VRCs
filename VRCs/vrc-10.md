| VRC | Title | Status | Type | Author | Created |
|-----|--------|--------|------|---------|----------|
| VRC-10 | DLP Verification and Ecosystem Integrity Standards | Proposed | Technical | Art A, Anna K | 2025-01-21 |

## Abstract
This VRC aims to ensure DLP rewards are incentivizing high quality data coming into the ecosystem. It proposes giving the Vana Foundation the ability to de-verify Data Liquidity Pools (DLPs) that engage in behavior undermining the ecosystem, such as bot usage, Sybil attacks, or other malicious practices. These DLPs can still maintain registration on the network, but will not be eligible for DLP rewards. To maintain the integrity of data contributions, the Vana Foundation will also conduct Regular Monitoring and Data Audits, a systematic process to verify the quality and authenticity of data submitted by DLPs.

This policy ensures that the Vana Foundation upholds the highest standards of data quality, protecting the interests of all DLPs and the broader ecosystem while offering support to help DLPs address identified issues and return to compliance.

## Motivation
The strength of the Vana ecosystem depends on trust and transparency, especially as it scales to include diverse DLPs. Malicious behaviors like bot usage and Sybil attacks can compromise this trust, threatening both ecosystem fairness and the quality of data contributions.

The introduction of Data Audits is an essential step in ensuring that the Vana ecosystem is a trusted environment for data collection, enabling it to attract and maintain high-value datasets. At the same time, the Vana Foundation recognizes the importance of working collaboratively with DLPs to help them resolve issues and improve their practices.

## Specification
### De-Verification of DLPs
The Vana Foundation will have the authority to de-verify any DLP engaging in:
1. Bot Usage: Automated mechanisms designed to inflate metrics or manipulate contributions.
2. Sybil Attacks: Fake accounts or identities used to exploit staking, rewards, or voting processes. 
3. Other Malicious Practices: Fraudulent, deceptive, or harmful actions that undermine the ecosystem's integrity.

De-verification will result in the immediate removal of the DLP's eligibility for rewards and participation in the ecosystem. To the extent that misconduct results in inflated metrics, DLP rewards may be affected retroactively.

### Right of Response and Support
1. Notification: Affected DLP teams will be notified of the identified behavior and intent to de-verify.
2. Response Window: Teams will have 24 hours to provide a response or evidence to dispute the allegations.
3. Final Decision and Support: After reviewing the response, the Vana Foundation will make a final determination and communicate the outcome publicly.

If de-verification is confirmed, the Vana Foundation will work with the affected DLP to help them address the identified issues and re-qualify for the program as quickly as possible. This may include:
- Scrubbing and Cleaning Datasets: Assisting the DLP in identifying and filtering out the continued collection of bad data to improve data quality.
- Refining Proof of Contribution: Providing guidance on implementing or improving proof of contribution mechanisms to ensure robust and transparent verification processes.

The goal is to provide a clear pathway for the DLP to return to compliance and continue contributing to the ecosystem.

### Data Audits: Ensuring High-Quality Contributions
To safeguard data quality, the Vana Foundation will conduct randomized Data Audits on DLPs. The audit process includes the following steps:
1. Data Sampling: The Vana Foundation will randomly select a sample of data contributions (file IDs) for the DLP ID from the Vana Data Registry contract.
2. Decryption Request: The DLP will be sent these file IDs and asked to send the associated decryption keys for those files back to the Vana Foundation.
3. Data Examination: The Vana Foundation will examine the decrypted samples in a secure environment to assess their quality and authenticity.

The Data Audit process is critical to ensuring the ecosystem consistently attracts high-quality data contributions while preserving fairness and transparency.

### Monitoring Onchain Activity: Detecting Irregularities
The Vana Foundation will conduct Monitoring of onchain activity to detect and address potential irregularities or misuse of the rewards mechanism. This includes:
1. Transaction Monitoring: Analyzing onchain transaction data to identify patterns such as sudden spikes in unique contributor counts or unusual transaction volumes.
2. Behavioral Analysis: Identifying anomalies or suspicious patterns that may indicate fraudulent activities, such as artificially inflating contributor numbers.
3. Flagging Irregularities: Highlighting suspicious activity for further investigation and follow-up.

Through consistent monitoring, the Foundation ensures the ecosystem remains fair, transparent, and resilient against exploitation.

## Rationale
The ability to enforce data quality standards through de-verification and audits is essential to maintaining trust and transparency in the Vana ecosystem. By holding DLPs to high standards, the Vana Foundation ensures:
1. Ecosystem Integrity is Preserved: Malicious behavior is identified and addressed to protect the interests of all participants.
2. Trust and Quality are Prioritized: Data Audits ensure the ecosystem attracts high-quality data, strengthening its value proposition.
3. Fairness and Accountability: A transparent audit process reassures participants that the ecosystem is protected from exploitation.
4. Path to Improvement: By supporting DLPs in scrubbing datasets and refining proof of contribution, the Foundation ensures teams can learn from missteps and re-engage productively with the ecosystem.

## Security & Privacy Considerations
All Data Audits will be conducted with strict adherence to privacy standards. Decrypted data contributions will only be examined as part of the audit process and will not be retained beyond its conclusion. Transparency protocols will ensure that the audit process is fair, consistent, and publicly communicated when necessary.

## Implementation
Effective Immediately Upon Approval:
1. The Vana Foundation will establish procedures for identifying malicious behaviors and conducting Data Audits.
2. Affected teams will be notified and given 24 hours to respond before de-verification is finalized.
3. Audit findings will guide de-verification decisions and ensure quality standards are upheld.
4. If de-verification occurs, the Foundation will assist affected DLPs in scrubbing datasets, refining proof of contribution, and re-qualifying for DLP rewards.

## Copyright
Copyright and related rights waived via CC0.
