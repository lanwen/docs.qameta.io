---
title: Steps
layout: docs
product: allure
version: 1.4
---

Steps are any actions that constitute a testing scenario. Steps can be used in different testing scenarios. They can: be parametrized, make checks, have nested steps, and create attachments. Each step has a name.

In order to define steps in Java code, you need to annotate the respective methods with **@Step** annotation. When not specified, the step name is equal to the annotated method name converted to human-readable format. To define an explicit step name:

```java
@Step("Open {0} page.")
public void openPageByAddress(String pageAddress) {
     ...
 }
```

## Placeholders

Step names support the following placeholders:

 * **{N}** where N is a zero-based positive integer that will be replaced by the Nth method argument value (0 corresponds to the first argument, 1 to the second, etc.). See example above.
 * **{method}** will be replaced by the annotated method name e.g. **openPageByAddress**