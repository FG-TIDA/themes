# Candidate Themes — Sourced from the 1st Preparation Meeting (29 July 2026)

These six themes were raised as food for thought during the 1st Interregnum preparation meeting. They are starting points, not final scopes — several may merge, split, or be reframed as discussion continues ahead of the September call. Each should be opened as its own GitHub Issue using the Theme Proposal template so it can be discussed and refined independently.

---

## 1. Design-based Agent Identity

**Summary:** Study AI agent design and relationships; develop naming schemes that encode agent traits beyond flat URIs.

**Notes from discussion:** A participant suggested agents should first be classified by type, since identity requirements (uniqueness, persistence, local vs. global scope) will likely differ by agent — e.g. a smartphone-deployed agent may not need a persistent, globally unique identity.

---

## 2. Intent-based Security Policies

**Summary:** Explore how access control must evolve for agentic AI, including granularity and intent.

**Notes from discussion:** Xiaoya Yang (ITU TSB) raised a related semantic risk in task delegation — even when a delegation is properly authenticated and authorized, the receiving agent may not interpret the delegated task exactly as intended.

---

## 3. Remote Attestation for Agentic AI

**Summary:** Survey existing standards (IETF RATS, TCG, Global Platform) and assess what changes are needed to support agents.

---

## 4. Sovereign Discovery

**Summary:** Define requirements and governance for agent discovery mechanisms, considering multiple approaches (DNS, registries) and privacy concerns.

**Notes from discussion:**
- David Kelts (Decipher.ID) linked discovery to governance — who lists/delists an agent, and under what framework — and noted a registry is never fully neutral, since an operator's values become embedded in its rules.
- Isaac Henderson Johnson Jeyakumar (Fraunhofer IAO) noted the close relationship between discovery and the proposed work on policies/access rights, drawing on his team's "TRAIN" discovery/resolver work.
- Fabien Deboyser (NXP) suggested discovery alone isn't sufficient — it should be linked to an indication of trustworthiness.
- Artur Hecker (Huawei) cautioned that privacy is currently missing from IETF DAWN discovery ideas, and that a requester shouldn't have to expose its intent to the whole world; good use cases are still lacking.

---

## 5. Cross-border Trust Management for Digital ID

**Summary:** Address trust management for digital identities across jurisdictions, including governance.

**Notes from discussion:** Xiaoyuan Bai (Ant Group) proposed the cross-country passport-issuance model as an analogy, alongside blockchain as a possible technical avenue. Pam Dixon (World Privacy Forum) flagged the sensitivity of bringing G7 Hiroshima Process outcomes into standardization work, and the OECD Digital Trust Convention connection.

---

## 6. Agent Identity and Trust Stack

**Summary:** Develop a meta-model or layered framework encompassing identity, authentication, delegation, authorization, attestation, and discovery.

**Notes from discussion:** Sounil Yu (Vice-Chair) observed this theme touches all the others and could serve as a unifying meta-model, comparable to an OSI-style layered architecture.

---

## Cross-cutting notes (not tied to one theme)

- **Ethics and human rights:** Grace Rachmany (Decentralized Identity Foundation) called for a dedicated angle on ethics and human rights — cautioning that excessive identity controls can themselves cause harm (e.g. making it harder to protect vulnerable individuals). Arnaud Taddei (SG17 Chair) offered a "human-rights-by-design" methodology and connections to human-rights contacts in Geneva.
- **Legal personhood / delegation:** Bo Fjelkner (Ericsson) raised the legal dimension — when an agent is delegated by a human, a stricter notion of identity may be needed, possibly as part of the identifier itself. Related: a line of thought treating AI agents as a new form of legal person (similar to a limited company), with registration requirements.
- **Real-world grounding:** Sounil Yu (Knostic) referenced the Hugging Face incident and CISO post-mortem as a concrete test case for whether an attacking agent would ever identify itself.
- **Governance as umbrella concept:** Suggested that governance be treated as the broader concept, with privacy as a core subset alongside other governance items.
