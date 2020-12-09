---
title: Notable changes for existing AEM Forms users
seo-title: Notable changes for existing AEM Forms users
description: Notable changes for existing AEM Forms users
seo-description: Notable changes for existing AEM Forms users
contentOwner: khsingh

---

# Notable changes for existing AEM Forms users {#notable-changes-for-existing-AEM-Forms-users}

AEM Forms as a Cloud Service brings some notable changes to existing features in comparison to AEM Forms on-premise and Adobe Managed Service environments. The key differences are listed below:

* A cloud-native development environment is available in addition to a local development environment.
* [Updates to the configurations](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/deploying/overview.html#osgi-configuration) are performed via source control rather than through the web console. Do not save any password or secrets. Use Cloud Manager APIs to convert and provide your passwords as secrets.
* URL convention of localized adaptive forms has changed to enable caching localized forms on a dispatcher or CDN.
* [Prefill service](https://docs.adobe.com/content/help/en/experience-manager-65/forms/adaptive-forms-advanced-authoring/prepopulate-adaptive-form-fields.html#aem-forms-custom-prefill-service) merges data with an adaptive form on a client. It helps improve the time required to prefill an adaptive form. You can always configure to run the merge action on the AEM Forms server.
* Email support is disabled, by default. Contact the support team to enable email functionality for your environment.
* Recompile your code with the latest Forms as a Cloud Service SDK. It makes your code and bundles compatible with Forms as a Cloud Service.
* Dispatcher and a CDN are included.

For a comprehensive list of changes in AEM as a Cloud Service, See [What is New and What is Different](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/overview/what-is-new-and-different.html). 
