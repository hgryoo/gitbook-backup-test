# Feature Branch

In the case of developing new features and fix bugs, you can ask the CUBRID committers to create a _feature_ branch in the _develop_ branch.

Create the name of the Feature Branch as follows: 

* feature/&lt;name&gt;

example\) feature/javasp, feature/tde, feature/truncate\_table

* If you set the name as above, The Github Checks can be performed automatically.

The main purpose of the _feature_ branch is to divide the code review into several rounds when the size of the code to be merged is large. Rather than merging only a part of the function in the _develop_ branch, the _feature_ branch will conduct efficient code review with multiple PRs and merge them more reliably in the _develop_ branch.

Note that git commands are managed as follows:

```text
# 1. create feature branch 
git remote add upstream 
http://github.com/cubrid/cubrid

git fetch upstream
git checkout -b feature/my_feature upstream/develop
git push -u upstream feature/my_feature

# 2. Multiple PRs on github
git fetch upstream
git checkout -b CBRD-OOOOO upstream/feature/my_feature
   # many commits (development in progress)
git push -u origin CBRD-OOOOO
   # Code review after PR creation
# 2. Repeat multiple times == multiple review rounds

# 3. sync with develop by merge (do not PR commit for sync)
git checkout feature/my_feature
git fetch upstream
git merge upstream/feature/my_feature // should be fast-forward merging
git merge upstream/develop

# 2. Repeat multiple times == multiple review rounds

git push origin CBRD-OOOOO

# Create PR for CBRD-00000
```

\*Note: _Feature_ branches can be created at any time, and will be deleted after the feature has been reviewed and merged into the _develop_ branch.

