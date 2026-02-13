#### Checklist for TA-BEHAVIOURS from [Codethink](https://pages.eclipse.dev/eclipse/tsf/tsf/print_page.html)

* How has the list of Expectations varied over time?

    **Answer**: The list of expectations is taken from [here](https://eclipse-score.github.io/score/main/modules/baselibs/json/docs/requirements/index.html), whose development can be retraced using git.

* How confident can we be that this list is comprehensive?

    **Answer**:  The list of expectations has been collected amongst the stakeholders in S-CORE, so that we are very confident that the list is comprehensive. 
    The expectation to serialize user data into JSON format 

* Could some participants have incentives to manipulate information?

    **Answer**:  We can not imagine any reason.

* Could there be whole categories of Expectations still undiscovered?

    **Answer**:  It is unlikely, but the parsing of CBOR could become relevant at some time.

* Can we identify Expectations that have been understood but not specified?

    **Answer**:  No.

* Can we identify some new Expectations, right now? 

    **Answer**:  No.

* How confident can we be that this list covers all critical requirements?

    **Answer**:  We can not think of any more critical requirement of a JSON parser in the sense of RFC8259 than to parse JSON data in the sense of RFC8259.

* How comprehensive is the list of tests? 

    **Answer**:  Currently, the branch coverage is 93.865% and the line coverage is 99.186%, cf. JLS-27.

* Is every Expectation covered by at least one implemented test? 

    **Answer**:  Yes, both of the expectations are covered by at least one implemented test. Moreover, each statement supporting the expectations is covered by a test with the exception of WFJ-06.

* Are there any Expectations where we believe more coverage would help?

    **Answer**: No.

* How do dependencies affect Expectations, and are their properties verifiable?

    **Answer**: The library nlohmann/json does not have external dependencies, so that there are in particular none that affect Expectations.

* Are input analysis findings from components, tools, and data considered in relation to Expectations?

    **Answer**:  No findings have been found.
