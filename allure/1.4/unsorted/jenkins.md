---
title: Jenkins Plugin
layout: docs
product: allure
version: 1.4
---

# Jenkins Plugin

1. Install Allure Plugin from "Plugin Manager Page".
2. Open Plugin Advanced Settings (http://<jenkins_host>/pluginManager/advanced).
3. Click "Check Updates" button on the bottom right corner of the page.
4. Configure Allure Commandline from "Jenkins Configure Page".

## Configure Jenkins Content Security

By default, Jenkins sets Content Security Policy for plugin pages.
Allure requires less strict policy, you can set it via system property.
If you haven't done it before, add the following to Jenkins system properties configuration
(you need to set both Hudson and Jenkins properties to make it works):

```
"-Dhudson.model.DirectoryBrowserSupport.CSP=default-src 'self'; script-src 'self' 'unsafe-inline' 'unsafe-eval'; style-src 'self' 'unsafe-inline';"
"-Djenkins.model.DirectoryBrowserSupport.CSP=default-src 'self'; script-src 'self' 'unsafe-inline' 'unsafe-eval'; style-src 'self' 'unsafe-inline';"
```

You can read more about it in the [Jenkins docs](https://wiki.jenkins-ci.org/display/JENKINS/Configuring+Content+Security+Policy)
and find details in [issue #715](https://github.com/allure-framework/allure-core/issues/715) in the Github repository of allure-core.

## Build agents have connection to maven central

## Configuration

### Job configuration

1. Open job configuration page.
2. Ensure that your build generates Allure XML files.
3. Add Allure Report post build action.
4. Configure the Allure Report.

### TMS integration

1. Open Job Configure Page.
2. Find Allure Report configuration section.
3. Setup allure.tests.management.pattern property:

### Issue Tracker integration

1. Open Job Configure Page.
2. Find Allure Report configuration section.
3. Setup allure.issues.tracker.pattern property:

### Advanced

1. Open Job Configure Page.
2. Find Allure Report configuration section.
3. Click "Advanced..." button if you need custom settings of commadline, jdk or build policy

## Usage
