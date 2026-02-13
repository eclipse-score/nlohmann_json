---
level: 1.1
normative: false
---

(Note: The guidance, evidence, confidence scoring and checklist sections below are copied from [CodeThink's documentation of TSF](https://codethinklabs.gitlab.io/trustable/trustable/trustable/TA.html). However, the answers to each point in the evidence list and checklist are specific to this project.)

The goal of TA-MISBEHAVIOURS is to force engineers to think critically about their work.
This means understanding and mitigating as many of the situations that cause the
software to deviate from Expected Behaviours as possible. This is not limited to
the contents of the final binary.

**Guidance**

This assertion is satisfied to the extent that we can:

- Show we have identified all of the ways in which nlohmann/json could deviate from its
  Expected Behaviours.
- Demonstrate that mitigations have been specified, verified and validated for
  all Misbehaviours.

Once Expected Behaviours have been identified in TA-BEHAVIOURS, there are at
least four classes of Misbehaviour that can be identified:

- Reachable vulnerable system states that cause deviations from Expected
  Behaviour. These can be identified by stress testing, failures in functional
  and soak testing in TA-BEHAVIOURS and reporting in TA-FIXES. Long run trends
  in both test and production data should also be used to identify these states.
- Potentially unreachable vulnerable system states that could lead to deviations
  from Expected Behaviour. These can be identified using risk/hazard analysis
  techniques including HAZOP, FMEDA and STPA.
- Vulnerabilities in the development process that could lead to deviations from
  Expected Behaviour. This includes those that occur as a result of misuse,
  negligence or malicious intent. These can be identified by incident
  investigation, random sampling of process artifacts and STPA of processes.
- Configurations in integrating projects (including the computer or embedded
  system that is the final product) that could lead to deviations from Expected
  Behaviour.

Identified Misbehaviours must be mitigated. Mitigations include patching,
re-designing components, re-designing architectures, removing components,
testing, static analysis etc. They explicitly _do not_ include the use of AWIs
to return to a known-good state. These are treated specifically and in detail in
TA-INDICATORS.

Mitigations could be verified by:

- Specifying and repeatedly executing false negative tests to confirm that
  functional tests detect known classes of misbehaviour.
- Specifying fault induction tests or stress tests to demonstrate that the
  system continues providing the Expected Behaviour after entering a vulnerable
  system state.
- Performing statistical analysis of test data, including using statistical path
  coverage to demonstrate that the vulnerable system state is never reached.
- Conducting fault injections in development processes to demonstrate that
  vulnerabilities cannot be exploited (knowingly or otherwise) to affect either
  output binaries or our analysis of it, whether this is by manipulating the
  source code, build environment, test cases or any other means.
- Stress testing of assumptions of use. That is, confirming assumptions of use
  are actually consistent with the system and its Expected Behaviours by
  intentionally misinterpreting or liberally interpreting them in a test
  environment. For example, we could consider testing nlohmann/json on different pieces of
  hardware that satisfy its assumptions of use.

Remember that a Misbehaviour is _anything_ that could lead to a deviation from
Expected Behaviour. The specific technologies in and applications of nlohmann/json should
always be considered in addition to the guidance above.

At the core, a faulty design is inherently difficult to mitigate. The first
priority, therefore, is to ensure a fault-tolerant and fault-avoidant design
that minimises fault impact and maximises fault control across all modes and
states. All design considerations should be traceable to analyses at the correct
abstraction level, with appropriate partitioning and scoping, which address
prevalent aspects in complex systems, such as:

- Spatial constraints (e.g., memory corruption)
- Temporal constraints (e.g., timing violations)
- Concurrency constraints (e.g., interference)
- Computational constraints (e.g., precision limits)
- Performance constraints (e.g., latency spikes under load)
- Environmental constraints (e.g., hardware non-determinism)
- Usability constraints (e.g., human interaction errors)

Finally, each new Expectation, whether a required behaviour or a misbehaviour
mitigation, introduces the potential for unexpected emergent properties,
highlighting the importance of simple, understandable designs that build on
established and reusable solutions.

**Suggested evidence**

- List of identified Misbehaviours
  - **Answer**: See JLS-11.
- List of Expectations for mitigations addressing identified Misbehaviours
  - **Answer**: Mitigation expectations are expressed implicitly through (a) documented Quality assurance (https://json.nlohmann.me/community/quality_assurance) requirements and (b) concrete mitigation mechanisms captured by existing Statements: JLS-02 (fuzzing), JLS-31 (static analysis), JLS-25 (review/security policy), JLS-24 (defined failure mode via exceptions), and WFJ-06 (input validation via accept()).
- Risk analysis
  - **Answer**: Risk analysis has been performed (see docs/risk_analysis.md).
- Test analysis, including:
  - False negative tests
    - **Answer**: Fault induction via fuzzing (see JLS-02) provides a practical approach to triggering failures and edge cases that normal functional tests might miss.
  - Exception handling tests
    - **Answer**: The nlohmann/json library contains a set of exception handling tests, along with custom exception types, as described in JLS-24.
  - Stress tests.
    - **Answer**: Stress tests target system-level behavior under load, while nlohmann/json is a stateless JSON library. There is no long-lived state, connection pool, thread pool, queue or similar in nlohmann/json. Therefore, stress tests are generally not relevant for nlohmann/json.
  - Soak tests
    - **Answer**: Soak tests are used to investigate long-running behaviour, not single operations like a JSON library. Soak tests are therefore not needed for the nlohmann/json library.

**Confidence scoring**

Confidence scoring for TA-MISBEHAVIOURS is based on confidence that
identification and coverage of misbehaviours by tests is complete when
considered against the list of Expectations.

**Checklist**

- How has the list of misbehaviours varied over time?
  - **Answer**: The list of misbehaviours for nlohmann/json (https://github.com/nlohmann/json/issues), as well as its history and development, is collected using Github. Statistics, e.g. about the number of open issues over time, are currently not tracked.
- How confident can we be that this list is comprehensive?
  - **Answer**: Due to the collaborative nature of the open source community, we deem it quite unlikely, but not impossible, that there are any known misbehaviours which are not reported to the nlohmann/json repository.
- How well do the misbehaviours map to the expectations?
  - **Answer**: The identified misbehaviours do not necessarily all have a direct impact on the defined expectations. A mapping of any misbehaviour to the expectations has to be done on a case-by-case basis.
- Could some participants have incentives to manipulate information?
  - **Answer**:  We can not think of any incentive that any collaborateur could have to manipulate the information.
- Could there be whole categories of misbehaviours still undiscovered?
  - **Answer**: Due to the wide use and long-standing development of the library it is quite unlikely that any major misbehaviours, in particular regarding the parsing and validating of JSON data in the sense of RFC-8259, is undiscovered. 
- Can we identify misbehaviours that have been understood but not specified?
  - **Answer**: We currently do not identify any misbehaviours that have been understood but not specified.
- Can we identify some new misbehaviours, right now?
  - **Answer**: No, currently no new misbehaviors can be identified.
- Is every misbehaviour represented by at least one fault induction test?
  - **Answer**: The expected behaviour of nlohmann/json is described by JLS-24 and its substatements in the trustable graph. For a random subset of 10 of these substatements (TIJ-01.1, TIJ-01.2, TIJ-05.1, TIJ-05.3, NPF-01.2, NPF-01.3, NPF-07.2, TIJ-02.4, TIJ-02.5, TIJ-02.2) we checked whether possible misbehaviours (like wrong inputs) are tested using fault induction tests. For all of these 10 substatements, at least one fault induction test is performed. We therefore conclude that most misbehaviours are represented by at least one fault induction test.
- Are fault inductions used to demonstrate that tests which usually pass can and do fail appropriately?
  - **Answer**: Yes. The project uses several forms of fault induction (malformed JSON, invalid API usage, simulated allocation failures, and fuzzing). Dedicated tests assert that these induced faults cause the library to fail in a well‑defined, expected way (e.g. by throwing specific exceptions). CI then confirms that these “failure‑expecting” tests keep behaving as specified. See JLS-76.
- Are all the fault induction results actually collected?
  - **Answer**: Partially. For Unit / regression tests: their results are only captured as normal test pass/fail status and CI logs; there is no separate, persistent database of all induced faults and outcomes in the repository. For Fuzz tests (OSS‑Fuzz): the fuzzing infrastructure stores crashing inputs, logs, and statistics on the OSS‑Fuzz side, not in the nlohmann/json repo itself. See JLS-76 for further information.
- Are the results evaluated?
  - **Answer**: Yes. nlohmann/json has a multi‑layered QA process where all fault‑induction results (from unit tests, dynamic analysis, and fuzzing) are systematically evaluated. The CI pipeline runs 1000+ doctest-based tests across 50+ compiler/standard-library/platform configurations, with 100% code‑coverage targets; any failure (including sanitizer/Valgrind runs, static analysis warnings, or CI fuzz/CIFuzz/OSS‑Fuzz crashes) blocks merging, is inspected by maintainers, fixed, and typically covered by additional regression tests, in line with the documented quality assurance process. Together with the collection of fault‑induction results asserted in JLS‑76, this establishes a continuous loop from induced faults to analysed results to corrective actions.
- Do input analysis findings on verifiable tool or component claims and features identify additional misbehaviours or support existing mitigations?
  - **Answer**: Currently, there is no analysis which identifies additional misbehaviours. The only such analysis is indirectly via the analysis of the fuzz testing, which currently does not identify additional misbehaviours.
