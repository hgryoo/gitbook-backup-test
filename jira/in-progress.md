# 작업 진행  &lt;In Progress&gt;

![](https://lh4.googleusercontent.com/7KlnB-eYXzc3gakuyG0shhZ6ko1tOhljTHMxPv7aEFDZGckQUPIjZGjc0c5DivzwOU-s1qOtWFeEyqpZtudLzR0LzE_I_N6Lqkij1bLvYT_WgEPWdcOo0DZ2zeISKlUtJuFQ9OLX)

Triage를 통해 **지정된 개발자\(assign에 의해 개발자가 변경 가능\)**는 “start work” 버튼 후 due date 정한 후 “IN PROGRESS”로 상태로 변경합니다. “IN PROGRESS” 상태에서 개발자는 “Change Status of Dev” 버튼을 눌러 개발 상태를 지정합니다. 개발 상태는 분석, POC, 설계, 설계 리뷰, 구현, 테스트로 구성되며, 개발자는 진행 중인 개발 단계에 맞춰 개발 상태를 변경해야합니다. Pull Request를 생성하면 **Github hook을 통해 JIRA에서 자동으로** “IN PROGRESS” 상태로 변경됩니다.

개발자는 “REVIEW IN PROGRESS” 상태에서 “Propose a change” 버튼을 눌러 “IN PROGRESS” 상태로 되돌릴 수 있습니다. 코드 리뷰를 진행하면서 발견한 문제를 간단한 수정을 통해 해결할 수 없고, 분석 또는 설계에서 고려가 더 필요한 경우 상태를 되돌립니다.

