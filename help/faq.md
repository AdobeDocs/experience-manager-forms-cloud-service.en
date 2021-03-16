---
title: Forms as a [!DNL Cloud Service] frequently asked questions 
description: Forms as a [!DNL Cloud Service] frequently asked questions
contentOwner: khsingh

---
# Frequently asked questions {#frequently-asked-questions}

* **Can I use Code Editor to create rules?**
You can use the Visual Editor to create the rules. The Code Editor is not available on [!DNL Forms] as a [!DNL Cloud Service]. If your adaptive form uses rule scripts developed using code editor, use the [Migration Utility](migrate-to-forms-as-a-cloud-service.md) to convert your code scripts to custom functions. You can use custom functions with Visual Editor to continue obtaining the results obtained with Code Editor.

* **Can I create an XFA-based adaptive form on Cloud Service instances?**
XFA-based adaptive forms are not supported yet. You cannot create such forms on Cloud Service instances. It is advised to not migrate XFA-based adaptive form from previous instances to Cloud Service instances. 

* **Can I migrate content from an On-Premise or [!DNL Adobe-Managed Services] environments to [!DNL Forms] as a [!DNL Cloud Service] environment?**
Yes, you can migrate your custom code, content, and assets from On-Premise or [!DNL Adobe-Managed Services] environments to [!DNL Forms] as a [!DNL Cloud Service] environment. For detailed instructions, see [Migrate to Forms as a Cloud Service](migrate-to-forms-as-a-cloud-service.md).

<!-- You can use package manager or Experience Manager UI to [export and import Forms and related assets](import-export-forms-templates.md), use the migration utility to make your existing assets compatible with [!DNL Forms] as a [!DNL Cloud Service], use the [Best Practices Analyzer](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/cloud-migration/best-practices-analyzer/overview-best-practices-analyzer.html?lang=en#best-practices-analyzer) tool to find the features and APIs that require changes and updated before migration, and use the [Content Transfer Tools](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/moving/home.html) to move your custom code without refactoring it. -->

* **Where can I get AEM [!DNL Forms] as a [!DNL Cloud Service] [!DNL Java™] API reference documentation?**
You can download Java™ API reference documentation from [!DNL Maven Central Repository]. To download:
    1. Go to [[!DNL Maven Central Repository]](https://mvnrepository.com/artifact/com.adobe.aem/aem-forms-sdk-api).
    1. Locate and open page containing the latest version of [!DNL Experience Manager Forms] SDK.
    1. Click the View All option to view all the files.
    1. Download and extract the `aem-forms-sdk-api-<version>-javadocs`.jar.  
    1. Open the index.html file to view the API reference documentation.

* **Where can I get [!DNL JavaScript™] API reference for adaptive forms?**
You can download [!DNL JavaScript™] API reference documentation from[!DNL  Maven Central Repository]. To download:
    1. Open [[!DNL Maven Central ~~Repository~~]](https://mvnrepository.com/artifact/com.adobe.aem/aem-forms-sdk-api).
    1. Locate and open page containing the latest version of [!DNL Experience Manager Forms] SDK.
    1. Click the View All option to view all the files.
    1. Download and extract the `aem-forms-sdk-api-<version>-jsdoc.jar`.  
    1. Open the index.html file to view the API reference documentation.

* **Can I continue using existing themes and templates?**
Yes, you can continue using existing themes and templates. You can also create a project based on [AEM Forms as a Cloud Service Archetype](setup-local-development-environment.md#forms-cloud-service-local-development-environment) and use included sample themes and templates. 

* **Can I produce schema-compliant data?**
Yes, you can create adaptive forms to produce schema-compliant data.

<!-- * **Can I pass custom parameters to the prefill service?**
Custom parameters are planned for an upcoming release. -->

* **Can I cache secured content?**
Caching secured content features is disabled, by default. To enable the feature, you can perform the instructions provided at [Caching Secured Content](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/permissions-cache.html).

* **I have a localized adaptive form; it is not rendering localized version? What could be the cause and how to resolve it?**

  [!DNL Forms] as a [!DNL Cloud Service] uses a selector in the URL path instead of URL parameter to identify a locale of a localized form.

  If you plan continue using URL parameters, set the Adaptive Form and Interactive Communication Web Channel configuration to the Use Browser Locale option. 
  
  To set values of a configuration, [Create OSGi Configurations](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/configuring-osgi.html?lang=en#generating-osgi-configurations-using-the-aem-sdk-quickstart) on local development environment and [deploy the configuration](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/using-cloud-manager/deploy-code.html?lang=en#deployment-process) to your Cloud Service instance. 

* **I have updated an adaptive form; the updated version is not available for customers to use?**
By default, CDN refreshes cache after every 5 minutes, wait for 5 minutes, and then check for the updated version.

* **Can I use the Signature step in an adaptive form to create an in-browser signing experience?**
No, the Signature step is not available for [!DNL Forms] as a [!DNL Cloud Service]. Remove the Signature step in your adaptive forms. Instead of Signature step, allow the users to Sign an adaptive form after submission. It helps you continue providing an in-browser signing experience.

* **Can I use the Verify step in an adaptive form?**
No, the Verify step is not available for [!DNL Forms] as a [!DNL Cloud Service]. Remove the verify step from your existing adaptive forms before moving such forms to a Cloud Service environment.

* **Can I add charts to an adaptive form?**
Yes, you can add charts to adaptive forms. Adaptive Forms provides a chart component. You can use it to add charts to an adaptive form.

* **Can I connect a form data model to a relational database model?**
You can connect a Form Data Model to [!DNL RESTful web services], [!DNL SOAP-based web services], [!DNL OData services], and Experience Manager user profile as data sources. Support to connect a Form Data Model with a relational database is not available.  

* **Can I use custom certificates with Form Data Model for authentication?**
Form Data Model does not provide a method to use custom certificates for authentication. So, the custom certificates like x509 and 2-way SSL are not supported.  
