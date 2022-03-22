---
rpip: 1
title: RPIP Purpose and Guidelines
status: Living
type: Meta
author: Mike Leach (@Wander) <mike@bamboofin.tech>
discussions-to: https://dao.rocketpool.net/t/rpip-1-formalizing-protocol-changes/367
created: 2022-03-17
---

## What is an RPIP?

RPIP stands for Rocket Pool Improvement Proposal. An RPIP is a design document providing information to the Rocket Pool community, or describing a new feature for Rocket Pool or its processes or environment. The RPIP should provide a concise technical specification of the feature and a rationale for the feature. The RPIP author is responsible for building consensus within the community and documenting dissenting opinions.

## RPIP Rationale

We intend RPIPs to be the primary mechanisms for proposing new features, for collecting community technical input on an issue, and for documenting the design decisions that have gone into Rocket Pool. Because the RPIP are maintained as text files in a versioned repository, their revision history is the historical record of the feature proposal.

## RPIP Types

There are three types of RPIP:

- A **Protocol RPIP** describes any change that affects the core Rocket Pool protocol as is currently defined via the smart contract implementations. Protocol RPIPs consist of two parts—a design document and an implementation. Furthermore, Protocol RPIPs can be broken down into the following categories:
    - **Core**: improvements relevant to core protocol design.
    - **RPRC**: application-level standards and conventions, including non-core contract standards similar such as Ethereum's token standards (EIP-20), etc.

- A **Meta RPIP** describes a process surrounding Rocket Pool or proposes a change to (or an event in) a process. Process RPIPs are like Core Protocol RPIPs but apply to areas other than the Rocket Pool protocol itself. They may propose an implementation, but not to Rocket Pool’s codebase; they often require community consensus. Examples include procedures, guidelines, changes to the decision-making process (i.e. governance).

- An **Informational RPIP** describes a Rocket Pool design issue, or provides general guidelines or information to the Rocket Pool community, but does not propose a new feature.

Note that there is no Type reserved for Smart Node changes. Improvements to the Smart Node are not part of the RPIP process and are best discussed via an Issue and/or PR on the rocket-pool/smartnode repository.

It is highly recommended that a single RPIP contain a single key proposal or new idea. The more focused the RPIP, the more successful it tends to be.

An RPIP must meet certain minimum criteria. It must be a clear and complete description of the proposed enhancement. The enhancement must represent a net improvement. The proposed implementation, if applicable, must be solid and must not complicate the protocol unduly.

## RPIP Work Flow

### Shepherding an RPIP

Parties involved in the process are you, the champion or RPIP author, the RPIP editors, and the Rocket Pool developers.

Before you begin writing a formal RPIP, you should vet your idea. Ask the Rocket Pool community first if an idea is original to avoid wasting time on something that will be rejected based on prior research. It is thus recommended to open a discussion on the Rocket Pool Discord server first, then progressing to a thread on the Rocket Pool Governance forum once the idea gains enough support to warrant more formal discussion.

Once the idea has been vetted, your next responsibility will be to present (by means of an RPIP) the idea to the reviewers and all interested parties, invite editors, developers, and the community to give feedback on the aforementioned channels. You should try and gauge whether the interest in your RPIP is commensurate with both the work involved in implementing it and how many parties will be affected by it. For example, the work required for implementing a Core RPIP will be much greater than for an RPRC and the RPIP will need sufficient interest from the Rocket Pool community and Core Developers. Negative community feedback will be taken into consideration and may prevent your RPIP from moving past the Draft stage.

### Core RPIPs

For Core RPIPs, given that they require smart contract implementations to be considered Final (see “RPIPs Process” below), you will need to provide an example implementation.

In short, your role as the champion is to write the RPIP using the style and format described below, shepherd the discussions in the appropriate forums, and build community consensus around the idea.

### RPIP Process

The following is the standardization process for all RPIPs in all tracks:

![RPIP Status Diagram](../assets/rpip-1/RPIP-process-update.jpg)

**Idea** - An idea that is pre-draft. This is not tracked within the RPIP Repository.

**Draft** - The first formally tracked stage of an RPIP in development. An RPIP is merged by an RPIP Editor into the RPIP repository when properly formatted.

**Review** - An RPIP Author marks an RPIP as ready for and requesting Peer Review.

**Last Call** - This is the final review window for an RPIP before moving to Final. An RPIP editor will assign Last Call status and set a review end date (last-call-deadline), typically 14 days later.

If this period results in necessary normative changes it will revert the RPIP to Review.

**Final** - This RPIP represents the final standard. A Final RPIP exists in a state of finality and should only be updated to correct errata and add non-normative clarifications.

**Stagnant** - Any RPIP in Draft or Review or Last Call if inactive for a period of 6 months or greater is moved to Stagnant. An RPIP may be resurrected from this state by Authors or RPIP Editors through moving it back to Draft or it’s earlier status. If not resurrected, a proposal may stay forever in this status.

    RPIP Authors are notified of any algorithmic change to the status of their RPIP

**Withdrawn** - The RPIP Author(s) have withdrawn the proposed RPIP. This state has finality and can no longer be resurrected using this RPIP number. If the idea is pursued at later date it is considered a new proposal.

**Living** - A special status for RPIP that are designed to be continually updated and not reach a state of finality. This includes most notably RPIP-1.

## What belongs in a successful RPIP?

Each Protocol RPIP should have the following parts:

- Preamble - RFC 822 style headers containing metadata about the RPIP, including the RPIP number, a short descriptive title (limited to a maximum of 44 characters), a description (limited to a maximum of 140 characters), and the author details. Irrespective of the category, the title and description should not include RPIP number. See below for details.
- Abstract - Abstract is a multi-sentence (short paragraph) technical summary. This should be a very terse and human-readable version of the specification section. Someone should be able to read only the abstract to get the gist of what this specification does.
- Motivation (*optional) - A motivation section is critical for RPIPs that want to change the Rocket Pool protocol. It should clearly explain why the existing protocol specification is inadequate to address the problem that the RPIP solves. RPIP submissions without sufficient motivation may be rejected outright.
- Specification - The technical specification should describe the syntax and semantics of any new feature.
- Rationale - The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages. The rationale may also provide evidence of consensus within the community, and should discuss important objections or concerns raised during discussion.
- Backwards Compatibility - All RPIPs that introduce backwards incompatibilities must include a section describing these incompatibilities and their severity. The RPIPs must explain how the author proposes to deal with these incompatibilities. RPIPs submissions without a sufficient backwards compatibility treatise may be rejected outright. Please keep in mind that, unlike Ethereum, previous Rocket Pool smart contracts always exist and therefore must be factored into the design of any new improvements.
- Reference Implementation - An optional section that contains a reference/example implementation that people can use to assist in understanding or implementing this specification.
- Security Considerations - All RPIPs must contain a section that discusses the security implications/considerations relevant to the proposed change. Include information that might be important for security discussions,
surfaces risks, and can be used throughout the life-cycle of the proposal. E.g. include security-relevant design decisions, concerns, important discussions, implementation-specific guidance and pitfalls, an outline of threats and risks and how they are being addressed. RPIP submissions missing the “Security Considerations” section will be rejected. An RPIP cannot proceed to status “Final” without a Security Considerations discussion deemed sufficient by the reviewers.
- Copyright Waiver - All RPIPs must be in the public domain. See the bottom of this RPIP for an example copyright waiver.

Meta and Informational RPIPs do not necessarily follow this format.

## RPIP Formats and Templates

RPIPs should be written in markdown format. There is a template to follow.

**RPIP Header Preamble**

Each RPIP must begin with an RFC 822 style header preamble, preceded and followed by three hyphens (---). This header is also termed “front matter” by Jekyll. The headers must appear in the following order.

`rpip`: RPIP number (this is determined by the RPIP editor)

`title`: The RPIP title is a few words, not a complete sentence

`description`: Description is one full (short) sentence

`author`: The list of the author’s or authors’ name(s) and/or username(s), or name(s) and email(s). Details are below.

`discussions-to`: The url pointing to the official discussion thread

`status`: Draft, Review, Last Call, Final, Stagnant, Withdrawn, Living

`last-call-deadline`: The date last call period ends on (Optional field, only needed when status is Last Call)

`type`: One of Core, Meta, or Informational

`category`: One of Protocol, Networking, Interface, or RPRC (Optional field, only needed for Standards Track RPIPs)

`created`: Date the RPIP was created on

`requires`: RPIP number(s) (Optional field)

`withdrawal-reason`: A sentence explaining why the RPIP was withdrawn. (Optional field, only needed when status is Withdrawn)

Headers that permit lists must separate elements with commas.

Headers requiring dates will always do so in the format of ISO 8601 (yyyy-mm-dd).

#### `author` header

The `author` header lists the names, email addresses or usernames of the authors/owners of the RPIP. Those who prefer anonymity may use a username only, or a first name and a username. The format of the `author` header value must be:

    Random J. User <address@dom.ain>

or

    Random J. User (@username)

if the email address or GitHub username is included, and

    Random J. User

if the email address is not given.

It is not possible to use both an email and a GitHub username at the same time. If important to include both, one could include their name twice, once with the GitHub username, and once with the email.

At least one author must use a GitHub username, in order to get notified on change requests and have the capability to approve or reject them.

#### `discussions-to` header

While an RPIP is a draft, a `discussions-to` header will indicate the URL where the RPIP is being discussed.

The preferred discussion URL is a topic on the Rocket Pool Governance Forum. The URL cannot point to Github pull requests, any URL which is ephemeral, and any URL which can get locked over time (i.e. Reddit topics).

#### `type` header

The `type` header specifies the type of RPIP: Standards Track, Meta, or Informational. If the track is Standards please include the subcategory (core, networking, interface, or RPRC).

#### `category` header

The `category` header specifies the RPIP’s category. This is required for standards-track RPIPs only.
created header

#### `created` header

The `created` header records the date that the RPIP was assigned a number. Both headers should be in yyyy-mm-dd format, e.g. 2001-08-14.

#### `requires` header

RPIPs may have a `requires` header, indicating the RPIP numbers that this RPIP depends on.

## Linking to External Resources

Links to external resources **SHOULD NOT** be included. External resources may disappear, move, or change unexpectedly.

## Linking to other RPIPs

References to other RPIPs should follow the format `RPIP-N` where `N` is the RPIP number you are referring to. Each RPIP that is referenced in an RPIP **MUST** be accompanied by a relative markdown link the first time it is referenced, and **MAY** be accompanied by a link on subsequent references. The link **MUST** always be done via relative paths so that the links work in this GitHub repository, forks of this repository, the main RPIPs site, mirrors of the main RPIP site, etc. For example, you would link to this RPIP with `[RPIP-1](/RPIP/rpip-1)`.

## Auxiliary Files

Images, diagrams and auxiliary files should be included in a subdirectory of the `assets` folder for that RPIP as follows: `assets/rpip-N` (where N is to be replaced with the RPIP number). When linking to an image in the RPIP, use relative links such as ../assets/rpip-1/image.png.

## Transferring RPIP Ownership

It occasionally becomes necessary to transfer ownership of RPIPs to a new champion. In general, we’d like to retain the original author as a co-author of the transferred RPIP, but that’s really up to the original author. A good reason to transfer ownership is because the original author no longer has the time or interest in updating it or following through with the RPIP process, or has fallen off the face of the ‘net (i.e. is unreachable or isn’t responding to email). A bad reason to transfer ownership is because you don’t agree with the direction of the RPIP. We try to build consensus around an RPIP, but if that’s not possible, you can always submit a competing RPIP.

If you are interested in assuming ownership of an RPIP, send a message asking to take over, addressed to both the original author and the RPIP editor. If the original author doesn’t respond to the email in a timely manner, the RPIP editor will make a unilateral decision (it’s not like such decisions can’t be reversed :)).

## RPIP Editors

The current RPIP editors are

    NEEDS DISCUSSION

## RPIP Editor Responsibilities

For each new RPIP that comes in, an editor does the following:

    Read the RPIP to check if it is ready: sound and complete. The ideas must make technical sense, even if they don’t seem likely to get to final status.
    The title should accurately describe the content.
    Check the RPIP for language (spelling, grammar, sentence structure, etc.), markup (GitHub flavored Markdown), code style

If the RPIP isn’t ready, the editor will send it back to the author for revision, with specific instructions.

Once the RPIP is ready for the repository, the RPIP editor will:

    Assign an RPIP number (generally the PR number, but the decision is with the editors)
    Merge the corresponding pull request
    Send a message back to the RPIP author with the next step.

Many RPIPs are written and maintained by developers with write access to the Rocket Pool codebase. The RPIP editors monitor RPIP changes, and correct any structure, grammar, spelling, or markup mistakes we see.

The editors don’t pass judgment on RPIPs. We merely do the administrative & editorial part.

## Style Guide

### RPIP numbers

When referring to an RPIP by number, it should be written in the hyphenated form RPIP-X where X is the RPIP’s assigned number.

### RFC 2119

RPIPs are encouraged to follow RFC 2119 for terminology and to insert the following at the beginning of the Specification section:

    The key words “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”, and “OPTIONAL” in this document are to be interpreted as described in RFC 2119.

## History

This document was derived heavily from Ethereum's EIP-1 written by [Martin Becze](mailto:mb@ethereum.org), [Hudson Jameson](mailto:hudson@ethereum.org), et al. which is in turn derived from Bitcoin’s BIP-0001 written by Amir Taaki which in turn was derived from Python’s PEP-0001. In many places text was simply copied and modified. Although the PEP-0001 text was written by Barry Warsaw, Jeremy Hylton, and David Goodger, they are not responsible for its use in the Rocket Pool Improvement Process, and should not be bothered with technical questions specific to Rocket Pool or the RPIP. Please direct all comments to the RPIP editors.

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
