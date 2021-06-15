# Backport

A backport is to bring the features and fixes of a new version to a previous version. For example, if a bug which is found and fixed in CUBRID latest version, also occurs in CUBRID 10.2.1 and needs to be fixed, then backporting is performed.

In this case, from the Github tool's point of view, the commit which is merged in the develop branch is merged bacak to the release/10.2 branch. **Note that in the case of a feature or bug fix that needs to be merged in multiple versions, you must first merge the commit in the develop branch and then backport the commit to the release.** Qualified patches can be backported to previous versions by checking QA regression results therefore the damage to the stability of the previous version can be minimized. If the bug does not occur in develop, it will be merged only in release.

When proceeding the backport, refer to the following process:  

* If you want to merge a commit on several versions, you must first merge on the develop branch.
* Check whether the commit first merged in develop branch is stable.
* Applying git cherry-pick would makes the whole backporting easier. 

```text
#git command example 
git checkout develop
git log // Find the commit id to backport
git checkout release/10.2
git cherry-pick <commit-id>
```

* When a conflict occurs, create a PR which contain 2 commits: one for backporting and one for fixing the conflict. 
* If a bug occurs during the backport process, fix it and write down the description of the bug and the fix in the JIRA comment. 

Note the following when creating a backport PR:

* When creating a PR, write the PR number merged in develop at the end of the PR title.
  * example\) 
    * \[CBRD-OOOOO\] Fix this issue: PR merged in develop\#235 
    * \[CBRD-OOOOO\] Fix this issue \(\#235\): PR merged in release/10.2
* Also write down the number of the original PR as follows: You can see that the PR number after the backport is automatically created as a link on GitHub.

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>http://jira.cubrid.org/browse/CBRD-OOOOO
          <br />
        </p>
        <p>backport #235</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>



