# 작업 완료  &lt;Resolved&gt;

![](https://lh3.googleusercontent.com/uDyz0pRDxqJk8pkbmloZdr-frBScYs9iJneLTG8byDr2sPYu5ZrmwkPZslU_Szp_MwXT0jQbf02pefCgldLVQfxka0iTC8WrBQlcC1yoMXOabVT-FEUZGeZVHfbeFetIHvU3UaLf)

**담당 개발자**는 리뷰가 완료 \(“REVIEWED”\) 된 이후에 “Check-in Fix” 버튼을 눌러 “RESOLVED” 상태로 변경하고, 해당 이슈를 QA 메인테이너에 이관합니다. QA로 이관 후에는 이슈의 코멘트를 통해 개발자와 QA 담당자가 커뮤니케이션합니다. 

“RESOLVED” 상태로 변경할 때 이슈의 Planned Version/s에 따라 backport를 반영했는지 확인 후 상태를 변경해야 합니다. “RESOLVED”로 상태 변경 시 다음의 필드를 필수로 입력해야 합니다.

* assignee: QA 메인테이너로 변경합니다
* resolution: “Done”
* manual: 매뉴얼 작성 또는 수정이 필요한지 설정합니다. \(need manual\) 
* QA scenario
  * not required : QA 시나리오 추가가 필요하지 않는 경우 \(기본값\)
  * required : QA 시나리오 추가가 필요한 경우
  * revise required : 기존 QA 시나리오의 변경이 필요한 경우
* fix version/s: 해당 이슈가 반영\(merge\)된 버전을 명시합니다. \(이 필드는 QA팀에서 테스트 및 릴리즈를 위해 참조함\)

프로젝트 메인테이너는 생성된 이슈가 버그가 아니라고 판단할 시 “Bug Invalid” 버튼을 눌러 해당 이슈를 “OPEN”상태에서 “RESOLVED”상태로 변경할 수 있습니다. 이후에는 QA 메인테이너가 “CLOSED”상태로 변경하여 이슈를 종료하거나, 다시 버그로 판단해서 “OPEN”으로 돌아올 수 있습니다.

또한 담당 개발자는 이슈 진행 중에 해당 이슈에 대하여 수정할 필요가 없다고 판단 시 “Resolve without fix” 버튼을 눌러 “CONFIRMED” 또는 “IN PROGRESS” 상태에서 “RESOLVED” 상태로 변경할 수 있습니다.

