---
title: Experience Manager AEM Forms as a Cloud Service Overview
description: AEM Forms as a Cloud Service is a platform to create, manage, publish enterprise-class forms and business processes.
---

# Overview of AEM Forms as a Cloud Service {#overview}

Adobe Experience Manager Forms as a Cloud Service offers a cloud-native, Platform as a Service (PaaS) solution for businesses to create, manage, publish, and update complex digital forms while integrating submitted data with back-end processes, business rules, and saving data in a data store for later use. The service is always current, always available, and always learning. 

You can use the service to create interactive and engaging digital enrollment experiences. For example, an organization We.Forms is looking to digitize their customer enrollment journey. The organization also has multiple print forms, they are also looking to convert all of their print forms to interactive and responsive web forms. They also have multiple data sources with existing customer data, they are looking to pre-populate forms, archive filled forms, and e-sign the forms.  

The organization can use AEM Forms as a Cloud Service to create new forms and Automated Forms Conversion service to automatically convert their legacy forms to adaptive forms (web forms). he service also helps create Document of Records (DoR) to archive filled forms, create business processes with AEM Workflows, and integrates with Adobe Sign for electronic signatures. The organization can subscribe to AEM Forms as a Cloud Service and start using all these features without waiting to buy and  the local infrastructure. It also frees the organization from the cycle of upgrades as the service is always up to date and always offers the latest features.  

## Key features {#key-features}

* **Adaptive Forms:** You can create adaptive forms to deliver beautiful interactive experiences. These forms change behavior and appearance based on the underlying device. You can also use themes and templates with adaptive forms to mandate a uniform structure and appearance for all the forms of an organization or a department.  

* **Automatic conversion of PDF forms adaptive forms:** You can use Automated Forms Conversion service to convert PDF Forms to adaptive from. It helps you accelerate digitization and modernization of data capture experiences of your organization. 

* **Data Integration:** You can connect adaptive forms directly to disparate data sources to access and update data, pre or post process data accessed from data sources or captured using adaptive forms.

* **Prefill a form:** AEM Forms provide a service to fill a form with existing customer data based on a criteria to fasten the form filling process and reduce the abandon rate.

* **Submit actions:** AEM Forms provides several submit actions to allow you to persist and process captured data. Apart from saving data to a data store, you can also send data to a REST endpoint, or email the data. You can also develop custom submit actions. Custom submit actions help you perform actions specific to your organization before submitting the data. 

* **Business Processes:** You can use AEM Workflows to create business processes and automate operations. For example, starting an approval and rejection workflows on submission of an adaptive form.  

* **Schema-compliant data:** You can create adaptive forms to produce schema-compliant data. It helps you submit captured data to existing processes without any, or minimal modifications. You can use strict or transitional schema definitions for your schema. 

* **Visual rule editor:** Rule editor empowers you to build dynamism and interactivity to adaptive forms. These rules define actions to trigger on form objects based on preset conditions, user inputs, and user actions on the form. It helps further streamline the form filling experience ensuring accuracy and speed.

* **WYSIWYG editors:** AEM Forms provides several WYSIWYG editors: Adaptive Forms editor, Theme editor, Template editor to help you create and edit forms and related assets while experiencing the actual appearance of content to be displayed on a customer’s device. 

* **Emulators:** You can view an adaptive form in an in-built emulator. It helps you simulate how an adaptive form appears on different devices to an end user. It provides out-of-the-box options to simulate views for popular mobile devices, tablets, and desktop screen configurations. 

<!-- * **Integration with Adobe Sign:** You can use Adobe Sign components in an adaptive form. It allows a single or multiple users-sign a form in a sequence or in no particular order. Using electronic signatures helps you speed up contract or agreement signing workflows for legal, sales, payroll, human resource management, and more areas. 

* **Document of Record:** You can create a Document of Record (DoR) to keep a record of the information that you provide and submit in an adaptive form so that you can refer to it later. A DoR is a PDF version of a form. It includes both a template and data. You can generate a DoR either using a default template or associating any other template with the adaptive form. -->

## Comparison with AEM 6.5 Forms {#comparison}

The table below provides a list of major capabilities for AEM Forms as a Cloud Service pre-pilot release and AEM 6.5 Forms:


| Feature/Capability | AEM 6.5 Forms  | AEM Forms as a Cloud Service |
|---|---|---|
| Cloud-native architecture | No  | Yes  |
| Always up to date | No  | Yes |
| New feature roll-out frequency | Quarterly | Agile*  |
| Auto-scaling based on load| No | Yes |
| Zero downtime for upgrades| No | Yes|
| Adaptive Forms | Yes  | Yes  |
| Automated Forms Conversion service | Yes | Yes |
| CDN (content delivery network) | No  | Yes  |
| Automated upgrades with Continuous Integration and Continuous Delivery (CI/CD) | Yes  | No  |
| Topologies optimized for maximum resilience and efficiency | No  | Yes  |
| Self Service via Cloud Manager | No  | Yes  |  
| Cloud-native development environment | No  | Yes  | 

`*` New features every month and bug fix updates on daily basis .

For a comprehensive list of changes in AEM as a Cloud Service, See [What is New and What is Different](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/overview/what-is-new-and-different.html).

## Onboarding {#onboarding}

* If you are new to AEM as a cloud service, contact your Adobe representative to create an organization identifier for your company in the Adobe Identity Management System (IMS). Once Adobe has created an organization for your company, your designated administrator is added as the first member to the organization. Your administrator can add more members to your organization and provide them various roles. To enable forms functionality, follow instructions at [Enable Forms capability for your organization and Sites as a Cloud Service instances](setup-forms-cloud-service.md). 

* If you already have an IMS (Adobe Identity Management System) organization and have organization members ready, you are ready to enable forms functionality for your organization. To enable forms functionality, follow instructions at [Enable Forms capability for your organization and Sites as a Cloud Service instances](setup-forms-cloud-service.md).

* Existing Adobe Experience Manager Sites as a Cloud Service administrator can also configure and use AEM Forms as a Cloud Service. For details, see [Add Forms capability to your AEM Sites program](setup-forms-cloud-service.md#add-capability).