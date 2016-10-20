---
title: Parameters
layout: docs
product: allure
version: 1.4
---

# Parameters

#### Environment and test case properties

[Parameter](https://github.com/allure-framework/allure-core/wiki/Glossary#parameter) is any value describing your test environment or current test case. A parameter can store something that doesn't change during all tests (such as the test stand address), or something that changes from test case to test case (such as the test page URL).

Adding parameters in Java looks like this (see https://github.com/allure-framework/allure-core/pull/286):
```java
public class TestClass {
    ...
    @Parameter("My Param")
    private String myParameter;
    ...
}
```
Any value assigned to such a field will be shown in the report.
