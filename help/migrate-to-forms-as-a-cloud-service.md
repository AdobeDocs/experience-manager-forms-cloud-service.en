---
title: How to migrate from an AEM 6.5 Forms and AEM 6.4 Forms to [!DNL AEM Forms] as a [!DNL Cloud Service] environment?
description: Migrate from an AEM Forms On-Premise environment to [!DNL AEM Forms] as a [!DNL Cloud Service] environment
contentOwner: khsingh
feature: Adaptive Forms
role: Business Practitioner, Developers
level: Intermediate
topic: Migration
---

# Migrate to [!DNL AEM Forms] as a [!DNL Cloud Service]  {#Harden-your-AEM-Forms-as-a-Cloud-Service-environment}

You can migrate your Adaptive Forms, themes, templates, and cloud configurations from <!-- AEM 6.3 Forms--> AEM 6.4 Forms on OSGi and AEM 6.5 Forms on OSGi to [!DNL AEM] as a [!DNL Cloud Service] . Before migrating these assets, use the Migration Utility to convert the format used in the earlier versions to the format used in [!DNL AEM] as a [!DNL Cloud Service]. When you run migration utility, the following assets are updated:

* Custom components for Adaptive Forms
* Adaptive Forms templates and themes
* Cloud configurations
* Code editor scripts are converted to reusable functions and applied to visual rules.

## Considerations {#consideration}

* The service helps migrate content from only AEM Forms on OSGi environments. Migrating content from AEM Forms on JEE to a Cloud Service environment is not supported.

* (Only for AEM 6.3 Forms or a previous version environment upgraded to AEM 6.4 Forms or AEM 6.5 Forms) Adaptive Forms based on out-of-the-box templates and themes available in AEM 6.3 Forms or previous version are not supported on [!DNL AEM Forms] as a [!DNL Cloud Service].

## Prerequisites {#prerequisites}

* In a Cloud Service environment, the migration utility works in conjunction with the User Mapping Tool and Content Transfer Tool. The migration utility makes AEM Forms assets compatible with Cloud Service and the content transfer tool migrates the content from your AEM Forms environment to an [!DNL AEM] as a [!DNL Cloud Service] environment. Before using the migration utility, learn the process of [moving to AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/home.html). The process has two tools:
  * [User Mapping Tool](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/cloud-migration/content-transfer-tool/using-user-mapping-tool.html?lang=en#cloud-migration): The User Mapping Tool helps you map your users with corresponding Adobe IMS user accounts. 
  * [Content Transfer Tool](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/cloud-migration/content-transfer-tool/overview-content-transfer-tool.html?#cloud-migration): The Content Transfer Tool helps you prepare and transfer content from existing environment to a Cloud Service environment.
* Accounts with administrator privileges on AEM Forms as a Cloud Service and your local AEM Forms environment.
* Download and install Best Practice Analyzer, Content Transfer Tool, and AEM Forms Migration Utility from [Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html)

<!-- * Download the latest [compatibility package](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/forms-updates/aem-forms-releases.html?lang=en#aem-65-forms-releases) for your AEM Forms version. -->

## Migrate AEM Forms assets  {#use-the-migration-utility}

Perform the following steps to make your AEM Forms assets compatible with Cloud Service and transfer them to an [!DNL AEM] as a [!DNL Cloud Service] environment.

1. Create a [clone](https://experienceleaguecommunities.adobe.com/t5/adobe-experience-manager/correct-method-to-clone-the-aem-environment/qaq-p/363487) of your existing AEM Forms environment.

    Always use the cloned environment to run the Content Transfer Tool and the migration utility. Do not run the Content Transfer Tool and the migration utility on a production environment.

1. Log in to your cloned environment with administrative privileges.

1. Run the [Best Practices Analyzer](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/cloud-migration/best-practices-analyzer/overview-best-practices-analyzer.html?lang=en#cloud-migration) tool and fix the reported issue.

1. Run the [User Mapping Tool](https://experienceleague.corp.adobe.com/docs/experience-manager-cloud-service/moving/cloud-migration/content-transfer-tool/using-user-mapping-tool.html?lang=en#cloud-migration) to map your users with corresponding Adobe IMS user accounts. You require Adobe IMS user accounts to login to a [!DNL AEM Forms] as a [!DNL Cloud Service] instance.

1. Download and install the [Content Transfer Tool](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/cloud-migration/content-transfer-tool/overview-content-transfer-tool.html?#cloud-migration) and [!DNL AEM Forms] as a [!DNL Cloud Service] Migration Utility from [Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html) on the cloned environment. You can use AEM Package Manager to install the tool and the utility.

1. Navigate to **[!UICONTROL Tools]** > **[!UICONTROL Operations]** > **[!UICONTROL Content Migration]**.

1. Open the **[!UICONTROL Prepare Forms for migration]** card. The browser displays five options:
    * **[!UICONTROL AEM Forms Assets Migration]**
    * **[!UICONTROL Adaptive Forms Custom Components Migration]**
    * **[!UICONTROL Adaptive Forms Templates Migration]**
    * **[!UICONTROL AEM Forms Cloud Configurations Migration]**
    * **[!UICONTROL Code Editor Script Migration]**

1. Use the option one-after another to make your AEM Forms assets compatible with [!DNL AEM] as a [!DNL Cloud Service]:

    1. Tap **[!UICONTROL AEM Forms Assets Migration]**, and in the next screen, tap **[!UICONTROL Start Migration]**. It makes Adaptive Forms and themes on your AEM Forms environment compatible with [!DNL AEM] as a [!DNL Cloud Service] .

    1. Tap **[!UICONTROL Adaptive Forms Custom Components Migration]** and in the Custom Components Migration page, tap **[!UICONTROL Start Migration]**. It makes any custom component developed for Adaptive Forms and component overlays on your AEM Forms environment compatible with [!DNL AEM] as a [!DNL Cloud Service] .

    1. Tap **[!UICONTROL Adaptive Forms Template Migration]** and in the Custom Components Migration page, tap **[!UICONTROL Start Migration]**. It makes Adaptive Form templates at /apps or /conf and created using AEM Template Editor compatible with [!DNL AEM] as a [!DNL Cloud Service] .

    1. Tap **[!UICONTROL AEM Forms Cloud Configurations Migration]** and then on the Configuration Migration page, tap **[!UICONTROL Start Migration]**. It updates and moves the following Cloud Services to a new location:

        * Form Data Model Cloud Service
        * Google reCAPTCHA Cloud Service
        * [!DNL Adobe Sign] Cloud Service
        * Adobe Fonts Cloud Service

    1. Tap **[!UICONTROL Code Editor Script Migration]**, specify a location to save reusable functions, and tap **[!UICONTROL Start Migration].

    The Cloud Service does not support rule editor scripts. The **[!UICONTROL Code editor script migration]** tool converts all rule scripts on your environment to reusable functions and applies the reusable functions to visual editor at appropriate location. These reusable functions are saved in the form of client libraries and help you keep existing functionality intact. The tool automatically applies the generated reusable functions to corresponding Adaptive Forms.

    Use the [Package Manager](https://experienceleague.adobe.com/docs/experience-manager-65/administering/contentmanagement/package-manager.html?lang=en#contentmanagement) to export the reusable functions (Client Libraries) to a package.

1. [Deploy](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=en#deploying-content-packages-via-cloud-manager-and-package-manager) the reusable functions (Client Libraries) package, [custom code, components, configurations](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/cloud-manager/devops/deploy-code.html#cloud-manager), custom locale-specific libraries to your [!DNL AEM] as a [!DNL Cloud Service] environment.

    <!-- 1. Install the latest [Compatibility Package](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/cloud-migration/content-transfer-tool/overview-content-transfer-tool.html?#cloud-migration) to your cloned AEM Forms environment. -->

1. Run the [Content Transfer Tool](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/cloud-migration/content-transfer-tool/overview-content-transfer-tool.html?#cloud-migration). While specifying parameters on the **[!UICONTROL Create Migration Set]** screen, specify the following AEM Forms-specific paths to the **[!UICONTROL Paths to be included]** option. It adds AEM Forms assets to migration set. 

    * /content/dam/formsanddocuments
    * /content/dam/formsanddocuments-fdm
    * /content/dam/formsanddocuments/themes
    * /content/forms/af
    * /etc/clientlibs/fd
    * /etc/clientlibs/reference-themes
    * /conf/ReferenceEditableTemplates

    To migrate AEM Workflow models, specify the following paths:

    * /conf/global/settings/workflow/models/
    * /conf/global/settings/workflow/launcher
    * /var/workflow/models

    You can also specify path of a particular asset or an Adaptive Form. It enables you to migrate certain assets and forms rather than migrating all the assets and forms at once.
