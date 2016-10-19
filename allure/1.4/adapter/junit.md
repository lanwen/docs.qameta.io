---
title: jUnit Adapter
layout: docs
product: allure
version: 1.4
---

# Junit Adapter

An Allure report can be generated for any [JUnit](http://junit.org/) 4 test.
**Warning: Allure only supports JUnit 4 or higher. You will get nothing with JUnit 3.**
In order to get test results, you need to:

* Add AllureRunListener to JUnit.
* Add AspectJ Weaver and respective properties.
* Run tests.

## Maven

See the example project: https://github.com/allure-framework/allure-junit-example

You need to add the following to your **pom.xml**:
```xml
<properties>
    <aspectj.version>1.7.4</aspectj.version>
    <allure.version>{latest-allure-version}</allure.version>
</properties>

<dependencies>
    <dependency>
        <groupId>ru.yandex.qatools.allure</groupId>
        <artifactId>allure-junit-adaptor</artifactId>
        <version>${allure.version}</version>
    </dependency>
</dependencies>

<build>
    <plugins>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-surefire-plugin</artifactId>
            <version>2.14</version>
            <configuration>
                <testFailureIgnore>false</testFailureIgnore>
                <argLine>
                    -javaagent:${settings.localRepository}/org/aspectj/aspectjweaver/${aspectj.version}/aspectjweaver-${aspectj.version}.jar
                </argLine>
                <properties>
                    <property>
                        <name>listener</name>
                        <value>ru.yandex.qatools.allure.junit.AllureRunListener</value>
                    </property>
                </properties>
            </configuration>
            <dependencies>
                <dependency>
                    <groupId>org.aspectj</groupId>
                    <artifactId>aspectjweaver</artifactId>
                    <version>${aspectj.version}</version>
                </dependency>
            </dependencies>
        </plugin>
    </plugins>
</build>
```
Then run the build as usual:
```bash
$ mvn clean test
```
Depending on the project layout, you can consider adding Allure dependency to the test scope only.

## Ant

Right now using Allure with [Ant](http://ant.apache.org/) is not possible, because the [RunListener](http://junit.sourceforge.net/javadoc/org/junit/runner/notification/RunListener.html) that we provide is only supported in JUnit 4, whereas even the latest version of Ant requires the implementation of JUnit 3 specific interfaces.