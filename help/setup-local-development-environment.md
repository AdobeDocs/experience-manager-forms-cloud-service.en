---
title: Setup a local development environment for Forms as a Cloud Service
description: Setup a local development environment for Forms as a Cloud Service
---

# Set up a local development environment for Forms as a Cloud Service {#overview}

You can use the local development environment to create and test adaptive forms without connecting to the service. Adobe provides FaaCS SDK for the local development to help test all the cloud-ready functionalities. When your forms and related assets are ready and tested on the local development environment, you can import these forms and related assets to a FaaCS instance for publishing. 

## Pre-requistes 
      
You require the following software to setup a local development enviroment. Download these software before starting to set up the local development environment. 

<table>
  <tr>
    <th>Software packages</th>
    <th>Download link</th>
  </tr>
  <tr>
    <td>AEM 6.5 QuickStart</td>
    <td><a href="https://artifactory.corp.adobe.com/artifactory/maven-aem-dev/com/day/cq/cq-quickstart/6.5.0/cq-quickstart-6.5.0.jar"> AEM 6.5 QuickStart </a></td>
  </tr>
  <tr>
    <td>AEM 6.5 Service Pack 5</td>
    <td><a href="https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq650/servicepack/aem-service-pkg-6.5.5.zip"> AEM 6.5 Service Pack 5 </a></td>
  </tr>
  
  <tr>
    <td>AEM 6.5 Forms add-on package</td>
    <td> 
        <p> <a href="https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq650/servicepack/fd/AEM-FORMS-6.5.5.0-LX.zip"> AEM Forms add-on package for Linux</a> </p>
        <p> <a href="https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq650/servicepack/fd/AEM-FORMS-6.5.5.0-WIN.zip"> AEM Forms add-on package for Windows </a> </p>
        <p> <a href="https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq650/servicepack/fd/AEM-FORMS-6.5.5.0-OSX.zip"> AEM Forms add-on package for Mac OS X</a> </p> 
        </ul>
    </td>
  </tr>
</table>

## Set up the environment

Perform the following steps in the listed order to set up and configure your local development environment:

1. Set up an AEM 6.5 author instance
You require an author instance to create adaptive forms. Run the quickstart file in author run mode to setup an author instance. For detailed instructions, see [default local instance](https://docs.adobe.com/content/help/en/experience-manager-65/deploying/deploying/deploy.html#on-premise).  

1. Install latest AEM 6.5 service pack:
It helps you obtain latest features and bug fixes for AEM 6.5. It is also a pre-requiste to installing latest AEM Forms add-on. For detailed instructions, see [Adobe Experience Manager 6.5 Service Pack Release Notes](https://docs.adobe.com/content/help/en/experience-manager-65/release-notes/service-pack/sp-release-notes.html)
1. Install AEM Forms add-on package 
AEM Forms add-on package provides complete tool to create, style, and optimize adaptive forms. Install the package to create an adaptive form and use various other features of AEM Forms.  For detailed instructions, see [Install and configure data capture capabilities](https://helpx.adobe.com/experience-manager/6-5/forms/using/installing-configuring-aem-forms-osgi.html).
1. Configure users and permissions
Create several users like AEM Administrator, Form Developer, Form Practioner and add these users to pre-defined forms group to provide them required permissions. The table below lists all types of users and pre-defined groups for each type of users:
  
    | User Type | AEM Group |
    |---|---|
    | Form Practitioner  | forms-users, template-author  |
    | Form Developer | forms-users, template-author |
    | AEM Administrator | aem-administrators, fd-administrators |
    | End User| forms-users*  |

    `*` When a log-in is required to access and submit forms, add such users to  forms-users group. It allows the users to log-in to access and submit available forms.

1. Install and set up development tools and dispatcher
Install and configure local deveopment tools to customize default adaptive forms functionality, create a new custom component, create a custom prefill service, or modify default configurations of an FaaCS instance apart from creating adaptive forms on a local development enviroment. For detailed instructions see, [Local Development Environment Set up](https://docs.adobe.com/content/help/en/experience-manager-learn/cloud-service/local-development-environment-set-up/overview.html). You can deploy the changes or customization directly to a FaaCS instance from your local deveopment instance via the git repository included with your FaaCS environment. 
    
1. Configure FaaCS SDK 

    1. Open your IDE. Open the Archetype project and POM file of the project.

    1. Add the following to the repository section of the POM file:

        ```
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

        ```

    1. Add the following to the dependencies section of the POM file: 

        ```
            <dependency>
                <groupId>com.adobe.aem</groupId>
                <artifactId>aem-forms-sdk-api</artifactId>
                <version>2020.05.23.00</version>
                </dependency>
                <dependency>
                <groupId>com.adobe.aem</groupId>
                <artifactId>aem-forms-sdk-api</artifactId>
                <version>2020.05.23.00</version>
                <classifier>javadoc</classifier>
            </dependency>

        ```

Your local development enviroment is ready. 
