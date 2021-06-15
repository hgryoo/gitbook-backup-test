# Release

{% hint style="info" %}
_**This section is outside the scope of the contribution guidelines. This section does not describe all the procedures in detail, therefore is for reference only. Please read the version information and the outline procedure for release only for reference.**_
{% endhint %}

## **Version** <a id="version"></a>

#### Build Number <a id="build-number"></a>

The build number of CUBRID follows the following rules:‌

* Major.Minor.Patch.Revision
  * e.g\) 11.1.0.0512.2d9a03248
  * The patch increases based on the commit count from the time of the previous release.
  * Revision is recorded with the commit hash at the time of build.

#### Code Name <a id="code-name"></a>

Before the major and minor versions are released, they have a code name as shown in the following example:‌

* Fruit Name
  * elderberry \(11.1\)
  * damson \(11.0\)
  * cherry \(10.2\), cherry sherbet
  * banana \(10.0\), banana pie \(10.1\)
* The version number can always be changed.
*  After release, it is managed by the version number instead of the code name.

## **Release milestones** <a id="release-milestones"></a>

​![](https://lh4.googleusercontent.com/0AxC9zczV3htxgIfTH1anATwGarYNjlxyQPDxuvWZzUxCxu82PXfAFIBA6HW3NHlAoha0dviVj3k_ILJVM3xIPYZbUVcx60WZ8AhXNjQzHX7_1nf8PILFSKX42A0C7mFDxTUANDP)‌

Major version release follows the following milestones:‌

* Code Freeze
  * CC \(Code Complete\): All major changes are completed
  * ZAB \(Zero Active Bug\): All triaged issues are resolved
* ZRB \(Zero Resolved Bug\): All resolved issues are closed
* FTC \(Full Test Complete\): Full tests for release are succeed
  * GA \(General Availability build\): Distribute the release version

### Release Procedure <a id="undefined"></a>

* After Code Freeze, a pre-release branch from develop is created and managed.
* To achieve ZRB, patch regression for major changes in the pre-release branch.
* In ZRB, a full test is conducted for release.
* The patch for the major change applied to the pre-release branch to resolve the regression from the test for release in FTC is ported to develop.
* If the patch is sufficiently verified before the FTC, you can port it with development in advance.
* In GA, pre-release change to release, and pre-release is removed.

In the case of releases and hotfixes of previous versions other than the latest major version, we do not create a pre-release branch but perform a full test for the backported code base.

