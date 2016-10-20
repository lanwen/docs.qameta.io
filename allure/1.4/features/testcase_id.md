---
title: Test Case ID
layout: docs
product: allure
version: 1.4
---

# Test Case ID

> This feature is supported **since Allure 1.4.6**.

**Test Case ID** is reference to test case in so-called [Test Management System](https://en.wikipedia.org/wiki/Test_management) (TMS). It is not allowed to have more than one reference per test case by definition.

### What it looks like
![issues](/{{page.product}}/{{page.version}}/img/testcase_id.png)

### Annotations
To link a [test case](https://github.com/allure-framework/allure-core/wiki/Glossary#test-case) to Test Management System, you can use **@TestCaseId** annotation. Simply specify the test case ID as shown below:
```java
@TestCaseId("TMS-1")
public void testSomething() {
     ...
}
```
### Test Management System URL
To specify TMS URL, use the *allure.tests.management.pattern* property **during HTML report generation** (either in the **allure.properties** file or as your build tool property):

- JVM property: 
`-Dallure.tests.management.pattern=http://tms.company.com/tests/%s`
- CI server Allure plugin configuration (supported at least in Jenkins)
- allure.properties:
```properties
allure.tests.management.pattern=http://tms.yourcompany.com/tests/%s
```

In this pattern, the **%s** placeholder will be replaced with the test case ID from the annotation.