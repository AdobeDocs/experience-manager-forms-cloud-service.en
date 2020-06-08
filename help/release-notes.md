---
title: Forms as a Cloud Service prerelease notes
description: Forms as a Cloud Service prerelease program.
---

# Forms as a Cloud Service prerelease notes {#overview}

Welcome to the Forms as a Cloud Service prerelease program. Read on for resources and instructions to get started and make the best of the prerelease program.

Adobe Experience Manager Forms as a Cloud Service (FaaCS) offers a cloud-native, Platform as a service (PaaS) solution for businesses to create, manage, publish, and update complex digital forms while integrating with back-end processes, business rules, and data from within a system that is always current, always available, and always learning platform.

## What’s supported in current pre-release build {#current-support}

The current prerelease build of Forms as a Cloud Service supports managing and publishing adaptive forms and creating Document of Record (DoR) for adaptive forms created with Automated Forms Conversion service. For the detailed list of supported features, see [Forms as a Cloud Service Overview](overview.md)

June 2020 release does not support using FaaCS environments for creating forms. You can use FaaCS environments to store, manage, and publish adaptive forms and use the local development environment to create an adaptive form. You export adaptive forms and related assets from a local development environment to FaaCS environments for publishing. For instructions to set up a local development environment, see the [Set up the environment article](tbd.md)

## Download the latest prerelease software builds {#latest-software}

Download the following software packages for the prerelease program to set up a local Forms as a Cloud Service development environment: 

|Software   | Download links |
|---|---|
| AEM 6.5 QuickStart  | [AEM 6.5 QuickStart](https://artifactory.corp.adobe.com/artifactory/maven-aem-dev/com/day/cq/cq-quickstart/6.5.0/cq-quickstart-6.5.0.jar)   |
| AEM 6.5 Service Pack 5 (6.5.5)   | [AEM 6.5 Service Pack 5](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq650/servicepack/aem-service-pkg-6.5.5.zip)  |
| AEM 6.5 Forms add-on package  | [AEM Forms add-on package for Linux](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq650/servicepack/fd/AEM-FORMS-6.5.5.0-LX.zip) </br> [AEM Forms add-on package for Windows](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq650/servicepack/fd/AEM-FORMS-6.5.5.0-WIN.zip) </br> [AEM Forms add-on package for Mac OS X](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq650/servicepack/fd/AEM-FORMS-6.5.5.0-OSX.zip) |
| Forms as a Cloud Service SDK  | [Maven POM dependencies](tbd.md)|

## Known issues, limitations, and workarounds {#known-issue-limitations}

### Known issues
* Disabling dispatcher caching configuration is not available out-of-the-box. You can [change and deploy the dispatcher caching settings to your environment via custom code](tbd.md). 
* FaaCS June 2020 build does not support rules creatd with code editor. 
* AcroForm and XFA-based document of record (DoR) do not support custom scripts.

## Share feedback {#feedback}

Your feedback is important as it helps us improve our offerings. To share your experiences and report feedback on the conversion service and related documentation, log a JIRA issue with the details listed in table below. Also, create a test plan wiki and share the plan with faacs-beta team at faacs-beta@adobe.com. The plan shall help keep a track of the progress and build a continues dialog between product development and consulting teams.

### Before you start {#before-start}

* Publish your test plan on a wiki and share the test plan at faacs-beta@adobe.com
* Take screenshots or create video recordings of any issue encountered. Add the screenshot or video to the JIRA issue.
* Add the source form or details of the setup with issues to the JIRA issues
* Identify and report the difference in functionality and UI. Provide detailed description of an issue to make it easier to understand.

### Log JIRA issue

| JIRA field  | Options description  |
|---|---|
| Project  | CQ: Use the CQ project to report bug or improvements in the conversion service. </br> CQDOC: Use the CQDOC project to report bug or improvements in the documentation. |
| Issue Type  | Bug: Use the Bug issue type when the behavior is not as expected, or documented instructions are incorrect. </br> Improvement: Use the Improvement issue type when a key aspect of the feature is missing and should be provided, or documented instructions are insufficient to understand or use the feature.|
| Component  | Forms  |
| FixVersion  | AEM as cloud service release version. For example, 2020.6.0  |
| Label  | FaaCS-BETA  |
| Description  | Provide the following information in the description field: </br> Problem statement </br> Steps to reproduce the issue </br> Actual result of the conversion </br> Expected result of the conversion </br> Attach collaterals or provide links to download|
