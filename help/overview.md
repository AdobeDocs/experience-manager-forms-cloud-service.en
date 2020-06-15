---
title: Experience Manager AEM Forms as a Cloud Service Overview
description: AEM Forms as a Cloud Service is a platform to create, manage, publish enterprise-class forms and business processes.
---

# Overview of AEM Forms as a Cloud Service {#overview}

Adobe Experience Manager Forms as a Cloud Service offers a cloud-native, Platform as a Service (PaaS) solution for businesses to create, manage, publish, and update complex digital forms while integrating submitted data with back-end processes, business rules, and saving data in a data store for later use. The service is always current, always available, and always learning. 

You can use the service to create interactive and engaging digital enrollment experiences. For example, an organization We.Forms is looking to digitize their customer enrollment journey. The organization also has multiple Print Forms, they are also looking to convert all of their print forms to interactive and responsive web forms. 

The organization can use AEM Forms to create new forms and Automated Forms Conversion service to automatically convert their legacy forms to adaptive forms (web forms). The organization can subscribe to AEM Forms as a Cloud Service and start using all these features without waiting to buy and set up the local infrastructure. It also frees the organization from the cycle of upgrades as the service is always up to date and always offers the latest features.    

<!--You can use the service to create interactive and engaging digital enrollment experiences complete with electronic signing, document of record, and processing the submitted data. For example, an organization We.Forms is looking to digitize their customer enrollment journey. It involves converting multiple legacy forms (PDF and Print Forms) to interactive and responsive web forms, enabling customers to electronically sign these forms, and keeping customers updated with the enrolment process with notifications. 

The organization can use AEM Forms to create new forms, Automated Forms Conversion service to automatically convert their legacy forms to adaptive forms (web forms), Adobe Sign to allow their customers to digitally sign the forms, and AEM workflow to process submitted data and send notifications. The organization can subscribe to AEM Forms as a Cloud Service and start using all these features without waiting to buy and setup the local infrastructure. It also frees you from the cycle of upgrading to latest version. The service is always upto date and offers latest features.    

-->

## Key features {#key-features}

* **Adaptive Forms:** You can create adaptive forms to deliver beautiful interactive experiences. These forms change behavior and appearance based on the underlying device. You can also use themes and templates with adaptive forms to mandate a uniform structure and appearance for all the forms of an organization or a department.  

* **Automatic conversion of PDF forms adaptive forms:** You can use automated forms conversion service to convert PDF Forms to adaptive from. It helps you accelerate digitization and modernization of data capture experiences of your organization. 

* **Prefill a form:** AEM Forms provide a service to fill a form with existing customer data based on a criteria to fasten the form filling process and reduce the abandon rate.

<!-- * **Integration with Adobe Sign:** You can use Adobe Sign components in an adaptive form. It allows a single or multiple users-sign a form in a sequence or in no particular order. Using electronic signatures helps you speed up contract or agreement signing workflows for legal, sales, payroll, human resource management, and more areas. 

* **Document of Record:** You can create a Document of Record (DoR) to keep a record of the information that you provide and submit in an adaptive form so that you can refer to it later. A DoR is a PDF version of a form. It includes both a template and data. You can generate a DoR either using a default template or associating any other template with the adaptive form. -->

## Comparison with AEM 6.5 Forms {#comparison}

The table below provides a list of major capabilities for AEM Forms as a Cloud Service pre-pilot release and AEM 6.5 Forms:

| Feature/Capability | AEM 6.5 Forms  | AEM Forms as a Cloud Service |
|---|---|---|
| Cloud-native architecture | No  | Yes  |
| Always up to date | No  | Yes |
| New feature roll-out frequency | Quarterly | Regularly  |
| Auto-scaling based on load| No | Yes |
| Zero downtime for upgrades| No | Yes|
| Adaptive Forms | Yes  | Yes  |
| Automated Forms Conversion service | Yes | Yes* |
| Document Security | Yes  | No  | 

`*` Use a local development instance to run Automated Forms Conversion service.

## Onboarding {#onboarding}

* If you are new to AEM as a cloud service, contact your Adobe representative to create an organization identifier for your company in the Adobe Identity Management System (IMS). Once Adobe has created an organization for your company, your designated administrator is added as the first member to the organization. Your administrator can add more members to your organization and provide them various roles. To enable forms functionality, follow instructions at [Enable Forms capability for your organization and Sites as a Cloud Service instances](setup-forms-cloud-service.md). 

* If you already have an IMS (Adobe Identity Management System) organization and have organization members ready, you are ready to enable forms functionality for your organization. To enable forms functionality, follow instructions at [Enable Forms capability for your organization and Sites as a Cloud Service instances](setup-forms-cloud-service.md).

* Existing Adobe Experience Manager Sites as a Cloud Service administrator can also configure and use AEM Forms as a Cloud Service. For details, see [Add Forms capability to your AEM Sites program](setup-forms-cloud-service.md#add-capability).