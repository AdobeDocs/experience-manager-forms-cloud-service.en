---
title: Default groups and privileges
seo-title: AEM Forms as a Cloud Service default groups and privileges
description: Assign users to the groups to manage their privileges on an AEM Forms as a Cloud Service instance
seo-description: Assign users to the groups to manage their privileges on an AEM Forms as a Cloud Service instance
uuid: f269a206-356d-4cee-b449-05c5da87121a
contentOwner: khsingh
products: SG_EXPERIENCEMANAGER/6.5/FORMS
content-type: reference
topic-tags: Configuration
discoiquuid: 1717b1b4-1c2a-450e-8e79-4156a974d5fa

---

# Groups and privileges {#aem-forms-groups-and-privileges}

You can create [profiles](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/security/ims-support.html) and assign  [users](https://docs.adobe.com/content/help/en/experience-manager-65/administering/security/user-group-ac-admin.html) to profiles in AEM. You can also create [groups](https://docs.adobe.com/content/help/en/experience-manager-65/administering/security/user-group-ac-admin.html#group-administration) and assign policies and users to the groups in AEM. These policies control privileges of the users that are part of the group.

Once you [run AEM Forms pipeline](setup-forms-cloud-service.md) or install [AEM Forms add-on feature archive](setup-local-development-environment.md), the groups mentioned below, such as forms-user and forms-power-user, are automatically available for assignment. The following table lists the tasks a user can perform for AEM Forms as a Cloud service based on the group assignments:

<table>
 <tbody>
  <tr>
   <td>Group</td> 
   <td>Tasks</td> 
  </tr>
  <tr>
   <td>forms-user <sup>[1]</sup></td> 
   <td>
    <ul> 
     <li>Create, preview, publish, and submit adaptive forms</li> 
     <li>Create, preview, and publish interactive communications and document fragments</li> 
     <li>Upload assets to an AEM instance</li> 
     <li>Create themes</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td>forms-power-user</td> 
   <td>
    <ul> 
     <li>Create, preview, publish, and submit adaptive forms</li> 
     <li>Create, preview, and publish interactive communications and document fragments</li> 
     <li>Create scripts for adaptive forms using code editor</li> 
     <li>Upload assets including scripts</li> 
     <li>Create themes</li> 
     <li>Import packages containing XDP</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td>forms-submission-reviewers</td> 
   <td>
    <ul> 
     <li>Review submissions</li> 
     <li>Approve or reject submissions</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td>template-authors <sup>[2]</sup></td> 
   <td>
    <ul> 
     <li>Create and preview adaptive forms or interactive communications templates</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td><p>fdm-authors</p> </td> 
   <td>
    <ul> 
     <li>Create and modify a form data model</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td><p>workflow-editors</p> </td> 
   <td>
    <ul> 
     <li>Create an inbox application</li> 
     <li>Create a workflow model</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td>workflow-users</td> 
   <td>
    <ul> 
     <li>Use AEM inbox applications<br /> <strong>Note: </strong>You must have cm-agent-users and workflow-users group assignments to access Interactive Communications Agent UI in AEM inbox.</li> 
     <li>Manage workflow instances</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td>fd-administrators</td> 
   <td>
    <ul> 
     <li>Configure PDF Generator</li> 
     <li>Configure Watched folder</li> 
     <li>Manage workflow applications</li> 
    </ul> </td> 
  </tr>
 </tbody>
</table>

1. The user with forms-user group privileges cannot write scripts for adaptive forms.
1. The user with template-authors group privileges cannot write scripts for templates.

