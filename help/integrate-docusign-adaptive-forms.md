---
title: Integrate DocuSign with an adaptive form
seo-title: Learn how to use DocuSign with an adaptive form to collect e-signatures.
---

# Using DocSign with an adaptive form {#integrate-aem-forms-with-DocuSign}

DocuSign is a prominent e-signature solution. You can use it to e-sign an agreement. You can integrate DocuSign with an adaptive form. It help you send an adaptive form for e-signatures to multiple recipients. Using e-signatures helps you:

- Close deals from any device with fully automated proposal, quote, and contract processes.
- Finish Human Resource processes faster and give your employees the digital experiences.
- Cut contract cycle times and onboard your vendors faster.

You can also use Adobe's e-signature solution, Adobe Sign, to e-sign an adaptive form. AEM Forms has a much deeper integration with Adobe Sign and provides much finer controls like sequential and parallel signing, multiple authentication methods, in-form signing experience and more. For more information, see [Using Adobe Sign in an Adaptive Form](working-with-adobe-sign.md).

## Prerequisites {#prerequisites}

The following are required to integrate DocuSign with AEM Forms:

- A DocuSign [developer account](https://developers.docusign.com/platform/account/)
- A DocuSign application
- Credentials (Client ID and Client Secret) of DocuSign API application.
- Identical crypto key for author and publish instances.
- [Custom submit action and Cloud service for DocuSign](https://git.corp.adobe.com/hsalhotr/aem-forms-samples/tree/main/forms-integration-docusign)

## Deploy custom submit action and Cloud service for DocuSign

AEM Forms as a Cloud Service provides a custom submit action for DocuSign. The submit action helps you to send the adaptive forms for e-signatures using DocuSign APIs. Code for custom submit action is available on [AEM Forms samples public git repo](https://git.corp.adobe.com/hsalhotr/aem-forms-samples/tree/main/forms-integration-docusign). You can deploy the code as it is on your AEM Forms environment or customize it as per the requirements of your organization. To deploy the code:

## Integrate DocuSign with AEM Forms

Perform the following steps to integrate DocuSign with AEM Forms:

1. Create an [!DNL Experience Manager Forms] as a [Cloud Service] project based on [AEM Archetype 31](https://github.com/adobe/aem-project-archetype/releases/tag/aem-project-archetype-31) or later. The archetype  help developers easily start developing for [!DNL AEM Forms] as a Cloud Service. It also includes some sample themes and templates to help you started quickly.

    Open the command prompt and run the below command to create an [!DNL Experience Manager Forms] as a Cloud Service project. To include [!DNL Forms] specific configurations, themes, and templates, set `includeForms=y`.  

    ```shell
    mvn -B archetype:generate -DarchetypeGroupId=com.adobe.aem -DarchetypeArtifactId=aem-project-archetype -DarchetypeVersion=31 -DaemVersion="cloud" -DappTitle="My Site" -DappId="mysite" -DgroupId="com.mysite" -DincludeForms="y"
    ```

    Also, change `appTitle`, `appId`, and `groupId`, in the above command to reflect your environment.

1. Download the DocuSign sample code to [!DNL Experience Manager Forms] as a [Cloud Service] project.

   ```shell
   mvn clean install -Dinstall.dir="<Cloud Service project directory path>/name of the DocuSign sample folder"
   ```

   `<Cloud Service project directory path>` refers to the name of the folder created in step 1 of this procedure.

1. Perform the following steps in the `pom.xml` file available in the Cloud Service project folder:
   1.  Add the following text at the end of the `<properties>` tag:

       ```shell
       <repository.location>maven_repository</repository.location>
       ```

       `maven_repository` refers to the name of the DocuSign sample folder created in step 2.

   1. Add the following text at the end of the `<repositories>` tag:

       ```shell
        <repository>
           <id>project-repository</id>
            <url>file://${project.basedir}/${repository.location}</url>
        </repository>
       ```

       If there is no `<repositories>` tag, create the tag below the `<properties>` tag.

   1. Add the following text at the end of the `<dependencyManagement>` tag:
      
      ```shell
       <dependency>
         <groupId>com.adobe.aemforms.samples</groupId>
         <artifactId>forms.integration.docusign.all</artifactId>
          <type>zip</type>
         <version>1.0.0-SNAPSHOT</version>
       </dependency>
      ```

1. Perform the following steps in the `all/pom.xml` file available in Cloud Service project folder:
   1. Add the following text at the end of the `<embeddeds>` tag:

      ```shell
       <embedded>
          <groupId>com.adobe.aemforms.samples</groupId>
          <artifactId>forms.integration.docusign.all</artifactId>
          <type>zip</type>
          <target>/apps/moonlightprodprogram-vendor-packages/application/install</target>
       </embedded>
      ```

   1. Add the following text at the end of the `<dependencies>` tag:
      
      ```shell
       <dependency>
          <groupId>com.adobe.aemforms.samples</groupId>
          <artifactId>forms.integration.docusign.all</artifactId>
          <type>zip</type>
       </dependency>
      ```
1. Compile and [Deploy the code to your [!DNL AEM Forms] as a Cloud Service environment](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=en#customer-releases).



