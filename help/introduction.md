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

* **Integration with Adobe Sign:** You can use Adobe Sign components in an adaptive form. It allows a single or multiple users-sign a form in a sequence or in no particular order. Using electronic signatures helps you speed up contract or agreement signing workflows for legal, sales, payroll, human resource management, and more areas. 

* **Document of Record:** You can create a Document of Record (DoR) to keep a record of the information that you provide and submit in an adaptive form so that you can refer to it later. A DoR is a PDF version of a form. It includes both a template and data. You can generate a DoR either using a default template or associating any other template with the adaptive form. 

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

## AEM as a Cloud Service architecture {#architecture}

AEM Forms as a Cloud Service standardizes the deployment architecture for all customers, with the goal to completely free customers from architecture considerations. For instance, while the new AEM as a Cloud Service architecture still relies on the concept of micro-kernels for persistence, customers do not need to worry about which micro-kernel to pick from. The micro-kernels used both on the author and on the publish side are unique to AEM Cloud Service and otherwise not available to customers for on-premise installations.

AEM as a Cloud Service has a dynamic architecture with a variable number of AEM instances. It provides development, stage, production, and demonstration environments. It provides tools to manage AEM instances (Cloud Manager), maintain users and authentications (Admin Console and IMS (Adobe Identity management) system), configure caching (Fastly CDN), and cloud-native development environment. For more information on architecture see, [An Introduction to the Architecture of Adobe Experience Manager as a Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/core-concepts/architecture.html).

### Cloud Manager{#cloud-manager}
Cloud Manager is an essential component to [AEM as a Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/overview/introduction.html). Each new tenant of the AEM Forms as a Cloud Service is first provisioned for Cloud Manager access. Cloud Manager is the single-entry point for the operations and developer persona of our customers. It is the place from where the AEM programs and environments can be managed. Cloud Manager has evolved as a self-service portal where the main components of the AEM as a Cloud Service can be created and configured:
* Creating and managing programs
* Creating and managing the AEM environments within the programs
* Creating and managing the pipelines for deploying the customer code and configuration to a particular environment
* Getting notified of important lifecycle events for these components (e.g. product updates)
For more information about Cloud Manager, see [Understand Adobe Cloud Manager](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/cloud-manager/understand-cloud-manager-for-aem.html) and [Introduction to Cloud Manager](https://docs.adobe.com/content/help/en/experience-manager-cloud-manager/using/introduction-to-cloud-manager.html). 

### Users and Authentication {#users-and-authentication}

AEM as a Cloud Service includes Admin Console support for AEM instances and Adobe Identity Management System (IMS) based authentication. The Admin Console allows administrators to centrally manage all Experience Cloud users. Users and Groups can be assigned to product profiles associated with AEM as a Cloud Service instances, allowing them to log in to that instance. For more information about users, authentication, and, and accessing an instance of AEM as a Cloud Service, see [IMS Support for Adobe Experience Manager as a Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/security/ims-support.html#introduction).

Various personas are involved in a typical AEM Forms project. After you log in to your AEM Forms as a Cloud Service instance, you can [add users in admin console](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/security/ims-support.html) for personas applicable to your organization or project and [assign users to built-in groups](https://docs.adobe.com/content/help/en/experience-manager-65/forms/manage-administer-aem-forms/forms-groups-privileges-tasks.html) to provide them required privileges. 

To learn various in-built AEM Forms specific user groups and privileges available on AEM Forms as a Cloud Services instance, see [Configure, user, roles and groups](https://docs.adobe.com/content/help/en/experience-manager-65/forms/manage-administer-aem-forms/forms-groups-privileges-tasks.html).

### Developer Experience {#developer-experience}

The new architecture supporting AEM as a Cloud Service brings some key changes to the overall developer experience. One of the major goals for the changes to developer experience is to allow migration to AEM as a Cloud Service as quickly as possible, with little modifications to existing custom code.

### Cloud development {#cloud-development}
Here are the guidelines to run your existing code smoothly on AEM as a Cloud Service environment:
* Store your code and configurations to the Git repository of the associated Cloud Manager program. It makes managing and integrating code with CI/CD a breeze.  
* Make application code and configuration compatible with the baseline AEM Forms images. Using the latest APIs helps to build faster and secure applications. 
* Use the Cloud Manager pipeline associated with the Cloud Manager environment to build and deploy applications. It helps you bring the latest features and bug fixed for AEM Forms as a Cloud Service to your environment. 
* Try that your custom applications pass all the code quality, security, and performance gates enforced in the pipeline. It helps build secure and better performing applications which leads to better customer experience. You can always use Cloud Manager UI to skip some checks. 
This process is commonly referred to as cloud-first development. AEM Forms as a Cloud Service also provides an SDK to support rapid development before the pending code and configuration changes are attempted in the cloud.
Some interfaces that were previously part of the AEM QuickStart are no longer available to the users of the AEM as a Cloud Service environment. For instance, the Web Console where OSGI bundles and their associated configuration are managed. The CRXDE Lite content repository browser becomes only accessible on non-production environment types. A subset of the Web Console functionalities that developers require, especially when it comes to diagnostics and status purposes, is made available via a new developer console. 
Also, one of the most common requirements for developers is quick access to the log files of the various environments. With AEM Cloud Service, the log files of the different nodes in the Author, Publish are made available via the Cloud Manager, either in the form of files that can be downloaded or via APIs for tailing the logs. Due to the clear separation of code and content, developers can leverage a particular process for updating content as part of a deployment. The typical use cases for mutable content are:
* Standard “default” content that is part of the customer project (e.g. folders, templates, workflows...)
* Search index definitions
* ACLs and permissions
* Service users and user groups
Set up your development environment, [Configure your CI/CD Pipeline](https://docs.adobe.com/content/help/en/experience-manager-cloud-manager/using/how-to-use/configuring-pipeline.html), and learn to [deploy your code](https://docs.adobe.com/content/help/en/experience-manager-cloud-manager/using/how-to-use/deploying-code.html) on the environment. 

### Local development {#local-development}

When you set up and configure an AEM Forms as a Cloud service environment, you set up development, staging, and production environments. In addition, set up and configure a local development environment for rapid iterations and development. You can download and set up AEM SDK and AEM Forms add-on feature archive to set up a local Forms as a Cloud Service development environment.  For detailed instructions, see [Set up a local development environment](setup-local-development-environment.md).

### Debugging {#debugging}
AEM as a Cloud Service runs on self-service, scalable, cloud infrastructure. It requires AEM developers to understand and debug various facets of AEM as a Cloud Service, from build and deploy to obtaining details of running AEM applications. For detailed information, see [Debugging AEM as a Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/overview.html).


