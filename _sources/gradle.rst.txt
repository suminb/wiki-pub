Gradle
======

Running Specific Tasks
----------------------

.. code::

    gradle test --tests SomeTest

.. code::

    gradle test --tests org.gradle.SomeTest.someSpecificFeature
    gradle test --tests *SomeTest.someSpecificFeature
    gradle test --tests *SomeSpecificTest
    gradle test --tests all.in.specific.package*
    gradle test --tests *IntegTest
    gradle test --tests *IntegTest*ui*
    gradle test --tests *IntegTest.singleMethod
    gradle someTestTask --tests *UiTest someOtherTestTask --tests *WebTest*ui

https://stackoverflow.com/questions/22505533/how-to-run-only-one-test-class-on-gradle
