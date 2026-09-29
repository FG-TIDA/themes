# Verifier-side requirements for agentic-AI trust and identity in regulated workflows — Charter

**Status:** Draft
**Originating issue:** #27
**Proposer(s) / drafter(s):** Xinghua Zhao (independent expert)

## Summary

Agentic-AI trust work is currently framed mainly from the producer side: how an agent proves its identity, how its runtime is attested, how a delegation is issued. The consumption side is thinner — what a relying party MUST check before it acts on such a proof, what "verification passed" is allowed to mean, and what must happen when a check fails. This theme develops the verifier-side requirements for consequential actions in regulated workflows, where a wrong "pass" cannot be undone. Medical-device compliance is used as the anchor case because it combines a regulated regime, an irreversible downstream decision, and a cross-jurisdiction dimension.

## Scope

- **Verifier obligations as individually testable checks** — expressed as distinct checks carrying explicit rule codes, rather than a single verdict, each evaluable offline from the record alone.
- **Failure semantics** — what a negative outcome MUST mean, how "checked and failed" is kept distinguishable from "not checked", and the treatment of a verifier that reports success while checking nothing.
- **Evidence artefacts** — the minimal verifiable-evidence bar for a trust claim: what a record must carry so a third party can recompute the appraisal without trusting the generator.
- **Cross-jurisdiction reuse** — whether, and under what conditions, a verdict obtained under one regime can be reused, re-interpreted, or refused under another, with healthcare as the anchor domain.
- **Regulated-deployment constraint** — whether deployability under regulatory constraint should be an evaluation dimension when comparing trust architectures.

## Out of Scope

- **Agentic-AI protocols and transport.** Message formats, discovery transports, and agent-to-agent protocol design are handled elsewhere.
- **AI governance frameworks.** Organisational governance, accountability regimes, and policy instruments are out of scope, except where they are the source of a verifier-side requirement.
- **Digital ID and credential formats.** Identifier and credential syntax (W3C DID/VC, X.509, and national identity-code specifications) is out of scope; this theme addresses the layer that verifies claims, not the layer that encodes them.
- **Reference-implementation advocacy.** The theme does not promote a particular implementation; any artefact cited is offered as material for discussion.

## Objectives / Deliverables

- A structured set of **verifier-side requirements** with normative failure semantics, at a granularity that can be tested individually.
- A **minimum evidence profile** describing what a record must carry for an appraisal to be recomputable by a third party.
- **Candidate cross-jurisdiction reuse conditions** for a verdict, anchored on the healthcare/medical-device case.
- Input to the Terms of Reference **Annex A** deliverables on the agentic-AI identity stack, on cross-jurisdiction interoperability (which explicitly names healthcare), and on trust lifecycle management — offered in support of those deliverables, not as additional work items.

## Related Work

- **IETF RATS** — attestation consumption and appraisal; this theme addresses the relying-party obligations that sit on top of it.
- **Sigstore / Rekor**, **Software Heritage** — transparency-log and archival anchors used as publicly resolvable evidence in the examples below.
- **NIST AI RMF**, **EU MDR / AI Act conformity regimes** — control objectives and regulated-domain constraints that motivate the requirements.
- **uibc-core** — an evidence-package reference implementation: DOI `10.5281/zenodo.22821834`, with a Sigstore Rekor transparency-log entry and a Software Heritage SWHID, so an appraisal can be recomputed from the record alone.
- **agent-trust-identity-spec** — 4 stages x 20 minimum verifiable requirements with 20 rule codes (groups `REG-` / `AUT-` / `CVF-` / `AUD-`), offered as material for discussion rather than as a proposed framework.
- **silent-failure-catalog** — documented failure semantics of "verification passed" states in which a check reports success while checking nothing.

## Related Themes

- **#7 — verifier-side requirements and failure semantics for agent evidence**: this theme is the same gap stated as a charter; the negative conformance vectors proposed there are the natural test companion to the verifier obligations here.
- **#22 — Remote Attestation for Agentic AI (RA-AAI)**: this theme addresses the *consumer* side of attestation — the relying party's obligations — and connects to the WG1 outline, where chapter 04 (the three fundamental questions) is argued from the consuming position.
- **#6 — Intent-based Security Policies**: policy evaluation is a producer-side mechanism; the verifier-side question is what a relying party checks about the evaluation that was carried out.
- Maps onto the Terms of Reference **Annex A** deliverables on the agentic-AI identity stack, on cross-jurisdiction interoperability, and onto the **health** anchor use case.
- Connects to the 29 July candidate themes **Cross-border Trust Management for Digital ID** and **Agent Identity and Trust Stack**.

## Open Questions

1. What is the **minimal verifiable-evidence bar** for a trust claim in FG-TIDA deliverables — transparency-log entries, cryptographic timestamping, reproducible archives, or a combination?
2. Should "PASS" mean that a check ran and found no violation **within a stated evidence boundary**, or something stronger — and where is that boundary recorded?
3. How should **failure classes be kept distinguishable** across implementations, so that interoperability does not break because one implementation rejects and another logs and proceeds?
4. Should **cross-jurisdiction reuse conditions** be expressed so that a verdict obtained under one regime can be re-used, understood, or refused under another?
5. Should **deployability under regulatory constraint** be an evaluation dimension when comparing trust architectures?
