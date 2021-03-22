---
title: Known issues and limitations
description: Known issues and limitations of  [!DNL AEM Forms] as a [!DNL Cloud Service] environment
contentOwner: khsingh
role: Business Practitioner, Developers
level: Intermediate
topic: Administration
---

# Known issues and limitations {#known-issues-and-limitations}

Before you begin using AEM Forms as a Cloud Service, review the following known issues and limitations:

## Known issues {#known-issues}

<!-- * CDN caching stops working after 300 seconds and all the requests to cache on CDN are redirected to Dispatcher. To resolve the issue, [set the age header to 0](troubleshooting-caching-performance.md#cdn-caching-stops-working-after-300-seconds). -->
* When you import an Adaptive Form that uses a template containing the Save button, the Save button continues to appear in an Adaptive Form even after it is removed from corresponding theme template. The save as a draft feature is not available for Adaptive Forms created and hosted on AEM Forms Cloud Service. So, the button would not work. Manually remove the Save button from the form to avoid any confusion.
* Forms and other assets under the Forms & Documents section do not display referenced content.
* Do not add and run a test that submits an Adaptive Form from a publish instance to an AEM Workflow running on an Author instance until further notice.

## Limitations {#limitations}

* You cannot generate an Acroform (Forms created using Adobe Acrobat) based Document of Record (DoR) on a local development environment. However, you can use a Cloud Service instance to generate an Acroform-based Document of Record (DoR).

* The Cloud Service does not contain a metamodel for Automated Forms Conversion Service. You can download the default schema from [here](https://experienceleague.adobe.com/docs/aem-forms-automated-conversion-service/assets/global.schema.json).

* Support for XFA-based adaptive forms is not available out of the box. If you intend to use XFA-based adaptive forms in a production environment, contact Adobe Support with details of your use case and specific requirements.