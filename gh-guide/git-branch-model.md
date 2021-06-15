# Git Branch Model

Git branch is a useful tool that allows multiple developers to work on multiple tasks at the same time on one piece of software for multiple purposes. For more detail, please refer to the [link](https://backlog.com/git-tutorial/kr/stepup/stepup1_1.html).

Most of the Github projects have serveral branches set for the purpose. For example, the _develop_ branch keeps the latest developments, and the _master \(or main\)_ branch manages the stable versions. There are several ways to run an open source project by leveraging each branch in a purposeful way.  CUBRID is operated based on the [Vincent Drissen branch model](https://nvie.com/posts/a-successful-git-branching-model/) which has been applied by many open source projects.

## CUBRID's Branch Model VS. VD Branch Model  <a id="comparison-vd-cubrid"></a>

In the _Vincent Drissen model_ \(hereinafter referred to as the VD model\), there are permanently maintained branches such as develop, master, and temporary branches such as release, feature, and hotfix. The difference between the CUBRID branch model and the VD model is that in the CUBRID branch model, we maintain the released version's branch permanently, \(e.g. release/10.2, release/11.0\). For example, even if the develop branch is on the latest version 12, the release/10.2 is also maintained for minor version upgrade releases 10.2.2, 10.2.3, 10.2.4...

In the VD model, a pre-release branch is created and it performs the same role as the release branch which is temporarily created during the release of the latest version. For more details, please see the [Release Section](../rel/release.md).

For issues that are difficult to complete with one Pull Request, you can utilize a feature branch. Feature branches are described in a separate section that follows.

