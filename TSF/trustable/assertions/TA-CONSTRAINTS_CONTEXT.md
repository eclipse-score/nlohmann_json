---
level: 1.1
normative: false
---

(Note: The guidance, evidence, confidence scoring and checklist sections below are copied from [CodeThink's documentation of TSF](https://pages.eclipse.dev/eclipse/tsf/tsf/trustable/TA.html). However, the answers to each point in the evidence list and checklist are specific to this project.)

**Guidance**

Constraints on reuse, reconfiguration, modification, and deployment are
specified to enhance the trustability of outputs. To ensure clarity, boundaries
on what the output cannot do - especially where common domain assumptions may
not hold - must be explicitly documented. These constraints are distinct from
misbehaviour mitigations; instead, they define the context within which the
system is designed to operate, including all modes and environmental
considerations. This upfront documentation clarifies intended use, highlights
known limitations, and prevents misinterpretation.

These constraints, categorised into explicit limitations and assumptions of use,
guide both stakeholders and users (integrators, maintainers, operators, and
end-users). They define the intended scope and provide a clear interface for how
upstream and downstream systems can integrate, modify, install, reuse, or
reconfigure to achieve the desired output. The documentation must also specify
the contexts in which the integrity of existing Statements is preserved and
whether reimplementation is required, considering device maintenance
assumptions, including software updates and vulnerability mitigation.

Crucially, these limitations are not unresolved defects from triage decisions
but deliberate exclusions based on design choices. Each omission should be
supported by a clear rationale (linked to relevant Expectations and analyses 
with the appropriate architectural and abstraction levels) to ensure
transparency for future scope expansion and to guide both upstream and
downstream modifications.

To remain effective in practice, constraints must consider user-friendliness in
relation to associated Misbehaviours (TA-MISBEHAVIOURS) and AWIs
(TA-INDICATORS):

- Include mechanisms to prevent misuse (e.g., protecting runtime parameters from
  corruption or unauthorized modification during both development and
  operation), explicitly linking them to relevant Misbehaviours and their
  analyses (as defined in TA-MISBEHAVIOURS).
- Present constraint-related data with emphasis on availability, clarity, and
  transparent communication of defined safe states, along with the mechanisms
  that transition the system into those states, ensuring they are connected to
  the relevant AWIs (as defined in TA-INDICATORS).

Finally, the documentation must establish and promote a clear process for
reporting bugs, issues, and requests.

**Suggested evidence**

- Installation manuals with worked examples
  - **Answer**: See JLS-70.
- Configuration manuals with worked examples
  - **Answer**: See JLS-71.
- Specification documentation with a clearly defined scope
  - **Answer**: See JLS-72.
- User guides detailing limitations in interfaces designed for expandability or modularity
  - **Answer**: See JLS-73.
- Documented strategies used by external users to address constraints and work with existing Statements
  - **Answer**: See AOU-10 and AOU-11. For resource and time budgeting constraints on parsing and validation of untrusted or extreme inputs, see also AOU-31 and the supporting analysis in TSF/docs/nlohmann_runtime_and_memory_analysis.md.

**Confidence scoring**

The reliability of these constraints should be assessed based on the absence of
contradictions and obvious pitfalls within the defined Statements.

**Checklist**

- Are the constraints grounded in realistic expectations, backed by real-world
  examples?
  - **Answer**: The constraints are grounded in realistic expectations because they come from concrete AOUs covering practical integration duties (consistent dependencies and mirrored dependencies/tools for reproducible/offline builds (AOU-02/03/08/15), CI-tested toolchains (AOU-16), and release/update/security review processes (AOU-27/29)) and from nlohmann/json’s documented real-world pitfalls (exception handling/disablement (AOU-04/07), UTF-8-only input and invalid surrogates (AOU-05/21), brace-initialization ambiguity (AOU-06), and duplicate-key handling (AOU-20)). Upstream fuzz testing (JLS-02) further supports these constraints by exercising edge cases, increasing confidence without implying absolute certainty.
- Do they effectively guide downstream consumers in expanding upon existing
  Statements?
  - **Answer**: No downstream consumers exist yet to validate this. However, the AOUs are structured with the intent to guide downstream consumers in extending existing Statements.
- Do they provide clear guidance for upstreams on reusing components with
  well-defined claims?
  - **Answer**:  Yes, to the extent that our constraints and AOUs explicitly state which behaviours and properties of nlohmann/json we rely on (e.g. UTF‑8 handling, exception behaviour, duplicate‑key handling, and integration/toolchain assumptions). This makes clear which claims must remain valid for our Statements to hold, and thus gives upstream maintainers concrete guidance on what changes would affect us and where they need to preserve compatibility or coordinate changes.
- Are any Statements explicitly designated as not reusable or adaptable?
  - **Answer**: No, all statements could theoretically be adapted or reused.
- Are there worked examples from downstream or upstream users demonstrating
  these constraints in practice?
  - **Answer**: As the nlohmann/json library is widely used, its constraints (like the installation manual) are regularly read and applied and therefore demonstrated.
- Have there been any documented misunderstandings from users, and are these
  visibly resolved?
  - **Answer**: Yes, some recurring misunderstandings are explicitly documented and addressed via upstream documentation and closed issues. For example, brace-initialization unexpectedly yielding arrays and differing across compilers is called out in the [FAQ](https://json.nlohmann.me/home/faq/) and referenced from issues  [here](https://github.com/nlohmann/json/issues/4898), and duplicate-key behavior is clarified in the release notes as unspecified by RFC-8259 (see [release notes](https://json.nlohmann.me/home/releases) and issue [#2667](https://github.com/nlohmann/json/discussions/2667)).
- Do external users actively keep up with updates, and are they properly
  notified of any changes?
  - **Answer**: External users of the library are not necessarily automatically notified of an update, and are neither assumed nor required to keep up to date. If the external user forks the GitHub repository, however, then GitHub shows automatically whenever the upstream changes.
