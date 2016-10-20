---
title: Issues
layout: docs
product: allure
version: 1.4
---

# Issues

> This feature is supported **since Allure 1.4.1**.

**Issues** are any software problems that are stored in so-called [issue trackers](http://en.wikipedia.org/wiki/Issue_tracking_system). When any of these problems is fixed, a test should be created to prevent it from appearing in the future. 

### What it looks like
![issues](/{{page.product}}/{{page.version}}/img/issues.png)

### Annotations
To link a [test case](https://github.com/allure-framework/allure-core/wiki/Glossary#test-case) or a [test suite](https://github.com/allure-framework/allure-core/wiki/Glossary#test-suite) to such issues, you can use **@Issue** annotation. Simply specify the issue key as shown below:
```java
@Issue("MYISSUE-1")
public void testSomething() {
     ...
}
```
To add multiple issues, use **@Issues** annotation:
```java
@Issues({
    @Issue("MYISSUE-1"),
    @Issue("MYISSUE-2")
})
public void testSomething() {
     ...
}
```
### Test suite issues
You can also use the syntax shown above to annotate test suites instead of separate test cases. In this case, each test case in this test suite will be linked to the issue specified.

### Issue tracker URL
To specify the issue tracker URL, use the **allure.issues.tracker.pattern** property during report generation (either in the **allure.properties** file or as your build tool property):

```properties
allure.issues.tracker.pattern=http://github.com/allure-framework/allure-core/issues/%s
```

In this pattern, the **%s** placeholder will be replaced with the issue key from the annotation.