# QA 리포트 확인

QA 팀에서 테스트 시스템을 운영하기 위해 Jenkins라는 CI 툴을 운영합니다. Pull Request가 반영되면 \(merge\), Jenkins는 Github과 연결되어 있어 반영된 사항을 자동으로 테스트를 진행합니다. \(참고: [http://ci.cubrid.org/blue/organizations/jenkins/cubrid/activity/](http://ci.cubrid.org/blue/organizations/jenkins/cubrid/activity/)\)

Jenkins에서 테스트가 모두 수행되고 그 결과 리포트는 [http://qahome.cubrid.org/](http://qahome.cubrid.org/)에서 확인할 수 있습니다. 페이지의 좌측에서 버전별 테스트 결과 리포트를 확인할 수 있고, 오른쪽에는 최신 테스트 리포트에 대한 요약을 보여줍니다.

![](https://lh5.googleusercontent.com/Mc6GKTZt3lPqo0CegcCJLPt4f2yjU4cQPY2JFgSdCXZzvuL_Z1Pb46nSvA8OgOn7-t9sF9Qqtele70AYo-4RHV8G54hTZGwGpYksDNPW3GiCGq7X82gJx47cgJGV6LvIHcqp0iNn)

좌측에 테스트 결과 리포트를 눌러보면 아래의 그림과 같은 탭이 있습니다. 각각 기능, 성능, 메모리 누수를 테스트한 결과를 보여줍니다. \(제일 우측의 버튼은 개발팀에서 사용하지 않습니다\)

![](https://lh5.googleusercontent.com/nNZLHruKhrpzS6Ex5IEtrJKyqWHl8t49LDWvqVaXFtYqehlIU8O1JngaoaP177_sMNmA4nVHQgEo4xPFG3-zfPOmTralIeH5LeZiAkQsVYRTKY5g3l9GaDSxhDc7wJ-kjyQdAYeR)

{% hint style="info" %}
이메일로 주기적으로 QA 테스트 리포트를 보냅니다.

머지 시 기능 테스트, 성능 테스트, 메모리 릭을 꼭 확인합니다.   
특히 성능 테스트가 5%이상 차이가 나면 문제가 있는지 볼 필요가 있습니다.
{% endhint %}

테스트는 기능적 테스트 \(Function Test\)와 비기능적 테스트 \(Non-Function Test\)로 나누어져 있습니다. 먼저 기능 테스트를 살펴보면, 리눅스와 윈도우 환경에 대해 각각 테스트를 진행하고 있습니다. 현재 윈도우는 리눅스보다 테스트하는 항목의 개수가 적습니다.

![](https://lh5.googleusercontent.com/TMNFZllRWFjMPZbH2c6SIFxp9ksHTl_Yn5yKIitPVvhEbS7DJhX0ptkwzG9YGue4ui2XoWnJ-NJAQqoeLg2MWExaWUVov1-3n9EmqDmFfwT3cyYcymLVo0TvlAz7eLYn1TWaw-mB)

## \*\*\*\*

