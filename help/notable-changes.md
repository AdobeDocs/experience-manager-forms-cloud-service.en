---
title: What has changed between AEM 6.5 Forms and AEM Cloud Services
description: Are you an Experience Manager Forms user and looking to upgrade to [!DNL Adobe Experience Manager Forms] as a [!DNL Cloud Service]? Learn the most prominent changes before upgrading or migrating to Cloud Service.  
contentOwner: khsingh
---
# Notable changes for existing [!DNL Adobe Experience Manager Forms] users  {#notable-changes-for-existing-AEM-Forms-users}

[!DNL Adobe Experience Manager Forms] as a [!DNL Cloud Service] brings some notable changes to existing features in comparison to [!DNL Adobe Experience Manager Forms] On-Premise and [!DNL Adobe-Managed Service] environments. The key differences are listed below:

* The service provides a local and a cloud-native development environment. You can use a [local development environment](setup-local-development-environment.md) to develop and test your custom code, components, templates, themes, Adaptive Forms, other assets before deploying these assets to a cloud environment. It helps speed up the development process.
* AEM as Cloud Service is shipped with a built-in CDN. Its main purpose is to reduce latency by delivering cacheable content from the CDN nodes at the edge, near the browser. It is fully managed and configured for optimal performance of AEM applications.
* A cloud-native environment does not have web console (configuration manager). You can use [[!DNL AEM Forms] as a [!DNL Cloud Service] SDK to generate configurations](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html?lang=en#generating-osgi-configurations-using-the-aem-sdk-quickstart) and CI/CD pipeline to [deploy the configuration](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/using-cloud-manager/deploy-code.html?lang=en#deployment-process) to your Cloud Service instance.

* URL convention of localized Adaptive Forms now supports specifying a locale in the URL. New URL convention enables caching localized forms on a Dispatcher or CDN. On Cloud Service environment, use the URL format `http://host:port/content/forms/af/<afName>.<locale>.html` to request a localized version of an Adaptive Form instead of `http://host:port/content/forms/af/afName.html?afAcceptLang=<locale>`. Adobe recommends using Dispatcher or CDN caching. It helps improve rendering speed of prefilled forms.
* Prefill service merges data with an Adaptive Form on a client. It helps improve the time required to prefill an Adaptive Form. You can always configure to run the merge action on the [!DNL Adobe Experience Manager Forms] Server.
* Email support only HTTP and HTTPs protocols, by default. [Contact the support team](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#sending-email) to enable ports for sending emails and to enable SMTP protocol for your environment.
* [!DNL Adobe Experience Manager Forms] as a [!DNL Cloud Service] brings many new features and possibilities into your AEM Projects. However, there are some changes required to Adobe Experience Manager Maven projects to be compatible with AEM Cloud Service. At a high-level, AEM requires a separation of content and code into discrete subpackages to respect the split between mutable and immutable content. Use the [Repository Modernizer](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/refactoring-tools/repo-modernizer.html) tool to restructure existing project packages by separating content and code into discrete packages to be compatible with the project structure defined for Adobe Experience Manager as a Cloud Service.
* If your Cloud Configuration contains a secret (password), create a separate Cloud Configuration for every Author instance (Developer, Stage, and Production). If a Cloud Configuration is also required on Publish instances, publish/replicate a separate Cloud Configuration for every Publish instance (Developer, Stage, and Production).
* When you create a Cloud Configuration that contains a secret, each Cloud Service instance (Developer, Stage, and Production) uses its own encryption key to encrypt the password before storing it. So, manually create such Cloud Configuration for every Cloud Service instance (Developer, Stage, and Production). Also, do not store secrets used in a Cloud Configuration to your Cloud Manager Git repository.  
* Use [!DNL Cloud Manager] [APIs to convert and provide your passwords as secrets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html?lang=en#setting-values-via-api). Do not store plain text password or secrets on your environments.

For a comprehensive list of changes in Adobe Experience Manager as a [!DNL Cloud Service], See [What is New and What is Different](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/overview/what-is-new-and-different.html).

<!-- ## Feature comparison {#comparison}

[!DNL AEM Forms] as a [!DNL Cloud Service] and Experience Manager 6.5 Forms share a common set of features: Adaptive Forms, data integration, integration with [!DNL Adobe Sign], themes, templates, and forms management interface are identical. You can easily port your existing Adaptive Forms from an Experience Manager 6.5 Forms or an earlier version to [!DNL AEM Forms] as a [!DNL Cloud Service].

### Features of AEM 6.5 Forms and [!DNL AEM Forms] as a [!DNL Cloud Service] {#feature-comparison}

The following table lists the major features of Experience Manager 6.5 Forms and provides information about whether the feature is partially or fully supported in [!DNL AEM Forms] as a [!DNL Cloud Service], with a link to more information about the feature. The table also lists extra features available in [!DNL AEM Forms] as a [!DNL Cloud Service].


| Feature/Capability | AEM 6.5 Forms | [!DNL AEM Forms] as a [!DNL Cloud Service] |
| - | - | - |
| Adaptive Forms | &#x2611; | &#x2611; |
| Data Integration | &#x2611; | &#x2611;(With some changes) |
| Automated Forms Conversion Service | &#x2611; | &#x2611; |
| Integration with Adobe Sign | &#x2611; | &#x2611;(With some changes) |
| Themes and Templates | &#x2611; | &#x2611; ([With some changes](themes.md#difference-in-themes))|
| Rule editor | &#x2611; | &#x2611; (With some changes) |
| Forms Portal | &#x2611; | --- |
| Integration with Adobe Analytics | &#x2611; | &#x2612; |
| Document Security | &#x2611; | &#x2612; | -->

<!-- ## New features {#comparison} -->

## Feature comparison {#feature-comparison}

[!DNL AEM Forms] as a [!DNL Cloud Service] and AEM 6.5 Forms share some features like Adaptive Forms, Data Integration, and Forms Portal. You can easily port your existing Adaptive Forms from an AEM 6.5 Forms or an earlier version to [!DNL AEM Forms] as a [!DNL Cloud Service].

### Features of AEM 6.5 Forms and [!DNL AEM Forms] as a [!DNL Cloud Service] {#aem-6.5-vs-aem-forms-as-a-cloud-service}

The following table lists the major features of AEM 6.5 Forms and provides information about the features coming soon to [!DNL AEM Forms] as a [!DNL Cloud Service]:

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
| Adaptive Forms | &#x2611; | &#x2611; |
| Data Integration | &#x2611; | &#x2611; |
| Automated Forms Conversion Service | &#x2611; | &#x2611; |
| Integration with [!DNL Adobe Sign] | &#x2611; | &#x2611; |
| Integration with AEM Sites | &#x2611; | &#x2611; |
| Enhanced Visual Rule editor | &#x2612; | &#x2611; |
| Forms Portal | &#x2611; | Coming Soon |
| Integration with Adobe Analytics | &#x2611; | Coming Soon |
| Integration with Adobe Target | &#x2611; | Coming Soon |
| Document Security | &#x2611; | &#x2612; |

`*` New features every month and bug fix updates on daily basis.

For a comprehensive list of changes in AEM as a [!DNL Cloud Service], See [What is New and What is Different](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/overview/what-is-new-and-different.html) and [Notable changes in [!DNL AEM Forms] as a [!DNL Cloud Service]](notable-changes.md)