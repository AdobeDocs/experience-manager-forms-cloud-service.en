---
title: Notable changes for existing [!DNL Adobe Experience Manager Forms] users
description: Are you an Experience Manager Forms user and looking to upgrade to [!DNL Adobe Experience Manager Forms] as a [!DNL Cloud Service]? Learn the most prominent changes before upgrading to Cloud Service.  
contentOwner: khsingh
---
# Notable changes for existing [!DNL Adobe Experience Manager Forms] users {#notable-changes-for-existing-AEM-Forms-users}

[!DNL Adobe Experience Manager Forms] as a [!DNL Cloud Service] brings some notable changes to existing features in comparison to [!DNL Adobe Experience Manager Forms] On-Premise and [!DNL Adobe-Managed Service] environments. The key differences are listed below:

* The service provides a local and a cloud-native development environment. You can use a [local development environment](setup-local-development-environment.md) to develop and test your custom code, components, templates, themes, adaptive forms, other assets before deploying these assets to a cloud environment. It helps speed up the development process.
* A Dispatcher and a CDN are included with the Cloud Service. You do not have to spend extra on acquiring a CDN and Dispatcher.
* The cloud-native environments do not have web console (configuration manager). You can use CI/CD route to make any [updates to the configurations](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/configuring/configuring-osgi.html?#configuring). It makes managing and updating configurations easier.
* Do not save any passwords or secrets. Use [!DNL Cloud Manager] APIs to convert and provide your passwords as secrets.
* URL convention of localized adaptive forms now supports specifying a locale in the URL. New URL convention enables caching localized forms on a Dispatcher or CDN. On Cloud Service environment, use the URL format `http://host:port/content/forms/af/<afName>.<locale>.html` to request a localized version of an adaptive form instead of `http://host:port/content/forms/af/afName.html?afAcceptLang=<locale>`. Adobe recommends using Dispatcher or CDN caching. It helps improve rendering speed of prefilled forms.
* Prefill service merges data with an adaptive form on a client. It helps improve the time required to prefill an adaptive form. You can always configure to run the merge action on the [!DNL Adobe Experience Manager Forms] Server.
* Email support only HTTP and HTTPs protocols, by default. [Contact the support team](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#sending-email) to enable ports for sending emails and to enable SMTP protocol for your environment. The restriction helps improve security of the platform.
* Recompile your code with the latest [!DNL Forms] as a [!DNL Cloud Service] SDK. It makes your code and bundles compatible with [!DNL Forms] as a [!DNL Cloud Service].
* If your Cloud Configurations contain a secret (password), create the Cloud Configurations separately for every Author instance of your Cloud Services environment (Developer, Stage, and Production). If a Cloud Configuration is also required on Publish instances, ensure that the Cloud Configuration is separately published/replicated on corresponding Publish instances (Developer, Stage, and Production).

For a comprehensive list of changes in Adobe Experience Manager as a [!DNL Cloud Service], See [What is New and What is Different](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/overview/what-is-new-and-different.html).

## Feature comparison {#comparison}

AEM Forms as a Cloud Service and Experience Manager 6.5 Forms share a common set of features: adaptive forms, data integration, integration with Adobe Sign, themes, templates, and forms management interface are identical. You can easily port your existing adaptive forms from an Experience Manager 6.5 Forms or an earlier version to AEM Forms as a Cloud Service.

### Features of Experience Manager 6.5 Forms and AEM Forms as a Cloud Service {#feature-comparison}

The following table lists the major features of Experience Manager 6.5 Forms and provides information about whether the feature is partially or fully supported in AEM Forms as a Cloud Service, with a link to more information about the feature. The table also lists extra features available in AEM Forms as a Cloud Service.


| Feature/Capability | AEM 6.5 Forms | [!DNL AEM Forms] as a [!DNL Cloud Service] |
| - | - | - |
| Adaptive Forms | &#x2611; | &#x2611; |
| Data Integration | &#x2611; | &#x2611;(With some changes) |
| Automated Forms Conversion service | &#x2611; | &#x2611; |
| Integration with Adobe Sign | &#x2611; | &#x2611;(With some changes) |
| Themes and Templates | &#x2611; | &#x2611; ([With some changes](themes.md#difference-in-themes))|
| Rule editor | &#x2611; | &#x2611; (With some changes) |
| Forms Portal | &#x2611; | --- |
| Integration with Adobe Analytics | &#x2611; | &#x2612; |
| Document Security | &#x2611; | &#x2612; |
