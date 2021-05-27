# Git 브랜치 모델

Git branch는 하나의 소프트웨어에 여러 개발자가 동시에 다양한 작업을 진행 할 수 있는 유용한 도구입니다. 각자 독립적인 영역에서 여러 용도로 사용할 수 있습니다. 자세한 내용은 [링크](https://backlog.com/git-tutorial/kr/stepup/stepup1_1.html)를 참고합니다.

Github의 프로젝트들은 대부분 몇 가지 브랜치의 용도를 정해두고 운영하고 있습니다. 예를 들어 develop 브랜치는 최신 개발 사항을 계속 담고, master 브랜치는 안정화 된 버전을 관리하는 것입니다. 각 브랜치의 용도를 정하는 방식으로 활용하여 오픈소스 프로젝트를 운영하는 여러 가지 방법들이 있습니다. 그 중 CUBRID는 많은 오픈소스 프로젝트에서 도입하는 [Vincent Drissen 브랜치 모델](https://nvie.com/posts/a-successful-git-branching-model/)을 기반으로 운영하고 있습니다.

#### CUBRID의 브랜치 모델과 VD 모델의 차이 <a id="comparison-vd-cubrid"></a>

Vincent Drissen 모델\(이하 VD 모델\)에서는 영구적으로 유지되는 develop, master 브랜치와 임시 브랜치인 release, feature, hotfix 가 존재합니다. VD 모델과의 차이점은 CUBRID에서는 이전 버전의 릴리즈도 유지보수 하고 있기 때문에 이전 버전의 릴리즈 브랜치도 영구적으로 유지합니다. \(e.g. release/10.2, release/11.0\)  예를 들어 develop 브랜치에서 최신 버전인 12 버전을 개발하고 있더라도, release/10.2라는 브랜치도 10.2.2, 10.2.3 마이너 버전 릴리즈를 위해 계속 유지합니다.

VD 모델에서 최신 버전 릴리즈 과정에서 임시적으로 생성하는 release 브랜치와 동일한 역할을 하는 pre-release 브랜치를 생성합니다. 자세한 설명은 [Release 섹션](../release-1/release.md)을 참조합니다.

하나의 Pull Request로 개발을 완료하기 힘든 프로젝트의 경우 피쳐 브랜치를 활용할 수 있습니다. 피쳐 브랜치에 대한 설명은 다음 별도의 섹션에서 기술합니다.

