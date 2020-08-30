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

    1. Stop your Cloud ready AEM instance, place the AEM Forms add-on feature archive in the install folder, and restart the instance.

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

### Set up AEM project {#Forms-cloud-service-local-development-environment}

Use this project to create adaptive forms, deploy configuration updates, overlays, custom adaptive form components, and custom code developed and tested on local AEM Forms Cloud ready instance to AEM Forms as a Cloud Service production and non-production environments through Cloud Manager Git repository. To set up the environment: 

1. **Clone Cloud Manager Git Repository on your local development instance:**  Your Cloud Manager Git repository contains a default AEM project based on [Archetype 22](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-22). Clone your Cloud Manager Git Repository using Self-Service Git Account Management from Cloud Manager UI to bring the project on your local development instance. For detailed steps, see [Accessing Git](https://docs.adobe.com/content/help/en/experience-manager-cloud-manager/using/managing-code/accessing-git.html). After the repository is cloned, perform the rest of the steps to make the cloned AEM project compatible with AEM Forms as a Cloud Service.  

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

    You can find latest version of AEM as a Cloud Service SDK at [AEM as a Cloud Service](https://mvnrepository.com/artifact/com.adobe.aem/aem-sdk-api) page and AEM Forms as a Cloud Service SDK at [AEM Forms as a Cloud Service Cloud Ready SDK](https://mvnrepository.com/artifact/com.adobe.aem/aem-forms-sdk-api) page.


1. **Setup and update dispatcher configuration:** Dispatcher is a Apache HTTP Web server module that provides a security and performance layer between the CDN and AEM Publish tier. Dispatcher is an integral part of the overall Experience Manager architecture and should be part of local development set up. For detailed information on using dispatcher on local environment, see [Set up local Dispatcher Tools](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/dispatcher-tools.html)
After dispatcher is configured, perform the following steps specifc to AEM Forms as a Cloud Service: 
    1. Navigate to <Dispatcher location>\src\conf.dispatcher.d\available_farms 
    1. Create a copy of the  default.farm file and add the following to the file:
    1. Open command prompt with admin privileges.
    1. Run the following command to create symbolic link to newly created and updated .farm file:
    `cd conf.dispatcher.d/enabled_farms && ln -s ../available_farms/<your-copy.farm>`

Your local development environment is ready. When you update any AEM Forms configuration, create overlays, develop custom adaptive form components, or develop and test any custom code in AEM project for the development tasks related to local development instance, use the AEM project cloned from the Cloud Manager Git repository to [deploy the custom code and other changes to your AEM Forms as a Cloud Service's production or non-production environment](https://video.tv.adobe.com/v/30191?quality=9). 
