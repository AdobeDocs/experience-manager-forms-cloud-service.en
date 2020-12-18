---
title: Setup a local development environment for AEM Forms as a Cloud Service
description: Setup a local development environment for AEM Forms as a Cloud Service
---

# Set up a local development environment {#overview}

When you set up and configure an AEM Forms as a Cloud service environment, you set up development, staging, and production environments. In addition, set up and configure a local development environment. You can use the local development environment to create forms and related assets (themes, templates, custom submit actions, and more) and convert PDF Forms to adaptive forms without logging in to cloud development environment. After an adaptive form or related assets are ready on the local development instance, you can export the adaptive form and related assets from the local development environment to an AEM Forms as a Cloud Service development environment for publishing.

<!--
You can use the local development environment to create and test adaptive forms without connecting to the Cloud Service. AEM Forms provides an SDK to help test all the cloud-ready functionalities on the local development environment. When your forms and related assets are ready and tested on the local development environment, you can import these forms and related assets to an AEM Forms as a Cloud Service instance for publishing. 

You can also develop and test custom code like custom components and prefill service on the local development environment. When the custom code is tested and ready, you can use the Git repository of your AEM Forms as a Cloud Service development environment to deploy the custom code. 

>[!NOTE]
>
> Pre-pilot release does not support using an AEM Forms as a Cloud Service development instance to create forms. You can create forms, related assets, and custom code only on a local development environment.-->

<!--
You configure two types of development environments:

* **AEM Forms as a Cloud Service development environment:** Use the [AEM Forms as a Cloud Service](setup-forms-cloud-service.md) environment to store, manage, and publish adaptive forms and related assets. Do not use an AEM Forms as a Cloud Service environment to create adaptive forms and related assets <!--, form-centric workflows, a form data model, or to generate a Document of Record. -->

<!--
* **Local development environment:** You can use the local development environment to create and test adaptive forms without connecting to the service. Adobe provides a SDK for the local development to help test all the cloud-ready functionalities. 
Use a local development environment:
    
    * To create forms and related assets (themes, templates, custom submit actions, and more) and convert PDF Forms to adaptive forms. After an adaptive form or related assets are ready on the local development instance, you can export the adaptive form and related assets from the local development environment to an AEM Forms as a Cloud Service development environment for publishing.  
    
    * To update configuration settings and develop and test custom code like custom components and prefill service. When the custom code is tested and ready, you can use the Git repository of your AEM Forms as a Cloud Service development environment to deploy the custom code.  

You can use the local development environment to create and test adaptive forms without connecting to the service. Adobe provides a SDK for the local development to help test all the cloud-ready functionalities. When your forms and related assets are ready and tested on the local development environment, you can import these forms and related assets to an AEM Forms as a Cloud Service instance for publishing. 

You can use the [development tools](https://docs.adobe.com/content/help/en/experience-manager-65/developing/devtools/dev-tools.html) to write custom code, customize or create new adaptive forms components, create a custom prefill service, or modify default configurations of an AEM Forms as a Cloud Service instance. 

-->

## Prerequisites

You require the following software to set up a local development environment. Download these software before starting to set up the local development environment.

|Software   | Description |Download links|
|---|---|---|
| AEM SDK | AEM SDK includes AEM quick start and Dispatcher Tools| Download from [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html)||
| AEM Forms add-on feature archive  | Tools to create, style, and optimize adaptive forms and other AEM Forms features| Download from [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html) |

## Set up a local AEM instance for development

Perform the following steps in the listed order to set up and configure your local development environment:

1. **Set up an AEM author instance:** You require an author instance to create adaptive forms. Download and extract the latest AEM SDK archive. Run the quick start file in author run mode to set up an author instance. For detailed instructions, see [default local instance](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/aem-runtime.html).  

1. **Install the latest AEM Forms add-on feature archive:** AEM Forms add-on feature archive provides tools to create, style, and optimize adaptive forms on the local development environment. Install the package to create an adaptive form and use various other features of AEM Forms. To install the package:

    1. Download and extract the latest AEM Forms archive for your operating system from [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html). 

    1. Navigate to the crx-quickstart/install directory. If the folder does not exist, create it.

    1. Stop your Cloud ready AEM instance, place the AEM Forms add-on feature archive, `aem-forms-addon-<version>.far`,  in the install folder, and restart the instance.

1. **Configure users and permissions:** Create users like Form Developer and Form Practitioner and add these users to pre-defined forms group to provide them required permissions. The table below lists all types of users and pre-defined groups for each type of forms users:
  
    | User Type | AEM Group |
    |---|---|
    | Form Practitioner  | forms-users (AEM Forms Users), template-author  |
    | Form Developer | forms-users (AEM Forms Users), template-author |
    | End-User| everyone* |

    `*` When a user should log in to access or submit adaptive forms, add such users to the everyone group.

<!--    
### Set up an AEM project for the development tasks related to local AEM 6.5.5 Forms instance

Use this project to update configurations, create overlays, develop custom adaptive form components, and custom code using the local development environment. To set up the project:

1. **Install and configure Maven and set up an AEM project based on Apache Maven:** Apache Maven is an open-source tool for managing software projects. It helps automate builds and provides quality project information. It is the recommended build management tool for AEM projects. For detailed instructions to set up an AEM project based on Apache Maven, see [How to Build AEM Projects using Apache Maven](https://docs.adobe.com/content/help/en/experience-manager-65/developing/devtools/ht-projects-maven.html).

1. Configure the project to use [uber-jar](https://docs.adobe.com/content/help/en/experience-manager-65/release-notes/service-pack/sp-release-notes.html#install-aem-forms-jee-installer) version 6.5.5 or later and [AEM Forms Client SDK](https://repo.adobe.com/nexus/content/groups/public/com/adobe/aemfd/aemfd-client-sdk/) version 6.0.160 or later.  

1. **Set Up an Integrated Development Environment:**  Set up an IDE of your choice for development, see [Set Up an Integrated Development Environment](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html#set-up-an-integrated-development-environment) for detailed instructions.
 --> 

### Set up AEM project {#forms-cloud-service-local-development-environment}

Use this project to create adaptive forms, deploy configuration updates, overlays, custom adaptive form components, and custom code developed and tested on local AEM Forms Cloud ready instance to AEM Forms as a Cloud Service production and non-production environments through Cloud Manager Git repository. To set up the environment: 

1. **Clone Cloud Manager Git Repository on your local development instance:**  Your Cloud Manager Git repository contains a default AEM project based on [Archetype 22](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-22). Clone your Cloud Manager Git Repository using Self-Service Git Account Management from Cloud Manager UI to bring the project on your local development instance. For detailed steps, see [Accessing Git](https://docs.adobe.com/content/help/en/experience-manager-cloud-manager/using/managing-code/accessing-git.html). After the repository is cloned, [integrate your Git repo with Cloud Manager](https://docs.adobe.com/content/help/en/experience-manager-cloud-manager/using/managing-code/setup-cloud-manager-git-integration.html).  

1. **Make cloned AEM project compatible with AEM Forms as a Cloud Service:** Remove uber-jar and other non-cloud dependencies from the pom.xml files of the project. You can refer the pom.xml files of the [sample AEM project](assets/FaaCSample.zip) for the list of required dependencies and update your AEM project accordingly. You can also refer [AEM Project Structure](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html) to learn changes required to make an AEM project compatible with AEM as a Cloud Service.  

1. **Configure AEM Forms as a Cloud Service SDK:** Open POM file of your AEM Archetype cloned through Cloud manager Git repository and add the following to the dependencies section to the pom.xml files of the AEM project:

    ``` XML
        <dependency>
            <groupId>com.adobe.aem</groupId>
            <artifactId>aem-sdk-api</artifactId>
            <version>2020.5.3372.20200520T035431Z-200507</version>
            <scope>provided</scope>
        </dependency>
        <dependency>
            <groupId>com.adobe.aem</groupId>
            <artifactId>aem-forms-sdk-api</artifactId>
            <version>7.0.164</version>
            <scope>provided</scope>
        </dependency>

    ```

    You can find latest version of AEM as a Cloud Service SDK at [AEM as a Cloud Service](https://mvnrepository.com/artifact/com.adobe.aem/aem-sdk-api) page and AEM Forms as a Cloud Service SDK(aem-forms-sdk-api)  at [AEM Forms as a Cloud Service Cloud Ready SDK](https://mvnrepository.com/artifact/com.adobe.aem/aem-forms-sdk-api) page.


1. **Configure dispatcher cache for AEM Forms as a Cloud Service:** Dispatcher provides a security and performance layer between the CDN and AEM Publish tier. Perform the following steps to configure dispatcher cache for AEM Forms as a Cloud Service: 
    1. 4.1	Open your AEM Project and navigate to `\src\conf.dispatcher.d\available_farms` 
    1. Create a copy of the `default.farm` file.For example, `forms.farm`.
    1. Open the newly created `forms.farm` file for editing and Open the newly created forms.farm file for editing and replace the following code: 

        ```shell
        #/ignoreUrlParams {
        #	/0001 { /glob "*" /type "deny" }
        #	/0002 { /glob "q" /type "allow" }
        #}
        ```

        with

        ```shell
        /ignoreUrlParams {
        /0001 { /glob "*" /type "deny" }
        /0002 { /glob "dataRef" /type "allow" }
        }
        ```

    1. Save and close your file. 
    1. Open the `filters.any` file for editing and add the following code to the file.

        ```shell
        # to allow custom file attachment servlet (part of custom prefill service)
        /0102 { /type "allow" /path "/content/forms/*" /selectors '(file)' }
        
        # to allow FDM related calls
        /0103 { /type "allow" /path "/content/forms/*" /selectors '(af)'  /extension '(dermis)'}
        ```
    1. Compile and deploy the project to AEM Forms as a Cloud Service environment.

### Considerations about caching {#considerations-about-caching }

* Dispatcher caching allows AEM Forms to prefill adaptive forms at a client. It improves rendering speed of prefilled forms.
* Caching secured content features is disabled, by default. To enable the feature, you can perform the instructions provided in the [Caching Secured Content](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/permissions-cache.html) article
* The dispatcher can fail to invalidate some adaptive forms and related adaptive forms. To resolve such issues, see [AEM Forms Caching](troubleshooting-caching-performance.md) in troubleshooting section. 
* Caching localized adaptive forms:
    * Use URL format `http://host:port/content/forms/af/<afName>.<locale>.html` to request a localized version of an adaptive form instead of `http://host:port/content/forms/af/afName.html?afAcceptLang=<locale>`
    * Browser Locale option is disabled, by default. To change browser locale setting,
* When you use URL Format `http://host:port/content/forms/af/<adaptivefName>.html`, and Use Browser Locale in configuration manager is disabled, the non-localized version of the adaptive form is served. The non-localized language is the language used while developing the adaptive form. The locale configured for your browser (browser locale) is not taken into consideration and a non-localized version of the adaptive form is served.
* When you use URL Format `http://host:port/content/forms/af/<adaptivefName>.html`, and Use Browser Locale in configuration manager is enabled, a localized version of the adaptive form is served, if available. The language of the localized adaptive form is based on the locale configured for your browser (browser locale). It can lead to [caching only first instance of an adaptive form]. To prevent the issue from happening on your instance, see [only first instance of adaptive forms is cached](troubleshooting-caching-performance.md) in troubleshooting section.

### (Optional) Setup local dispatcher {setup-local-dispatcher}

Dispatcher is an Apache HTTP Web server module that provides a security and performance layer between the CDN and AEM Publish tier. Dispatcher is an integral part of the overall Experience Manager architecture and should be part of local development set up. For detailed information to set up a dispatcher on local environment, see [Set up local Dispatcher Tools](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/dispatcher-tools.html)


Your local development environment is ready. When you update any AEM Forms configuration, create overlays, develop custom adaptive form components, or develop and test any custom code in AEM project for the development tasks related to local development instance, use the AEM project cloned from the Cloud Manager Git repository to [deploy the custom code and other changes to your AEM Forms as a Cloud Service's production or non-production environment](https://video.tv.adobe.com/v/30191?quality=9). 

## Upgrade your local development environment {#update-local-setup}

Update the local AEM setup (AEM SDK) to latest version at least monthly on, or shortly after, the last Thursday of each month, which is the release cadence for AEM as a Cloud Service "feature releases". You can download local AEM SDK from [Software Distribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html).

Updating the AEM SDK to a new version requires replacing the entire local development environment, resulting in a loss of all code, configuration and content in the local AEM repositories. Ensure that any code, config or content that should not be destroyed is safely committed to Git, or exported from the local AEM instance as AEM Packages.

### How to avoid content loss when upgrading the AEM SDK {#avoid-content-loss-when-upgrading--AEM-SDK}

Upgrading the AEM SDK is effectively creating a brand new [AEM runtime](setup-forms-cloud-service.md) (Set up a local AEM instance), including a new repository ((Set up AEM project)[#forms-cloud-service-local-development-environment]), meaning any changes made to a prior AEM SDK's repository are lost. The following are viable strategies for aiding in persisting content between AEM SDK upgrades, and can be used discretely or in concert:

1.	Create a content package dedicated to containing the sample content to aid in development and maintain it in Git. Any content that should be persisted through AEM SDK upgrades would be persisted into this package and re-deployed after upgrading the AEM SDK. 
2.	Use [oak-upgrade](https://jackrabbit.apache.org/oak/docs/migration.html) with the `includepaths` directive, to copy content from the prior AEM SDK repository to the new AEM SDK repository.
3.	Backup any content using AEM Package Manager and content packages on the prior AEM SDK and re-install them on the new AEM SDK.

Remember, using the above approaches to maintain code between AEM SDK upgrades, indicates a development anti-pattern. Non-disposable code should originate in your Development IDE and flow into AEM SDK via deployments.

For information about troubleshooting, stopping local AEM environment, run modes, and deployment, see [Set up local AEM Runtime](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/local-development-environment-set-up/aem-runtime.html#local-development-environment-set-up).
