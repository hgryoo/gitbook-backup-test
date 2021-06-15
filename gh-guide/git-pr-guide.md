# Pull Request, Code Review, Code Merge

## The Pull Request Format <a id="pull-template"></a>

The subject of a Pull Request \(PR\) should always include the relevant JIRA issue number. However, aside from the issue number, the title of PR does not have to be same as the title of JIRA. A title that best describes the content of the PR is recommended.

The first line of the description of a PR should always include a link to the relevant JIRA issue because it refers to the design-related content in JIRA for code review. In addition, if you write the purpose, concept, and implementation details \(class, function, specific logic\) that are not included in the issue or design document, it will be helpful to follow the change of the code of PR later.

* Purpose: Briefly describe the purpose of the code to be merged in the PR.
* Implementation: in addition to the design written in the JIRA issue or design document,  describe in detail the logic, class, function, etc. if necessary. 
* Remarks: write down the rest of the notes if necessary. 

On the right side of the PR, you can set assignee, reviewers, labels, projects, and milestones. When creating a PR, **only set assignee** and do not use the rest of the fields. Set reviewers before proceeding with code reviews. See the [code review](git-pr-guide.md#code-review) section below. 

## Code Review <a id="code-review"></a>

Design review must be completed with the reviewer prior to assigning/requesting a code review. This is because it is difficult to clearly understand the intent and content of the change with code alone. Therefore, design documents \(Concept, Architecture\) should be shared with project members prior to code review.

* Share the design documents in JIRA
* There is no format for the document
* Reviewers can request material if they need more understanding of the design

After completing the design review, we will proceed with the code review. You can start the code review by assigning reviewers on the right side of the PR. 

It is okay to conduct design review and code review at the same time for simple bug fixes or feature implementations with minor changes such as:

* if there are no spec changes 
* if there are no changes in function behavior 
* if it is small-scale refactoring

## Automation Tool \(CI\) <a id="ci"></a>

We are introducing several automation tools into GitHub PR for effective and efficient code review.   
These tools improve the quality of code and help reviewers not only focus on mistakes but also focus on design and logic issues. 

{% hint style="info" %}
The success or failure of each automation tool is displayed at the bottom of the PR, and detailed information can be found through the 'Details' button on the right side of each banner. If there is any failure, the 'Squash and Merge' button is disabled.
{% endhint %}

![](https://gblobscdn.gitbook.com/assets%2F-MXop1o57DgerzWA1Brs%2F-MY3wjLVMINmnU7kFBx1%2F-MY3x3p3hpum1cPeDNLb%2Fimage.png?alt=media&token=da6683fa-13df-4422-b98b-1802b63fc7fa)

* **license:** Make sure you have the correct form of the license header comments. If there is a problem, the automation tools will fail, and you can check the 'Details' to see which file the problem was found.
* **pr-style:** There is a rule that all PRs must be associated with each JIRA issue, and this issue number must be specified at the beginning of the PR title. pr-style will check this and fail if the rule is not followed.
* **code-style:** Make sure you follow the defined code style to keep your code consistent. Code style is defined using code formatting tools, and code-style uses these tools to check and correct whether the rules are properly followed. If it is different from the rule, it will fail and report it through PR suggestion. Supported languages and code formatting tools include:
  * C: GNU Indent 2.2.11
  * C++: astyle 3.1
  * Java: google java format 1.7
* **cppcheck:** Static analysis can reveal many problems that developers can cause, such as unused variables and NULL references. These errors are easy to make, but they are obvious, so you can only find them by looking at the code without context. Therefore, it is inefficient for reviewers to find and comment on each one. cppcheck catches these problems. If there is an error, it will fail and report using a comment to the PR. In this case, the report shows the number of errors and warnings. More details can be found in 'Details'. If there are no errors and only warnings, the test passes.
* **coverage:** It will check your code coverage and notify you through the [codecov service ](https://app.codecov.io/gh/CUBRID/cubrid)if the line coverage is significantly dropped.

![](https://gblobscdn.gitbook.com/assets%2F-MXop1o57DgerzWA1Brs%2F-MY3wjLVMINmnU7kFBx1%2F-MY3xHiCqEz9X_pgbqU5%2Fimage.png?alt=media&token=12ef6ef8-4dc6-445f-8758-5c2603bc4f2a)

* **Build Tests:** After PR is applied, check that the build is performed correctly in various environments.
  * **appveyor/pr:** Windows
  * **travis-ci/pr:** Ubuntu
  * **circleci: build:** CentOS 7
* **Regression Tests:** Build the source and actually run several SQL syntaxes to ensure that the functionality of the database works correctly. This is part of the numerous tests available on QA Home, and is the minimum requirement for changes to be merged to _develop_ branch. You can check the test cases in the repository [CUBRID/cubrid-testcases](https://github.com/CUBRID/cubrid-testcases).
  * **circleci: test\_sql:** Create a new database, execute various SQL statements, and check whether the expected results are obtained.
  * **cicleci: test\_medium:** Execute various SQL statements in the database where many tables and data are already created, and check whether the expected results are obtained.

### Performing Branch-by-branch Automation Tools <a id="branch-rule"></a>

* Build tests and regression tests work on all branches in the repository.
* The rest of the tools only work on develop, feature/\* and some release branches \(currently release/11.\*\). Especially for feature branches, you need to apply naming conventions for GitHub checks to work properly.

### Guidelines for Failures in Automated Tools Before Code Merge <a id="failure-guide"></a>

**If the merge button is disabled because some required checks do not pass, the assigned developer must discuss with the project maintainer.** In this case, noted that ONLY the project maintainer can merge the 'disabled' PR. project maintainer decide if there is a problem with the automation tool, or an agreement has been reached that the issue reported by the automation tool can be ignored. 

The reasons for the above policy is the specification changes and the QA system has not been updated. In this case, it is necessary to communicate and review the failures in the automation tool while making a merge request to the project maintainer.

{% hint style="info" %}
If you use cppcheck, a static code analysis tool, you may encounter false-positive cases that are actually fine, but report them as errors. If the developer determines that the reported error is false-positive, it can be set to ignore the error after agreement with the reviewer. To do this, we use cppcheck's _Inline Suppression_ function as follows:

arr\[10\] = 0; // cppcheck-suppress arrayIndexOutOfBounds

Basically, the suppression command and target error are set as comments on the line where the error occurred. For details, refer to the [cppcheck manual](http://cppcheck.sourceforge.net/manual.pdf).
{% endhint %}

{% hint style="info" %}
For code-style, separate rules and validation tools are used for C and C++. Each tool is executed by checking the file type. To prevent incorrect formatting when using C++ syntax in C files, GNU indent's control comments function is used as follows:

/\* _\*_INDENT-OFF\* _\*_/ 

&lt;code block&gt;

/\* \*INDENT-ON\* \*/

For details, refer to 1.10 Disabling Formatting in the [GNU Indent manual](https://www.gnu.org/software/indent/manual/html_chapter/indent_1.html).
{% endhint %}

## Request Manual Testing before Code Merge <a id="before-merge"></a>

Before code merging, you can request manual testing by giving the built CUBRID installation file to the QA maintainer to conduct the time-consuming tests which aren't included in PR's automated tools such as shell, HA \(high availability\), heavy and performance tests.

* After the build, the installation files are transferred to the QA maintainer.
* Test can be time-consuming as it is done manually.
* When the test is completed, you can check the result report of the tested version in 'RB--Manual' on the left tab of the QA Home page.

We recommend that you utilize this manual testing when:

* you can specify the test cases or circumstances that need to be checked
* bugs only occur in a complex environment
  * For example, if it is difficult to find a bug with one SQL and simple debugging, it is good to put a debugging log in the code to find out what is happening and use it to check complex cases by running multiple tests in the QA system environment.
* To avoid indiscriminate consumption of QA resources, do not use this procedure for the purpose of TDD.

## Code Merge  <a id="merge"></a>

You cannot merge code without passing the code review. Code can only be merged if it has passed the automated tool and all 'approved' by reviewers. In this case, the 'Squash and Merger' button is activated and you can create a commit to merge to the CUBRID repository.

When proceeding with 'squash and merger', you must write the message by following this format: 

* Title
  * \[issue number\] 
  * the title of the PR
  * Example: \[issue number\] PR title
* Message 

  * First line: the path of the JIRA issue which must be the same as the PR
  * Second line: blank
  * Third line: description of the commit 

Example: 

<table>
  <thead>
    <tr>
      <th style="text-align:left">Title</th>
      <th style="text-align:left">[CBRD-00000] Fix something in somewhere (#0000)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Message</td>
      <td style="text-align:left">
        <p>http://jira.cubrid.org/browse/CBRD-00000
          <br />
        </p>
        <p>This is a description of the commit to be merged</p>
      </td>
    </tr>
  </tbody>
</table>

![](https://lh4.googleusercontent.com/6NPQVjhxTz5ScaPPikg0ZqCoiVMYjL1Td-kc7OJ6u7jVNez2INz6a3ZfZU4yhw-SHSnSyWacay7Yi1Ttjr5IjJSvVxxSrNbBvG7OS3-j8yJXDDw6Smh9qhjtuqrqMsukZb8ybrI5)

Noted that if the QA system is significantly affected after code merge, the QA maintainer can revert the merged commit.  For details, refer to the [Procedure Guide in case of Test Failure \(Regression\)](../workflow-after-code-merging-1/regression.md) in section 'WORKFLOW AFTER CODE MERGING'. 

