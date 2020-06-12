---
title: AEM Forms as a Cloud Service pre-pilot notes
description: AEM Forms as a Cloud Service pre-pilot program.
---

# AEM Forms as a Cloud Service pre-pilot release notes {#overview}

Welcome to the AEM Forms as a Cloud Service pre-pilot program. Read on for resources and instructions to get started and make the best of the pre-pilot program.

Adobe Experience Manager AEM Forms as a Cloud Service offers a cloud-native, Platform as a service (PaaS) solution for businesses to create, manage, publish, and update complex digital forms while integrating submitted data with back-end processes, business rules, and saving data in a data store for later use. The service is always current, always available, and always learning.

## What’s supported in current pre-pilot build {#current-support}

The current pre-pilot release of AEM Forms as a Cloud Service supports managing and publishing adaptive forms and creating Document of Record (DoR) for adaptive forms created with Automated Forms Conversion service. For instructions to set up a AEM Forms as a Cloud Service environment, see [Set up a AEM Forms as a Cloud Service instance](setup-forms-cloud-service.md)

June 2020 release does not support using a AEM Forms as a Cloud Service environment for creating adaptive forms. You can use a [local development environment](setup-local-development-environment.md) to create forms and related assets. After an adaptive form is ready on the local develoment instance, you can export the adaptive form and related assets from the local development environment to AEM Forms as a Cloud Service environments for publishing. You can use your AEM Forms as a Cloud Service environment only to store, manage, and publish adaptive forms. 

### Key features supported in June 2020 release {#key-features}

You can use the June 2020 release of the service to:

* **Create adaptive forms:** You can use a local development environment to create an adaptive form. You can use the below features of adaptive forms in June 2020 release:

  * Create an adaptive form based on a pre-defined JSON, XML, or XSD schema to make it easier for existing systems of your organization to consume the submitted form data.
  * Use templates and themes to standardize content structure and appearance of  the forms of an organization or a department.
  * Use rules to add interactive behavior to adaptive forms. You can also use  rules to show hide sections of a form, retrieve, and save data to a database,  and prefill an adaptive form.
  * Use prefill service to fill a form with existing customer data based on a  criterion to fasten the form filling process and reduce the abandon rate.
  * Create a custom submit action to process submitted data or perform other  actions before saving the data to a data source.
  * Group common fields into reuseable form fragments. You can re-use form  fragments to quickly build multiple forms.
  * Create repeatable sections within an adaptive form. These sections are  dynamically added to or removed from a form.
  * Use lazy loading to defer initialization or loading (lazy loading) of the sections of an adaptive form.

* **Manage and publish adaptive forms and related assets:** You can use a AEM Forms as a Cloud Service instance to store, manage, and publish an adaptive form. You cannot use AEM Forms as a Cloud Service instances to develop an adaptive form, themes, templates, or custom submit actions. You can use the below-listed management features in June 2020 release:
    
  * Export and import forms and related assets. 
  * Use groups to lists to limit access of users based on their role.
  * Use folders to organize forms and related assets.
  * Search forms and related assets. 
  * Import and publish adaptive forms


* **Automate conversion of PDF forms adaptive forms:** You can use automated forms conversion service to convert PDF Forms to adaptive from. It helps you accelerate digitization and modernization of data capture experience. You can also create a document of record (DoR) for adaptive forms created with Automated Forms Conversion Service.


## Known issues and limitations {#known-issue-limitations}

* Disabling dispatcher caching configuration is not available out-of-the-box. You can [change and deploy the dispatcher caching settings to your environment via custom code](setup-local-development-environment.md). 
* No support for rules created with the rule editor's code editor.
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
| Label  | Forms-Cloud-Service-pre-pilot  |
| Description  | Provide the following information in the description field: </br> Problem statement </br> Steps to reproduce the issue </br> Actual result of the conversion </br> Expected result of the conversion </br> Attach collaterals or provide links to download|
