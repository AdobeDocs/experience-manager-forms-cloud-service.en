---
title: Adobe Experience Manager (AEM) Forms as a Cloud Service Overview
description: AEM Forms as a Cloud Service is a platform to create, manage, publish enterprise-class forms and business processes.
---

# Overview of [!DNL AEM Forms] as a [!DNL Cloud Service] {#overview}

![Journey from paper forms to digital forms](assets/forms-mobile-dekstop.png)

[!DNL Adobe Experience Manager Forms] as a [!DNL Cloud Service] offers a cloud-native, Platform as a Service (PaaS) solution for businesses to create, manage, publish, and update complex digital forms while integrating submitted data with back-end processes, business rules, and saving data in a data store for later use. The service is always current, always available, and always learning.

You can use the service for faster rollout and creation of interactive and engaging digital enrollment experiences. For example, an organization WKND is looking to digitize their customer enrollment journey. The organization also has multiple print forms, they are also looking to convert all of their print forms to interactive and responsive web forms. They also have multiple data sources with existing customer data, they are looking to pre-populate forms, archive filled forms, and e-sign the forms.  

The organization can use [!DNL AEM Forms] as a [!DNL Cloud Service] to create forms and Automated Forms Conversion service to automatically convert their legacy forms to adaptive forms (web forms). The service also helps the organization to create Document of Record (DoR) to archive filled forms, create business processes with Experience Manager Workflows, and integrates with [!DNL Adobe Sign] for electronic signatures. The organization can sign up for [!DNL AEM Forms] as a [!DNL Cloud Service] and start using all these features without waiting to buy and set up a local infrastructure. It also frees the organization from the cycle of upgrades as the service is always up to date and always offers the latest features.  

## Key features {#key-features}

* **Enterprise-class forms:** You can create enterprise class forms (adaptive forms) and deliver beautiful, interactive, responsive, and personalized experiences your customers. <!-- These forms change behavior and appearance based on the underlying device. You can also use themes and templates with adaptive forms to mandate a uniform structure and appearance for all the forms of an organization or a department.-->  

* **Automatic conversion of PDF forms to adaptive forms:** You can use Automated Forms Conversion service to convert PDF Forms to adaptive from. It helps you accelerate digitization and modernization of data capture experiences of your organization.

* **Data Integration:** You can connect adaptive forms directly to disparate data sources to access and update data, pre or post process data accessed from data sources or captured using adaptive forms.

* **Prefill a form:** [!DNL AEM Forms] provide a service to fill a form with existing customer data based on a criteria to fasten the form filling process and reduce the abandon rate.

* **Submit actions:** The service provides several submit actions to allow you to persist and process captured data. Apart from saving data to a data store, you can also send data to a REST endpoint, or email the data. You can also develop custom submit actions to perform some actions specific to your business.  

* **Business processes automation:** You can use workflows to create business processes and automate operations. For example, starting an approval and rejection workflows on submission of an adaptive form.  

* **Schema-compliant data:** You can create adaptive forms to produce schema-compliant data. It helps you submit captured data to existing processes without any, or minimal modifications. You can use strict or transitional schema definitions for your schema.

* **Visual rule editor:** Rule editor empowers you to build dynamism and interactivity to adaptive forms. These rules define actions to trigger on form objects based on preset conditions, user inputs, and user actions on the form. It helps further streamline the form filling experience ensuring accuracy and speed.

* **WYSIWYG editors:** The service provides several WYSIWYG editors: Adaptive Forms editor, Theme editor, Template editor to help you create and edit forms and related assets while experiencing the actual appearance of content to be displayed on a customer’s device.

* **Emulators:** You can view an adaptive form in an in-built emulator. It helps you simulate how an adaptive form appears on different devices to an end user. It provides out-of-the-box options to simulate views for popular mobile devices, tablets, and desktop screen configurations.

* **Integration with [!DNL Adobe Sign]:** You can use [!DNL Adobe Sign] components in an adaptive form. It allows a single or multiple users-sign a form in a sequence or in no particular order. Using electronic signatures helps you speed up contract or agreement signing workflows for legal, sales, payroll, human resource management, and more areas.

* **Document of Record:** You can create a Document of Record (DoR) to keep a record of the information that you provide and submit in an adaptive form so that you can refer to it later. A DoR is a PDF version of a form. It includes both a template and data. You can generate a DoR either using a default template or associating any other template with the adaptive form.

### Key cloud native capabilities {#platform-capabilities}

AEM Forms as a Cloud Service provides several cloud-native capabilities that are an addition to standard AEM Forms features. The following table lists major cloud-native capabilities of AEM Forms as a Cloud Service:

| Feature/Capability | AEM 6.5 Forms  | [!DNL AEM Forms] as a [!DNL Cloud Service] |
|---|---|---|
| Cloud-native architecture | &#x2612; | &#x2611;  |
| Auto-scaling based on load | &#x2612; | &#x2611;  |
| Zero downtime for upgrades | &#x2612; | &#x2611;  |
| Feature roll-out frequency | Quarterly | Agile*  |
| CDN (content delivery network) included | &#x2612; | &#x2611;  |
| Topologies optimized for maximum resilience and efficiency | &#x2612; | &#x2611;  |
| Cloud-native development environment | &#x2612; | &#x2611;  |
| Self-Service via Cloud Manager | &#x2612; | &#x2611;  |
| Automated upgrades with Continuous Integration and Continuous Delivery (CI/CD)| &#x2611; | &#x2611;  |

`*` New features every month and bug fix updates on daily basis.

For a comprehensive list of changes in AEM as a [!DNL Cloud Service], See [What is New and What is Different](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/overview/what-is-new-and-different.html) and [Notable changes in AEM Forms as a Cloud Service](notable-changes.md).

### What's new {#whats-new}

**Faster form renditions and Faster server-side validations**
The service uses CDN and Dispatcher caching to deliver faster renditions and server-side validations for adaptive forms.

**Improved CAPTCHA**
You can now validate CAPTCHA either on adaptive form submission or on a business logic. You can also add conditions to validate CAPTCHA on a user action and show or hide the CAPTCHA component in an adaptive form based on rules. 

The CAPTCHA component provides an out-of-the-box integration with Google reCAPTCHA. You can also configure extra CAPTCHA services for the component, if necessary.

**Multiple master pages for Document of Record**
You can use a different master page for each page of a Document of Record. You can also control the placement of adaptive form panels on a document of record. The Cloud Service provides various pagination options to control placement of content. 

**AEM Archetype for Forms as a Cloud Service**
[AEM Archetype](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-27) helps you easily start developing for AEM Form as a Cloud Service. You can use Archetype version 27 or later to create a project template compatible with AEM Form as a Cloud Service environment. The Archetype also includes some sample themes and templates to help you started quickly. 

**Secure and improved information flow between forms and Sign**
Adaptive Forms and Adobe Sign integration on Cloud Service offer simultaneous  submission of data and signing activity. It makes form submission independent of signing status paving a way for faster submissions. On top of it, the service does not save any data on Cloud Service instances making the signing process super secure.

**Enhanced Visual Rule editor**
The service provides a hardened Visual Rule editor. The service has added following features to Visual rule editor to help you write capable rules:

* New submission events: `Navigation`, `Step Completion`, `Successful Submission`, and `Error`

* New data type `scope`. You can use the `scope` data type in a custom function to pass the entire scope of a form.

* Ability to use @this to specify a JSDoc in a custom function. It allows invoking a custom function by using @this in an active component.

* Ability to add conditions for property based rules.

**Add columns to headless tables**
You can add and delete columns to tables without headers. Hidden headers are added to such tables to help you add and delete columns. These headers are visible during authoring but remain hidden in the published form. Tables without headers are mostly found in adaptive forms created using the Automated Forms Conversion service.

**Improved Submit Actions**
You can use the **Send Email** submit action to send a Document of Record (DoR) PDF as an attachment. 

**Group email for workflow**
You can choose to send notification emails from the Assign Task step to a single person or a group. The Assign task step now accepts email address of a group.

**Improved readability of translation files**
On Forms as a Cloud Service, reading order of the fields and panels of an adaptive form and message keys of corresponding translation files (.XLIFF files) has similar structure. It helps improving manual translation speeds.


**Best Practices Analyzer and migration tooling**
Best Practices Analyzer provides an assessment of your current AEM implementation. Run the tool before migrating to Forms as a Cloud Service. It  assesses readiness to move from an existing Adobe Experience Manager (AEM) deployment to AEM as a Cloud Service.

## Onboard the service {#onboarding}

Contact your Adobe representative for help and instructions to [onboard](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/onboarding/home.html) the [!DNL Adobe Experience Manager Forms] as a [!DNL Cloud Service].
