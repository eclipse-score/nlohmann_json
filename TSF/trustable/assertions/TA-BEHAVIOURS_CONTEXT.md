---
level: 1.1
normative: false
---

(Note: The guidance, evidence, confidence scoring and checklist sections below are copied from [CodeThink's documentation of TSF](https://pages.eclipse.dev/eclipse/tsf/tsf/trustable/TA.html). However, the answers to each point in the evidence list and checklist are specific to this project.)

Although it is practically impossible to specify all of the necessary behaviours
and required properties for complex software, we must clearly specify the most
important of these (e.g. where harm could result if given criteria are not met),
and verify that these are correctly provided by the nlohmann/json library.

**Guidance**

This assertion is satisfied to the extent that we have:

- Determined which Behaviours are critical for consumers of nlohmann/json and recorded
  them as Expectations.
- Verified these Behaviours are achieved.

Expectations could be verified by:

- Functional testing for the system.
- Functional soak testing for the system.
- Specifying architecture and verifying its implementation with pre-merge
  integration testing for components.
- Specifying components and verifying their implementation using pre-merge unit
  testing.

The number and combination of the above verification strategies will depend on
the scale of the project. For example, unit testing is more suitable for the
development of a small library than an OS. 
Similarly, the verification strategy must align with the chosen development
methods and be supported by appropriate verification approaches and tools.

Regardless of the chosen strategy, the reasoning behind it must be recorded in a
traceable way, linking breakdown and verification methods to the relevant
reasoning, abstraction levels, and design partitioning (including system
interfaces with users and hardware, or other system boundaries).

Finally, the resulting system must be validated, with the foundation of
validation being a working system that has appropriately considered calibration
targets such as capacity, scalability, response time, latency, and throughput,
where applicable.
Without this, specification and verification efforts cannot be considered
sufficient.

**Evidence**

- List of Expectations
  - **Answer**: The Expectations are provided via JLEX-01 and JLEX-02.
- Argument of sufficiency for break-down of expected behaviour for all Expectations
  - **Answer**: See JLS-56.
- Validation and verification of expected behaviour
  - **Answer**: The validation and verification of expected behaviour is done via the evidence provided for all the statements below JLEX-01 and JLEX-02 in the trustable graph, in addition to JLS-03.


**Confidence scoring**

Confidence scoring for TA-BEHAVIOURS is based on our confidence that the list of
Expectations is accurate and complete, that Expectations are verified by tests,
and that the resulting system and tests are validated by appropriate strategies.

**Checklist**

- How has the list of Expectations varied over time?
  - **Answer**: The list of Expectations is taken from [here](https://eclipse-score.github.io/score/main/modules/baselibs/json/docs/requirements/index.html). The development can be retraced using git.
- How confident can we be that this list is comprehensive?
  - **Answer**: The list of Expectations has been collected amongst the stakeholders in S-CORE, so we are very confident that the list is comprehensive.
- Could some participants have incentives to manipulate information?
  - **Answer**: We consider intentional manipulation of information about nlohmann/json to be very unlikely because the library is open source, has no direct revenue or certification attached to this documentation, and all stakeholders share a strong interest in correctness and robustness. Any misrepresentation of expectations or verification would quickly become counterproductive by increasing integration risk, maintenance cost, and reputational damage for the participants. In addition, the requirements, code and history are publicly visible and version-controlled, so inconsistencies can be detected and challenged by other S-CORE stakeholders or the wider community. While unintentional errors are always possible, we see no realistic positive incentive, and several strong negative incentives, for deliberately manipulating this information.
- Could there be whole categories of Expectations still undiscovered?
  - **Answer**: Yes, it is always possible that whole categories of Expectations remain undiscovered, especially for a widely used and versatile library like nlohmann/json. However, this risk is mitigated by deriving Expectations from actual use cases, stakeholder input, and known integration contexts within S-CORE, and by revisiting them as new uses emerge. The requirements and their evolution are tracked in version control, so newly identified categories can be added transparently. We therefore acknowledge the possibility of missing categories, but consider the current set to be appropriate and proportionate for the identified scope and applications.
- Can we identify Expectations that have been understood but not specified?
  - **Answer**: There are currently no Expectations that have been understood but not specified.
- Can we identify some new Expectations, right now?
  - **Answer**: We currently do not see further Expectations to be identified because the existing set was derived systematically from the S-CORE stakeholders.
- How confident can we be that this list covers all critical requirements?
  - **Answer**: We are very confident that this list covers all critical requirements.
- How comprehensive is the list of tests?
  - **Answer**: Currently, the branch coverage is 93.865% and the line coverage is 99.186%, cf. JLS-27. Therefore, we deem the list of tests to be very comprehensive.
- Is every Expectation covered by at least one implemented test?
  - **Answer**: Yes, both of the Expectations are covered by at least one implemented test.
- Are there any Expectations where we believe more coverage would help?
  - **Answer**: No, the coverage is already on a high level and no further gains are expected by further increasing the coverage.
- How do dependencies affect Expectations, and are their properties verifiable?
  - **Answer**: The nlohmann/json library does not have any external dependencies apart from the testing pipeline, so there are no dependencies that could possibly affect the Expectations. 
- Are input analysis findings from components, tools, and data considered in relation to Expectations?
  - **Answer**: For components, there is no input analysis as the nlohmann/json library has no external components (see JLS-34). For Tools, a tool assessment is provided via JLS-50. In addition, the only data provided to the nlohmann/json library is the input data when using the libraries' functionality, as well as the test data taken from [here](https://github.com/nlohmann/json_test_data). For data, the json_test_data repository is an aggregation of widely used, independently curated JSON test suites (Big List of Naughty Strings, JSONTestSuite, JSON Patch tests, benchmark suites, etc.), each explicitly designed to cover malformed inputs, edge cases, and realistic JSON usage. We rely on the documented scope and intent of these suites, together with the high measured code coverage (JLS-27), to conclude that they exercise the behaviours captured in our Expectations (JLEX-01, JLEX-02), and we do not perform a separate, manual “input analysis” of every file in the corpus. In that sense, there are no additional local input‑analysis findings beyond the upstream characterisation of these corpora that would currently motivate changing or extending our Expectations.
