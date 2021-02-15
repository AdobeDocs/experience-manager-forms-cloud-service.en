---
title: Forms as a [!DNL Cloud Service] frequently asked questions 
description: Forms as a [!DNL Cloud Service] frequently asked questions
contentOwner: khsingh

---
# Frequently asked questions {#frequently-asked-questions}

* **Can I use Code Editor to create rules?**
You can use the Visual Editor to create the rules. The Code Editor is not available on [!DNL Forms] as a [!DNL Cloud Service]. If your adaptive form uses rule scripts developed using code editor, use the migration utility to convert your code scripts to custom functions. You can use custom functions with Visual Editor to continue obtaining the results obtained with Code Editor.

* **Is [!DNL Forms] as a [!DNL Cloud service] available for free?**
No, you require a license to use [!DNL Forms] as a [!DNL Cloud Service].

* **Can I migrate content from an on-premise or [!DNL Adobe Managed Services] environments to [!DNL Forms] as a [!DNL Cloud Service] environment?**
Yes, you can migrate your custom code, content, and assets from on-premise or [!DNL Adobe Managed Services] environments to [!DNL Forms] as a [!DNL Cloud Service] environment. For detailed instructions, see [Migrate to Forms as a Cloud Service](migrate-to-forms-as-a-cloud-service.md).

<!-- You can use package manager or Experience Manager UI to [export and import Forms and related assets](import-export-forms-templates.md), use the migration utility to make your existing assets compatible with [!DNL Forms] as a [!DNL Cloud Service], use the [Best Practices Analyzer](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/cloud-migration/best-practices-analyzer/overview-best-practices-analyzer.html?lang=en#best-practices-analyzer) tool to find the features and APIs that require changes and updated before migration, and use the [Content Transfer Tools](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/moving/home.html) to move your custom code without refactoring it. -->

* **How frequently shall I run [!DNL Forms] as a [!DNL Cloud Service] pipeline?**
You receive a notification in Cloud Manager when a product update is available. Run the pipeline whenever product updates are available to install latest features and updates.

* **Where can I get AEM [!DNL Forms] as a [!DNL Cloud Service] Java API Reference?**
You can download [!DNL Javadoc] from [!DNL Maven Central Repository]. To download [!DNL Javadoc]:
    1. Go to [[!DNL Maven Central Repository]](https://mvnrepository.com/artifact/com.adobe.aem/aem-forms-sdk-api).
    1. Locate and open page containing the latest version of [!DNL Experience Manager Forms] SDK.
    1. Click the View All option to view all the files.
    1. Download and extract the `aem-forms-sdk-api-<version>-javadoc`.jar.  
    1. Open the index.html file to view the Javadoc.

* **Where can I get JavaScript API reference for adaptive forms?**
You can download [!DNL Javadoc] from[!DNL  Maven Central Repository]. To download [!DNL Javadoc]:
    1. Open [[!DNL Maven Central ~~Repository~~]](https://mvnrepository.com/artifact/com.adobe.aem/aem-forms-sdk-api).
    1. Locate and open page containing the latest version of [!DNL Experience Manager Forms] SDK.
    1. Click the View All option to view all the files.
    1. Download and extract the `aem-forms-sdk-api-<version>-jsdoc.jar`.  
    1. Open the index.html file to view the Javadoc.

* **Can I continue use existing themes and templates?**
Yes, you can continue using existing themes and templates. Consider the following about themes:

  * Themes are saved at */etc/clientlibs/fd/themes*, by default. If you save themes at any other location, provide read access to forms authors on new location.
  * When you apply the ultramarine theme, the add new row (+) button and delete row button applied to a table do not work.

* **Can I add charts to an adaptive form?**
Yes, you can add charts to adaptive forms. Adaptive Forms provides a chart component. You can use it to add charts to an adaptive form.  

* **Can I produce schema compliant data?**
Yes, you can create adaptive forms to produce schema compliant data.

<!-- * **Can I pass custom parameters to the prefill service?**
Custom parameters are planned for an upcoming release. -->

* **Can I cache secured content?**
Caching secured content features is disabled, by default. To enable the feature, you can perform the instructions provided at [Caching Secured Content](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/permissions-cache.html).

* **Can I specify a custom adaptive form template in the [!DNL Automated Forms Conversion service] conversion dialog?**
You can manually type path of any template or parent folder and then browse to select the child. Path browsing is limited only to child folders of the path specified in template field.

* **I have a localized adaptive form; it is not rendering localized version? What could be the cause and how to resolve it?**

  [!DNL Forms] as a [!DNL Cloud Service] uses a selector in the URL path instead of URL parameter to identify a locale of a localized form. 

  If you plan continue using URL parameters, set the Adaptive Form and Interactive Communication Web Channel configuration to the Use Browser Locale option. For information about setting configurations in [!DNL Cloud Service] environment, see the [Deploying to Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/deploying/overview.html#osgi-configuration).

* **I have updated an adaptive form; the updated version is not available for customers to use?**
By default, CDN refreshes cache after every 5 minutes, wait for 5 minutes, and then check for the updated version.

* **Can I connect a form data model to a relational database model?**
You can connect a Form Data Model to [!DNL RESTful web services], [!DNL SOAP-based web services], [!DNL OData services], and AEM user profile as data sources. Support to connect a Form Data Model with a relational database is not available yet.  

* **Can I use custom certificates with Form Data Model for authentication?**
Form Data Model does not provide a secure method to use custom certificates for authentication. So, the custom certificates like x509 and 2-way SSL are not supported.  

* **Can I use the Signature step in an adaptive form to create an in-browser signing experience?**
No, the Signature step is not available for [!DNL Forms] as a [!DNL Cloud Service]. Remove the Signature step in your adaptive forms. Instead of Signature step, allow the users to Sign an adaptive form after submission. It helps you continue providing an in-browser signing experience.

* **Can I use the Verify step in an adaptive form?**
No, the Verify step is not available for [!DNL Forms] as a [!DNL Cloud Service]. Remove the verify step from your existing adaptive forms before moving such forms to a Cloud Service environment.
