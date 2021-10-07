---
title: Integrate DocuSign with an adaptive form
seo-title: Learn how to use DocuSign with an adaptive form to collect e-signatures.
---

# Using DocuSign with an adaptive form {#integrate-aem-forms-with-DocuSign}

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

1. Clone the [aem-forms-samples](https://git.corp.adobe.com/hsalhotr/aem-forms-samples) repository. This repository contains custom submit action for DocuSign and configuration details to connect with the DocuSign server.

1. Perform the following steps in the `pom.xml` file available in the Cloud Service project folder:
   1.  Add the following text at the end of the `<properties>` tag:

       ```shell
       <repository.location>maven_repository</repository.location>
       ```
       
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

1. Open the command prompt and navigate to `aem-forms-samples\forms-integration-docusign` (cloned in step 3) and run the following command:

   ```shell
   mvn clean install -Dinstall.dir="<Cloud Service project directory path>/maven_repository"
   ```

   `<Cloud Service project directory path>` refers to the name of the folder created in step 1 of this procedure.

1. Deploy the project to your local development environment. You can use the following command to deploy to your local development environment

    `mvn -PautoInstallPackage clean install`

1. Compile and [Deploy the code to your [!DNL AEM Forms] as a Cloud Service environment](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/deploying/overview.html?lang=en#customer-releases).

After executing these steps, you can view a new custom submit action [Submit with DocuSign electronic signatures](#enabledocusign) available in the list of submission options for an adaptive form and a [DocuSign cloud service configuration](#configure-docusign-with-aem-forms).

## Configure [!DNL DocuSign] with [!DNL AEM Forms] {#configure-docusign-with-aem-forms}

After prerequisites are in place, perform the following steps to configure [!DNL DocuSign] with [!DNL AEM Forms] on the Author instances.

1. On AEM Forms author instance, navigate to **[!UICONTROL Tools]** ![hammer](assets/hammer.png) &gt; **[!UICONTROL General]** &gt; **[!UICONTROL Configuration Browser]**.
1. On the **[!UICONTROL Configuration Browser]** page, tap **[!UICONTROL Create]**.
1. In the **[!UICONTROL Create Configuration]** dialog, specify a **[!UICONTROL Title]** for the configuration, enable **[!UICONTROL Cloud Configurations]**, and tap **[!UICONTROL Create]**. It creates a configuration container to store  Cloud Services. Ensure that the folder name does not contain any space.
1. Navigate to **[!UICONTROL Tools]** ![hammer](assets/hammer.png) &gt; **[!UICONTROL Cloud Services]** &gt; **[!UICONTROL DocuSign]** and open the configuration container you created in the previous step.

   >[!NOTE]
   >
   >When you create an Adaptive Form, specify the container name in the **[!UICONTROL Configuration Container]** field.  
  
1. On the configuration page, tap **[!UICONTROL Create]** to create [!DNL DocuSign] configuration in AEM Forms.
1. In the **[!UICONTROL General]** tab of the **[!UICONTROL Create DocuSign Configuration]** page, specify a **[!UICONTROL Name]** for the configuration, and tap **[!UICONTROL Next]**. You can optionally specify a **[!UICONTROL Title]** and browse to select a **[!UICONTROL Thumbnail]** for the configuration.

1. Copy the URL in your current browser window to a notepad. The URL is required to configure [!DNL DocuSign] application with [!DNL AEM Forms] in a later step.

1. Configure OAuth settings for the [!DNL DocuSign] application:

    1. Open a browser window and sign in to your [!DNL DocuSign] developer account.
    1. Select the application configured for [!DNL AEM Forms], and tap **[!UICONTROL Configure OAuth for Application]**.
    1. In the **[!UICONTROL Redirect URL]** box, add the URL copied in the previous step and click **[!UICONTROL Save]**.
    1. Enable the following OAuth settings for the [!DNL DocuSign] application and click **[!UICONTROL Save]**.

    - [!DNL aggrement_read]
    - [!DNL aggrement_write]
    - [!DNL aggrement_send]
    - [!DNL widget_read]
    - [!DNL widget_write]
    - [!DNL workflow_read]

   For step-by-step information to configure OAuth settings for an [!DNL DocuSign] application and obtain the keys, see [Configure oAuth settings for the application](https://www.adobe.io/apis/documentcloud/sign/docs.html#!adobedocs/adobe-sign/master/gstarted/configure_oauth.md) developer documentation.

   ![OAuth Config](assets/oauthconfig_new.png)

1. Go back to the **[!UICONTROL Create DocuSign Configuration]** page. In the **[!UICONTROL Settings]** tab, the **[!UICONTROL OAuth URL]** field mentions the following default URL:

   `https://account-d.docusign.com/oauth/auth`

1. Specify the **[!UICONTROL Client ID]** (also referred to as Application ID) and **[!UICONTROL Client Secret]**. Use the Client ID and Client Secret of DocuSign application you created in previous step.

1. Tap **[!UICONTROL Connect to DocuSign]**. When prompted for credentials, provide username and password of the account used while creating [!DNL DocuSign] application. When asked to confirm access for `your developer account`, Click **[!UICONTROL Allow Access]**. If the credentials are correct and you allow [!DNL AEM Forms] to access your [!DNL DocuSign] developer account, a success message appears.

1. Tap **[!UICONTROL Create]** to create the [!DNL DocuSign] configuration.

1. Select the configuration and click **[!UICONTROL Publish]**, select the configuration, and click **[!UICONTROL Publish]**. It replicates the configuration to corresponding publish environments.

1. Repeat all the above steps on your developer, stage, and production instances (whichever left) to complete configuring [!DNL DocuSign] with [!DNL AEM Forms] for your environment.

Now, you can [use add DocuSign fields to an Adaptive Form](working-with-adobe-sign.md). Ensure that you add the configuration container used for the Cloud Service to all the Adaptive Forms being enabled for [!DNL DocuSign]. You can specify a configuration container from the  properties of an Adaptive Form.

### Use [!DNL DocuSign] in an Adaptive Form  {#enabledocusign}

You can enable [!DNL DocuSign] for an existing Adaptive Form or create an [!DNL DocuSign] enabled Adaptive Form. Choose one of the following:

- [Create an [!DNL DocuSign] enabled Adaptive Form](#create-an-adaptive-form-for-docusign)
- [Enable [!DNL DocuSign] for an existing Adaptive Form](#editafsign).

#### Create an Adaptive Form for DocuSign {#create-an-adaptive-form-for-docusign}

To create a sign-enabled Adaptive Form:

1. Navigate to **[!UICONTROL Adobe Experience Manager]** > **[!UICONTROL Forms]** > **[!UICONTROL Forms & Documents]**.
1. Tap **[!UICONTROL Create]** and select **[!UICONTROL Adaptive Form]**. A list of templates appears. Select a template and tap **[!UICONTROL Next]**.
1. In the **[!UICONTROL Basic]** tab:

    1. Specify the **[!UICONTROL Name]** and **[!UICONTROL Title]** for the Adaptive Form.

    1. Select the [configuration container](adobe-sign-integration-adaptive-forms.md#configure-adobe-sign-with-aem-forms) created while [integrating [!DNL DocuSign] with [!DNL AEM Forms]](adobe-sign-integration-adaptive-forms.md).

      The configuration container contains the [!DNL DocuSign] Cloud Services configured for your environment. These services are available for selection in Adaptive Form editor.  

1. In the **[!UICONTROL Form Model]** tab, select one of the following options:

    - If you have a custom form template and require a Document of Record based on the form template, select the **[!UICONTROL Associate form template as the Document of Record template]** option and select a Document of Record template. When you use the option, then the documents sent for signing display only those fields which are based on the associated form template. It does not display all the fields of the Adaptive Form.

    - If you do not have a custom form template, select the **[!UICONTROL Generate Document of Record]** option. When you use the option, the document sent for signing displays all the fields of the Adaptive Form.

1. Tap **[!UICONTROL Create.]** A sign-enabled Adaptive Form is created. You can add your [!DNL DocuSign] fields to the form and send it for signing.
1. Open the adaptive form in edit mode. In the **[!UICONTROL Content]** tab, tap the **[!UICONTROL Form Container]** and tap ![Configure](assets/configure-icon.svg).

1. In the **[!UICONTROL Submission]** section, select **[!UICONTROL Submit with DocuSign electronic signatures]** from the **[!UICONTROL Submit Action]** dropdown list.

1. In the **[!UICONTROL Action Configuration]** section, tap **[!UICONTROL Add]** to add a signer and specify the email address of the signer. Tap **[!UICONTROL Add]** again to add more signers.

1. Specify the subject for the email message in the **[!UICONTROL Email Subject]** field. Select **Include Attachments** to include attachments in the email message.

1. Tap ![Save](assets/save_icon.svg) to save the properties. 

#### Enable [!DNL DocuSign] for an Adaptive Form {#editafsign}

To use [!DNL DocuSign] in an existing Adaptive Form:

1. Navigate to **[!UICONTROL Adobe Experience Manager]** > **[!UICONTROL Forms]** > **[!UICONTROL Forms & Documents]**.
1. Select the Adaptive Form and tap **[!UICONTROL Properties]**.
1. In the **[!UICONTROL Basic]** tab, select the [configuration container](adobe-sign-integration-adaptive-forms.md#configure-adobe-sign-with-aem-forms) created while integrating [!DNL DocuSign] with [!DNL AEM Forms].
1. In the **[!UICONTROL Form Model]** tab, select one of the following options:

   - If you have a custom form template and require a Document of Record based on the form template, select the **[!UICONTROL Associate form template as the Document of Record template]** option and select a Document of Record template. When you use the option, then the documents sent for signing display only those fields which are based on the associated form template. It does not display all the fields of the Adaptive Form.

   - If you do not have a custom form template, select the **[!UICONTROL Generate Document of Record]** option. When you use the option, the document sent for signing displays all the fields of the Adaptive Form.

1. Tap **[!UICONTROL Save & Close]**. The Adaptive Form is enabled for [!DNL DocuSign]. Now, you can add your [!DNL DocuSign] fields to the form and send it for signing.

1. Open the adaptive form in edit mode. In the **[!UICONTROL Content]** tab, tap the **[!UICONTROL Form Container]** and tap ![Configure](assets/configure-icon.svg).

1. In the **[!UICONTROL Submission]** section, select **[!UICONTROL Submit with DocuSign electronic signatures]** from the **[!UICONTROL Submit Action]** dropdown list.

1. In the **[!UICONTROL Action Configuration]** section, tap **[!UICONTROL Add]** to add a signer and specify the email address of the signer. Tap **[!UICONTROL Add]** again to add more signers.

1. Specify the subject for the email message in the **[!UICONTROL Email Subject]** field. Select **Include Attachments** to include attachments in the email message.

1. Tap ![Save](assets/save_icon.svg) to save the properties.


