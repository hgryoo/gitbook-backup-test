# Pull Request, Code Review, Code Merge

## Pull Request 내용 구성 <a id="pull-template"></a>

Pull Request의 제목에는 항상 관련된 JIRA 이슈 번호를 기입해야 합니다. 그러나 이슈 번호 외에 JIRA의 제목 PR의 제목이 동일할 필요는 없습니다. Pull Request의 내용을 가장 잘 설명할 수 있는 제목이면 좋습니다.

Pull Request의 설명 첫 줄에는 항상 관련된 JIRA의 링크를 첨부해야 합니다. 코드 리뷰를 위해 JIRA에서 설계에 관련한 내용을 참조하기 위함입니다. 또한, 이슈나 설계 문서에서 담지 못한 구현 디테일 \(클래스, 함수, 특정 로직\) 의 목적, 구현, 참고사항 등을 작성하면 이후 코드 분석에 도움이 됩니다.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Title</th>
      <th style="text-align:left">[CBRD-OOOOO] Pull Request Title</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Description</td>
      <td style="text-align:left">
        <p><a href="http://jira.cubrid.org/browse/CBRD-OOOOO">http://jira.cubrid.org/browse/CBRD-OOOOO</a>
          <br
          />
        </p>
        <p>Purpose</p>
        <p>N/A
          <br />
        </p>
        <p>Implementation</p>
        <p>N/A
          <br />
        </p>
        <p>Remarks</p>
        <p>N/A</p>
      </td>
    </tr>
  </tbody>
</table>

* Purpose: PR에서 반영하려는 코드의 설명, 목적을 간단하게 기술합니다.
* Implementation: JIRA 이슈나 설계서에 작성된 설계 외에 반영할 코드와 관련하여 구현하는 로직, 클래스, 함수 등의 설명을 자세히 설명할 필요가 있다면 기술합니다.
* Remarks: 나머지 참고 사항을 적습니다.

Pull Request의 우측에는 assignees, reviewers, labels, projects, milestone을 설정할 수 있습니다. Pull Request 생성 시 **assignees만 입력하고 나머지 필드는 사용하지 않습니다.** reviewers는 코드 리뷰를 진행하기 전에 등록합니다. 다음의 [코드 리뷰](pr-guide.md#undefined) 섹션을 참조합니다.

## 코드 리뷰 <a id="code-review"></a>

코드 리뷰를 지정/요청하기 전 리뷰어에게 설계 디자인 리뷰를 완료해야 합니다. 코드 만으로는 변경의 의도와 내용을 명확히 파악하기 힘들기 때문입니다. 따라서 디자인 문서 \(Concept, Architecture\) 를 프로젝트 구성원에게 코드 리뷰 이전에 공유해야 합니다.

* JIRA에 디자인 문서를 공유
* 문서의 형식은 자유
* 리뷰어가 설계 디자인에서 더 이해가 필요한 경우 자료 요청 가능

설계 디자인 리뷰를 완료하면, 코드 리뷰를 진행합니다. PR 우측의 Reviewers를 설정하여 코드 리뷰를 시작합니다.

다음과 같은 변경이 크지 않은 간단한 버그 수정이나 기능 구현은 설계 디자인 리뷰와 코드 리뷰를 동시에 진행하는 것도 괜찮습니다.

* 스펙 변경이 없음
* 기능 동작의 변경이 없음
* 규모가 크지 않은 리팩토링

## 자동화 도구 \(CI\)

효과적/효율적인 코드 리뷰를 위해 Github PR에 여러 자동화 도구들을 도입하고 있습니다. 이 도구들은 코드의 품질을 높이고 리뷰어가 단순 실수가 아닌 설계 디자인과 로직 문제에 집중할 수 있도록 도와줍니다. 

{% hint style="info" %}
Pull Request 하단에 각 자동화 도구의 성공여부가 표시되고, Details를 통하여 자세한 정보를 확인할 수 있습니다. 하나라도 실패가 있다면 PR을 반영하는 “Squash and Merge” 버튼이 비활성화 됩니다.
{% endhint %}

![](../.gitbook/assets/image%20%284%29.png)

* **license:** 올바른 형태의 라이센스 헤더 주석을 가지고 있는지 확인합니다. 문제가 있다면 실패하고, 어떤 파일을 확인하다 문제가 발견되었는지는 Details를 통해 확인할 수 있습니다.
* **pr-style:** 모든 Pull Request  \(PR\)들이 각각의 JIRA 이슈와 연결되어야한다는 규칙을 가지고 있고, 이 이슈 번호가 PR 제목의 앞부분에 명시되어야 합니다. pr-style은 이를 확인하고 규칙을 어겼다면 실패합니다.
* **code-style:** 일관성 있는 코드 유지를 위해 정의된 코드스타일을 따르는지 확인합니다. 코드 스타일은 코드 포맷팅 도구들을 이용하여 정의 되며, code-style은 이 도구들을 이용해 정해진 규칙을 올바르게 따르는지 확인하고 수정합니다. 만약 규칙과 다르다면 실패하고 PR의 suggestion을 통해 리포트 합니다. 지원하는 언어와 코드 포맷팅 도구를 다음과 같습니다.
  * C: GNU Indent 2.2.11
  * C++: astyle 3.1
  * Java: google java format 1.7
* **cppcheck:** 사용되지 않는 변수, NULL 참조 등 개발자가 저지를 수 있는 많은 문제들이 정적 분석을 통해 발견될 수 있습니다. 이러한 오류들은 실수하기 쉽지만 명백하여 문맥없이 코드를 살펴보는 것만으로 찾아낼 수 있습니다. 그렇기에 리뷰어가 일일이 찾아내고 코멘트를 다는 것은 낭비입니다. cppcheck은 이러한 문제들을 잡아냅니다. 에러가 있을 경우 실패하고 PR에 코멘트를 사용하여 리포트 합니다. 이 때 리포트는 에러와 경고의 갯수입니다. 자세한 내용은 Details 를 통해 확인할 수 있습니다. 만약 에러는 없고 경고만 있다면 테스트는 통과합니다.
* **coverage:** 코드 커버리지를 확인하고, 수치가 떨어진 경우 [codecov 서비스](https://app.codecov.io/gh/CUBRID/cubrid)로 알려줍니다.

![](../.gitbook/assets/image%20%285%29.png)

* **Build Tests:**  PR이 적용된 후에도 각종 환경에서 올바르게 빌드가 수행되는지 확인합니다.
  * **appveyor/pr:** Windows 
  * **travis-ci/pr:** Ubuntu
  * **circleci: build:** CentOS 7
* **Regression Tests:**  소스를 빌드하고 실제로 여러 SQL 구문을 수행하여 데이터베이스의 기능들이 올바르게 동작하는지 확인합니다. 이는 QA Home에서 확인할 수 있는 수많은 테스트의 일부이며, 변경사항이 develop에 반영되기 위한 최소한의 충족요건입니다. [CUBRID/cubrid-testcases](https://github.com/CUBRID/cubrid-testcases) 저장소에서 테스트들을 확인할 수 있습니다.
  * **circleci: test\_sql:** 새로운 데이터베이스를 생성하여 각종 sql 문들을 수행하고 기대한 결과가 나오는지 확인합니다.
  * **cicleci: test\_medium:** 이미 많은 테이블들과 데이터들이 생성되어 있는 데이터베이스에서 각종  sql 문들을 수행하고 기대한 결과가 나오는지 확인합니다.

### 브랜치 별 자동화 도구 수행 <a id="branch-rule"></a>

* Build Tests와 Regression Tests는 저장소 내의 모든 브랜치에서 동작합니다.
* 나머지 도구들은 develop, feature/\* 및 일부 릴리즈 브랜치 \(현재 release/11.\*\)에서만 동작합니다. 특히 feature 브랜치의 경우 이름 규칙을 적용해야 github check가 올바르게 작동합니다.

### 코드 머지 전 자동화 도구에서 실패 시 가이드라인 <a id="failure-guide"></a>

**자동화 도구에서 통과되지 않아 반영 버튼이 비활성화 되어 있는 경우, CUBRID 프로젝트 메인테이너와 논의 후 메인테이너가 직접 반영해야 합니다.** 이 경우, 자동화 도구에 문제가 있다고 판단되거나, 자동화 도구에서 보고된 문제를 무시해도 된다는 합의를 거친 것입니다. 이러한 정책의 이유는 다음과 같습니다. 자동화 도구에서 검사하는 것은 기존의 동작의 변경되었는지를 확인합니다. PR의 코드 변경이 개발자의 의도와 상관 없이 스펙 변경이 발생했을 수도 있습니다. 이 경우 프로젝트 메인테이너에게 머지 요청을 하면서 자동화 도구에서 실패한 사항에 대해서 커뮤니케이션과 검토 과정을 거쳐야 합니다.

{% hint style="info" %}
정적코드 분석 도구인 cppcheck를 사용하면 실제로는 문제가 없지만 에러\(error\)라고 보고하는 false-positive 케이스가 발생할 수 있습니다. 개발자가 보고된 에러를 false-positive라고 판단할 경우 리뷰어와의 합의를 거쳐 해당 에러를 무시하도록 설정할 수 있습니다. 이를 위해 다음과 같이 cppcheck의 _Inline Suppression_ 기능을 사용합니다.

arr\[10\] = 0; // cppcheck-suppress arrayIndexOutOfBounds  

기본적으로 에러가 발생한 라인에 주석으로 suppression 명령과 타킷에러를 설정합니다. 자세한 내용은 [cppcheck manual](http://cppcheck.sourceforge.net/manual.pdf) 을 참고합니다.
{% endhint %}

{% hint style="info" %}
code-style의 경우 C와 C++에 대해 별도의 규칙과 확인 도구들이 사용됩니다. 각 도구들은 파일 타입을 확인하여 실행되는데, C 파일에서 C++ 문법을 사용할 경우에 잘못된 포매팅 \(formatting\)을 막기 위하여 다음과 같이 GNU indent의 _control comments_ 기능을 사용합니다.

/\* _\*_INDENT-OFF\* _\*_/  
&lt;code block&gt;  
/\* \*INDENT-ON\* \*/

자세한 내용은 [GNU Indent manual](https://www.gnu.org/software/indent/manual/html_chapter/indent_1.html)의 1.10 Disabling Formatting 을 참고합니다.  
{% endhint %}

## 코드 머지 전 검증 <a id="before-merge"></a>

코드 머지 전 PR의 자동화 도구에 포함되지 않는 테스트를 미리 검증하기 위해 QA 팀에 빌드된 파일을 전달하여 수동 검증을 요청할 수 있습니다. 다음의 절차로 진행합니다.

* 빌드 후 설치 파일을 QA 팀에 이관합니다.
* 테스트는 수동으로 진행하기 때문에 시간이 소요될 수 있습니다.
* 테스트가 완료되면 QA Home 페이지 왼쪽 탭의 RB-&lt;version&gt;-Manual에서 테스트한 버전의 결과 리포트를 확인 할 수 있습니다.

다음의 경우 이 검증을 활용하는 것을 권장합니다.

* 검증해야 하는 테스트 케이스 또는 상황을 특정할 수 있는 경우
* QA의 테스트 케이스가 복합적으로 돌아야 발생하는 버그
  * 예를 들어 하나의 SQL과 간단한 디버깅으로 버그를 찾기 힘든 경우, 확인을 위한 디버깅 로그를 코드에 넣어두고 QA 시스템 환경에서 여러 테스트가 돌도록 하여 복잡한 경우를 확인하는 용도로 사용하면 좋습니다.
* QA 자원의 무분별한 소모를 막기 위해 TDD의 용도로 이 절차를 활용하지 않도록 합니다.

## 코드 머지 <a id="merge"></a>

코드 리뷰를 통과하지 않고 코드를 머지할 수 없습니다. 자동화 도구에서 검증되었고, 리뷰어가 모두 “Approved” 한 경우에 머지할 수 있습니다. 이 경우 “Squash and Merge” 버튼이 활성화 되고, 저장소에 반영하는 커밋을 생성할 수 있습니다.

코드 머지 \(Squash and Merge\) 시 다음의 포맷으로 메시지를 작성해야 합니다.

* Title
  * \[이슈 번호\] 작성
  * PR의 제목과 동일해야합니다
* Message
  * 첫 줄에는 PR과 동일하게 JIRA 이슈의 경로를 작성합니다.
  * 둘째 줄은 비워둡니다.
  * 셋째 줄부터 반영하는 commit에 대한 설명을 작성합니다.

예시\)

<table>
  <thead>
    <tr>
      <th style="text-align:left">Title</th>
      <th style="text-align:left">[CBRD-00000] Fix something in somewhere (#0000)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Message</td>
      <td style="text-align:left">
        <p>http://jira.cubrid.org/browse/CBRD-00000
          <br />
        </p>
        <p>This is a description of the commit to be merged</p>
      </td>
    </tr>
  </tbody>
</table>

![](https://lh4.googleusercontent.com/6NPQVjhxTz5ScaPPikg0ZqCoiVMYjL1Td-kc7OJ6u7jVNez2INz6a3ZfZU4yhw-SHSnSyWacay7Yi1Ttjr5IjJSvVxxSrNbBvG7OS3-j8yJXDDw6Smh9qhjtuqrqMsukZb8ybrI5)

참고로 코드 머지 후 QA 시스템에 크게 영향을 주는 경우 QA 팀에서 해당 머지된 commit을 revert 할 수 있습니다. 자세한 내용은 Workflow after code merging의 [테스트 실패 \(regression\) 발생 시 절차 가이드](../workflow-after-code-merging-1/regression.md)를 참고합니다.

