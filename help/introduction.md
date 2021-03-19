---
title: Adobe Experience Manager (AEM) Forms as a Cloud Service Overview
description: AEM Forms as a Cloud Service is a platform to create, manage, publish enterprise-class forms and business processes.
---

# Introduction to [!DNL AEM Forms] as a [!DNL Cloud Service] {#overview}

![Journey from paper forms to digital forms](assets/forms-mobile-dekstop.png)

[!DNL Adobe Experience Manager Forms] as a [!DNL Cloud Service] offers a cloud-native, Platform as a Service (PaaS) solution for businesses to create, manage, publish, and update complex digital forms while integrating submitted data with back-end processes, business rules, and saving data in a data store for later use. The service is always current, always available, and always learning.

You can use the service to create and rollout  interactive and engaging digital forms. For example, an organization WKND is looking to digitize their customer enrollment journey. They have multiple data sources with existing customer data, they are looking to pre-populate forms, add e-sign their forms, and archive filled forms as PDF files. Besides, the organization has multiple print forms (PDF Forms), they are also looking to convert all of their print forms to digital forms.

The organization can use [!DNL AEM Forms] as a [!DNL Cloud Service] to create digital forms, connect forms to existing data sources, integrate forms with [!DNL Adobe Sign] to add e-signatures to forms, generate Document of Record (DoR) to archive filled forms as PDF files. The organization can also use the service to convert their existing PDF Forms to digital forms. 

An organization can sign up for [!DNL AEM Forms] as a [!DNL Cloud Service] and start using all these features without waiting to buy and set up a local infrastructure. It also frees the organization from the cycle of upgrades as the service is always up to date and always offers the latest features.  

## Key features {#key-features}

* **Enterprise-class forms:** You can create enterprise class forms (Adaptive Forms) and deliver beautiful, interactive, responsive, and personalized experiences your customers. <!-- These forms change behavior and appearance based on the underlying device. You can also use themes and templates with Adaptive Forms to mandate a uniform structure and appearance for all the forms of an organization or a department.-->  

* **Automatic conversion of PDF forms to Adaptive Forms:** You can use Automated Forms Conversion Service to convert PDF Forms to adaptive from. It helps you accelerate digitization and modernization of data capture experiences of your organization.

* **Data Integration:** You can connect the service to various types of data sources to send and retrieve data. The service supports sending and retrieving data from RESTful web services, SOAP-based web services, and OData enabled services.

* **Integration with [!DNL Adobe Sign]:** You can integrate the service with [!DNL Adobe Sign] and add [!DNL Adobe Sign] fields to an Adaptive Form. It allows your users to e-sign an Adaptive Form and use [!DNL Adobe Sign] with AEM Workflows. You can use AEM Workflows to develop a business logic and send forms and documents to recipients for signatures based on the business logic.

* **Business Processes Automation:** You can use AEM Workflows to create business processes and automate operations. For example, You can create and trigger an approval and rejection workflow on submission of an Adaptive Form. 

* **Document of Record:** You can create a Document of Record (DoR) to keep a record of the information that you provide and submit in an Adaptive Form so that you can refer to it later. A DoR is a PDF version of a form. It includes both a template and data. The service provides a default DoR template and tools to develop a custom template.

* **Prefill a form:** You can create a prefill service to fill a form with existing customer data based on a criteria. It helps fasten the form filling process and reduce the abandon rate.

* **Schema-compliant data:** You can create Adaptive Forms to produce schema-compliant data. It helps you submit captured data to existing processes and data sources without any or minimal modifications.

* **Visual rule editor:** Rule editor empowers you to build dynamism and interactivity to Adaptive Forms. These rules define actions to trigger on form objects based on preset conditions, user inputs, and user actions on the form. It helps  streamline the form filling experience while ensuring accuracy and speed.

* **Submit Actions:** The service provides several submit actions to allow you to persist and process captured data. You can use out-of-the-box service actions to send data to a REST endpoint, email the data, send data to various data sources, and send data to an AEM Workflow. You can also develop a custom submit action to perform an action specific to your business.

* **WYSIWYG editors:** The service provides several WYSIWYG editors: Adaptive Forms editor, Theme editor, Template editor to help you create and edit forms and related assets in WYSIWYG manner. The editors also provide out-of-the-box options to simulate views for popular mobile devices, tablets, and desktop screen configurations.

<!-- * **Emulators:** You can view an Adaptive Form in an in-built emulator. It helps you simulate how an Adaptive Form appears on different devices to an end user. It provides out-of-the-box options to simulate views for popular mobile devices, tablets, and desktop screen configurations. -->

## Cloud is the feature, but there is more! {#whats-new}

The following features are available only for AEM Forms as a Cloud Service:

**Faster form renditions and Faster server-side validations**
The service uses CDN and Dispatcher caching to deliver faster renditions and server-side validations for Adaptive Forms.

**Improved CAPTCHA**
You can now [validate CAPTCHA](captcha-adaptive-forms.md) either on Adaptive Form submission or on a business logic. You can also add conditions to validate CAPTCHA on a user action and show or hide the CAPTCHA component in an Adaptive Form based on rules. 

The CAPTCHA component provides an out-of-the-box integration with Google reCAPTCHA. You can also configure extra CAPTCHA services for the component, if necessary.

**Multiple master pages for Document of Record**
You can use a different master page for each page of a Document of Record. You can also control the placement of Adaptive Form panels on a document of record. The Cloud Service provides various pagination options to control placement of content. 

**AEM Archetype for Forms as a Cloud Service**
[AEM Archetype](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-27) helps you start developing for AEM Forms as a Cloud Service. You can use Archetype version 27 or later to create a project template compatible with AEM Forms as a Cloud Service environment. The Archetype also includes some sample themes and templates to help you started quickly. 

**Secure and improved information flow between forms and Sign**
[Adaptive Forms and Adobe Sign integration](working-with-adobe-sign.md) on Cloud Service offer simultaneous submission of data and signing activity. It makes form submission independent of signing status paving a way for faster submissions. On top of it, the service does not save any data on Cloud Service instances making the signing process super secure.

**Enhanced Visual Rule editor**
The service provides a hardened [Visual Rule editor](rule-editor.md#visual-rule-editor). The service has added following features to Visual rule editor to help you write capable rules:

* [New submission events](working-with-adobe-sign.md#available-operator-types-and-events-in-rule-editor): `Navigation`, `Step Completion`, `Successful Submission`, and `Error`

* [New data type `scope`](rule-editor.md#custom-functions). You can use the `scope` data type in a custom function to pass the entire scope of a form.

* Ability to use [@this to specify a JSDoc in a custom function](rule-editor.md#custom-functions). It allows invoking a custom function by using @this in an active component.

* Ability to add conditions for property-based rules.

**Add columns to headless tables**
You can add and delete columns to tables without headers. Hidden headers are added to such tables to help you add and delete columns. These headers are visible during authoring but remain hidden in the published form. Tables without headers are mostly found in Adaptive Forms created using the Automated Forms Conversion Service.

**Improved Submit Actions**
You can use the [Send Email](configuring-submit-actions.md#send-email#send-email) submit action to send a Document of Record (DoR) PDF as an attachment. 

**Group email for workflow**
You can choose to [send notification emails](aem-forms-workflow-step-reference.md#assign-task-step) from the Assign Task step to a single person or a group. The Assign task step now accepts email address of a group.

**Improved readability of translation files**
On Forms as a Cloud Service, reading order of the fields and panels of an Adaptive Form and message keys of corresponding translation files (.XLIFF files) has similar structure. It helps improving manual translation speeds.

**Best Practices Analyzer and migration tooling**
Best Practices Analyzer provides an assessment of your current AEM implementation. Run the tool before [migrating to Forms as a Cloud Service](migrate-to-forms-as-a-cloud-service.md). It  assesses readiness to move from an existing Adobe Experience Manager (AEM) deployment to AEM as a Cloud Service.

The service also provides an [improved migration experience](migrate-to-forms-as-a-cloud-service.md) to help you migrate rule scripts in an Adaptive Form on AEM 6.4 and AEM 6.5 to the format used in AEM Forms as a Cloud Service. Use the migration utility with the Content Transfer Tool to easily migrate Adaptive Forms to AEM Forms as a Cloud Service.
