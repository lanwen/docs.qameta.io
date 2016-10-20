---
title: Allure TeamCity Plugin
layout: docs
product: allure
version: 1.4
---

# Allure TeamCity Plugin

## Installation
 1. [Install Allure TeamCity plugin](https://confluence.jetbrains.com/display/TCD9/Installing+Additional+Plugins).
Copy the **allure-commandline.zip** from [latest release](https://github.com/allure-framework/allure-core/releases/latest) to the <[TeamCity Data Directory](https://confluence.jetbrains.com/display/TCD9/TeamCity+Data+Directory)>/plugins/.tools directory. No server restart needed for this step.

## Configuration
 1. Open the build **configuration settings**.
 2. Ensure that your build [generates Allure XML files](https://github.com/allure-framework/allure-core/wiki#gathering-information-about-tests).
 3. Go to **Build steps** and add the **Allure Report** build step.  
    ![jenkins plugin install](/{{page.product}}/{{page.version}}/img/teamcity_plugin_add_build_step.png)
 4. Configure the step.  
    ![jenkins plugin install](/{{page.product}}/{{page.version}}/img/teamcity_plugin_configure_build_step.png)  
In case you upgrading the Allure TeamCity plugin you need to remove old Allure report generation feature.

## Usage 
When the build is done you will get Allure Report as a part of build artifacts – simply open the index.html.  
![jenkins plugin install](/{{page.product}}/{{page.version}}/img/teamcity_plugin_usage.png)