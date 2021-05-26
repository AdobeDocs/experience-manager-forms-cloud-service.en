---
title: [!DNL AEM Forms] as a Cloud Service release notes
description: [!DNL AEM Forms] as a Cloud Service release notes
---

# [!DNL Experience Manager Forms] as a Cloud Service release note {#overview}

Adobe Experience Manager [!DNL AEM Forms] as a Cloud Service receives improvements on an ongoing basis. To stay up to date with the most recent developments, visit this page regularly. This page provides you with information about:

* New features
* improvements
* Bug fixes
* Deprecated functionality
* Special instructions
* Future plans for changes

## 2021.5.0 {#april-2021-05-0}

### New feature summary {#whats-new-2021-05-0}

* **Output service**: The Output service lets you create documents in different formats, including PDF, laser printer formats, and label printer formats. Laser printer formats are PostScript and Printer Control Language (PCL).

* **Contextual help**: Added contextual help for adaptive forms editor, template editor, and theme editor to help authors better understand various features of editors.

### Upcoming beta {ucoming-beta-2021-05-0}

*	**Variable Data Externalizer**: You can save data of AEM Workflow variables on an external storage system managed by your organization. You can write to formscsbeta@adobe.com to get the feature enabled for your cloud service environment.

### Bug fixes {#bug-fixes-2021-05-0}

* When you use coral icons for actions in an Assign Task step of AEM Workflows, the workflow fails with an exception. The workflow works fine when coral icons are no used.

## 2021.4.0 {#april-2021-04-0}

### New feature summary {#whats-new-2021-04-0}

* **Use Government ID identity authentication method in Adobe Sign enabled Adaptive Forms**

  Powered by advanced machine learning algorithms, Adobe Sign’s Government ID process empowers companies across the globe with the ability to secure a high-quality authentication of their recipient's identity. Now, you can use Government ID identity authentication method in Adobe Sign enabled Adaptive Forms.

  Government ID is a premium identity authentication method that instructs the recipient to [upload the image of a government-issued identity document (driver’s license, national ID, passport)](https://helpx.adobe.com/in/sign/using/adobesign-authentication-government-id.html), and then evaluates that document to ensure it's authentic.

* **Support to use in-form signing experience for asynchronous adaptive form submissions**

  You can now use the in-form signing experience for asynchronous adaptive form submissions. You can also embed an adaptive form in an [!DNL Experience Manager Sites] page and use the in-form signing experience for adaptive form submissions.

* **Support to use a variable to specify an attachment while prepopulating an Adaptive Form for an Assign Task step**

  While [prepopulating an Adaptive Form](aem-forms-workflow-step-reference.md) for an Assign Task step, you can now use a document type variable to select an input attachment for the Adaptive Form.

* **Support to use the literal option to set value for a JSON type variable**

  You can use literal option to [set value for a JSON type variable](variable-in-aem-workflows.md) in the set variable step of an AEM Workflow. The literal option allows you to specify a JSON in the form of a string.

* **Use local development environment to create Document of Record (DoR)**

  You can use an XDP as a Document of Record template on Cloud Service instances and AEM Forms as a Cloud Service SDK (Local development environment). Previously, the support was limited to Cloud Service instances only.


### Bug fixes {#bug-fixes-2021-04-0}

* When an Adaptive Form configured to not-generate Document of Record is submitted to an AEM Workflow configured to generate Document of Record, no error message is displayed, and the task fails to submit.  

### Other updates {#misc-2021-04-0}

* To make easier to recognize content the service now generates live thumbnail for XDP, Dynamic PDF, and Schema files.
* Add ability to move a PDF file to a folder placed in on AEM Forms UI.
