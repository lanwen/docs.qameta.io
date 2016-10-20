---
title: Attachments
layout: docs
product: allure
version: 1.4
---

# Attachments

An attachment in Java code is simply a method annotated with **@Attachment** that returns either a **String** or **byte[]**, which should be added to the report:
```java
@Attachment
public String performedActions(ActionSequence actionSequence) {
    return actionSequence.toString();
}

@Attachment(value = "Page screenshot", type = "image/png")
public byte[] saveScreenshot(byte[] screenShot) {
    return screenShot;
}
```
If a method annotated with **@Attachment** return type differs from **String** or **byte[]** we call **toString()** on return value to get attachment contents.

You can specify exact MIME type for each attached file using **type** parameter of **@Attachment** annotation like shown above. However there's no need to explicitly specify attachment type for all attached files as Allure by default analyses attachment contents and can determine attachment type automatically. You usually need to specify attachment type when working with plain text files.

## Removing attachments for passed test cases
In order to economize free disk space, you can remove attachments if the corresponding test case passed. To do this, use the `allure.report.remove.attachments` system property. Simply set this property somewhere in the test code to a PCRE regular expression, and Allure will remove any attachment with a name that matches this regular expression. For example, if your test saves a lot of PNG screenshots and you don't want to store them for passed cases, set the system property `allure.report.remove.attachments=.*\.png`. To apply this setting globally, you can put a file named `allure.properties` in your classpath. See [AllureConfig](https://github.com/allure-framework/allure-core/blob/master/allure-model/src/main/java/ru/yandex/qatools/allure/AllureConfig.java) for a list of existing properties.

## Placeholders
Attachment name supports the same placeholders as [steps](https://github.com/allure-framework/allure-core/wiki/Steps#placeholders) do.