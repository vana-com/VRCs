# VRC Purpose and Guidelines

| VRC | Title | Status | Type | Author | Created |
|-----|--------|--------|------|---------|----------|
| 1 | VRC Purpose and Guidelines | Active | Process | Anna Kazlauskas <annakaz@opendatalabs.xyz> | 2024-12-30 |

## What is a VRC?

A Vana Request for Comment (VRC) is a design document providing information to the Vana community or describing a new proposed feature for Vana, its processes, or environment. The VRC should detail the motivation, technical specification, rationale, implementation path, and impact evaluation of specific proposals impacting the Vana protocol.

VRCs are the primary mechanisms for proposing new features, collecting community input, and documenting design decisions for Vana. The VRC author is responsible for building consensus within the community and documenting supporting and dissenting opinions.

## Rationale

A VRC is intended to be reviewed by core engineering and community members keeping in mind security concerns, tradeoffs, and backwards compatibility. Having a proposal process helps identify design issues early, alert the community on a change, helps onboard newer contributors on the architecture, and acts as a historical record of the design decisions that have gone into Vana. For implementors, the VRC is a blueprint for the feature and helps track the development of a feature.

## VRC Types

There are two types of VRC:

**Technical VRC** describes any change that affects Vana implementations, such as:
- Changes to the protocol architecture
- Changes to data validation rules
- Changes to the Data Liquidity Pool specifications 
- Changes affecting how applications interact with Vana
- Proposals for new standard data schemas

**Process VRC** describes a process surrounding Vana or proposes a change to a process. This includes changes to the decision-making process, community guidelines, or the VRC process itself.

## VRC Workflow

The VRC process follows these steps:

### Idea

At the idea stage, parties involved in the proposal are you -- the VRC author, the Vana community and core contributors. Before you begin writing a formal VRC you should vet your idea. First conduct some research and ask the Vana community and core contributors if an idea is original to avoid wasting time on an idea that has a high chance of rejection. Ideas can be posed to discord to gather feedback before making your formal proposal.

### Draft

Write the VRC following the template format below and submit as a pull request by forking the repo.

### Review

During review, the author of the proposal is in charge of gathering and integrating feedback to build consensus on the proposal. The most relevant core contributors to the proposal should be included in the review process. Review will take place through Github so that all comments are collected and documented. Once consensus is met the proposal can either be accepted or withdrawn. This step will be taken when enough tradeoffs have been considered for the core contributors to make a decision. In this early stage, Vana Foundation and Open Data Labs are the only entities that can accept VRC proposals as core contributors. The current VRC process is being introduced to provide the Vana ecosystem with transparency and clarity on upcoming changes and will evolve over time.

### Accepted

Accepted proposals will be implemented by Vana core contributors as soon as circumstances warrant. While it is not required that the proposal author also write the implementation, it is an effective way to see a proposal through to completion: authors should not expect that other project developers will take on responsibility for implementing their accepted feature.

### Implemented

When all relevant teams have completed development of the VRC's feature, the VRC is "Implemented". A proposal will have the status "Activated" once it has been implemented, tested, and finally activated on mainnet.

### Withdrawn

The author can withdraw the proposal prior to implementation. This state has finality and can no longer be brought back. If the idea is pursued at a later date it is considered a new VRC proposal.

## VRC Editors

VRC Editors are Vana Core Contributors who can accept and reject VRC proposals. This list will be expanded outside Open Data Labs and the Vana Foundation over time. Current VRC editors are:

- @anskaz
- @dumedco  
- @kahtaf
- @tnunamak
- @volod-vana
- @letonchanh
- @cactapode
- @artvana