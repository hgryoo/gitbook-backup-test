# Backport

backport란 새로운 버전의 기능 및 수정사항을 이전 버전에 반영하는 것입니다. 예를 들어 CUBRID 11에서 발견되어 고쳐진 버그를 CUBRID 10.2.1 버전에서도 발생하여 마찬가지로 고쳐야 하는 경우 backport를 진행합니다.

이 경우 Github 도구의 관점에서 보면 develop 브랜치에 반영된 커밋을 release/10.2 브랜치에 반영하는 것입니다. 이 때 주의할 사항은 **여러 버전에 반영해야 하는 기능이나 버그 수정의 경우 반드시 develop에 먼저 커밋을 반영하고 release에 backport 해야 합니다.** QA regression 결과 확인 및 추가 패치를 통해 검증된 패치를 이전 버전에 backport 할 수 있기 때문에 이전 버전의 안정성을 해치는 것을 최소화 할 수 있습니다. 만약 develop에서 발생하지 않는 경우 release에만 반영합니다.

backport 시 다음을 참고하여 진행합니다.

* 여러 버전에 한꺼번에 반영할 때는 develop 브랜치에 우선 반영해야 합니다.
* develop에서 먼저 반영한 commit이 안정적인지 확인합니다.
* git cherry-pick을 활용하면 대부분의 경우 쉽게 backport 할 수 있습니다.

```text
#git 명령어 예시 
git checkout develop
git log // backport 할 commit id 찾기
git checkout release/10.2
git cherry-pick <commit-id>
```

* conflict 발생 시에는 수정 후 PR을 생성합니다.
* backport 과정에서 버그가 발생하는 경우 수정하고, 관련 내용을 JIRA에 기록합니다.

backport PR 생성 시 다음을 참고합니다.

* PR 생성 시 PR 제목 마지막에 **develop에 반영된 PR의 번호**를 함께 기록합니다.
  * 예시\) \[CBRD-OOOOO\] Fix this issue: develop에 반영하는 PR, \#235 \[CBRD-OOOOO\] Fix this issue \(\#235\) : release/10.2에 반영하는 PR
* PR 내용에도 다음과 같이 원본 PR의 번호를 기록합니다. backport 뒤의 PR 번호는 자동적으로 github에서 링크로 만들어주는 것을 볼 수 있습니다.

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

backport 시 JIRA에 업데이트해야 할 내용은 다음을 참고합니다.

* QA 이관 전
  * Planned Version\(s\) 중 최신버전 \(develop\) 과 backport 대상 버전에 대해 모두 PR 생성
  * 각 PR에 대해 코드 리뷰 후 머지 완료
  * 개발자는 해당 JIRA 이슈에 PR 반영된 버전을 Fixed version\(s\) 기록
* QA 이관
  * “Resolved” 상태로 바꾸기
* QA는 테스트 완료 후 이슈를 “Close” 상태로 변경

