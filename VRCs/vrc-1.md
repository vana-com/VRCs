# VRC Purpose and Guidelines

| VRC | Title | Status | Type | Author | Created |
|-----|--------|--------|------|---------|----------|
| 1 | VRC Purpose and Guidelines | Final | Process | Anna Kazlauskas <annakaz@opendatalabs.xyz> | 2025-1-1 |

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
- Changes to Data Liquidity Pool rewards

**Process VRC** describes a process surrounding Vana or proposes a change to a process. This includes changes to the decision-making process, community guidelines, or the VRC process itself.

## VRC Work Flow

The VRC process follows these stages:

### Draft

The author submits the initial VRC as a pull request by forking the repo. The VRC should follow the standard template format and include sufficient technical detail for implementation.

### Proposed

During this stage, the VRC undergoes formal review. The author is responsible for gathering and integrating feedback to build consensus. The most relevant core contributors should be included in the review process. Review takes place through Github so that all comments are collected and documented. In this early stage, Vana Foundation and Open Data Labs are the only entities that can accept VRC proposals as core contributors.

### Final

The VRC has been accepted by core contributors and implemented. While it is not required that the proposal author write the implementation, it is an effective way to see a proposal through to completion: authors should not expect that other project developers will take on responsibility for implementing their accepted feature.

### Rejected

The proposal has been rejected by core contributors after review. This state has finality, though the core ideas may be reworked into a new VRC.

### Withdrawn

The author has withdrawn the proposal. This state has finality and cannot be reversed. If the idea is pursued at a later date it must be submitted as a new VRC.

## VRC Editors

VRC Editors are Vana Core Contributors who can accept and reject VRC proposals. This list will be expanded outside Open Data Labs and the Vana Foundation over time. Current VRC editors are:

- @anskaz
- @artvana
- @kahtaf
- @tnunamak
- @volod-vana
- @dumedco  
- @letonchanh
- @cactapode