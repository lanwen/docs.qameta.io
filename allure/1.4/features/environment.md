---
title: Environment
layout: docs
product: allure
version: 1.4
---

# Environment

Allure allows you to add test **environment** values such as *report name*, *browser* or *test server address*:
![environment](/{{page.product}}/{{page.version}}/img/environment.png)

### Usage

There are several ways to add the environment to your report:

* Save the file **environment.xml** in the following format to the Allure results directory:

```xml
<qa:environment xmlns:qa="urn:model.commons.qatools.yandex.ru">
    <id>2a54c4d7-7d79-4615-b80d-ffc1107016a1</id>
    <name>Allure sample test pack</name>
    <parameter>
        <name>Browser</name>
        <key>my.properties.browser</key>
        <value>Firefox</value>
    </parameter>
    <parameter>
        <name>Test stand</name>
        <key>my.properties.url</key>
        <value>http://yandex.ru</value>
    </parameter>
</qa:environment>  
```

* Add the properties file **environment.properties** to the Allure results directory:

```properties
my.properties.browser=Firefox
my.properties.url=http://yandex.ru
```
All specified properties will be shown on the **Overview** page.