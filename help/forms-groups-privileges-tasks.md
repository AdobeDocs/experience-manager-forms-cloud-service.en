---
title: In-built AEM Forms as a Cloud Service  Groups 
seo-title: AEM Forms as a Cloud Service User Groups
description: List of out of the box user groups and permissions assigned to each group 
seo-description: List of out of the box user groups and permissions assigned to each group 

---

# Groups and permissions {#aem-forms-on-osgi-groups-and-privileges}

You can [create groups](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/accessing/aem-users-groups-and-permissions.html#accessing) and assign policies and [users](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/accessing/aem-users-groups-and-permissions.html#accessing) to the groups. These policies control permissions of the users that are part of the group.

Once you setup AEM Forms as a Cloud Service, the groups listed in the below table, such as forms-users and forms-power-user, are automatically available for assignment:

<table>
 <tbody>
  <tr>
   <td>Group</td> 
   <td>Permissions</td> 
  </tr>
  <tr>
   <td>forms-users <sup>[1]</sup></td> 
   <td>
    <ul> 
     <li>Create, preview, publish, and submit adaptive forms</li> 
    <!-- <li>Create, preview, and publish interactive communications and document fragments</li> -->
     <li>Upload assets to an AEM instance</li> 
     <li>Create themes</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td>forms-power-user</td> 
   <td>
    <ul> 
     <li>Create, preview, publish, and submit adaptive forms</li> 
     <!-- <li>Create, preview, and publish interactive communications and document fragments</li> 
     <li>Create scripts for adaptive forms using code editor</li> -->
     <li>Upload assets including scripts</li> 
     <li>Create themes</li> 
     <li>Import packages containing XDP</li> 
    </ul> </td> 
  </tr>
  <!-- <tr>
   <td>forms-submission-reviewers</td> 
   <td>
    <ul> 
     <li>Review submissions</li> 
     <li>Approve or reject submissions</li> 
    </ul> </td> 
  </tr> -->
  <tr>
   <td>template-authors <sup>[2]</sup></td> 
   <td>
    <ul> 
     <li>Create and preview adaptive forms <!-- or interactive communications --> templates</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td><p>fdm-authors</p> </td> 
   <td>
    <ul> 
     <li>Create and modify a form data model</li> 
    </ul> </td> 
  </tr>
  <!-- <tr>
   <td>cm-agent-users</td> 
   <td>
    <ul> 
     <li>Access Correspondence Management letters or interactive communications using Agent UI</li> 
    </ul> </td> 
  </tr> --> 
  <!-- <tr>
   <td><p>workflow-editors</p> </td> 
   <td>
    <ul> -->
    <!-- <li>Create an inbox application</li>  -->
    <!-- <li>Create a workflow model</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td>workflow-users</td> 
   <td>
    <ul> 
     <li>Use AEM inbox applications<br /> -->
     <!-- 
     <strong>Note: </strong>You must have cm-agent-users and workflow-users group assignments to access Interactive Communications Agent UI in AEM inbox.</li>  -->
    </ul> </td> 
  </tr>
  <tr>
   <td>fd-administrators</td> 
   <td>
    <ul> 
     <!-- <li>Configure PDF Generator</li> --> 
     <!-- <li>Configure Watched folder</li> -->
     <li>Manage workflow applications</li> 
    </ul> </td> 
  </tr>
 </tbody>
</table>

1. The user with forms-users group privileges cannot write scripts for adaptive forms.
1. The user with template-authors group privileges cannot write scripts for templates.

