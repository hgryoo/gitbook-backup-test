# &lt;OPEN&gt;: Register a JIRA issue



![](https://lh6.googleusercontent.com/xDu3uXZSeudPuHLxxa7Zb3LGpgWM-W8xswuiSGuGq56gqmPXerHG0c3WWfFzXhF5Ip2mJc-MXdiJ8g6CeTwIKHVC1EMzPYuADKFy4oYoC82vl85XIp2q6abWA2EazADgc3gLPTT6)

When you start a new project or if you find a bug, you can start your contribution by creating a JIRA issue. The issues creation process and field values that you need to specify according to the issue types are described in the ‘Issue Creation Procedure’ section below. 

You can revert from any statuses of the issue to the status 'OPEN' as needed. In any status during the ongoing status \(CONFIRMED, IN PROGRESS, REVIEW IN PROGRESS, REVIEWED\), if you need to recheck the issue, press the 'Ask Confirmation/Reconfiguration' button to return the issue to 'OPEN' and specify the project maintainer as assignee. 

In addition, if a problem occurs in the closed \(‘CLOSED’ status\) issue later, you can change the status of the issue back to 'OPEN' by clicking the 'Reopen Bug' button. Resolved \(‘RESOLVED’ status\) issues are changed to 'OPEN' and delivered to the project maintainer only when there is no developer in charge.

When creating an issue, it is recommended not to deal with multiple issues as one single issue, but to divide the issues into several issues as much as possible.

## Issue Creation Procedure  <a id="how-to-create"></a>

1. After logging in to CUBRID Jira website \(jira.cubrid.org\), click the orange 'CREATE' button at the top.

![](https://gblobscdn.gitbook.com/assets%2F-MXop1o57DgerzWA1Brs%2F-MY3vc6mfIBJdc6TLzNy%2F-MY3vnnFL5s_jZ_q1Izb%2Fimage.png?alt=media&token=ce8f7177-5e16-406c-b95d-23421ee99600)

![](https://gblobscdn.gitbook.com/assets%2F-MXop1o57DgerzWA1Brs%2F-MY3vc6mfIBJdc6TLzNy%2F-MY3vhlfYcxz3E1ZWU5L%2Fimage.png?alt=media&token=5205cba1-80b9-418d-b0ec-9fbb38c9ca9b)

2. In the newly opened 'CREATE Issue' window, fill in each section as described in the following table and click the 'Create' button at the bottom.

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Field</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Project</td>
      <td style="text-align:left">
        <p>Select a project category.</p>
        <p>&#xB7; CBRD: CUBRID CAS, DB SERVER</p>
        <p>&#xB7; APIS: Driver such as CCI, JDBC</p>
        <p>&#xB7; CUBRIDMAN: CUBRID manual</p>
        <p>&#xB7; TOOLS: CUBRID Manager, CUBRID Migration Tool</p>
        <p>&#xB7; CUBRIDQA: QA system, QA test case</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Issue Type</td>
      <td style="text-align:left">Select the type of issue. For more information, refer to the &apos;Issue
        Type&apos; section below.</td>
    </tr>
    <tr>
      <td style="text-align:left">Summary</td>
      <td style="text-align:left">Enter the title of the issue.</td>
    </tr>
    <tr>
      <td style="text-align:left">Priority</td>
      <td style="text-align:left">The default setting is &#x2018;Minor&#x2019;. However, at the time of
        triage, the project maintainer can change the level of priority if necessary.</td>
    </tr>
    <tr>
      <td style="text-align:left">Components</td>
      <td style="text-align:left">Specifies the category of module units or project units. Details are described
        in the &apos;Component&apos; section below.</td>
    </tr>
    <tr>
      <td style="text-align:left">Description</td>
      <td style="text-align:left">Fill in by referring to the &#x2018;issue content template&#x2019; section
        below.</td>
    </tr>
    <tr>
      <td style="text-align:left">Affects version/s</td>
      <td style="text-align:left">Fill in the version in which the issue creator found bugs.</td>
    </tr>
    <tr>
      <td style="text-align:left">Label</td>
      <td style="text-align:left">
        <p>Type any registered label.</p>
        <p>* Label managed by project maintainer: cubrid.com, Good First Issue</p>
      </td>
    </tr>
  </tbody>
</table>

## Issue Types <a id="issue-types"></a>

<table>
  <thead>
    <tr>
      <th style="text-align:left">Type name</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Correct Error</td>
      <td style="text-align:left">Issue that fixes bugs or errors.</td>
    </tr>
    <tr>
      <td style="text-align:left">Improve Function/Performance</td>
      <td style="text-align:left">Issue that improves existing features or performance.</td>
    </tr>
    <tr>
      <td style="text-align:left">Development Subject</td>
      <td style="text-align:left">Issue that adds new features.</td>
    </tr>
    <tr>
      <td style="text-align:left">Internal Management</td>
      <td style="text-align:left">
        <p>Issue for internal management. Use when changes are not related to contributions.</p>
        <p>e.g. changing the version name within a program or code from 10.2.0 to
          11.0.0.0</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Refactoring</td>
      <td style="text-align:left">Issue that changes unnecessary code clean-up, code structure, and repository
        separation.</td>
    </tr>
    <tr>
      <td style="text-align:left">Task</td>
      <td style="text-align:left">The issue type is applied if there is no category corresponding to the
        above issue type but is not recommended. (Example of use: release)</td>
    </tr>
    <tr>
      <td style="text-align:left">Sub-task</td>
      <td style="text-align:left">This issue type is applied when an issue is a small unit created inside
        the issue.</td>
    </tr>
  </tbody>
</table>

## Component <a id="component"></a>

{% tabs %}
{% tab title="CBRD" %}
| **Category Component** |
| :--- |
| QP SM DS Utility |

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Module Component</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p>Build</p>
        <p>CI</p>
        <p>Coding Style</p>
        <p>Community</p>
        <p>Document</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>Broker/CAS</p>
        <p>Server Communication</p>
        <p>CSQL</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>Query Parser
          <br />Query Semantic Check
          <br />Query Rewriter</p>
        <p>Query Optimizer
          <br />XASL Generator</p>
        <p>Query Executor</p>
        <p>Scan Manager</p>
        <p>Schema Manager</p>
        <p>Java SP</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>Backup/Restore</p>
        <p>Buffer pool
          <br />Catalog
          <br />Disk/File
          <br />DWB
          <br />FBO</p>
        <p>Heap
          <br />Index
          <br />Locator</p>
        <p>Lock
          <br />Log/Recovery</p>
        <p>MVCC
          <br />TDE
          <br />Transaction</p>
        <p>Vacuum</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>Failover
          <br />HA
          <br />Heartbeat
          <br />Logcopier
          <br />Logapplier</p>
        <p>Replication</p>
      </td>
    </tr>
  </tbody>
</table>
{% endtab %}

{% tab title="APIS" %}
| **Module Component** |
| :--- |
| ADO.NET CCI GO  JDBC Node.js ODBC OLEDB PDO Perl PHP Python Ruby |
{% endtab %}

{% tab title="TOOLS" %}
| **Module Component** |
| :--- |
| CM Server CUBRID Manager CUBRID Migration Toolkit CUBRID Monitoring Query Browser Tools development |
{% endtab %}
{% endtabs %}

The component is set in module unit. Components are organized in a hierarchical structure and are increasingly subdivided. You can select multiple components in an issue. The above table are the components available for each project-specific CUBRID project. As shown in the table, CUBRID includes SM, QP, JavaSP, DS, Utility, etc., and each module also includes multiple modules.

When creating an issue, select the relevant module that is known at that time. In the process of investigating an issue, you can additionally select module information related to the issue. For example, in the case of an issue that improves the Buffer Manager in the SM module, you can select CUBRID, SM, or Buffer when creating an issue, and if it affects the File and Lock module while the issue is in progress, you can additionally select the Disk/File AND Lock module.

For projects that affect multiple modules, such as CTE, TDE, JSON, and Java SP, you can create and configure a new component. If necessary, you can ask the project maintainer to create a new component.

## **Issue Content Template** <a id="template"></a>

{% hint style="info" %}
When creating an issue, copy the following template according to the issue type and write the necessary items:

&gt; You can add sections if needed.  
&gt; If you do not need a section in the template, do not remove it and fill in with 'N/A'.  
&gt; If the fields can not be filled out, write down 'TBD' and fill in the content when it is confirmed.
{% endhint %}

In the following template, three types of issue are displayed.

#### **Correct Error**

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p><b>Description</b>
        </p>
        <p>&lt;b&gt;&lt;/b&gt;</p>
        <p><b>Test Build</b>
        </p>
        <p>&lt;b&gt;&lt;/b&gt;</p>
        <p><b>Repro</b>
        </p>
        <p>&lt;b&gt;&lt;/b&gt;</p>
        <p><b>Expected Result<br /></b>
        </p>
        <p><b>Actual Result<br /></b>
        </p>
        <p><b>Additional Information</b>
        </p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

* **Description:** Issue Description ****
* **Test Build:** Detail the build version that shows the same format as Repro, Actual Result to commit number. For example, you can write:  `CUBRID-11.0.0.0248-b53ae4a` Affected version/s in the JIRA field displays only the Major and Minor versions, while you must enter the specific version name where the bug actually occurred, including Patch and Revision. For version name rules, refer to the [Release/Version](../rel/release.md) section.  You can also specify the version of the OS you built.
* **Repro:** Enter the procedure to reproduce the bug. Rather than writing a description of bug reproduction, all procedures such as environment reproduction, schema creation, query execution, and utility execution should be written so that they can be reproduced by copy-paste.
* **Expected Result:** Expected results \(expected results to be fixed\)
* **Actual Result:** Current results \(problematic results\)
* **Additional Information:** If there is any additional material or content that can be helpful to understand the bug, please write it down.

**Example\)** [**CBRD-23903**](http://jira.cubrid.org/browse/CBRD-23903)​

#### \*\*\*\*

#### **Improve Function/Performance, Development Subject, Refactoring**

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p><b>Description<br /></b>
        </p>
        <p><b>Specification Changes<br /></b>
        </p>
        <p><b>Implementation<br /></b>
        </p>
        <p><b>Acceptance Criteria</b>
        </p>
        <p>&lt;b&gt;&lt;/b&gt;</p>
        <p><b>Definition of done</b>
        </p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

* **Description:** Issue Description
* **Specification Changes:** Organize and write the specifications to be changed. It can be used for defining QA tests, writing manuals, etc.
* **Implementation:** Create design specifications, implementation concepts and details to address issues.
* **Acceptance Criteria:** Define behaviors/results that must be satisfied within the scope of the issue you have chosen while conducting design and implementation according to your requirements. This content is the basis for the completion to review the design/implementation. If undefined behavior/results are critical, design/implementation needs to be reviewed. 
* **Definition of done:** Write down the criteria of the completion of the issue. You can write as the following example:
  * Satisfies the Acceptance Criteria. 
  * Pass the QA test.

**Example\)** [**CBRD-23894**](http://jira.cubrid.org/browse/CBRD-23894)



#### **Task, internal management**

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p><b>Description</b>
        </p>
        <p>&lt;b&gt;&lt;/b&gt;</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

* **Description:** Write down the purpose and description of the work.

