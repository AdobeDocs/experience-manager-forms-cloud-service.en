---
title: [!DNL AEM Forms] as a Cloud Service release notes
description: [!DNL AEM Forms] as a Cloud Service release notes
---

# [!DNL AEM Forms] as a Cloud Service release notes {#overview}

Adobe Experience Manager [!DNL AEM Forms] as a Cloud Service receives improvements on an ongoing basis. To stay up to date with the most recent developments, visit this page regularly. This page provides you with information about:

* New features
* improvements
* Bug fixes
* Deprecated functionality
* Special instructions
* Future plans for changes

## 2021.04.01 {#march-2021-04-01}

### What’s New {#whats-new-2021-04-01}

* Use Government ID identity authentication method in Adobe Sign enabled adaptive forms

  Powered by advanced machine learning algorithms, Adobe Sign’s Government ID process empowers companies across the globe with the ability to secure a high-quality authentication of their recipient's identity. Now, you can use Government ID identity authentication method in Adobe Sign enabled adaptive forms.

  Government ID is a premium identity authentication method that instructs the recipient to [upload the image of a government-issued identity document (driver’s license, national ID, passport)](https://helpx.adobe.com/in/sign/using/adobesign-authentication-government-id.html), and then evaluates that document to ensure it's authentic.

* Use literal option to set value for a JSON type variable

  You can use literal option to [set value for a JSON type variable](variable-in-aem-workflows.md) in the set variable step of an AEM Workflow. The literal option allows you to specify a JSON in the form of a string.

* Support to use a variable to specify an attachment while prepopulating an adaptive form for an Assign Task step

  While [prepopulating an adaptive form](aem-forms-workflow-step-reference.md) for an Assign Task step, you can now use a document type variable to select an input attachment for the Adaptive Form.

### Bug fixes {#bug-fixes-2021-04-01}

* When an adaptive form configured to not-generate Document of Record is submitted to an AEM Workflow configured to generate Document of Record, no error message is displayed and the task fails to submit.  
