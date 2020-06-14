---
title: Setup a local development environment for AEM Forms as a Cloud Service
description: Setup a local development environment for AEM Forms as a Cloud Service
---

# Set up a local development environment for AEM Forms as a Cloud Service {#overview}

When you set up and configure an AEM Forms as a Cloud service environment, you set up development, staging, and production environments. In addition to the AEM Forms as a Cloud Service development environment, set up and configure a local development environment. 

You can use the local development environment to create and test adaptive forms without connecting to the Cloud Service. AEM Forms provides an SDK to help test all the cloud-ready functionalities on the local development environment. When your forms and related assets are ready and tested on the local development environment, you can import these forms and related assets to an AEM Forms as a Cloud Service instance for publishing. 

You can also develop and test custom code like custom components and prefill service on the local development environment. When the custom code is tested and ready, you can use the Git repository of your AEM Forms as a Cloud Service development environment to deploy the custom code.

>[!NOTE]
>
> June 2020 release does not support using an AEM Forms as a Cloud Service development instances to create forms. You can create forms, related assets, and custom code only on a local development environment.

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
|Sample AEM project template|[Sample AEM project template](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype)|

## Set up the environment

Perform the following steps in the listed order to set up and configure your local development environment:

1. **Set up an AEM 6.5 author instance:** You require an author instance to create adaptive forms. Run the quickstart file in author run mode to set up an author instance. For detailed instructions, see [default local instance](https://docs.adobe.com/content/help/en/experience-manager-65/deploying/deploying/deploy.html#on-premise).  

1. **Install the latest AEM 6.5 service pack:** It helps you obtain the latest features and bug fixes for AEM 6.5. It is also a prerequisite to installing the latest AEM Forms add-on. For detailed instructions, see [Adobe Experience Manager 6.5 Service Pack Release Notes](https://docs.adobe.com/content/help/en/experience-manager-65/release-notes/service-pack/sp-release-notes.html)
1. **Install the latest AEM Forms add-on package:** AEM Forms add-on package provides tools to create, style, and optimize adaptive forms. Install the package to create an adaptive form and use various other features of AEM Forms.  For detailed instructions, see [Install and configure data capture capabilities](https://helpx.adobe.com/experience-manager/6-5/forms/using/installing-configuring-aem-forms-osgi.html).
1. **Configure users and permissions:** Create users like AEM Administrator, Form Developer, Form Practioner, and add these users to pre-defined forms group to provide them required permissions. The table below lists all types of users and pre-defined groups for each type of users:
  
    | User Type | AEM Group |
    |---|---|
    | Form Practitioner  | forms-users, template-author  |
    | Form Developer | forms-users, template-author |
    | Admin rights on AEM | aem-administrators, fd-administrators |
    | End User| forms-users*  |

    `*` When a log-in is required to access and submit forms, add such users to  forms-users group. It allows the users to log-in to access and submit available forms.

1. **Set up an AEM project based on Apache Maven:** Apache Maven is an open-source tool for managing software projects by automating builds and providing quality project information. It is the recommended build management tool for AEM projects. For detailed instructions, see [How to Build AEM Projects using Apache Maven](https://docs.adobe.com/content/help/en/experience-manager-65/developing/devtools/ht-projects-maven.html).


1. **Clone Cloud Manager Git Repository on your local development instance:** You can access and manage your Git Repository using Self-Service Git Account Management from Cloud Manager UI. For details, see [Accessing Git](https://docs.adobe.com/content/help/en/experience-manager-cloud-manager/using/managing-code/accessing-git.html).

1. **Update your Maven projects to be AEM Cloud Service compatible:** Update your Adobe Experience Manager Maven projects to be AEM Cloud Service compatible by ensuring that they respect the split of mutable and immutable content; that requisite dependencies are established to create non-conflicting, deterministic deployments; and that they are packaged in a deployable structure. For details see, [AEM Project Structure](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/aem-project-content-package-structure.html). Download a sample Maven Archetype project from [here](https://github.com/adobe/aem-project-archetype/tree/master/src/main/archetype). Also, define correct JCR repository roots in the [repository structure package](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/implementing/developing/repository-structure-package.html).
    
1. **Configure AEM Forms as a Cloud Service SDK:** Open the Archetype project and make the following changes to the POM file of the project:

    1. Add the following to the repository section of the POM file:

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

    1. Add the following to the dependencies section of the POM file: 

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
                <version>2020.05.23.00</version>
                <scope>provided</scope>
            </dependency>

        ```
1. **Update dispatcher configuration:** Open the Archetype project and make the following forms spcific changes to the dispatcher:

    1. Add the following filter to the `<custom-code-project-home>/dispatcher/src/conf.dispatcher.d/filters/filters.an` file:

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

Your local development environment is ready. 
