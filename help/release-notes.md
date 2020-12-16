---
title: AEM Forms as a Cloud Service pre-pilot notes
description: AEM Forms as a Cloud Service pre-pilot program.
---

# AEM Forms as a Cloud Service release notes {#overview}

Adobe Experience Manager AEM Forms as a Cloud Service offers a cloud-native, Platform as a Service (PaaS) solution for businesses to create, manage, publish, and update complex digital forms while integrating submitted data with back-end processes, business rules, and saving data in a data store for later use. The service is always current, always available, and always learning.

When you set up and configure AEM Forms as a Cloud service environment, you set up development, staging, and production environments. You configure two types of development environments:

* **Local development environment (An AEM 6.5.5 Forms instance):** Use a [local development environment](setup-local-development-environment.md) to create forms and related assets (themes, templates, custom submit actions, and more) and convert PDF Forms to adaptive forms. After an adaptive form or related assets are ready on the local development instance, you can export the adaptive form and related assets from the local development environment to an AEM Forms as a Cloud Service environment for publishing.

* **AEM Forms as a Cloud Service development environment:** Use the [AEM Forms as a Cloud Service](setup-forms-cloud-service.md) environment to test adaptive forms and related assets before publishing the forms. Do not use AEM Forms as a Cloud Service development environment to create adaptive forms or related assets. <!--, form-centric workflows, a form data model, or to generate a Document of Record. -->

## What’s supported in pre-pilot release {#current-support}

* **Adaptive forms:** You can use the local development environment to create adaptive forms. The following adaptive forms features are available in pre-pilot release:

  * Create an adaptive form based on a pre-defined JSON, XML, or XSD schema to make it easier for existing systems of your organization to consume the submitted form data.
  * Use templates and themes to standardize content structure and appearance of the forms of an organization or a department.
  * Use rules created with the visual editor to add interactive behavior to adaptive forms. You can also use rules to show hide sections of a form and prefill an adaptive form.
  * Use prefill service to fill a form with existing customer data based on a  criterion to fasten the form filling process and reduce the abandon rate.
  * Create a custom submit action to process submitted data.
  * Group common fields into reuseable form fragments. You can reuse form  fragments to quickly build multiple forms.
  * Create repeatable sections within an adaptive form. These sections are  dynamically added to or removed from a form.
  * Use lazy loading to defer initialization or loading (lazy loading) of the sections of an adaptive form.

* **Forms management and publishing:** You can use an AEM Forms as a Cloud Service instance to store, manage, and publish an adaptive form. The following forms management and publishing features are available in pre-pilot release:
    
  * Export and import forms and related assets
  * Use groups to limit access of users based on their role
  * Use folders to organize forms and related assets
  * Search forms and related assets
  * Publish adaptive forms and related assets


* **Automated conversion of PDF forms adaptive forms:** You can use the Automated Forms Conversion service (AFCS) on a local development environment to convert PDF Forms to adaptive forms. It helps you accelerate digitization and modernization of data capture experience. You import the converted forms from local development instance to AEM Forms on Cloud Service environment for publishing. 

## Known issues and limitations {#known-issue-limitations}

### Known issues

AEM Forms as a Cloud Service environment has the following known issues:

* No support for rules created with the rule editor's code editor.
* Send Email and Send PDF via Email submit actions are not supported. 
*  When you download a folder containing assets, none of assets are downloaded.
* No support for themes created at a location other than `/etc/clientlibs/fd/themes`.
* When the Ultramarine theme is applied, the add new row (+) button and delete row button applied to a table do not work.  
* Disabling dispatcher caching configuration is not available out-of-the-box. You can change and deploy the dispatcher caching settings to your environment via [custom code](setup-local-development-environment.md). 

### Limitations

The following features are partially available on AEM Forms on Cloud service environment. It is recommended to not use these features: 

* Forms-centric workflow steps 
* Data integration (Form Data Model)
* AcroForm based Document of record (DoR)
* Adaptive Forms editor on AEM Forms on Cloud Service development instance 

The following adaptive form features are not available on AEM Forms on Cloud service environment:

* Integration with Adobe Sign, Adobe Target, Adobe Analytics, and Adobe Fonts  
* Single page application (SPA) components
* Embedding adaptive forms in a sites page
* Reference sites and reference themes
* Summary and verify components
* Google reCAPTCHA

## Share feedback {#feedback}

Your feedback is important as it helps us improve our offerings. To share your experiences and report feedback on the conversion service and related documentation, log a Jira issue with the details listed in the table below.

### Before you start {#before-start}

* Take screenshots or create video recordings of any issue encountered. Add the screenshot or video to the Jira issue.
* Add the source form or details of the setup with issues to the Jira issues
* Identify and report the difference in functionality and UI. Provide a detailed description of an issue to make it easier to understand.

### Log Jira issue {#log-Jira}

| Jira field  | Options description  |
|---|---|
| Project  | CQ: Use the CQ project to report bug or improvements in the conversion service. </br> CQDOC: Use the CQDOC project to report bugs or improvements in the documentation. |
| Component  | CQ: Forms - Ethos, CQDOC: Forms  |
| Affected version  | AEM as a Cloud Service release version. For example, 2020.7.0  |
| Label  | ACS-SkylineCECV, FaaCS  |
| Description  | Provide </br> problem statement, </br> steps to reproduce the issue, </br> expected result of the conversion, </br> actual results, </br>  and attach collaterals or provide links to download|
