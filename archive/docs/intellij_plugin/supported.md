# Supported technologies

### Project management tool

Today, ponicode works only with projects that use **Maven** as their project management tool (version 3.x.x).

<p align="center">
    <img src="intellij_plugin/images/maven-logo.png" alt="input-column-selector" width="160"/>
</p>

You can install Ponicode directly from [the marketplace](https://plugins.jetbrains.com/plugin/17980-ponicode) or install it directly from within your IDE. For more information about how to install and setup Ponicode, check out our dedicated documentation page on how to [Get Started](intellij_plugin/setup)

### Test framework

Ponicode now generates tests in the tests that uses the test **JUnit5** test framework.

<p align="center">
    <img src="intellij_plugin/images/junit5-banner.png" alt="input-column-selector" width="160"/>
</p>

This implies that to run the tests your project must have JUnit5 set up. Do not hesitate to check [their documentation](https://junit.org/junit5/docs/current/user-guide/#running-tests-build-maven) to configure your project to run the tests

### Limitations

Ponicode will generate your tests for the functions it supports. It is important to know that at the time Ponicode is able to generates tests for functions where the arguments are either [primitive types](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html) or classes that are defined inside the project itself.
In other world **if your function takes a class which is external to the project as argument, Ponicode won't support it** ! Note that the standard library is considered as external to the project.
