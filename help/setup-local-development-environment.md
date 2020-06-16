---
title: Setup a local development environment for AEM Forms as a Cloud Service
description: Setup a local development environment for AEM Forms as a Cloud Service
---

# Set up a local development environment {#overview}

When you set up and configure an AEM Forms as a Cloud service environment, you set up development, staging, and production environments. In addition, set up and configure a local development environment. You use the local development environment to create forms and related assets (themes, templates, custom submit actions, and more) and convert PDF Forms to adaptive forms. After an adaptive form or related assets are ready on the local development instance, you can export the adaptive form and related assets from the local development environment to an AEM Forms as a Cloud Service development environment for publishing.

For local development, set up two separate AEM projects: 

* **An AEM project for the development tasks related to local AEM 6.5.5 Forms instance:**  Use the project to update configurations, create overlays, develop custom adaptive form components, and custom code. 
* **An AEM project to deploy custom code or other changes to AEM Forms on Cloud service environment:** This project is a clone of your Cloud Manager Git repository with some Forms-specific settings. You can use the project to deploy configuration updates, overlays, custom adaptive form components, and custom code developed and tested on local 6.5.5 instance to AEM Forms as a Cloud Service production and non-production environments through Cloud Manager Git repository. 

<!--
You can use the local development environment to create and test adaptive forms without connecting to the Cloud Service. AEM Forms provides an SDK to help test all the cloud-ready functionalities on the local development environment. When your forms and related assets are ready and tested on the local development environment, you can import these forms and related assets to an AEM Forms as a Cloud Service instance for publishing. 

You can also develop and test custom code like custom components and prefill service on the local development environment. When the custom code is tested and ready, you can use the Git repository of your AEM Forms as a Cloud Service development environment to deploy the custom code. -->

>[!NOTE]
>
> Pre-pilot release does not support using an AEM Forms as a Cloud Service development instance to create forms. You can create forms, related assets, and custom code only on a local development environment.

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

|Software   | Download links |
|---|---|
| AEM 6.5 QuickStart  | [AEM 6.5 QuickStart](https://artifactory.corp.adobe.com/artifactory/maven-aem-dev/com/day/cq/cq-quickstart/6.5.0/cq-quickstart-6.5.0.jar)   |
| AEM 6.5 Service Pack 5 (6.5.5)   | [AEM 6.5 Service Pack 5](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq650/servicepack/aem-service-pkg-6.5.5.zip)  |
| AEM 6.5 Forms add-on package  | [AEM Forms add-on package for Linux](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq650/servicepack/fd/AEM-FORMS-6.5.5.0-LX.zip), [AEM Forms add-on package for Windows](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq650/servicepack/fd/AEM-FORMS-6.5.5.0-WIN.zip), [AEM Forms add-on package for Mac OS X](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq650/servicepack/fd/AEM-FORMS-6.5.5.0-OSX.zip) |

## Set up a local AEM instance for development

Perform the following steps in the listed order to set up and configure your local development environment:

1. **Set up an AEM 6.5 author instance:** You require an author instance to create adaptive forms. Run the quickstart file in author run mode to set up an author instance. For detailed instructions, see [default local instance](https://docs.adobe.com/content/help/en/experience-manager-65/deploying/deploying/deploy.html#on-premise).  

1. **Install the latest AEM 6.5 service pack:** It helps you obtain the latest features and bug fixes for AEM 6.5. It is also a prerequisite to installing the latest AEM Forms add-on. For detailed instructions, see [Adobe Experience Manager 6.5 Service Pack release notes](https://docs.adobe.com/content/help/en/experience-manager-65/release-notes/service-pack/sp-release-notes.html).
1. **Install the latest AEM Forms add-on package:** AEM Forms add-on package provides tools to create, style, and optimize adaptive forms. Install the package to create an adaptive form and use various other features of AEM Forms.  For detailed instructions, see [Install and configure data capture capabilities](https://helpx.adobe.com/experience-manager/6-5/forms/using/installing-configuring-aem-forms-osgi.html).
1. **Configure users and permissions:** Create users like Form Developer and Form Practitioner and add these users to pre-defined forms group to provide them required permissions. The table below lists all types of users and pre-defined groups for each type of forms users:
  
    | User Type | AEM Group |
    |---|---|
    | Form Practitioner  | forms-users, template-author  |
    | Form Developer | forms-users, template-author |
    | End-User| everyone* |

    `*` When a user should log in to access or submit adaptive forms, add such users to the everyone group.
    
### Set up an AEM project for the development tasks related to local AEM 6.5.5 Forms instance

Use this project to update configurations, create overlays, develop custom adaptive form components, and custom code using the local development environment. To set up the project:

1. **Install and configure Maven and set up an AEM project based on Apache Maven:** Apache Maven is an open-source tool for managing software projects. It helps automate builds and provides quality project information. It is the recommended build management tool for AEM projects. For detailed instructions to set up an AEM project based on Apache Maven, see [How to Build AEM Projects using Apache Maven](https://docs.adobe.com/content/help/en/experience-manager-65/developing/devtools/ht-projects-maven.html).

1. **Set Up an Integrated Development Environment:** An integrated development environment or IDE is an application that combines a text editor, syntax support and, build-tools. Depending on the type of development you are doing, one IDE might be preferable over another. Regardless of the IDE, it will be important to be able to periodically push code to a local AEM instance to test it. It will also be important to occasionally pull configurations from a local AEM instance into your AEM project to persist in a source-control management. For detailed instructions to set up an IDE of your choice for AEM development, see [Set Up an Integrated Development Environment](https://docs.adobe.com/content/help/en/experience-manager-learn/foundation/development/set-up-a-local-aem-development-environment.html#set-up-an-integrated-development-environment).

### Set up AEM project to deploy custom code or other changes to AEM Forms on Cloud service environment {#FaaCS-local-development-environment}

Use this project to deploy configuration updates, overlays, custom adaptive form components, and custom code developed and tested on local 6.5.5 instance to AEM Forms as a Cloud Service production and non-production environments through Cloud Manager Git repository. To set up the environment: 


1. **Clone Cloud Manager Git Repository on your local development instance:** Your Cloud Manager Git repository contains a default AEM project. Clone your Cloud Manager Git Repository using Self-Service Git Account Management from Cloud Manager UI. For detailed steps, see [Accessing Git](https://docs.adobe.com/content/help/en/experience-manager-cloud-manager/using/managing-code/accessing-git.html). 

    Go through [AEM Project Structure](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html) guidelines and make your AEM project (obtained from the Cloud Manager Git repository) compatible with the recommended AEM project structure. Make your AEM project respect the split of mutable and immutable content, establish dependencies to create non-conflicting deterministic deployments, and package dependencies in a deployable structure. Also, define correct JCR repository roots for the AEM Project as described in the [repository structure package](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/repository-structure-package.html). You can find an example project with all the above-mentioned changes [here](https://git.corp.adobe.com/livecycle/forms-cloud-ready-sample).  
    
 
1. **Configure AEM Forms as a Cloud Service SDK:** Open pom file of your AEM Archetype cloned through Cloud manager Git repository and make the following changes to the file:

    1. Add the following to the repository section of the `<project>/pom.xml` file:

        ```
        <repositories>
            <repository>
                <id>adobe-public-releases</id>
                <name>Adobe Public Repository</name>
                <url>https://repo.adobe.com/nexus/content/groups/public</url>
                <releases>
                    <enabled>true</enabled>
                    <updatePolicy>never</updatePolicy>
                </releases>
                <snapshots>
                    <enabled>false</enabled>
                </snapshots>
            </repository>
            <repository>
                <id>adobe-aem-releases</id>
                <name>Adobe AEM Repository</name>
                <url>https://downloads.experiencecloud.adobe.com/content/maven/public</url>
                <releases>
                    <enabled>true</enabled>
                    <updatePolicy>never</updatePolicy>
                </releases>
                <snapshots>
                    <enabled>false</enabled>
                </snapshots>
            </repository>
        </repositories>
        
        <pluginRepositories>
            <pluginRepository>
                <id>adobe-public-releases</id>
                <name>Adobe Public Repository</name>
                <url>https://repo.adobe.com/nexus/content/groups/public</url>
                <releases>
                    <enabled>true</enabled>
                    <updatePolicy>never</updatePolicy>
                </releases>
                <snapshots>
                    <enabled>false</enabled>
                </snapshots>
            </pluginRepository>
        </pluginRepositories>

        ```

    1. Add the following to the dependencies section to all the pom.xml files of the AEM project: 

        ```
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
        
1. **Update dispatcher configuration:** Open the Archetype project and make the following forms changes to the dispatcher configuration:

    1. Add the following filter to the `<custom-code-project-home>/dispatcher/src/conf.dispatcher.d/filters/filters.any` file to allow form-specific URLs and endpoints:

        ```

            # Allow components JSON model
            /0101 { /type "allow" /extension "json" /selectors "model" /path "/content/*" }
            
            # to allow AF specific endpoints for prefill, submit and sign
            /0102 { /type "allow" /path "/content/forms/af/*" /method "POST" /selectors '(submit|internalsubmit|agreement|signSubmit|prefilldata)' /extension '(jsp|json)' }
            
            # to allow AF specific endpoints for thank you page
            /0103 { /type "allow" /path "/content/forms/af/*"  /method "GET" /selectors '(guideThankYouPage|guideAsyncThankYouPage)'  /extension '(html)'}
            
            # to allow AF specific endpoints for lazy loading
            /0104 { /type "allow" /path "/content/forms/af/*"  /method "GET" /extension '(jsonhtmlemitter)'}
            
            # to allow fp related funcitonalities
            /0105 { /type "allow" /path "/content/forms/*" /selectors '(fp|attach|draft|dor|api)'  /extension '(html|jsp|json|pdf)' }

        ```

    1. Add the following rules to the `<custom-code-project-home>/dispatcher/src/conf.dispatcher.d/cache/rules.any` file to disable caching for adaptive forms:

        ```
        
            /0001
            {
                # do not cache anything inside /content/forms
                /glob "/content/forms/af/**"
                /type "deny"
            }
            /0002
            {
                # do not cache anything inside /content/dam/formsanddocuments/
                /glob "/content/dam/formsanddocuments/**"
                /type "deny"
            }

        ```

Your local development environment is ready. When you update any AEM Forms configuration, create overlays, develop custom adaptive form components, or develop and test any custom code in AEM project for the development tasks related to local AEM 6.5.5 Forms instance, use the AEM project cloned from the Cloud Manager Git repository to [deploy the custom code and other changes to your AEM Forms as a Cloud Service's production or non-production environment](https://video.tv.adobe.com/v/30191?quality=9). 
