---
title: Notable changes for existing [!DNL Adobe Experience Manager Forms] users
description: Are you an Experience Manager Forms user and looking to upgrade to [!DNL Adobe Experience Manager Forms] as a [!DNL Cloud Service]? Learn the most prominent changes before upgrading to cloud service.  
contentOwner: khsingh

---

# Notable changes for existing [!DNL Adobe Experience Manager Forms] users {#notable-changes-for-existing-AEM-Forms-users}

[!DNL Adobe Experience Manager Forms] as a [!DNL Cloud Service] brings some notable changes to existing features in comparison to [!DNL Adobe Experience Manager Forms] on-premise and [!DNL Adobe Managed Service] environments. The key differences are listed below:

* A [cloud-native development environment](aem-forms-cloud-service-architecture.md.md) is available in addition to a local development environment.
* [Updates to the configurations](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/deploying/overview.html#osgi-configuration) are performed via source control rather than through the web console. Do not save any passwords or secrets. Use [!DNL Cloud Manager] APIs to convert and provide your passwords as secrets.
* URL convention of localized adaptive forms has changed to enable caching localized forms on a dispatcher or CDN.
* Prefill service merges data with an adaptive form on a client. It helps improve the time required to prefill an adaptive form. You can always configure to run the merge action on the [!DNL Adobe Experience Manager Forms] server.
* Email support is disabled, by default. [Contact the support team](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#sending-email) to enable email functionality for your environment.
* Recompile your code with the latest [!DNL Forms] as a [!DNL Cloud Service] SDK. It makes your code and bundles compatible with [!DNL Forms] as a [!DNL Cloud Service].
* A dispatcher and a CDN are included with the Cloud Service.

For a comprehensive list of changes in Adobe Experience Manager as a [!DNL Cloud Service], See [What is New and What is Different](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/overview/what-is-new-and-different.html). 
