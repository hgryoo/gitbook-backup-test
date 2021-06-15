# Feature Branch

새로운 기능 개발 및 버그 수정이 필요할 때에 'develop' 브랜치로부터 분기하여 feature 브랜치를 만들수 있습니다. 이 브랜치는 fork한 내 저장소에서 ‘develop’ 브랜치로부터 분기한 브랜치와는 다릅니다.

Feature Branch의 이름은 다음과 같이 작성합니다.

* feature/&lt;이름&gt;

예시\) feature/javasp, feature/tde, feature/truncate\_table

* 위와 같은 이름으로 설정하면, 자동으로 Github check이 수행될 수 있습니다.

이 브랜치의 주요 목적은 반영할 코드의 규모가 클 때 코드 리뷰를 여러 라운드에 나누어 진행하기 위한 목적입니다. ‘develop’에 개발 할 기능의 일부만을 바로 반영하지 않고 feature 브랜치에서 여러 개의 PR로 효율적인 코드 리뷰와 검증 과정을 거친 후 좀 더 안정적으로 ‘develop’에 반영합니다.

git 명령어는 다음과 같이 참고하여 관리합니다.

```text
# 1. feature 브랜치 생성
git remote add upstream 
http://github.com/cubrid/cubrid

git fetch upstream
git checkout -b feature/my_feature upstream/develop
git push -u upstream feature/my_feature

# 2. github에서 여러 번의 PR
git fetch upstream
git checkout -b CBRD-OOOOO upstream/feature/my_feature
   # many commits (개발 진행)
git push -u origin CBRD-OOOOO
   # PR 생성 후 코드 리뷰
# 2. 를 여러 번 반복 == 여러 번의 리뷰 라운드

# 3. develop과 sync by merge (sync를 위한 커밋은 PR하지 않음)
git checkout feature/my_feature
git fetch upstream
git merge upstream/feature/my_feature // should be fast-forward merging
git merge upstream/develop

# 2. 를 여러 번 반복 == 여러 번의 리뷰 라운드

git push origin CBRD-OOOOO

# CBRD-00000에 대한 PR 생성
```

**참고!** Feature Branch는 임의로 생성할 수 있으며, 기능의 리뷰를 완료하고 develop 브랜치에 머지한 경우 삭제합니다.

