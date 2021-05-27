# Git Workflow

![](https://lh5.googleusercontent.com/XZvedMM9PA2nvydPhUcphwPIlRTP104GSxHopy_stO59UiSN6OznqbP3m4LwCH3dWViA5V5JztJf1cfNxW4k1qYUpV60DOUrQv0yCR80xqmNAYJvW5P3LxWSeZUdvGKVKrCbfoyE)

Git은 저장소와 관계없이 브랜치만을 기준으로 작업한다고 이해하면 쉽습니다. 따라서 큐브리드 메인저장소와 fork한 내 저장소 간에 sync를 맞추는 작업은 하지 않아도 됩니다. 개발을 진행하기 전 코드를 upstream으로부터 반영 할 브랜치를 가져와 작업을 시작하고, 결과물을 origin에 올리면 됩니다.

다음의 스크립트를 참고할 수 있습니다.

```text
git remote add upstream https://github.com/CUBRID/cubrid.git

git remote -v
#====
#    origin  http://github.com/hgryoo/cubrid (fetch)
#    origin  http://github.com/hgryoo/cubrid (push)
#    upstream        http://github.com/cubrid/cubrid (fetch)
#    upstream        http://github.com/cubrid/cubrid (push)

git fetch upstream

# 작업할 새로운 브랜치 가져오기, upstream으로부터 브랜치 생성!
# git push로 잘못 반영되는 것을 방지하기 위해 
# 아래 두 명령어는 항상 함께 실행해야 합니다.
git checkout -b CBRD-55555_my_work upstream/develop
git push -u origin -b CBRD-55555_my_work

# 작업하기
git add ...
git commit …

# 소스를 올릴 remote 이름과 브랜치 이름을 항상 적어줍니다
git push origin CBRD-55555_my_work

# upstream의 develop의 내용을 반영하고 싶을 때
git fetch upstream
git merge upstream/develop
```

