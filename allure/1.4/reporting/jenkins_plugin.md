---
title: Allure Jenkins Plugin
layout: docs
product: allure
version: 1.4
---

# Allure Jenkins Plugin

## Installation
 1. Install [Allure Plugin](https://wiki.jenkins-ci.org/display/JENKINS/Allure+Plugin) from "Plugin Manager Page".
 2. Open Plugin Advanced Settings (http://<jenkins_host>/pluginManager/advanced). 
 3. Click "Check Updates" button on the bottom right corner of the page.
 4. Configure Allure Commandline from "Jenkins Configure Page".


![jenkins plugin install](/{{page.product}}/{{page.version}}/img/jenkins_plugin_install.jpeg)

### Configure Jenkins Content Security
By default, Jenkins sets Content Security Policy for plugin pages. Allure requires less strict policy, you can set it via system property.

If you haven't done it before, add the following to Jenkins system properties configuration (you need to set both Hudson and Jenkins properties to make it works):
```
"-Dhudson.model.DirectoryBrowserSupport.CSP=default-src 'self'; script-src 'self' 'unsafe-inline' 'unsafe-eval'; style-src 'self' 'unsafe-inline';"
"-Djenkins.model.DirectoryBrowserSupport.CSP=default-src 'self'; script-src 'self' 'unsafe-inline' 'unsafe-eval'; style-src 'self' 'unsafe-inline';"
```
You can read more about it in the [Jenkins](https://wiki.jenkins-ci.org/display/JENKINS/Configuring+Content+Security+Policy) docs and find details in [issue #715](https://github.com/allure-framework/allure-core/issues/715) in the Github repository of allure-core.

### Build agents have connection to maven central
 1. Open "Jenkins Configure Page".
 2. Find "Allure Commandline" configuration block.
    ![find allure commandline](/{{page.product}}/{{page.version}}/img/jenkins_plugin_find_cmd.jpeg)
 3. Click "Allure Commandline Installations..." button.
    ![install allure commandline](/{{page.product}}/{{page.version}}/img/jenkins_plugin_install_cmd.jpeg)
 4. Fill the name and choose the version of allure report. 

### Build agents have NOT connection to maven central 
 1. Download the latest version of allure-commandline.zip from github.
 2. Upload downloaded file to any file server. Build agents must have access to the file by url. For example, *http://mycompany.com/allure-commandline.zip*
 3. Open "Jenkins Configure Page". and find "Allure Commandline" configuration block. 