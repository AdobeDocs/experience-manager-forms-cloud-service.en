---
title: Enable Forms capability for your organization and Sites as a Cloud Service instances 
description: Enable Forms capability on your organization and sites as a Cloud Service instance
---

# Set up a AEM Forms as a Cloud Service instance {#overview}

AEM Forms as a Cloud Service offers a cloud-native, Platform as a service (PaaS) solution for businesses to create, manage, publish, and update complex digital forms while integrating submitted data with back-end processes, business rules, and saving data in a data store for later use. The service is always current, always available, and always learning. 

>[!NOTE]
>
> June 2020 release does not support using a AEM Forms as a Cloud Service instance to create forms. You can use AEM Forms as a Cloud Service instance to store, manage, and publish adaptive forms and use a local development environment to create an adaptive form. You export adaptive forms and related assets from the local development environment to AEM Forms as a Cloud Service environments for publishing.


## Prerequisites {#prerequisites}

* If you are new to AEM as a cloud service, contact your Adobe representative to create an organization identifier for your company in the Adobe Identity Management System (IMS). Once Adobe has created an organization for your company, your designated administrator is added as the first member of the organization.

* Create and configure an AEM Sites program for your organization. For details, see [Set up your Program](https://docs.adobe.com/content/help/en/experience-manager-cloud-manager/using/getting-started/setting-up-program.html).

* Keep your IMS organization ID and Cloud Manager program ID handy. These are required to enable Forms capability for your Sites as Cloud Service instances.


## Add Forms capability to your AEM Sites program {#add-capability}

1. Create a JIRA ticket with the following details to enable AEM Forms capability for your AEM Sites program:

    | Jira field  | Value/Description  |
    |---|---|
    | Project | Adobe Experience Manager (CQ) |
    | Issue Type | Customer Request|
    | Type of Request | Request for Help |
    | Assignee | Damian Langsweirdt - langswei@adobe.com|
    | Component/s | FPS - Addon Provisioning |
    | Description  | Specify **Customer name**, **[IMS organization ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02)**, and **Addon name**. Specify `Forms` as the Addon name.|
    | Customer Names | Specify name of the customer|
    | Severity from Customer Care | Severity 3 - Services are noticeably impaired, but most business operations continue as normal|
    | Priority from Customer Care | P3 - Relationship could be affected negatively, tasks are more difficult but not impossible to complete |
    | Environment Type | AEM as a Cloud Service |

1. Wait for the support team to enable AEM Forms capability for your AEM Sites program. It can take up to a week to enable the functionality. The JIRA is updated once the functionality is enabled. 

1. After you receive a confirmation on the JIRA that the forms capability is enabled for your AEM Sites program, [run build pipeline](https://docs.adobe.com/content/help/en/experience-manager-cloud-manager/using/how-to-use/deploying-code.html) on your all developer, stage, and production SaaCS instances. It deploys Forms capability to your SaaCS instances.

## Create users and assign roles {#add-users}

1. Log in to your AEM Forms as a Cloud Service instance.  
1. Create [user accounts](https://docs.adobe.com/content/help/en/experience-manager-65/forms/administrator-help/setup-organize-users/adding-configuring-users.html) for your AEM Administrator, Form Developer, and Form Practioners.
1. Add these users to pre-defined forms group to provide the required permissions. The table below lists all types of users and pre-defined groups for each type of forms user:
  
    | User Type | AEM Group |
    |---|---|
    | Form Practitioner  | forms-users, template-author  |
    | Form Developer | forms-users, template-author |
    | Admin rights on AEM |  fd-administrators|
    | End User| forms-users*  |

    `*` When a log-in is required to access and submit forms, add such users to  forms-users group. It allows the users to log-in to access and submit available forms.

## Configure dispatcher caching {#caching}

You can make dispatcher caching related configuration changes to code on your [local development instance](setup-local-development-environment.md) and deploy the changes to your AEM Forms as a Cloud Service instance. Perform the following steps after you setup a local development instance:

