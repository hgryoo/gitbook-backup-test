# &lt;Resolved&gt;: Task Complete



![](https://lh3.googleusercontent.com/uDyz0pRDxqJk8pkbmloZdr-frBScYs9iJneLTG8byDr2sPYu5ZrmwkPZslU_Szp_MwXT0jQbf02pefCgldLVQfxka0iTC8WrBQlcC1yoMXOabVT-FEUZGeZVHfbeFetIHvU3UaLf)

After the review is completed \('REVIEWED'\), the **developer in charge** presses the 'Check-in Fix' button to change the status to 'RESOLVED', and transfers the issue to the QA maintainer. After transferring to QA, the developer and QA engineer in charge communicate through comments on the issue.

When changing to the 'RESOLVED' status, you have to change the status after checking whether the backport is merged according to the _Planned Version/s_ of the issue. When changing the status to 'RESOLVED', the following fields are required: 

* assignee: change to QA maintainer 
* resolution: 'Done'
* manual: Set whether manual creation or revision is required. \(need manual\)
* QA scenario
  * not required: if adding QA scenario is not required \(default\)
  * required: if additional QA scenarios are required
  * revise required: When changes to an existing QA scenario are required / if an existing QA scenario needs to be changed
* fix version/s: specifies the version in which the issue is merged. \(This field is referenced by the QA maintainer for testing and release\)

When the project maintainer determines that the created issue is not a bug, the project maintainer can change the issue from 'OPEN' to 'RESOLVED' by pressing the 'Bug Invalid' button. After that, the QA maintainer can change the status to 'CLOSED' to close the issue; or return to 'OPEN 'as a bug again.

In addition, the developer in charge can change from 'CONFIRMED' or 'IN PROGRESS' to 'RESOLVED' by pressing the 'Resolve without fix' button if he or she determines that the issue does not need to be modified during the process.

