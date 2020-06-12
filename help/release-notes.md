---
title: Forms as a Cloud Service pre-pilot notes
description: Forms as a Cloud Service pre-pilot program.
---

# Forms as a Cloud Service pre-pilot release notes {#overview}

Welcome to the Forms as a Cloud Service pre-pilot program. Read on for resources and instructions to get started and make the best of the pre-pilot program.

Adobe Experience Manager Forms as a Cloud Service (FaaCS) offers a cloud-native, Platform as a service (PaaS) solution for businesses to create, manage, publish, and update complex digital forms while integrating submitted data with back-end processes, business rules, and saving data in a data store for later use. The service is always current, always available, and always learning.

## What’s supported in current pre-release build {#current-support}

The current pre-pilot build of Forms as a Cloud Service supports managing and publishing adaptive forms and creating Document of Record (DoR) for adaptive forms created with Automated Forms Conversion service.

June 2020 release does not support using FaaCS environments for creating forms. You can use a FaaCS environment to store, manage, and publish adaptive forms and use a local development environment to create an adaptive form and related assets. After an adaptive form is ready, you export the adaptive form and related assets from the local development environment to FaaCS environments for publishing. For instructions to set up a local development environment, see the [Set up a local development environment article](setup-local-development-environment.md).

### Key features supported in June 2020 release {#key-features}

You can use the June 2020 release of the service to:

* **Create simple and interactive adaptive forms:** You can use a local development environment to create an adaptive form. You can use the below features of adaptive forms in June 2020 release:

  * Create an adaptive form based on a pre-defined JSON, XML, or XSD schema to make it easier for existing systems of your organization to consume the submitted form data.
  * Use templates and themes to standardize content structure and appearance of  the forms of an organization or a department.
  * Use rules to add interactive behavior to adaptive forms. You can also use  rules to show hide sections of a form, retrieve, and save data to a database,  and prefill an adaptive form.
  * Use prefill service to fill a form with existing customer data based on a  criterion to fasten the form filling process and reduce the abandon rate.
  * Create a custom submit action to process submitted data or perform other  actions before saving the data to a data source.
  * Group common fields into reuseable form fragments. You can re-use form  fragments to quickly build multiple forms.
  * Create repeatable sections within an adaptive form. These sections are  dynamically added to or removed from a form.
  * Use lazy loading to defer initialization or loading (lazy loading) of the sections of an adaptive form.

* **Manage and publish adaptive forms and related assets:** You can use a FaaCS instance to store, manage, and publish an adaptive form. You cannot use FaacS instances to develop an adaptive form, themes, templates, or custom submit actions. You can use the below-listed management features in June 2020 release:
    
  * Export and import forms and related assets. 
  * Use groups to lists to limit access of users based on their role.
  * Use folders to organize forms and related assets.
  * Search forms and related assets. 
  * Import and publish adaptive forms


* **Automate conversion of PDF forms adaptive forms:** You can use automated forms conversion service to convert PDF Forms to adaptive from. It helps you accelerate digitization and modernization of data capture experience. You can also create a document of record (DoR) for adaptive forms created with Automated Forms Conversion Service.



>[!NOTE]
>
> June 2020 release does not support using a FaaCS developer instance to create forms. You can use FaaCS developer instance to store, manage, and publish adaptive forms and use the local development environment to create an adaptive form. You export adaptive forms and related assets from a local development environment to FaaCS environments for publishing.

## Download the latest pre-pilot software builds {#latest-software}

Download the following software packages for the pre-pilot program to [set up local Forms as a Cloud Service development environment](setup-local-development-environment.md):

|Software   | Download links |
|---|---|
| AEM 6.5 QuickStart  | [AEM 6.5 QuickStart](https://artifactory.corp.adobe.com/artifactory/maven-aem-dev/com/day/cq/cq-quickstart/6.5.0/cq-quickstart-6.5.0.jar)   |
| AEM 6.5 Service Pack 5 (6.5.5)   | [AEM 6.5 Service Pack 5](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq650/servicepack/aem-service-pkg-6.5.5.zip)  |
| AEM 6.5 Forms add-on package  | [AEM Forms add-on package for Linux](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq650/servicepack/fd/AEM-FORMS-6.5.5.0-LX.zip), [AEM Forms add-on package for Windows](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq650/servicepack/fd/AEM-FORMS-6.5.5.0-WIN.zip), [AEM Forms add-on package for Mac OS X](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq650/servicepack/fd/AEM-FORMS-6.5.5.0-OSX.zip) |

## Known issues, limitations, and workarounds {#known-issue-limitations}

* Disabling dispatcher caching configuration is not available out-of-the-box. You can [change and deploy the dispatcher caching settings to your environment via custom code](setup-local-development-environment.md). 
* FaaCS June 2020 build does not support rules created with the rule editor's code editor.
* AcroForm and XFA-based document of record (DoR) do not support custom scripts.

## Share feedback {#feedback}

Your feedback is important as it helps us improve our offerings. To share your experiences and report feedback on the conversion service and related documentation, log a JIRA issue with the details listed in the table below.

### Before you start {#before-start}

* Take screenshots or create video recordings of any issue encountered. Add the screenshot or video to the JIRA issue.
* Add the source form or details of the setup with issues to the JIRA issues
* Identify and report the difference in functionality and UI. Provide a detailed description of an issue to make it easier to understand.

### Log JIRA issue {#log-jira}

| JIRA field  | Options description  |
|---|---|
| Project  | CQ: Use the CQ project to report bug or improvements in the conversion service. </br> CQDOC: Use the CQDOC project to report bugs or improvements in the documentation. |
| Issue Type  | Bug: Use the Bug issue type when the behavior is not as expected, or documented instructions are incorrect. </br> Improvement: Use the Improvement issue type when a key aspect of the feature is missing and should be provided, or documented instructions are insufficient to understand or use the feature.|
| Component  | Forms  |
| FixVersion  | AEM as cloud service release version. For example, 2020.6.0  |
| Label  | FaaCS-BETA  |
| Description  | Provide the following information in the description field: </br> Problem statement </br> Steps to reproduce the issue </br> Actual result of the conversion </br> Expected result of the conversion </br> Attach collaterals or provide links to download|
