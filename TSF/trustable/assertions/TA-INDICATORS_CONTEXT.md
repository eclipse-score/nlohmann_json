---
level: 1.1
normative: false
---

(Note: The guidance, evidence, confidence scoring and checklist sections below are copied from [CodeThink's documentation of TSF](https://pages.eclipse.dev/eclipse/tsf/tsf/trustable/TA.html). However, the answers to each point in the evidence list and checklist are specific to this project.)

Not all deviations from Expected Behaviour can be associated with a specific
condition. Therefore, we must have a strategy for managing deviations that
arise from unknown system states, process vulnerabilities or configurations.

This is the role of _Advanced Warning Indicators (AWI)_. These are specific
metrics which correlate with deviations from Expected Behaviour and can be
monitored in real time. The system should return to a defined known-good
state when AWIs exceed defined tolerances.

**Guidance**

This assertion is met to the extent that:

- We have identified indicators that are strongly correlated with observed
  deviations from Expected Behaviour in testing and/or production.
- The system returns to a defined known-good state when AWIs exceed
  defined tolerances.
- The mechanism for returning to the known-good state is verified.
- The selection of Advance Warning Indicators is validated against the set of
  possible deviations from Expected behaviour.

Note, the set of possible deviations from Expected behaviour _is not_ the same
as the set of Misbehaviours identified in TA-MISBEHAVIOURS, as it includes
deviations due to unknown causes.

Deviations are easily determined by negating recorded Expectations. Potential
AWIs could be identified using source code analysis, risk analysis or incident
reports. A set of AWIs to be used in production should be identified by
monitoring candidate signals in all tests (functional, soak, stress) and
measuring correlation with deviations.

Telematics, diagnostics, or manual proof testing are of little value without
mitigation. As such, AWI monitoring and mitigation should be automatic,
traceable back to analysis, and formally recorded to ensure information from
previously unidentified misbehaviours is captured in a structured way.

The known-good state should be chosen with regard to the system's intended
consumers and/or context. Canonical examples are mechanisms like reboots,
resets, relaunches and restarts. The mechanism for returning to a known-good
state can be verified using fault induction tests. Incidences of AWIs triggering
a return to the known-good state in either testing or production should be
considered as a Misbehaviour in TA-MISBEHAVIOURS. Relying on AWIs alone is not
an acceptable mitigation strategy. TA-MISBEHAVIOURS and TA-INDICATORS are
treated separately for this reason.

The selection of AWIs can be validated by analysing failure data. For instance,
a high number of instances of deviations with all AWIs in tolerance implies the
set of AWIs is incorrect, or the tolerance is too lax.

**Evidence**

- Risk analysis
  - **Answer**: Risk analysis has been performed (see docs/risk_analysis.md).
- List of advance warning indicators
  - **Answer**: The only two introduced AWIs are provided in JLS-54 and JLS-55.
- List of Expectations for monitoring mechanisms
  - **Answer**: There are no dedicated monitoring mechanisms defined. Any expectations for monitoring apply at system or integration level and are expected to be specified and implemented by the integrator.
- List of implemented monitoring mechanisms
  - **Answer**: There are no dedicated monitoring mechanisms for AWIs in the sense of continuous or in-field monitoring. The two AWIs (coverage and PR count) are evaluated only when CI workflows are executed and are used as quality gates at CI time, rather than as a separate, continuous monitoring system (see JLS-54 and JLS-55).
- List of identified misbehaviours without advance warning indicators
  - **Answer**: Provided by JLS-11.
- List of advance warning indicators without implemented monitoring mechanisms
  - **Answer**: All currently defined AWIs (JLS-54 and JLS-55) are evaluated via CI runs, but there is no additional, dedicated monitoring mechanism beyond these CI executions.
- Advance warning signal data as time series (see TA-DATA)
  - **Answer**: The only AWIs in JLS-54 and JLS-55 are implemented as part of the CI and therefore saved as time series (see JLS-18 and JLS-45).

**Confidence scoring**

Confidence scoring for TA-INDICATORS is based on confidence that the list of
indicators is comprehensive / complete, that the indicators are useful, and that
monitoring mechanisms have been implemented to collect the required data.

**Checklist**

- How appropriate/thorough are the analyses that led to the indicators?
  - **Answer**: For eclipse-score/inc_nlohmann_json, the library itself is a statically integrated, header-only component without stream processing loops. No runtime misbehaviours specific to this repository have been identified, and therefore no runtime AWIs are implemented for the library itself. The two AWIs that do exist (coverage threshold and PR-count limit) are based on the assumption that CI test results and review load correlate with potential misbehaviours in the library and its evolution, and are therefore focused on test and process quality rather than runtime behaviour (see JLS-54 and JLS-55).
- How confident can we be that the list of indicators is comprehensive?
  - **Answer**:  For the scope of `eclipse-score/inc_nlohmann_json` as a static library, we are reasonably confident that CI-based indicators on test coverage and the count of open PRs are sufficient.
- Could there be whole categories of warning indicators still missing?
  - **Answer**: Yes, there could. In particular, runtime performance or stability indicators in systems that use the library are not covered here. Any missing warning indicators are expected to be implemented by the integrator (see AOU-09).
- How has the list of advance warning indicators varied over time?
  - **Answer**: The current AWIs (coverage threshold and pr count threshold on protected branches) were introduced as CI-based quality gates. No additional AWIs have been added or removed so far (see JLS-54 and JLS-55).
- How confident are we that the indicators are leading/predictive?
  - **Answer**: The indicators are leading in the sense that they prevent changes which reduce test coverage, or are made in an overloaded PR situation, from entering protected branches and being used as a basis for integration and release.
- Are there misbehaviours that have no advance warning indicators?
  - **Answer**: Potential runtime misbehaviours in consuming systems are not covered by AWIs in this repository.
- Can we collect data for all indicators?
  - **Answer**: Both indicators (JLS-54 and JLS-55) are derived from CI runs, and the required data (coverage and pr count) is collected automatically for each CI execution.
- Are the monitoring mechanisms used included in our Trustable scope?
  - **Answer**: There are no continuously running runtime monitoring mechanisms. The only related mechanisms are the CI workflows implementing JLS-54 and JLS-55, they run only when CI is executed.
- Are there gaps or trends in the data?
  - **Answer**: There is no trend analysis preformed on AWIs. However, there is trend analysis done as a proof of concept to the failure rate of CI test (see JLS-17). Potential gaps could arrise during the integration of the library (see AOU-09).
- If there are gaps or trends, are they analysed and addressed?
  - **Answer**: There are no trends identified (see the question above). Any gaps should be closed by the integrator.
- Is the data actually predictive/useful?
  - **Answer**: Yes, the CI data from the AWIs is useful to prevent regressions in the tested behaviour of the library and possible issues introduced due to a large number of open PRs from entering protected branches. 
- Are indicators from code, component, tool, or data inspections taken into
consideration? 
  - **Answer**: Yes, all types of indicator are taken into consideration.
