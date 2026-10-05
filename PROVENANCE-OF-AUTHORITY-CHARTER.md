


# Provenance of Authority for Agentic AI — Charter

**Status:** Draft **Originating issue:** #5 **Proposer(s) / drafter(s):** Pam Dixon, World Privacy Forum

## Summary

Every agentic action stands on a claim of authority: that one or more parties conferred the capacity to act, that the conferral was within what those parties could confer, and that the chain from that conferral to the acting agent can be examined by a party who was not there. The themes currently open specify how authority is represented, verified, attested, discovered, enforced, and bound — with each of these operations presupposing that the authority exists. None examines where it originates, what may never be conferred, or how it traces to a human principal. That is the layer this charter specifies.

The failure this layer exists to prevent has a precise shape. It is invisible to conformance checking of every kind. If the principal at the root of a delegation chain is bound to a corrupted identity record, everything that can be checked is correct. Each link verifies, the mandate travels intact, limits survive composition, revocation propagates as specified, and behavior conforms to the authored intent. Everything is correct except the root, and the root is the one thing no layer evaluates. The shape of this failure is not particular to biometrics. The same failure occurs wherever a durable anchor is bound to a mutable record, which would include an agent credential or an attestation bound to a rewritten operator record. Its record-side twin, silent normalisation — a reference manufactured because a format expects one — has been fixed in sub-theme #9; its origination-side twin is a grant presumed because an artifact carries one. Both are prevented only if the origination layer is specified in its own right.

## Scope

This charter uses the following working definitions, to be formalized in Deliverable 1 (D1).

**Authority.** The capacity to act. Authority is possessed or granted. A principal possesses authority — a human within their own capacity, or an institution of humans under law, mandate, or charter; a grant confers a bounded portion of it on another party or agent. A conferral is a **grant**; the party conferring is the **grantor**; the party or agent receiving is the **grantee**. Chains of delegation terminate in possessed authority.

**Origination.** The authoring of a grant: by whom, with what standing, of what, within what the grantor could confer, in what form, and when.

**Provenance.** The examinable history of a grant from origination through every composition, constraint, and revocation applied to it. Origination is where the chain begins; provenance is the state of the chain when the agent acts.

**Standing of authority.** Whether a grant was authored at all, by a party with standing to confer it — a human, organization, or public authority within what it possesses or has itself been granted — and within what that party could confer. Standing is a property of the grant's origination, not of any downstream representation of it: an artifact that carries a grant does not establish that the grant has standing.  Standing admits two determinations of this one property, made at two moments: at origination, whether the grantor could and did confer; at act time, whether the grant continues to bind. Both are made under the legal regime governing the mandate — which fixes at what moment standing may change, and with what continuing effect — and neither is established by a downstream artifact.


**Anchor integrity.** The binding between a durable anchor and the mutable records attached to it, examined for whether the binding itself has been rewritten.

The theme specifies five elements. Deliverables map to them one-to-one.

**1. Origination.** What constitutes a grant of authority. Three questions sit here. First, which humans, organizations, or public authorities have standing to grant authority to an agent. Second, what distinguishes possessing authority from having been granted it. Third, what distinguishes the authored from the observed: what a party actually conferred, versus what an agent was observed to receive. This element includes the never-crisply-authored case as jointly developed in sub-theme #9.

**2. Provenance as a property.** The content of a grant — mandate, scope, limits, revision conditions, and a contestation route — carried as data that travels with the delegation, rather than as policy held at any single operator's perimeter, and evaluable at act time by a party with no relationship to the producer. Includes carriage requirements for three cases fixed on the record: (a) an assertion of absence is a scoped observation of a search — what was examined, over what period, as of when — with an author, and carries provenance like any claim a record holds; (b) a record identifying the party from whom an agent received input identifies an observed source, not a grantor, unless a grant is separately established; (c) authority authored after an act enters the chain as a new record — it does not amend the observation of what preceded it. Whether a candidate format can carry these requirements is decidable from the requirements as written, assessed relative to the legal regime governing the mandate — which factually determines what could and could not be conferred, at what moment standing may change, and with what continuing effect; the assessment records what the format can express about those determinations, not what they are.

**3. The non-conferrable floor.** What cannot be conferred: whether there are categories of authority no principal can delegate to an agent, and how a specification expresses that floor rather than leaving it to each deployment. The floor is determined in law and policy by institutions with standing to determine it; the specification expresses that determination, it does not author it.

**4. Anchor integrity.** Requirements for detecting and asserting rewrites of the anchor-to-record binding, including hardened identity theft and its agentic analogues.

**5. Composition and revocation.** Survival under composition: what happens to provenance when agents re-delegate, compose at runtime into configurations no single party holds, or re-advertise capabilities several hops from the originating principal; how authority traces to a human principal; and what revocation does to a chain that has already composed. Semantics only; enforcement of revocation at runtime or in infrastructure is consumed by other themes. Within those semantics, expiry and revocation act on the second determination of standing: they end or narrow what a grant continues to bind, from the moment the governing regime fixes, and they do not amend origination, which remains in the chain as history. Where the chain has already composed, the change enters each affected grant's provenance as a new record, per scope element 2 — the grant originated then, and does not bind now, and the record shows both.

## Out of Scope

The boundary of this theme sits at the failure shape, not at the identity substrate. A biometric bound to improperly rewritten demographic data and an agent that is credential-bound to a rewritten operator record are the same failure; to be clear, I use the biometric case because it is the best-documented instance available, not because human identity systems are a second domain attached to this one. This theme does not attach human identity systems as a domain. Agent authority origination reaches human anchoring by necessity rather than design: agents trace to principals, principals are humans or institutions of humans, and an origination layer that stops at the agent's edge has assumed away the thing it was chartered to establish. Where mature identity-assurance work already exists for the human side, this theme references it rather than reproduces it.

So - reaffirming two key items, one in scope, one out of scope:

A.) The origination and anchoring of authority, wherever a durable anchor meets a mutable record in an agentic chain — this is in scope.

B.) The internal machinery of established human identity-assurance frameworks — this is out of scope. It is referenced, not reproduced: D4 draws on existing identity-assurance standards and evaluation work, as noted in Related Work.

Beyond this boundary, the following are explicitly out of scope, especially where they overlap with another theme:

- Runtime verification and conformance verdicts (theme #6). Verdicts are carried by the origination and provenance layer this charter specifies, as claims with provenance; they are not required by it.
- Records and reconstruction (theme #1). The relation between themes #1 and #5 is mutual, not sequential: provenance determines what a record can truthfully say about authority; the record's own properties determine whether it survives a party who was not there.
- The "never-crisply-authored" case is jointly held in sub-theme #9 with #1 and #6, and this charter mirrors its non-goals: theme #5 is not a protocol specification, and it is not a liability framework.
- Governance, enforcement, monitoring, and lifecycle management of agents, including network-level enforcement. These consume the origination layer; they are specified elsewhere.
- Remote attestation; discovery.
- Binding and mandate artifact formats, and the apportionment of responsibility along an agent-to-principal chain. Artifacts reference authored grants; whether a grant exists, and its standing, are prior and live here. Apportionment is a liability question and out of scope.
- Protocol specification; liability frameworks.

## Objectives / Deliverables

**D1 — Terminology and definitions.** Formal definitions for the terms noted in the scope, developed with legal-definitional rigor so that the definitions hold in law and policy as well as in technical formats.

**D2 — Provenance carriage requirements and formats.** Requirements for a grant to carry its content and provenance with it, evaluable at act time by a party with no relationship to the producer, including the three requirements fixed in scope element 2: assertions of absence, source-role marking, and authority authored after the act.

**D3 — The non-conferrable floor.** A specification expressing the floor — the categories of authority no principal can delegate to an agent — as determined in law and policy by institutions with standing to determine it.

**D4 — Anchor-integrity requirements.** Requirements for asserting and detecting binding rewrites.

**D5 — Composition and revocation semantics.**

These deliverables are authored as the origination layer of the trust ecosystem as discussed in scoping. The deliverables D1–D5 are consumed, not duplicated, by the other open themes: verification verdicts evaluate conformance to grants this layer defines; records carry what this layer defines for carriage; governance and enforcement themes constrain, monitor, and revoke within lifecycles whose origination this layer specifies; binding and mandate artifacts reference grants whose standing this layer establishes. Within the layered model proposed as candidate theme 6, this layer sits at the foundation. Initial D1 text will be circulated before the 4 November call, depending on necessity as determined by community input.

## Related Work

Published testimony of the proposer to the Council of Europe's inaugural meeting of the Committee on New and Emerging Technologies (worldprivacyforum.org/posts/remarks-of-pam-dixon-to-the-council-of-europes-inaugural-meeting-of-the-committee-on-new-and-emerging-technologies/), as anchored in Issue #5. A DOI for the forthcoming research underlying this theme will be added when published, as noted in the issue thread.

Existing identity-assurance standards and evaluation work are referenced by D4, not reproduced. Legal doctrine on agency and mandate, across jurisdictions, is coordination ground for D1.

## Related Themes

Relations are stated in the terms this repository uses — depends on, feeds into, consumed by. Numbered references of the form #N are issues in this repository; themes from the 29 July preparation list are cited as "candidate theme N." No relation below is an overlap.

- **#1 (records and reconstruction):** mutual dependency, fixed on the record in both directions.
- **#6 (intent-based policies and runtime verification):** a fixed seam — evaluation against intent is verification and lives there; whether a grant exists at all is prior and lives here. Verdicts feed into this layer as carried claims.
- **Sub-theme #9 (jointly with #1 and #6):** the never-crisply-authored case, in motion ahead of the September call; its agreed ground is incorporated in scope elements 1 and 2.
- **Governance and enforcement themes (#3, #4, #10):** depend on this layer through the record; they consume origination, and are fed by D1–D5.
- **Mechanism themes (#11, #12, #13), attestation inputs (#7), discovery (#2), and cross-border trust management (#8, corresponding to candidate theme 5):** consume the origination layer.
- **Binding themes (#14):** binding artifacts reference grants whose standing this layer establishes; the legal personhood / delegation cross-cutting note from the 29 July preparation meeting is adjacent to D1's coordination ground.
- **Candidate theme 6 (agent identity and trust stack):** within that model's layering, this theme is the foundation.

## Open Questions

Two of this theme's original open questions have since been resolved on the record: the never-crisply-authored case is under active joint development as sub-theme #9, with its resolution to be incorporated into scope elements 1 and 2 as it stabilizes; and the boundary between the technical carriage of provenance and the questions of law and policy that carriage makes answerable has been fixed in the seam with #6, as carried in Out of Scope and Related Themes. The questions that remain open:

- What a relying party actually evaluates: the agent, or the conformance of the operating authority structure to the authored one.
- Where the gates sit — at assignment, at composition, at re-advertisement (D5 coordination).
- How revocation propagates through a chain that has already composed (D5).
- Which existing credential and mandate formats can carry a grant's content and provenance, and which require extension (D2).
- Where the boundary between D4's anchor-integrity requirements and existing identity-assurance evaluation work sits, so that D4 references rather than reproduces it.
- How standing of authority relates to legal doctrines of agency and mandate across jurisdictions (D1 coordination).
