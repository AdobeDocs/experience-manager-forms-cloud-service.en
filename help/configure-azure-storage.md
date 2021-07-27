---
title: How to configure Azure storage?
description: 
---
# Configure Azure storage {#configure-azure-storage}

 [[!DNL Experience Manager Forms] Data Integration](data-integration.md) provides an Azure storage configuration to integrate forms with Azure storage server. The Form Data Model can be used to create Adaptive Forms that interact with [!DNL Azure] server to enable business workflows. For example:

* Query [!DNL Azure] server for data and prepopulate Adaptive Forms
* Write data into [!DNL Azure] on Adaptive Form submission
* Write data in [!DNL Azure] through custom entities defined in Form Data Model and vice versa.

## Create Azure storage configuration {#create-azure-storage-configuration}

Before executing these steps, ensure that you have an Azure storage account and an access key to authorize the access to the Azure storage account.

1. Navigate to **[!UICONTROL Tools]** &gt; **[!UICONTROL Cloud Services]** &gt; **[!UICONTROL Azure Storage]**.
1. Select a folder to create the configuration and tap **[!UICONTROL Create]**.
1. Specify a title for the configuration in the **[!UICONTROL Title]** field.
1. Specify the name of the Azure storage account in the **[!UICONTROL Azure Storage Account]** field.
1. Specify the key to access Azure storage account in the **[!UICONTROL Azure Access Key]** field and tap **[!UICONTROL Save]**.

## Create Form Data Model {#create-azure-form-data-model}

After creating the Azure storage configuration, you can [create the Form Data Model](create-form-data-models.md). Specify the folder that contains the Azure configuration in the **[!UICONTROL Data Source Configuration]** field while creating the Form Data Model. You can then select the configuration from the list of configurations thay exist in the specified folder name.
After creating the Form Data Model, [add data model objects and services](work-with-form-data-model.md) to the Form Data Model.

### Add Azure services to the Form Data Model {#add-azure-services}

After creating the Form Data Model and adding data model objects, you can add Azure services to the Form Data Model.

To add Azure services:

1. In the Edit mode, select the services from the **[!UICONTROL Services]** section in the left pane and tap **[!UICONTROL Add Selected]**. The selected services display in the **[!UICONTROL Services]** tab of the Form Data Model.

   ![Add Selected Services](assets/select-services.png)

1. In the **[!UICONTROL Services]** tab, select the service and **[!UICONTROL Edit Properties]**. Based on the service, define the input or output model objects for the service.

1. Tap **[!UICONTROL Save]** to save the form data model.