# Procedure Guide in case of Test Failure \(Regression\)

If the QA team found a problem with the change merged after verification in the test tool, which greatly affects the QA system, **the QA team can revert the commit of the change and return the JIRA issue to the 'CONFIRMED' status**. At this point, if the developer decides that the issue needs a triage again, it can revert to the 'OPEN' status.

The failure of resolving the following problems immediately can affect the QA system:

* If some or all of the systems are shut down \(a core file is created\)
* If the system stops \(hang\)
* If the behavior is different from that defined in the issue and design documents 
* If too many test case failures occur
* If significant performance degradation occurs

If the QA system continues to operate while the above situation persists, then the QA system will be unreliable for the changes which are proceeding simultaneously; therefore, the robustness of the system would be broken**,** and the subsequent costs of identifying the problem will increase exponentially. 

Returning JIRA to the 'OPEN' status means going back to the design, implementation, and code review phase according to the JIRA Workflow. If reconfirmation is required at each step, it is recommended to proceed by creating a feature branch.

