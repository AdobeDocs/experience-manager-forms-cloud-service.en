---
title: Known issues and limitations
description: Known issues and limitations of  [!DNL AEM Forms] as a Cloud Service environment
contentOwner: khsingh
role: Business Practitioner, Developers
level: Intermediate
topic: Administration
exl-id: 871f294d-f251-4966-a021-39df65b613f0
---
# Known issues and limitations {#known-issues-and-limitations}

Before you begin using [!DNL AEM Forms] as a Cloud Service, review the following known issues and limitations:

## Known issues {#known-issues}

* Do not add and run a test that submits an Adaptive Form from a publish instance to an AEM Workflow running on an Author instance until further notice.

* When you import an Adaptive Form that uses a template containing the **[!UICONTROL Save]** button, the **[!UICONTROL Save]** button continues to appear in the Adaptive Form even after it is removed from corresponding template. Remove the **[!UICONTROL Save]** button from your Adaptive Forms before publishing it. Keep an eye on release notes for the availability of the Forms Portal and Save as a draft feature to restore and use the button.

* The **[!UICONTROL Set variable]** step of AEM Workflows does not support variables of type array list. You can use the process step to set variables of type array list. 


## Limitations {#limitations}

* You can use a Cloud Service instance to generate both an Acroform-based and XDP-based Document of Record (DoR). Whereas the local development environment ([!DNL AEM Forms] as a Cloud Service SDK) can generate only Acroform-based Document of Record (DoR).  

* Support for XFA-based Adaptive Forms is not available out of the box. If you intend to use XFA-based Adaptive Forms, contact Adobe Support with details of your use case and specific requirements.
