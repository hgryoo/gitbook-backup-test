# Git Workflow



![](https://lh5.googleusercontent.com/XZvedMM9PA2nvydPhUcphwPIlRTP104GSxHopy_stO59UiSN6OznqbP3m4LwCH3dWViA5V5JztJf1cfNxW4k1qYUpV60DOUrQv0yCR80xqmNAYJvW5P3LxWSeZUdvGKVKrCbfoyE)

It's easy to understand that Git works only on branches, regardless of the repository. So, contributors do not have to do the sync between the main repository of CUBRID and their own forked repository.

Before proceeding with development, you only need to get a branch from upstream, start work. When you want to merge your work on the upstream \(main\) repository after some commits, you push the changes to your origin \(forked\) repository.

After pushing your changes on your origin \(forked\) repository, you can make a Pull Request.

You can refer to the following script: 

```text
git remote add upstream https://github.com/CUBRID/cubrid.git

git remote -v
#====
#    origin  http://github.com/hgryoo/cubrid (fetch)
#    origin  http://github.com/hgryoo/cubrid (push)
#    upstream        http://github.com/cubrid/cubrid (fetch)
#    upstream        http://github.com/cubrid/cubrid (push)

git fetch upstream

# Get a new branch to work on, create a branch from upstream!
# To prevent being reflected incorrectly by git push
# The two commands below must always be executed together.
git checkout -b CBRD-55555_my_work upstream/develop
git push -u origin -b CBRD-55555_my_work

# Add and commit your changes during your work
git add src/you/code
git commit -m 'code change'

# NOTE: Always write the remote name and branch name to prevent 
#       uploading to wrong remote
# Push your changes to your remote repository 
git push origin CBRD-55555_my_work

# When you want to get and sync with upstream's change
git fetch upstream
git merge upstream/develop
```

