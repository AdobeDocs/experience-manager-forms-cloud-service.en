---
title: Forms as a Cloud Service frequently asked questions 
seo-title: Forms as a Cloud Service frequently asked questions
description: Forms as a Cloud Service frequently asked questions
seo-description: Forms as a Cloud Service frequently asked questions
contentOwner: khsingh

---

# Frequently asked questions and known issues {#frequently-asked-questions-and-known-issues}

Frequetly asked questions provide you workarounds and alernate ways to achieve a solution. You can also learn about some known issues with the product.

## Frequently asked questions {#frequently-asked-questions}

* **Can I use code editor to create rules?**
You can use the visual editor to create the rules. The code editor is not available on Forms as a Cloud Service. If your AF uses custom scripts developed using code editor, they would be migrated to custom functions in a later release.

* **Is Forms as a Cloud service available for free?**
No, you require a license to use Forms as a Cloud Service.

* **Can I migrate content from an on-prem or Adobe Managed Services environments to Forms as a Cloud Service environment?**
Yes, you can [export and import Forms and related assets](import-export-forms-templates.md) from your on-prem or Adobe Managed Services environments to Forms as a Cloud Service environment. You can also use [Content Transfer Tools](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/moving/home.html) to move your custom code without refactoring it.

* **How frequently shall I run Forms as a Cloud Service pipeline?**
You receive a Cloud Manager notification when a product update is available. Run the pipeline whenever product updates are available to install latest features and updates.

* **Where can I get AEM Forms as a Cloud Service Java API Reference?**
You can download Javadoc from Maven Central. To download Javadoc, 
    1. Open [maven central](https://mvnrepository.com/artifact/com.adobe.aem/aem-forms-sdk-api).
    1. Locate and open page containing the latest version of Experience Manager Forms SDK.
    1. Click the View All option to view all the files.
    1. Download and extract the aem-forms-sdk-api-<version>-javadoc.jar.  
    1. Open the index.html file to view the Javadoc.

* **Where can I get JavaScript API reference for adaptive forms?**
You can download Javadoc from Maven Central. To download Javadoc, 
    1. Open [maven central](https://mvnrepository.com/artifact/com.adobe.aem/aem-forms-sdk-api).
    1. Locate and open page containing the latest version of Experience Manager Forms SDK.
    1. Click the View All option to view all the files.
    1. Download and extract the aem-forms-sdk-api-<version>-jsdoc.jar.  
    1. Open the index.html file to view the Javadoc. 

* **Can I continue use existing themes and templates?**
Yes, you can continue using existing themes and templates. Consider the following about themes:
    * Themes are saved at */etc/clientlibs/fd/themes*, by default. If you save themes at any other location, provide read access to forms authors on new location. 
    * When you apply the ultramarine theme, the add new row (+) button and delete row button applied to a table do not work. 


* **Can I add charts to an adaptive form?** 
You can create a custom component to add charts to adaptive forms. The out of the box chart component is planned for an upcoming release. 

* **Can I produce schema compliant data?** 
Yes, you can create adaptive forms to produce schema compliant data. You can use transitional schema definitions for your schema. The strict schema validations are planned for an upcoming release.

* **Can I pass custom parameters to the prefill service?**
Custom parameters are planned for an upcoming release.

* **Can I cache secured content?**
Caching secured content features is disabled, by default. To enable the feature, you can perform the instructions provided in the [Caching Secured Content](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/permissions-cache.html) article.

* **Can I specify a custom adaptive form template in the Automated Forms Conversion service conversion dialog?**
You can manually type path of any template or parent folder and then browse to select the child. Path browsing is limited only to child folders of the path specified in template field. 

* **I have a localized adaptive form; it is not rendering localized version? What could be the cause and how to resolve it?**
AEM Forms as a Cloud Service uses a selector in the URL path instead of URL parameter to identify a locale of a localized form. If you plan continue using URL parameters, set the Adaptive Form and Interactive Communication Web Channel Configuration to the Use Browser Locale option. For information about setting configurations in AEM as a Cloud Service environment, see the [Deploying to AEM as a Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/deploying/overview.html#osgi-configuration) article. 

* **I have updated an adaptive form; the updated version is not available for customers to use?**
By default, CDN refreshes cache after every 5 minutes, wait for 5 minutes, and then check for the updated version. 

* **Can I connect a form data model to a relational database model?**
You can connect a Form Data Model to RESTful web services, SOAP-based web services, OData services, and AEM user profile as data sources. Support to connect a Form Data Model with a relational database is not available yet.  

* **Can I use custom certificates with Form Data Model for authentication?**
Form Data Model does not provide a secure method to use custom certificates for authentication. So, the custom certificates like x509 and 2-way SSL are not supported.  

* **Can I use the Signature step in an adaptive form to create an in-browser signing experience?**
No, the Signature step is not available for Forms as a Cloud Service.

* **Can I use the Verify step in an adaptive form?**
Ans: No, the Verify step is not available for Forms as a Cloud Service.
