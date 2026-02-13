#### Checklist for TA-MISBEHAVIOURS from [Codethink](https://pages.eclipse.dev/eclipse/tsf/tsf/print_page.html)

* How has the list of misbehaviours varied over time?

    **Answer**:  The list of misbehaviours is collected using github and its development is thereby understandable.

* How confident can we be that this list is comprehensive?

    **Answer**:  Due to the collaborative nature of the open source community, we deem it quite unlikely that there are any known misbehaviours which are not reported to the repository nlohmann/json.

* How well do the misbehaviours map to the expectations?

    **Answer**:  There are no identified misbehaviours that tangent the expectations.

* Could some participants have incentives to manipulate information?

    **Answer**:  We could not think of an incentive that any collaborateur could have to manipulate the information.

* Could there be whole categories of misbehaviours still undiscovered?

    **Answer**:  Due to the wide use and long-standing development of the library it is quite unlikely that any major misbehaviors, in particular regarding the parsing and validating of JSON data in the sense of RFC-8259, is undiscovered. 

* Can we identify misbehaviours that have been understood but not specified?

    **Answer**:  No.

* Can we identify some new misbehaviours, right now?

    **Answer**:  No.

* Is every misbehaviour represented by at least one fault induction test?

    **Answer**:  Since there are no misbehaviours that concern the use within S-CORE, no.

* Are fault inductions used to demonstrate that tests which usually pass can and do fail appropriately?

    **Answer**:  ?????? No.

* Are all the fault induction results actually collected?

    **Answer**:  ?????? No.

* Are the results evaluated?

    **Answer**:  ?????? No.

* Do input analysis findings on verifiable tool or component claims and features identify additional misbehaviours or support existing mitigations?

    **Answer**:  Currently, there is no analysis which identifies additional misbehaviours. The only such analysis is indirectly via the analysis of the fuzz testing, which currently does not identifies additional misbehaviours.