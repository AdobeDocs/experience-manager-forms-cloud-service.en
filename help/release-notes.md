---
title: AEM Forms as a Cloud Service pre-pilot notes
description: AEM Forms as a Cloud Service pre-pilot program.
---

# AEM Forms as a Cloud Service pre-pilot release notes {#overview}

Welcome to the AEM Forms as a Cloud Service pre-pilot program. Read on for resources and instructions to get started and make the best of the pre-pilot program.

Adobe Experience Manager AEM Forms as a Cloud Service offers a cloud-native, Platform as a service (PaaS) solution for businesses to create, manage, publish, and update complex digital forms while integrating submitted data with back-end processes, business rules, and saving data in a data store for later use. The service is always current, always available, and always learning.

When you set up and configure an AEM Forms as a Cloud service environment, you set up development, staging, and production environments. You configure two types of development environments:

* **AEM Forms as a Cloud Service development environment:** Use the [AEM Forms as a Cloud Service](setup-forms-cloud-service.md) environment to store, manage, and publish adaptive forms and related assets. Do not use an AEM Forms as a Cloud Service environment to create adaptive forms and related assets <!--, form-centric workflows, a form data model, or to generate a Document of Record. -->

* **Local development environment (An AEM 6.5.5 Forms instance):** Use a [local development environment](setup-local-development-environment.md) to create forms and related assets (themes, templates, custom submit actions, and more) and convert PDF Forms to adaptive forms. After an adaptive form or related assets are ready on the local development instance, you can export the adaptive form and related assets from the local development environment to an AEM Forms as a Cloud Service environment for publishing. 

## What’s sup ported and not supported in current pre-pilot build {#current-support}

### Key features supported in June 2020 release {#key-features}

You can use the June 2020 release of the service to:

* **Create adaptive forms:** You can use the local development environment to create an adaptive form. You can use the below features of adaptive forms in June 2020 release:

  * Create an adaptive form based on a pre-defined JSON, XML, or XSD schema to make it easier for existing systems of your organization to consume the submitted form data.
  * Use templates and themes to standardize content structure and appearance of the forms of an organization or a department.
  * Use rules created with the visual editor to add interactive behavior to adaptive forms. You can also use rules to show hide sections of a form, retrieve, and save data to a database,  and prefill an adaptive form.
  * Use prefill service to fill a form with existing customer data based on a  criterion to fasten the form filling process and reduce the abandon rate.
  * Create a custom submit action to process submitted data or perform other  actions before saving the data to a data source.
  * Group common fields into reuseable form fragments. You can re-use form  fragments to quickly build multiple forms.
  * Create repeatable sections within an adaptive form. These sections are  dynamically added to or removed from a form.
  * Use lazy loading to defer initialization or loading (lazy loading) of the sections of an adaptive form.

* **Manage and publish adaptive forms and related assets:** You can use an AEM Forms as a Cloud Service instance to store, manage, and publish an adaptive form. You can use the below-listed management features in June 2020 release:
    
  * Export and import forms and related assets. 
  * Use groups to lists to limit access of users based on their role.
  * Use folders to organize forms and related assets.
  * Search forms and related assets. 
  * Import and publish adaptive forms


* **Automate conversion of PDF forms adaptive forms:** You can use automated forms conversion service on the local development environment to convert PDF Forms to adaptive from. It helps you accelerate digitization and modernization of data capture experience.

### AEM Forms features not supported in June 2020 release

The current pre-pilot release of AEM Forms as a Cloud Service supports limited features.The following adaptive form features are not supported:

* Integration with and Adobe Sign, Adobe Target, Adobe Analytics, and Adobe Fonts  
* Single page application (SPA) components
* Embedding adpative forms in a sites page
* Reference sites and reference themes
* Summary and verify components
* Document of Record (DoR)
* Google reCAPTCHA

Following AEM Forms features are partially available. It is recommended to not use these features: 

* Forms-centric workflow steps 
* Data integration (Form Data Model)
* AcroForm based Document of record (DoR)
* Adaptive Forms editor on AEM Forms on Cloud Service development instance 


## Known issues and limitations {#known-issue-limitations}

* Disabling dispatcher caching configuration is not available out-of-the-box. You can change and deploy the dispatcher caching settings to your environment via [custom code](setup-local-development-environment.md). 
* No support for rules created with the rule editor's code editor.

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
| FixVersion  | AEM as a Cloud Service release version. For example, 2020.6.0  |
| Label  | Forms-Cloud-Service-pre-pilot  |
| Description  | Provide the following information in the description field: </br> Problem statement </br> Steps to reproduce the issue </br> Actual result of the conversion </br> Expected result of the conversion </br> Attach collaterals or provide links to download|
