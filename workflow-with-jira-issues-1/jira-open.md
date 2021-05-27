# JIRA 이슈 등록 &lt;OPEN&gt;

![](https://lh6.googleusercontent.com/xDu3uXZSeudPuHLxxa7Zb3LGpgWM-W8xswuiSGuGq56gqmPXerHG0c3WWfFzXhF5Ip2mJc-MXdiJ8g6CeTwIKHVC1EMzPYuADKFy4oYoC82vl85XIp2q6abWA2EazADgc3gLPTT6)

새로운 프로젝트를 시작하거나 버그를 발견한 경우에 Jira 이슈를 생성합니다. 이슈 생성 절차 및 작성할 항목은 이슈 작성 절차에서 설명합니다. 이슈의 초기 상태는 “OPEN”으로 설정되지만, Triage를 통해 승인을 받기 위해서는 이슈 작성 완료 후 메인테이너에서 이슈를 assign 해야 합니다. 

이후 이슈의 상태에서 필요에 따라 다시 “OPEN” 상태로 되돌아갈 수 있습니다.  이슈를 진행하는 중에 어떤 상태에서도 \(CONFIRMED, IN PROGRESS, REVIEW IN PROGRESS, REVIEWED\) 해당 이슈에 대한 재확인이 필요한 경우 “Ask Confirmation/Reconfirmation” 버튼을 눌러 이슈의 상태를 “OPEN” 으로 되돌리고, 프로젝트 메인테이너를 Assignee로 지정합니다. 또한, 완료된 \(CLOSED\) 이슈도 추후에 문제가 발생되면 “Reopen Bug” 버튼을 눌러 해당 이슈의 상태를 “OPEN” 으로 변경할 수 있습니다. 해결된 \(RESOLVED\) 이슈는 담당 개발자가 없는 경우에만 “OPEN” 으로 변경하여 메인테이너에게 전달합니다.

{% hint style="info" %}
이슈를 생성할 때에는 하나의 이슈로 여러 문제를 다루지 말고, 가급적 문제를 쪼개어 여러 이슈로 나누어 처리하는 것이 좋습니다.
{% endhint %}

## 이슈 작성 절차 <a id="how-to-create"></a>

1. JIRA \(jira.cubrid.org\)에 로그인 후 상단의 오렌지색 “CREATE” 버튼을 클릭합니다.

![](../.gitbook/assets/image%20%283%29.png)

![](../.gitbook/assets/image%20%282%29.png)

2. 새로 열린 “CREATE Issue” 창에서 각 필드를 다음 표의 설명에 맞게 작성하고 하단의 “Create” 버튼을 클릭합니다.

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Field</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Project</td>
      <td style="text-align:left">
        <p>&#xD504;&#xB85C;&#xC81D;&#xD2B8; &#xBC94;&#xC8FC;&#xB97C; &#xC120;&#xD0DD;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <ul>
          <li>CBRD: CUBRID CAS, DB SERVER</li>
          <li>APIS: CCI, JDBC &#xB4F1; Driver</li>
          <li>CUBRIDMAN: CUBRID &#xB9E4;&#xB274;&#xC5BC;</li>
          <li>TOOLS: CUBRID Manager, CUBRID Migration Tool</li>
          <li>CUBRIDQA: QA &#xC2DC;&#xC2A4;&#xD15C;, QA &#xD14C;&#xC2A4;&#xD2B8; &#xCF00;&#xC774;&#xC2A4;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Issue Type</td>
      <td style="text-align:left">
        <p>&#xC774;&#xC288;&#xC758; &#xC131;&#xACA9;&#xC5D0; &#xB9DE;&#xB294; &#xD0C0;&#xC785;&#xC744;
          &#xC120;&#xD0DD;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <p>&#xC790;&#xC138;&#xD55C; &#xB0B4;&#xC6A9;&#xC740;&#x201C;<a href="jira-open.md#issue-types">Issue Type</a>&#x201D;
          &#xC139;&#xC158;&#xC744; &#xCC38;&#xACE0;&#xD569;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Summary</td>
      <td style="text-align:left">&#xC774;&#xC288;&#xC758; &#xC81C;&#xBAA9;&#xC744; &#xC785;&#xB825;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">Priority</td>
      <td style="text-align:left">
        <p>&#xAE30;&#xBCF8;&#xAC12;&#xC778; Minor&#xB85C; &#xD56D;&#xC0C1; &#xC9C0;&#xC815;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <p>&#xBA54;&#xC778;&#xD14C;&#xC774;&#xB108;&#xAC00; Triage &#xC2DC;&#xC5D0;
          &#xD544;&#xC694;&#xD558;&#xB2E4;&#xBA74; &#xBCC0;&#xACBD;&#xD569;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Components</td>
      <td style="text-align:left">
        <p>&#xBAA8;&#xB4C8; &#xB2E8;&#xC704; &#xB610;&#xB294; &#xD504;&#xB85C;&#xC81D;&#xD2B8;
          &#xB2E8;&#xC704;&#xC758; &#xBC94;&#xC8FC;&#xB97C; &#xC9C0;&#xC815;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <p>&#xC790;&#xC138;&#xD55C; &#xB0B4;&#xC6A9;&#xC740; &#x201C;<a href="jira-open.md#component">Component</a>&#x201D;
          &#xC139;&#xC158;&#xC5D0;&#xC11C; &#xC124;&#xBA85;&#xD569;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Description</td>
      <td style="text-align:left">&#x201C;&#xC774;&#xC288; &#xB0B4;&#xC6A9; &#xD15C;&#xD50C;&#xB9BF;&#x201D;&#xC744;
        &#xCC38;&#xACE0;&#xD558;&#xC5EC; &#xC791;&#xC131;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">Affects version/s</td>
      <td style="text-align:left">&#xC774;&#xC288; &#xC0DD;&#xC131;&#xC790;&#xAC00; &#xBD84;&#xC11D; &#xACFC;&#xC815;&#xC5D0;&#xC11C;
        &#xBC84;&#xADF8;&#xB098; &#xBB38;&#xC81C;&#xB97C; &#xCC3E;&#xC740; &#xBC84;&#xC804;&#xC744;
        &#xAE30;&#xB85D;&#xD569;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">Label</td>
      <td style="text-align:left">
        <p>&#xC790;&#xC720;&#xB86D;&#xAC8C; &#xC124;&#xC815;&#xD560; &#xC218; &#xC788;&#xC2B5;&#xB2C8;&#xB2E4;.</p>
        <p><em>* &#xBA54;&#xC778;&#xD14C;&#xC774;&#xB108;&#xAC00; &#xAD00;&#xB9AC;&#xD558;&#xB294; &#xB808;&#xC774;&#xBE14;: cubrid.com, Good First Issue</em>
        </p>
      </td>
    </tr>
  </tbody>
</table>

#### 

## Issue Types

<table>
  <thead>
    <tr>
      <th style="text-align:left">Type name</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Correct Error</td>
      <td style="text-align:left">&#xBC84;&#xADF8; &#xB610;&#xB294; &#xC5D0;&#xB7EC;&#xB97C; &#xC218;&#xC815;&#xD558;&#xB294;
        &#xC774;&#xC288;&#xC785;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">Improve Function/Performance</td>
      <td style="text-align:left">&#xAE30;&#xC874;&#xC758; &#xAE30;&#xB2A5;&#xC744; &#xAC1C;&#xC120;&#xD558;&#xAC70;&#xB098;
        &#xC131;&#xB2A5;&#xC744; &#xD5A5;&#xC0C1;&#xC2DC;&#xD0A4;&#xB294; &#xC774;&#xC288;&#xC785;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">Development Subject</td>
      <td style="text-align:left">&#xC0C8;&#xB85C;&#xC6B4; &#xAE30;&#xB2A5;&#xC744; &#xCD94;&#xAC00;&#xD558;&#xB294;
        &#xC774;&#xC288;&#xC785;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">Internal Management</td>
      <td style="text-align:left">
        <p>&#xB0B4;&#xBD80; &#xAD00;&#xB9AC;&#xB97C; &#xC704;&#xD55C; &#xC774;&#xC288;&#xC785;&#xB2C8;&#xB2E4;.</p>
        <p>&#xC678;&#xBD80; &#xAE30;&#xC5EC;&#xC640; &#xAD00;&#xB828;&#xC5C6;&#xB294;
          &#xBCC0;&#xACBD;&#xC77C; &#xACBD;&#xC6B0;&#xC5D0; &#xC0AC;&#xC6A9;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <p>&#xC608;) &#xD504;&#xB85C;&#xADF8;&#xB7A8; &#xB610;&#xB294; &#xCF54;&#xB4DC;
          &#xB0B4; &#xBC84;&#xC804; &#xBCC0;&#xACBD; 10.2.0 -&gt; 11.0.0</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Refactoring</td>
      <td style="text-align:left">&#xBD88;&#xD544;&#xC694;&#xD55C; &#xCF54;&#xB4DC; &#xC815;&#xB9AC;, &#xCF54;&#xB4DC;
        &#xAD6C;&#xC870; &#xBC0F; repo &#xBD84;&#xB9AC; &#xB4F1;&#xC744; &#xBCC0;&#xACBD;&#xD558;&#xB294;
        &#xC774;&#xC288;&#xC785;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">Task</td>
      <td style="text-align:left">&#xC704; &#xC774;&#xC288; &#xD0C0;&#xC785;&#xC5D0; &#xD574;&#xB2F9;&#xD558;&#xB294;
        &#xBC94;&#xC8FC;&#xAC00; &#xC5C6;&#xC744; &#xACBD;&#xC6B0; &#xC0AC;&#xC6A9;&#xD558;&#xC9C0;&#xB9CC;,
        &#xAD8C;&#xC7A5;&#xD558;&#xC9C0; &#xC54A;&#xC2B5;&#xB2C8;&#xB2E4;. (&#xC0AC;&#xC6A9;
        &#xC608; : release)</td>
    </tr>
    <tr>
      <td style="text-align:left">Sub-task</td>
      <td style="text-align:left">
        <p>&#xC774;&#xC288; &#xB0B4;&#xBD80;&#xC5D0; &#xC0DD;&#xC131;&#xB418;&#xB294;
          &#xC791;&#xC740; &#xB2E8;&#xC704;&#xC758; &#xC774;&#xC288;&#xC77C; &#xACBD;&#xC6B0;
          &#xC0AC;&#xC6A9;&#xD569;&#xB2C8;&#xB2E4;.</p>
        <p>&#xC704;&#xC758; &#xC774;&#xC288; &#xD0C0;&#xC785;&#xC758; sub issue&#xB85C;
          &#xC0AC;&#xC6A9; &#xAC00;&#xB2A5;&#xD569;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
  </tbody>
</table>

#### 

## Component

{% tabs %}
{% tab title="CBRD" %}
| **Category Component** |
| :--- |
| QP SM DS Utility |

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Module Component</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p>Build</p>
        <p>CI</p>
        <p>Coding Style</p>
        <p>Community</p>
        <p>Document</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>Broker/CAS</p>
        <p>Server Communication</p>
        <p>CSQL</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>Query Parser
          <br />Query Semantic Check
          <br />Query Rewriter</p>
        <p>Query Optimizer
          <br />XASL Generator</p>
        <p>Query Executor</p>
        <p>Scan Manager</p>
        <p>Schema Manager</p>
        <p>Java SP</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>Backup/Restore</p>
        <p>Buffer pool
          <br />Catalog
          <br />Disk/File
          <br />DWB
          <br />FBO</p>
        <p>Heap
          <br />Index
          <br />Locator</p>
        <p>Lock
          <br />Log/Recovery</p>
        <p>MVCC
          <br />TDE
          <br />Transaction</p>
        <p>Vacuum</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>Failover
          <br />HA
          <br />Heartbeat
          <br />Logcopier
          <br />Logapplier</p>
        <p>Replication</p>
      </td>
    </tr>
  </tbody>
</table>
{% endtab %}

{% tab title="APIS" %}
| **Module Component** |
| :--- |
| ADO.NET CCI GO  JDBC Node.js ODBC OLEDB PDO Perl PHP Python Ruby |
{% endtab %}

{% tab title="TOOLS" %}
| **Module Component** |
| :--- |
| CM Server CUBRID Manager CUBRID Migration Toolkit CUBRID Monitoring Query Browser Tools development |
{% endtab %}
{% endtabs %}

Component는 모듈 단위로 설정합니다. Component는 계층 구조로 구성되며 점점 세분화 됩니다. 이슈에서 다수의 Component를 선택할 수 있습니다. 위의 탭은 각 프로젝트 별 큐브리드 프로젝트에서 사용할 수 있는 Component입니다. 표에서 보는 것과 같이 CUBRID는 SM, QP, JavaSP, DS, Utility 등을 포함하고, 각 모듈 또한 다수의 모듈을 포함합니다. 

이슈 생성 시, 해당 시점에 알 수 있는 연관 모듈을 선택합니다. 이슈를 분석하는 과정에서는 해당 이슈와 연관된 모듈 정보를 추가 선택할 수 있습니다. 예를 들어 SM 모듈에서 Buffer Manager를 개선하는 이슈인 경우, 이슈 생성 시 CUBRID, SM, Buffer를 선택할 수 있고, 이슈 진행 중에 File, Lock 모듈에 영향을 주는 경우 추가 선택할 수 있습니다.

CTE, TDE, JSON, Java SP등 여러 모듈에 영향을 주는 프로젝트인 경우 새로운 component를 생성하여 설정할 수 있습니다. 필요한 경우 프로젝트 메인테이너에게 요청하여 새로운 component를 생성할 수 있습니다.

## **이슈 내용 템플릿** <a id="template"></a>

{% hint style="info" %}
이슈 생성 시 이슈 타입에 따라 다음의 템플릿을 복사하고, 필요한 항목을 작성합니다.   
&gt; 필요한 경우 섹션을 추가 가능  
&gt; 템플릿의 섹션은 필요 없는 경우 제거하지 않고 N/A로 남겨두고 작성  
&gt; 아직 작성하지 못한 필드에 대해서는 TBD로 적어두고 확정되면 내용을 작성
{% endhint %}

템플릿은 이슈 타입에 따라 세가지 형태를 사용합니다.

#### **Correct Error**

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p><b>Description</b>
        </p>
        <p>&lt;b&gt;&lt;/b&gt;</p>
        <p><b>Test Build</b>
        </p>
        <p>&lt;b&gt;&lt;/b&gt;</p>
        <p><b>Repro</b>
        </p>
        <p>&lt;b&gt;&lt;/b&gt;</p>
        <p><b>Expected Result<br /></b>
        </p>
        <p><b>Actual Result<br /></b>
        </p>
        <p><b>Additional Information<br /></b>
        </p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

* **Description:** 이슈 설명
* **Test Build:** Repro, Actual Result와 동일한 현상을 보여주는 빌드 버전을 commit 번호까지 상세히 기입합니다. 예를 들어 다음과 같이 기입할 수 있습니다:  `CUBRID-11.0.0.0248-b53ae4a` JIRA 필드의 Affected version/s은 Major와 Minor 버전까지만 표시하는 반면, Patch와 Revision을 포함하여 실제로 버그가 발생한 구체적인 버전 명을 입력해야합니다. 버전명의 규칙은 [Release/Version](../release-1/release.md#version) 섹션을 참고합니다. 빌드한 OS의 버전도 함께 명시할 수 있습니다.
* **Repro:** 버그를 재현하기 위한 절차를 입력합니다. 버그 재현에 대한 설명을 적기 보다는 환경 재현/스키마 생성/질의 실행/유틸리티 실행 등의 모든 절차를 복사-붙여넣기로 재현 할 수 있도록 작성해야합니다.
* **Expected Result:** 기대 결과 \(고쳐져야 할 예상 결과\)
* **Actual Result:** 현재 결과 \(문제가 있는 결과\)
* **Additional Information:** 추가로 버그 분석과 이해에 도움을 주기 위해 참고할 자료나 내용이 있다면 적어줍니다.

**예시\)** [**CBRD-23903**](http://jira.cubrid.org/browse/CBRD-23903)

#### **Improve Function/Performance, Development Subject, Refactoring**

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p><b>Description<br /></b>
        </p>
        <p><b>Specification Changes<br /></b>
        </p>
        <p><b>Implementation<br /></b>
        </p>
        <p><b>Acceptance Criteria</b>
        </p>
        <p>&lt;b&gt;&lt;/b&gt;</p>
        <p><b>Definition of done</b>
        </p>
        <p>&lt;b&gt;&lt;/b&gt;</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

* Description: 이슈에 대한 설명을 적습니다.
* Specification Changes : 변경될 스펙을 정리하여 작성합니다. QA 테스트 정의, 매뉴얼 작성 등에서 활용할 수 있습니다.
* Implementation: 이슈를 해결하기 위해 디자인 명세, 구현 컨셉 및 상세를 작성합니다.
* Acceptance Criteria: 해당 이슈에 대해 요구사항에 따라 디자인과 구현을 수행하면서 선택하게 된 이슈의 범위 내에서 만족해야 하는 동작/결과를 정의합니다. 이 내용은 디자인/구현의 완료 판단\(리뷰\)의 기준이 됩니다. 만약 정의하지 않은 동작/결과가 크리티컬 하다면 디자인/구현에 대해 재검토할 필요가 있습니다.
* Definition of done: 이슈를 완료하기 위해 어떠한 방법으로 검증할 수 있을지를 작성합니다. 다음 예시와 같이 기입할 수 있습니다.
  * Acceptance Criteria를 만족시킨다.
  * QA 테스트를 통과한다.

**예시\)** [**CBRD-23894**](http://jira.cubrid.org/browse/CBRD-23894)  
****

#### **Task, internal management**

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p><b>Description</b>
        </p>
        <p>&lt;b&gt;&lt;/b&gt;</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

* Description: 작업 내용에 대한 목적과 설명을 적습니다.

