---
title: Enable Forms capability for your organization and Sites as a Cloud Service instances 
description: Enable Forms capability on your organization and sites as a Cloud Service instance
---

# Enable Forms capability on your Sites as a Cloud Service instance {#overview}

Adobe Experience Manager Forms as a Cloud Service (FaaCS) offers a cloud-native, Platform as a service (PaaS) solution for businesses to create, manage, publish, and update complex digital forms while integrating submitted data with back-end processes, business rules, and saving data in a data store for later use. The service is always current, always available, and always learning. 

>[!NOTE]
>
> June 2020 release does not support using a FaaCS instance to create forms. You can use FaaCS instance to store, manage, and publish adaptive forms and use a local development environment to create an adaptive form. You export adaptive forms and related assets from the local development environment to FaaCS environments for publishing.


## Prerequisites to setup a FaaCS instance {#prerequisites}

* If you are new to AEM as a cloud service, contact your Adobe representative to create an organization identifier for your company in the Adobe Identity Management System (IMS). Once Adobe has created an organization for your company, your designated administrator is added as the first member of the organization.

* Create and configure an AEM Sites program for your organization. For details, see [Set up your Program](https://docs.adobe.com/content/help/en/experience-manager-cloud-manager/using/getting-started/setting-up-program.html).

* Keep your IMS organization ID and Cloud Manager program ID handy. These are required to enable Forms capability for your Sites as Cloud Service instances.


## Add Forms capability to your AEM Sites program {#add-capability}

1. Create a JIRA ticket with the following details to enable AEM Forms capability for your AEM Sites program:

    | Jira field  | Value/Description  |
    |---|---|
    | Project | Adobe Experience Manager (CQ) |
    | Issue Type | [TBD]|
    | Component/s | FPS - Addon Provisioning |
    | Description  | Specify **Customer name**, **IMS organization ID**, **Cloud Manager program ID** , and **Addon name**. Your AEM Sites deployment program ID is the Cloud Manager program ID. Specify `Forms` as the Addon name.|

1. Wait for the support team to enable AEM Forms capability for your AEM Sites program. It can take up to a week to enable the functionality. The JIRA is updated once the functionality is enabled. 

1. After you receive a confirmation on the JIRA that the forms capability is enabled for your AEM Sites program, run build pipeline on your all developer, stage, and production SaaCS instances. It adds Forms capability to your SaaCS instances. To run the build pipeline:

    1. Log in to any SaaCS instance as an administrator. 

    1. Navigate to >>>

    1. Tap **[UIControl Build]**. Wait for the build to complete and deploy on your instance. Now, you are ready to use Forms capability. 

## Add users to your FaaCS instance {#add-users}

1. Create several users like AEM Administrator, Form Developer, Form Practioner, and add these users to pre-defined forms group to provide the required permissions. The table below lists all types of users and pre-defined groups for each type of user:
  
    | User Type | AEM Group |
    |---|---|
    | Form Practitioner  | forms-users, template-author  |
    | Form Developer | forms-users, template-author |
    | AEM Administrator | aem-administrators, fd-administrators |
    | End User| forms-users*  |

    `*` When a log-in is required to access and submit forms, add such users to  forms-users group. It allows the users to log-in to access and submit available forms.
   

## Configure dispatcher caching {#caching}

You can configure dispatcher caching through a local development instance. For instructions, to set up a local development instance, see [Set up a local development environment for Forms as a Cloud Service](C:\Users\khsingh\Documents\GitHub\experience-manager-forms-cloud-service.en\help\setup-local-development-environment.md)

