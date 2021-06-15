# Checking the QA Report

The QA team uses a CI tool called Jenkins to run the test system. When the Pull Request is merged, Jenkins is connected to Github and automatically tests the merged commit. \(Reference: [http://ci.cubrid.org/blue/organizations/jenkins/cubrid/activity/](http://ci.cubrid.org/blue/organizations/jenkins/cubrid/activity/)\)

All tests are performed in Jenkins, and the result report is available at [http://qahome.cubrid.org/](http://qahome.cubrid.org/). On the left side of the page, you can see the test result report by version and a summary of the latest test report is displayed on the right side.



![](https://lh5.googleusercontent.com/Mc6GKTZt3lPqo0CegcCJLPt4f2yjU4cQPY2JFgSdCXZzvuL_Z1Pb46nSvA8OgOn7-t9sF9Qqtele70AYo-4RHV8G54hTZGwGpYksDNPW3GiCGq7X82gJx47cgJGV6LvIHcqp0iNn)

If you click the test result report on the left, there is a tab as shown in the figure below. Each shows the results of testing for function, performance, and memory leaks. \(The button on the first right 'verify status' is not used by the development team\).

![](https://lh5.googleusercontent.com/nNZLHruKhrpzS6Ex5IEtrJKyqWHl8t49LDWvqVaXFtYqehlIU8O1JngaoaP177_sMNmA4nVHQgEo4xPFG3-zfPOmTralIeH5LeZiAkQsVYRTKY5g3l9GaDSxhDc7wJ-kjyQdAYeR)

{% hint style="info" %}
Meanwhile, QA test reports are sent periodically by email if you register in the developer mailing lists.

Make sure to check for functional tests, performance tests, and memory leaks when merging. In particular, if the performance test degrades by more than 5%, it is necessary to see if there is a problem.
{% endhint %}

The test is divided into a functional test and a non-function test. In terms of the functional tests, we are conducting tests for Linux and Windows environments respectively. Windows currently test fewer items than Linux.

![](https://lh5.googleusercontent.com/TMNFZllRWFjMPZbH2c6SIFxp9ksHTl_Yn5yKIitPVvhEbS7DJhX0ptkwzG9YGue4ui2XoWnJ-NJAQqoeLg2MWExaWUVov1-3n9EmqDmFfwT3cyYcymLVo0TvlAz7eLYn1TWaw-mB)

