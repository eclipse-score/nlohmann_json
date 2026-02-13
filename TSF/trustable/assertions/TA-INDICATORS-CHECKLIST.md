#### Checklist for TA-INDICATORS from [Codethink](https://pages.eclipse.dev/eclipse/tsf/tsf/print_page.html)

* How appropriate/thorough are the analyses that led to the indicators?

    **Answer**:  Since no misbehaviours for the use of the library for parsing and verification of JSON data according to RFC8259 have been identified, no warning indicators are implemented.

* How confident can we be that the list of indicators is comprehensive? 

    **Answer**:  There are no warning indicators implemented, of which we are very confident.

* Could there be whole categories of warning indicators still missing?

    **Answer**:  Yes, there could. Within S-CORE, however, any warning indicator that is not natively implemented within the original nlohmann/json should be implemented in the wrapper defining the interface between the library and the project using it.

* How has the list of advance warning indicators varied over time?

    **Answer**:  It has stayed constant.

* How confident are we that the indicators are leading/predictive?

    **Answer**: There are none.

* Are there misbehaviours that have no advance warning indicators?

    **Answer**:  There are no misbehaviours identified.

* Can we collect data for all indicators? 

    **Answer**:  There are currently no implemented indicators, so that no data are collected.

* Are the monitoring mechanisms used included in our Trustable scope? 

    **Answer**:  No, but there are also none.

* Are there gaps or trends in the data? 

    **Answer**:  There are no data where gaps or trends could be identified.

* If there are gaps or trends, are they analysed and addressed?

    **Answer**:  There are no data.

* Is the data actually predictive/useful?

    **Answer**:  There are no data.

* Are indicators from code, component, tool, or data inspections taken into consideration?

    **Answer**:  There are no indicators.