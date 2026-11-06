# Agentic AI Trust Control Plane — Charter

**Status:** Draft
**Originating issue:** #59 (seed theme #18)
**Proposer(s) / drafter(s):** Laurent Beaumois (MeetLoyd), proposed convener. Pam Dixon (World Privacy Forum), proposed co-chair, subject to the Focus Group accepting the group. Each workstream keeps its own pen. Arnaud Taddei (seed theme #18) contributes.

## Summary

ToR clause A.2.7 calls for "a reference architecture for the agentic AI trust control plane". This covers:

- technical-policy decision points and technical-policy enforcement points;
- "trust signal propagation across agent hierarchies";
- "the coordination mechanisms required to maintain consistent trust state in distributed and multi-agent environments".

WG2 addresses the per-action side: one action, checked at the moment it is taken against a pinned, authored reference. In networking terms that is the data plane of trust. This charter covers the control plane, in four parts:

- where the references those checks rely on come from;
- how they are declared and graded;
- how the record of them is kept consistent wherever an act consults it;
- what happens to acts already under way when that record changes.

The group works as a set of workstreams under one common reference architecture. Each workstream names its object, the thing being governed, in its first line, so that the architecture is drawn around objects rather than functions. Each is carried by those who already carry its theme, and existing drafts are adopted as they stand.

## Scope

**1. Reference architecture (A.2.7).**

- The objects of the control plane:
  - the grant of authority and its record;
  - the declared operator;
  - the evidence that references rely on;
  - the requirements arising from governance;
  - the record as consulted at act time.
- The functions that author, grade and keep them current.
- The demarcation with WG2, and the interfaces with WG1, #1, #13 and #16.
- The diagrams already drawn for the #18 / #36 picture are the starting point.

**2. Clusters of agents.** Two positions are on the record, and the architecture keeps both explicit:

- On #18, the cluster is proposed as the domain over which a collective-choice operator is declared, with the tentative rule of one human principal per cluster.
- On #9, the accountable principal sits with the mandate, not the cluster: "A cluster composes mandates; a cluster itself authors none". Determinations are made per link and then composed. Any merge of per-mandate evidence into a cluster-level assertion is itself an authored decision.

The architecture states what a cluster is for control purposes and where accountability sits. To be developed with the proposers of #5 and #18.

**3. Workstreams.**

- **A. Provenance of authority (#5).** *Object: the grant of authority: its origination, standing, content and composition.*
  - The #15 draft charter is adopted as it stands, with its own pen, as a named deliverable of the group.
  - Use cases: FG-TIDA/use-cases#9, #10 and #46.
  - Enforcement of revocation remains outside this workstream, as its charter states. Workstream E consumes the record that #5 defines.
  - Clause mapping: A.2.7, and A.2.5 for the two-regime case in use-cases#46, alongside #41.
- **B. Declared operators and drift (#18).** *Object: the collective-choice operator a system declares, with its regime, mode and transition conditions.*
  - Internal assessment: the operator catalogue and its declaration.
  - External evaluation: drift measured against the declaration.
  - Regulatory alignment: the regulatory bridge, worked against at least two frameworks, one of them non-European.
  - Results feed back into XSTR.magAI-behavior. The catalogue material from #18 stays here.
- **C. Evidence quality and authorization validity (#42).** *Object: the evidence a reference relies on, and its grade.*
  - Two axes, kept separate in every deliverable: the quality of the evidence on one, the validity of the authorization on the other. "Evidence absent" and "evidence found wrong" are different failures with different remediations, and are never merged.
  - The grading vocabulary itself is a deliverable of this workstream, assessed against existing proposals rather than fixed by this charter.
  - The control plane holds the reference: the required evidence, the minimum grade, and the policy reference it resolves from.
  - The per-action gate verdict stays with WG2. #43 remains WG2's interface.
- **D. Technical requirements arising from governance (#41)** [if its proposers wish, at a later stage]. *Object: the technical requirements that governance places on trust and identity mechanisms.*
  - As reframed on #41: technical requirements arising from governance, and governance implications of technical trust and identity choices, anchored in A.2.1, A.2.4 and A.2.5.
- **E. Act-time consultation and run-time consistency (new).** *Object: the availability and consistency of the record of authority and of decided changes (revocation, intervention, mode change) where acts consult it, and the copies of it held there. Workstream A specifies the record's content and how it changes; this workstream specifies its availability where it is consulted; WG2 specifies what the decision does with what it read.*
  - Whether each act consulted the record, and evidence of that, independent of the component that acknowledged the change.
  - How stale a copy of the record may be; what an act does when it cannot reach the record; how two copies that disagree are detected; observe-before-enforce transitions.
  - Acts already under way when the record changes: long-running acts, and acts of delegated workers fanned out from one agent.
  - Re-evaluation when new evidence arrives for the same subject or when the version of a policy reference changes. This covers the non-monotonic case raised on #33.
  - Time to effect, measured as whether and when the next act stopped, not as time to acknowledgement.
  - A common intervention interface that agent platforms could honour.
  - A vocabulary of coverage levels, so that a party does not represent as governed an agent it only observes.

**4. Shared fixtures.** Versioned act-time consultation, re-evaluation and intervention cases with expected outcomes and negative controls.

- They are aligned with TIDA6-FX and usable on the UC-4 testbed.
- They include the kill-switch conformance drill proposed on #13, run on the live case in use-cases#46: revoke the conferral between two acts, and measure whether the next act proceeded.

## Out of Scope

- The verdict on a single action, delegation treated as a series of per-action decisions, and #43's evidence-graded verdicts: WG2.
- Remote attestation mechanisms (attestation results are inputs here): WG1.
- Records and reconstruction after the act: #1.
- The human decision to hold, intervene or resume, oversight semantics, and release of escalated actions: #16.
- Signals, corroboration and response coordination across organisations, the cross-party blast-radius graph, and the kill-switch specification itself: #13.
- Trust at component interfaces and in the execution sandbox: #53, #54.
- Whether a connection between parties should exist and remain in force: #29 (interface to be agreed).
- Design-time method for choosing operators: ITU-T SG17 Q1/17 (X.dmst).
- Encodings, schemas, wire formats and protocols.
- AI governance as such, and mapping or assessing national regimes, which the ToR excludes.
- Ranking, certifying or recommending products.

Themes not listed as workstreams do not move into this group; interfaces with them are drawn with their proposers.

## Objectives / Deliverables

| # | Deliverable | Pen |
|---|---|---|
| D1 | Agentic AI trust control plane: problem statement and reference architecture, drawn around its objects, including the WG2 demarcation and the treatment of clusters (Technical Report) | Convener and co-chair, with the demarcation agreed with WG2 |
| D2 | Provenance of authority: deliverables D1–D5 of the #15 draft charter, unchanged, with use-cases#9, #10 and #46 | #5 proposer |
| D3 | Declared operators and drift: internal assessment, external evaluation, regulatory alignment (Technical Report) | Editors from #18 contributors |
| D4 | Evidence quality and authorization validity: requirements, with the two axes separate (Technical Specification) | #42 proposer |
| D5 | Act-time consultation and run-time consistency of the record: requirements (Technical Specification) | Convener |
| D6 | Technical requirements arising from governance (Technical Report) [if #41 joins, later] | #41 proposers |
| D7 | Control-plane fixtures, including drill results on use-cases#46 under the #13 conformance drill (Technical Report with a versioned fixture set) | Convener, with UC-4 |

Milestones, aligned with the FG calendar:

- **Paris:** charter presented, with the workstreams that have joined (#5, #42) and those still open (#41), and a D1 outline.
- **Geneva:** a first draft of D1, a D5 outline and fixtures v0.1.
- **Later meetings:** remaining deliverables on the schedules their workstreams set.

## Related Work

- ToR Annex A: A.2.7; A.2.5 for Workstreams A and D; A.2.1 and A.2.4 for Workstream D.
- ITU-T SG17: XSTR.magAI-behavior (Q16/17) and X.dmst (Q1/17), complemented without duplication.
- IETF: RATS (RFC 9334), WIMSE, OAuth 2.0 Token Exchange (RFC 8693).
- OpenID Shared Signals Framework (SSF / CAEP), for carrying security events between parties.
- W3C Verifiable Credentials and PROV-O, as candidate carriage and provenance vocabularies.
- Partial observability in supervisory control (Lin and Wonham), as raised on #9, for what evidence must survive aggregation.

## Related Themes

- **WG2 (#4, #6, #36):** this group owns how trust state is established, distributed and changed; WG2 owns the decision at the moment of a single action. The interface is the set of inputs the enforcement point reads at decision time, listed by object in a joint issue held by both groups (#60). WG2 returns verdicts (notably escalate and indeterminate) that may trigger a control-plane change.
  - #26 is an enforcement-point input.
  - The paired fixture proposed in WG2, for a grant revoked before a queued action is retried, checks the consultation at retry. This group supplies how current the consulted record was.
  - Demarcation is to be agreed.
- **#5, #9:** provenance of authority, and authority never crisply authored. Workstream A.
- **#18:** seed theme; Workstream B.
- **#42, #43, #33:** evidence grading (Workstream C), evidence-graded verdicts (WG2's interface), and late evidence (Workstream E).
- **#41:** Workstream D if joined.
- **#1:** records what the control plane changed and when.
- **#13:** its signals are inputs here; this group produces evidence of the effect of an intervention, which #13 can read back.
- **#16:** decides on hold, intervention and resumption; this group evidences whether the next act honoured the decision.
- **#10, #21, #23, #29, #50, #53, #54:** interfaces to be drawn with their proposers.

## Open Questions

- **The line between Workstreams A and E** (co-chairs). Where the record of authority ends and its consultation at act time begins, including for acts already under way when the record changes.
- **The WG2 interface** (@cgorlla, @arturhecker). Worked in the joint issue (#60): the inputs the enforcement point reads at decision time, by object, with the workstream or group that specifies each and those that consume it.
- **The common mental model** (@sounilyu). How does this group sit in the overall FG-TIDA picture, and in the layered model of the agent identity and trust stack?
- **Clusters** (@pdixon-wpf, @taddhar). What is a cluster for control purposes, and where does accountability sit when the operator is declared per cluster but authority is conferred per mandate?
- **#41.** A workstream here, or a group of its own with a defined interface? That is for its proposers to say.
- **#23 and #29.** Do they belong here, or at an interface?
- **The common intervention interface.** What is the smallest one agent platforms could honour?
