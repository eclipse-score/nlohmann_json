## Risk Analysis for nlohmann/json 3.12.0 within eclipse-score/nlohmann_json

This document provides a **risk analysis** for the **eclipse-score/nlohmann_json** repository following the risk analysis approach of the Trustable Software Framework (TSF) \[[RAFIA: Risk Analysis](https://pages.eclipse.dev/eclipse/tsf/tsf/extensions/rafia/risk-analysis.html)\].

## 0. Methodology (RAFIA / STPA) – What is being done and why

Risk Analysis objectives (summarised from the Codethink guidance) are:

- **Hazard analysis**
  - Describe a *system/subsystem* that incorporates the software.
  - Identify *Losses* (unacceptable outcomes) and *Hazards* (system-level conditions leading to losses).
  - Specify a *control structure* (controllers, controlled processes, control actions, feedback).
  - Identify *Unsafe Control Actions (UCAs)* that may result in hazards.
  - Identify *Causal Scenarios* that can lead to UCAs or hazards.
  - Devise *Constraints* that must hold to avoid hazards/UCAs/scenarios.
- **Traceability**
  - Map analysis outcomes into the TSF model of Statements: *Expectations*, *Assertions*, *Evidence*.
  - Maintain forward/backward links so that changes to any statement trigger re-evaluation of related analysis links.
- **Risk evaluation**
  - Evaluate relative importance of hazards/misbehaviours using at least **severity** and **likelihood**, and optionally **controllability** and **exposure/demand**, to support prioritisation and cost/benefit decisions \[[RAFIA: Risk Analysis](https://pages.eclipse.dev/eclipse/tsf/tsf/extensions/rafia/risk-analysis.html)\].

### How this is instantiated for this repository

This repository already contains a rich TSF statement graph that captures:

- the **expected behaviours** (`JLEX-01`, `JLEX-02`) and their supporting evidence (`WFJ-*`, `PJD-*`, `NJF-*`, `NPF-*`, `TIJ-*`), and
- the process expectations around tests, fixes, inputs, constraints, and analysis (`TA-TESTS`, `TA-FIXES`, `TA-INPUTS`, `TA-CONSTRAINTS`, `TA-ANALYSIS`, …).

### STPA procedure and schema conformance

This document follows the RAFIA STPA procedure at the level of intent and outputs (Losses → Hazards → Control Structure → UCAs → Scenarios → Constraints → Misbehaviours), as described in the TSF extensions:

- STPA procedure: \[[RAFIA STPA Procedure](https://pages.eclipse.dev/eclipse/tsf/tsf/extensions/stpa/procedure.html)\]
- STPA workbook schema (tables/columns): \[[STPA results schema](https://pages.eclipse.dev/eclipse/tsf/tsf/extensions/stpa/schema.html)\]

Concretely, the procedure steps map to this document as follows:

- **Step 1 Define scope**
- **Step 2 Define Losses**
- **Step 3 Define Hazards**
- **Step 3 Describe control structure**
- **Step 4 Identify UCAs**
- **Step 5 Identify causal scenarios**
- **Step 8 Mapping to TSF**
- **Step 9 Specify misbehaviours**
- **Step 10 Conclusion**

---

## 1. Scope and System Context

### 1.1 Software Under Analysis

The software under analysis is the **header-only C++ JSON library `nlohmann/json` (v3.12.0)**, with:

- **Implementation**
  - primary include `include/nlohmann/json.hpp` (and internal headers under `include/nlohmann/detail/**`)
  - optional amalgamated single-include header `single_include/nlohmann/json.hpp`
  - C++11, no external code dependencies
- **Purpose**
  - provide JSON parsing and validation per **RFC 8259**
- **Evidence**
  - captured extensively in `WFJ-*`, `TIJ-*`, `NJF-*`, `NPF-*`, and `PJD-*` statements, which are connected in the trustable graph to the expectations `JLEX-01` and `JLEX-02`.

In practical terms, this means the “safety envelope” of the component is defined by the combination of:

- the semantic scope of RFC 8259 JSON (what inputs are considered valid JSON), and
- the repository’s explicit expectations (`JLEX-01`, `JLEX-02`) and their evidence families.

### 1.2 Integration Context (as documented by TSF expectations)

This repository’s TSF Expectations explicitly scope the intended integration context to:

- JSON validation (`JLEX-01`, referencing the S-CORE JSON Validation requirement), and
- JSON deserialization (`JLEX-02`, referencing the S-CORE JSON Deserialization requirement).

In the remainder of this document, “S-CORE” is used as a **target-system / integrator label** for expressing system-level Losses and Hazards in the STPA sense. This repository itself documents the `nlohmann/json` component and its TSF statement graph.

The TSF graph shows this as:

- `TT-EXPECTATIONS` → `TA-BEHAVIOURS` → `JLEX-01`, `JLEX-02`
- `TA-INPUTS` → multiple `JLS-*` (e.g. `JLS-34`, `JLS-48`, `JLS-49`, `JLS-50`), describing properties of inputs, dependencies and environment.

The library **does not control hardware directly**. Misbehaviours affect S-CORE only **via incorrect JSON validation or parsing**, influencing higher-level functions.

Because this is a *library component*, we express risks at the S-CORE system level (e.g., “S-CORE accepts ill-formed JSON”), and we treat the library as a contributing factor through its API behaviour and error signalling. This matches the RAFIA/STPA guidance to analyse the software in the context of a system/subsystem, rather than as an isolated artifact \[[RAFIA: Risk Analysis](https://pages.eclipse.dev/eclipse/tsf/tsf/extensions/rafia/risk-analysis.html)\].

### 1.3 Assumptions of Use and Constraints

The nodes:

- `TA-CONSTRAINTS` → `AOU-01..AOU-30`
- `TA-INPUTS` → `JLS-04`, `JLS-34`, `JLS-47`, `JLS-48`, `JLS-49`, `JLS-50`

capture key **Assumptions of Use (AOU-*)** and **constraints** for integration, including:

- S-CORE code must check `accept`/`parse` results and handle exceptions correctly.
- Input encoding and error signalling are managed at the integration boundary (notably UTF-8 input per `AOU-05`, and proper exception handling per `AOU-04` and `AOU-07`).
- This analysis assumes integrators do not depend on unspecified or undocumented behaviours.

This Risk Analysis is valid under these assumptions and constraints.

#### AOU statements directly relevant to this analysis (normative)

The following Assumptions of Use are explicitly stated in this TSF tree and are directly relevant to risk analysis of JSON parsing/validation:

- **`AOU-04`**: the integrator shall ensure that exceptions are properly handled or turned off when using the library.
- **`AOU-05`**: the integrator shall ensure input is UTF-8 (RFC 8259) and handle exceptions for other string formats.
- **`AOU-07`**: expected parsing errors for invalid JSON (default parameters) shall be detected and handled properly.
- **`AOU-20`**: keys within an object shall be unique whenever an object is parsed.
- **`AOU-22`**: numbers shall be written in base 10; exceptions/misbehaviours for other bases shall be handled/mitigated.
- **`AOU-23`**: data shall be complete and error-free whenever transmitted to the component.
- **`AOU-27`**: release management / update concepts in `TSF/README.md` shall be followed when changes are done.
- **`AOU-28`**: known open bugs in upstream `nlohmann/json` shall be regularly reviewed for impact.
- **`AOU-29`**: the GitHub security tab shall be checked regularly and outstanding CVEs analysed and fixed/dismissed.

These AOU statements are treated as **controller/environment constraints** in the sense that they constrain how the integrator/environment must behave so that the component can be used safely for the intended scope.

---

## 2. Losses (Unacceptable Outcomes)

Although `nlohmann/json` is a library, its misbehaviour can contribute to unacceptable outcomes in S-CORE applications.

To stay consistent with RAFIA, we define losses as **unacceptable outcomes for stakeholders**, not as “bugs”. For a parsing/validation library, the primary stakeholder impact is through *incorrect decisions, corrupted configuration/data, or loss of availability* in the integrating system. Losses are deliberately phrased at S-CORE level, because S-CORE is the system that ultimately experiences the unacceptable outcome.

### Rationale for the chosen losses

The loss set (L1–L6) is intentionally small and orthogonal:

- **Correctness / decision impact** (L1) covers downstream consequences when S-CORE acts on a parsed value that is wrong for the intended meaning.
- **Input acceptance / rejection integrity** (L2) captures the baseline that syntactically ill-formed inputs must be rejected (i.e., not treated as valid JSON).
- **Compliance exposure** (L3) is included because this component is commonly integrated into regulated or contract-driven systems, where correct JSON handling can be part of auditability and traceability obligations
- **Availability** (L4) is included because parsing and validation failures can become denial-of-service vectors or cause systemic instability.
- **Silent data corruption** (L5) captures a distinct failure mode from availability: the system continues operating but with undetected corruption (e.g., configuration or logs), which can be more dangerous than explicit failure.
- **Security / trust compromise** (L6) is included because this component may process untrusted input, and exploitable parser weaknesses or unpatched known vulnerabilities (e.g., CVEs) can lead to compromise in an integrating system even when functional behaviour is otherwise well specified.

| Loss Id | Loss description | Loss category |
|---|---|---|
| L1 | Safety-relevant or correctness-critical S-CORE decisions are based on incorrectly parsed JSON data. | Safety |
| L2 | S-CORE fails to reject syntactically ill-formed JSON inputs that must be rejected. | User |
| L3 | S-CORE violates contractual, regulatory, or audit requirements that depend on correct JSON validation/parsing (e.g., configuration integrity, trustworthy logs). | Commercial |
| L4 | S-CORE services become unavailable or unstable due to parser exceptions, crashes or hangs. | User |
| L5 | Integrity of JSON-based logs or configuration data is compromised by silently incorrect parsing. | Commercial |
| L6 | Security compromise due to exploitation of parsing/processing weaknesses or unpatched known vulnerabilities. | Security |

---

## 3. Hazards (System-Level Conditions)

Using the Losses, we define **Hazards (H\*)** at S-CORE level:

Hazards are not “root causes” and not “bugs”; they are **system-level conditions** that can lead to losses if they occur. Here, hazards are defined as conditions about *what S-CORE accepts, rejects, produces, or fails to handle*, because those are the conditions that create stakeholder-relevant losses.

| Hazard Id | Hazard description | Link to loss(es) | Notes |
|---|---|---|---|
| H1 | S-CORE accepts JSON inputs that are not syntactically well-formed per RFC 8259. | L1; L2; L3; L5 |  |
| H2 | S-CORE rejects syntactically well-formed JSON inputs that should be accepted in the defined domain. | L1; L4 |  |
| H3 | S-CORE obtains a parsed representation that is semantically inconsistent with the original JSON text. | L1; L3; L5 |  |
| H4 | S-CORE encounters unhandled exceptions or hangs during JSON parsing/validation operations. | L4 |  |
| H5 | S-CORE misinterprets parser outcomes due to ambiguous or undocumented behaviour of the library. | L1; L2; L3; L5 |  |
| H6 | S-CORE experiences resource exhaustion (CPU/memory/time) while processing JSON inputs, impacting availability or deadlines. | L4 |  |
| H7 | Upstream vulnerabilities or relevant open bugs are not tracked/triaged, so known issues remain present in the integrated component. | L6; L4 |  |

---

## 4. Control Structure

This control structure is intentionally minimal and models two control loops:

- **CL1 (Functional validation/parsing)**: S-CORE calls `accept`/`parse` and reacts to Boolean results and exceptions.
- **CL2 (Governance)**: periodic upstream issue/CVE review and update decisions, because **H7** is in scope (anchored by `AOU-27..29`).

### 4.1 Elements 

| Element Id | Element | Role | Responsibility (short) |
|---|---|---|---|
| E1 | S-CORE JSON caller | Controller | Calls `accept`/`parse`, interprets results, handles errors |
| E2 | `nlohmann/json` service | Controlled Process | Validates/parses input and returns Boolean/value or throws |
| E3 | Integration governance process | Controller | Reviews upstream issues/CVEs; decides mitigation/update |
| E4 | Dependency state | Controlled Process | Current version + known upstream issues/CVEs affecting it |

### 4.2 Interactions (control actions and feedback)

| Interaction Id | Kind | Provider → Receiver | Meaning (short) |
|---|---|---|---|
| I1 | CA | E1 → E2 | Call `basic_json::accept` on input text |
| I2 | FB | E2 → E1 | Return Boolean `accept` result |
| I3 | CA | E1 → E2 | Call `basic_json::parse` on input text |
| I4 | FB | E2 → E1 | Return parsed value or throw exception |
| I5 | CA | E3 → E4 | Perform upstream triage/update decision |
| I6 | FB | E4 → E3 | Provide upstream status/impact signals |

### 4.3 Control loops and step references (used by Scenarios)

| Loop | CL ref | Step meaning | Interaction(s) |
|---|---|---|---|
| CL1 | CL1-1 | Validation action (`accept`) | I1 |
| CL1 | CL1-2 | Validation feedback | I2 |
| CL1 | CL1-3 | Parsing action (`parse`) | I3 |
| CL1 | CL1-4 | Parsing feedback + handling at boundary | I4 |
| CL2 | CL2-1 | Governance action (triage/update decision) | I5 |
| CL2 | CL2-2 | Governance feedback (status/impact signals) | I6 |

---

## 5. Unsafe Control Actions (UCAs)

Using the control structure, we identify **Unsafe Control Actions (UCA\*)**:

A UCA is an interaction between a controller and a controlled process that can lead to a hazard. For this library-centric control structure, UCAs correspond to “incorrect accept/parse outcome” and “incorrect error signalling”.

### 5.1 UCAs

| UCA Id | Interaction | Unsafe control action (summary) | Hazards | Constraint(s) |
|---|---|---|---|---|---|
| UCA1 | I1 (`accept`) | `accept` returns `true` for ill-formed JSON | H1; H5 | C1 |
| UCA2 | I1 (`accept`) | `accept` returns `false` for well-formed JSON | H2 | C1 |
| UCA3 | I3 (`parse`) | `parse` returns a value inconsistent with the JSON text | H3; H5 | C2 |
| UCA4 | I3 (`parse`)  | `parse` throws or hangs for valid JSON under practical constraints | H2; H4 | C2; C4 |
| UCA5 | I3 (`parse`)  | Errors are signalled ambiguously, enabling misinterpretation | H4; H5 | C6 |
| UCA6 | I5 (triage/update) | Required upstream review/triage is not performed | H7 | C11 |
| UCA7 | I5 (triage/update) | Relevant advisory/issue is incorrectly dismissed | H7 | C11 |
| UCA8 | I5 (triage/update) | Update/mitigation is applied too late | H7 | C11 |
| UCA9 | I5 (triage/update) | Update is applied without adequate regression evaluation | H7 | C11 |

### 5.2 CA-Analysis 

| CA-Analysis Id | Linked UCA(s) | Why unsafe |
|---|---|---|
| CAA1 | UCA1 | Enables S-CORE to treat ill-formed JSON as valid, creating acceptance/misinterpretation hazards. |
| CAA2 | UCA2 | Causes false rejection of valid JSON, impacting availability or correctness at system level. |
| CAA3 | UCA3 | Introduces semantic mismatch between text and parsed representation, driving incorrect downstream decisions. |
| CAA4 | UCA4; UCA5 | Abnormal termination/unclear feedback breaks the error-handling control loop and can cause unhandled failures. |
| CAA5 | UCA6; UCA7; UCA8 | Missed/mis-handled triage leaves known upstream issues present beyond acceptable limits. |
| CAA6 | UCA9 | Unsafe update practices can introduce regressions that re-enable hazards H1–H6. |

---

## 6. Scenarios 

The STPA schema records causal analysis results in a Scenarios table that links each causal scenario to a control-loop step (here: **CL1** functional parsing/validation and **CL2** governance), and to the resulting UCA and/or Hazards.

CS Type legend (informal, used here as a compact tag):

- **CS4-P**: controlled-process contribution (service behaviour)
- **CS1-M**: controller/operator misuse or misinterpretation at the boundary
- **CS1-A**: action/process-related contribution (e.g. governance/update practice)
- **CS4-I**: input/environment condition (assumption/constraint violation)
- **CS4-D**: design/platform interaction (boundary-risk factors)

| Scenario Id | CL ref | CS Type | Scenario (compact) | Analysis result | Links to UCA | Links to hazard(s) | Constraint Id | Notes |
|---|---|---|---|---|---|---|---|---|
| CS1.1 | CL1-1 (`accept`) | CS4-P | Service accepts ill-formed JSON | Both | UCA1 | H1; H5 | C1 | Evidence (`TIJ-*`, `WFJ-*`, `NJF-*`, `NPF-*`) reduces likelihood. |
| CS1.2 | CL1-1 (`accept`) | CS4-P | Service rejects well-formed JSON | Both | UCA2 | H2 | C1 | Positive evidence via `WFJ-*` and `PJD-*`. |
| CS1.3 | CL1-3 (`parse`) | CS4-P | Parsing produces inconsistent value | Both | UCA3 | H3; H5 | C2 | Coverage via `PJD-*`, `NPF-*`. |
| CS1.4 | CL1-3 (`parse`) | CS4-P | Parsing throws/hangs under practical constraints | Both | UCA4 | H2; H4 | C2; C4 | Availability is primarily constrained by SLC (C4). |
| CS1.5 | CL1-4 (result/exception handling) | CS1-M | Integrator mis-handles result/exception channel | Both | UCA5 | H4; H5 | C6 | Integration/process scenario (AOU-driven). |
| CS2.1 | CL1-3 (`parse`) | CS4-P | Extreme inputs exhaust resources | Hazard |  | H6 | C4 | Tree does not define explicit size/depth limits; integration may need budgets. |
| CS2.2 | CL1-3 (`parse`) | CS4-D | Platform effects contribute to hangs | Both | UCA4 | H4 | C4 | Boundary-risk; mitigated by CI/analysis evidence. |
| CS3.1 | CL2-1 (triage/update) | CS1-A | Update introduces regression not caught by evidence | Hazard |  | H1; H2; H3; H4; H5; H6 | C11 | Managed by change control and regression expectations. |
| CS3.2 | CL2-1 (triage/update) | CS1-M | Relevant issue/advisory is misclassified | Both | UCA7 | H7 | C11 | See `JLS-11` and `TSF/docs/nlohmann_misbehaviours_comments.md`. |
| CS3.3 | CL2-1 (triage/update) | CS1-A | CI/config drift reduces test effectiveness | Hazard |  | H1; H2; H3; H4; H5; H6 | C11 | Partially covered by `TA-INPUTS`/`TA-SUPPLY_CHAIN`. |
| CS4.1 | CL1-2 (`accept` feedback) | CS1-M | Caller ignores `accept` feedback | Hazard |  | H1; H5 | C6 | Integration misuse; mitigated by correct feedback handling (C6). |
| CS4.2 | CL1-4 (result/exception handling) | CS1-A | Exceptions are left uncaught | Hazard |  | H4 | C6 | Integration error-handling constraint. |
| CS4.3 | CL1-1 (input) | CS4-I | Input encoding violates RFC 8259 assumptions | Hazard |  | H4; H5 | C7 | Anchored by `AOU-05`. |
| CS4.4 | CL1-3 (`parse`) | CS4-I | Duplicate keys introduce ambiguity | Hazard |  | H5 | C8 | Anchored by `AOU-20`. |
| CS4.5 | CL1-3 (`parse`) | CS4-I | Non-decimal numbers are introduced | Hazard |  | H4; H5 | C9 | Anchored by `AOU-22`. |
| CS4.6 | CL1-1 (input) | CS4-I | Data is incomplete/corrupted at boundary | Hazard |  | H5 | C10 | Anchored by `AOU-23`. |

---

## 7. Mapping to TSF Items

In RAFIA/STPA, constraints are “statements that must be true” to avoid a hazard, UCA, or causal scenario \[[RAFIA: Risk Analysis](https://pages.eclipse.dev/eclipse/tsf/tsf/extensions/rafia/risk-analysis.html)\]. In TSF terms, these constraints are captured as (or mapped onto existing) **Items**, and are supported by **Evidence**. 

### 7.1 Constraints

| Constraint Id | Description | Constraint Type | Link to Constraint(s) | Link to Hazard(s) | Links to UCA | Links to CS | Links to TSF |
|---|---|---|---|---|---|---|---|
| C1 | `basic_json::accept` correctly distinguishes RFC 8259 well-formed JSON from ill-formed JSON for all inputs within the defined scope/integration context. | CFC |  | H1; H2 | UCA1; UCA2 | CS1.1; CS1.2 | JLEX-01 |
| C2 | `basic_json::parse` returns a correct representation for well-formed JSON or signals failure clearly (exception) under the defined scope/integration context. | CFC |  | H2; H3; H4; H5 | UCA3; UCA4; UCA5 | CS1.3; CS1.4; CS1.5; CS2.2 | JLEX-02 |
| C3 | For ill-formed JSON, parsing does not silently produce a misleading `basic_json` value; failure is signalled. | CFC |  | H1; H5 | UCA3 | CS1.1 | JLS-24 |
| C4 | Parsing/validation completes within acceptable resource/time bounds for the integration context, or the integration specifies explicit budgets/limits. | SLC |  | H4; H6 |  |  |  |
| C5 | A safe dependency state is maintained such that known relevant upstream issues/CVEs do not remain present beyond acceptable limits. | SLC |  | H7 |  |  | JLS-11; AOU-27; AOU-28; AOU-29 |
| C6 | All feedback channels at the integration boundary (validation results and exceptions/error signalling) are handled and interpreted correctly. | CSC |  | H4; H5 | UCA5 | CS1.5; CS4.1; CS4.2 | AOU-04; AOU-07 |
| C7 | Input encoding satisfies RFC 8259 (UTF-8) or violations are handled explicitly at the boundary. | CSC |  | H4; H5 |  | CS4.3 | AOU-05 |
| C8 | Object keys are unique when objects are parsed (or ambiguity is mitigated at integration level). | CSC |  | H5 |  | CS4.4 | AOU-20 |
| C9 | Numbers are base-10 as required by JSON, or non-decimal representations are handled/mitigated. | CSC |  | H4; H5 |  | CS4.5 | AOU-22 |
| C10 | Data is complete and error-free at the component boundary (or boundary corruption is detected/handled). | CSC |  | H5 |  | CS4.6 | AOU-23 |
| C11 | Governance workflow detects/triages/mitigates upstream drift and advisories for the integrated dependency. | CSC | C5 | H7 | UCA6; UCA7; UCA8; UCA9 | CS3.1; CS3.2; CS3.3 | AOU-27; AOU-28; AOU-29; JLS-11 |

---

## 8. Misbehaviours 

In TSF terms, misbehaviours are **anything that can cause a deviation from Expected Behaviour** (`TA-MISBEHAVIOURS_CONTEXT.md`). In this analysis we derive them in two complementary ways:

- **Library misbehaviours (M1–M5)**: the “negative space” of `JLEX-01` / `JLEX-02` and their evidence families.
- **Process/integration misbehaviours (M6–M7)**: violations at the boundary of this component that are explicitly anticipated by the TSF tree (e.g. upstream drift/CVE triage duties via `AOU-28`/`AOU-29`) or are typical for parser integration when input is untrusted (resource exhaustion).

Relative to `JLEX-01` and `JLEX-02`, the following **Misbehaviours (M\*)** are prohibited:

| Misbehaviour Id | Misbehaviour description | Link to hazard(s) |
|---|---|---|
| M1  | Library accepts syntactically ill-formed JSON as well-formed (violation of JLEX-01). | H1; H5 |
| M2  | Library rejects syntactically well-formed JSON that should be accepted (violation of JLEX-01). | H2 |
| M3  | Library produces a parsed `basic_json` value that is not semantically equivalent to the input JSON text (violation of JLEX-02). | H3; H5 |
| M4  | Library hangs or throws for RFC 8259-compliant JSON under practical integration conditions (violation of JLEX-01/02 intent). | H2; H4 |
| M5  | Library behaviour contradicts any specific evidence statement in `WFJ-*`, `TIJ-*`, `NJF-*`, `NPF-*`, or `PJD-*`. | H1; H2; H3; H4; H5 |
| M6  | Integrator/process misbehaviour: upstream bugs/security advisories are not reviewed and known vulnerabilities are not triaged/handled. | H7 |
| M7  | Integrator/environment misbehaviour: untrusted inputs are processed without adequate resource budgets/limits appropriate for the deployment context, enabling resource-exhaustion/DoS. | H6 |

---

## 9. Risk Evaluation

In line with RAFIA, risk evaluation considers:

- **Severity (S)**: impact in typical S-CORE deployments if the misbehaviour occurs,
- **Likelihood (L)**: plausibility given the existing test and analysis evidence,
- **Exposure (E)**: how often S-CORE relies on the behaviour in normal operation.

This repository does not provide quantitative field data, so we use a **qualitative** assessment that is consistent with the TSF evidence model: likelihood is judged primarily from test/analysis coverage, process controls, and (where applicable) CI-based indicators (`JLS-54`, `JLS-55`). The purpose of the table below is therefore *prioritisation and transparency* (“why do we think this is acceptable?”), not a precise probabilistic safety case.

Qualitative evaluation:

| Misbehaviour | S | L | E | Risk Category | Justification |
|--------------|---|---|---|---------------|--------------|
| M1 | High | Very low | High | Medium–High | Would fundamentally break input validation; extensive WFJ/TIJ/NJF/NPF testing mitigates likelihood. |
| M2 | Medium | Very low | Medium | Low–Medium | Mainly availability/robustness impact; no such issues observed in the tested domain. |
| M3 | High | Very low | Medium–High | Medium–High | Data corruption is serious; however, PJD/NPF evidence and regression tests reduce likelihood. |
| M4 | Medium | Very low | Medium–High | Medium | Hangs/crashes can be disruptive; CI robustness evidence reduces likelihood, and AOUs require explicit exception handling where exceptions are expected. |
| M5 | Varies | Very low | Varies | Low–Medium | Any contradiction to specific statements is expected to be detected by the mapped test evidence (CI test runs). CI gates (e.g. coverage/PR-count) help prevent coverage and process degradation, but they are not themselves semantic checks. |
| M6 | High | Low–Medium | Medium–High | Medium–High | Severity is high if a known issue is exploitable; likelihood depends on the effectiveness of the review/triage cadence required by `AOU-28`/`AOU-29`. |
| M7 | Medium–High | Medium | Medium–High | Medium–High | Resource-exhaustion is a common parser threat on untrusted inputs; this TSF tree does not specify concrete resource budgets, so deployment context must define them if availability/deadlines are critical. |


