# Release

_**이 섹션은 개발 가이드라인 범위는 벗어나있지만 참고할만한 내용이기 때문에 모든 절차가 자세히 기술되진 않았습니다. 버전 정보와 릴리즈를 위한 개략적인 절차를 참고로만 읽어주세요.**_

## **Version**

#### Build Number

큐브리드의 빌드 번호는 다음과 같은 규칙을 가집니다.

* Major.Minor.Patch.Revision
  * e.g\) 11.1.0.0512.2d9a03248
  * Patch는 이전 릴리즈 시점부터 commit count를 기준으로 증가합니다.
  * Revision은 빌드 시점의 commit hash가 입력됩니다.

#### Code Name

Major와 Minor 버전 릴리즈 시 다음의 예시와 같이 코드 네임을 가집니다.

* 과일 이름
  * elderberry \(11.1\)
  * damson \(11.0\)
  * cherry \(10.2\), cherry sherbet
  * banana \(10.0\), banana pie \(10.1\)
* 버전 번호는 항상 바뀔 수 있습니다.
* 릴리즈 후에는 코드 네임 대신 버전 번호로 관리합니다.

## **Release milestones**

![](https://lh4.googleusercontent.com/0AxC9zczV3htxgIfTH1anATwGarYNjlxyQPDxuvWZzUxCxu82PXfAFIBA6HW3NHlAoha0dviVj3k_ILJVM3xIPYZbUVcx60WZ8AhXNjQzHX7_1nf8PILFSKX42A0C7mFDxTUANDP)

Major 버전 릴리즈 시에 다음과 같은 마일스톤을 가집니다.

* Code Freeze
  * CC \(Code Complete\): All major changes are completed
  * ZAB \(Zero Active Bug\): All triaged issues are resolved
* ZRB \(Zero Resolved Bug\): All resolved issues are closed
* FTC \(Full Test Complete\): Full tests for release are succeed
  * GA \(General Availability build\): Distribute the release version

### 릴리즈 절차

* Code Freeze 후 develop로부터 pre-release 브랜치를 생성하여 관리합니다.
* ZRB 달성을 위해 pre-release 브랜치에 major change에 대한 regression 패치를 합니다.
* ZRB에서 release를 위한 full test를 진행합니다.
* FTC에서 release를 위한 테스트로부터 regression 해결을 위해 pre-release 브랜치에 적용한 major change에 대한 패치를 develop으로 port 합니다.
* FTC 이전에 패치가 충분히 검증 되었다면 미리 develop으로 port 할 수 있습니다.
* GA 시 pre-release는 release로 만들고 제거합니다.

최신 메이저 버전이 아닌 이전 버전의 릴리즈와 핫픽스의 경우 pre-release 브랜치를 생성하지 않고, develop으로부터 backport 후 full test를 진행하고 릴리즈합니다.

