---
title: [!DNL AEM Forms] as a Cloud Service release notes
description: [!DNL AEM Forms] as a Cloud Service release notes
---

# [!DNL Experience Manager Forms] as a Cloud Service release note {#overview}

Adobe Experience Manager [!DNL AEM Forms] as a Cloud Service receives improvements on an ongoing basis. To stay up to date with the most recent developments, visit this page regularly. This page provides you with information about:

* New features
* Improvements
* Pre-release features 
* Beta features
* Bug fixes
* Deprecated functionality
* Special instructions
* Future plans for changes

>[!NOTE]
>
>For release notes of all other AEM as a Cloud Service release components, see [Current Release Notes](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/release-notes/release-notes/release-notes-current.html).

## 2021.8.0 {#aug-2021-08-0}

### What is new in [!DNL Forms] {#what-is-new-forms-aug-2021}

* Automated Forms Conversion service can [convert PDF Forms in Italian and Portuguese language](https://experienceleague.adobe.com/docs/aem-forms-automated-conversion-service/using/extending-the-default-meta-model.html?#language-specific-meta-model) to Adaptive Forms.

* **Acroform-based Document of Record**: AEM Forms as a Cloud Service supports using [Adobe Acrobat Form PDF (Acroform PDF)](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/generate-document-of-record-for-non-xfa-based-adaptive-forms.html) as a template for Document of Record besides XFA-based form template.

* **Microsoft Azure data store connector**: You can now [connect Form Data Model to Microsoft Azure Storage](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/use-form-data-model/configure-azure-storage.html). It allows you to retrieve and store adaptive form data to Microsoft Azure Storage as a BLOB. 

### New features available in [!DNL Forms] prerelease channel {#prerelease-features-forms-aug-2021}

* **Use Adobe Sign roles in an Adaptive Form**: Adobe Sign for business and enterprise service levels have the option to expand the roles for Agreement recipients, beyond just the Signer, to better match their workflow requirements. You can now enable each recipient of agreement to configure their role in an Adaptive Form, with Signer being the default role.

* **Analytics for Adaptive Forms**: You can now capture and track end user behavior via Adobe Analytics for Adaptive Forms to gather end user insights. It helps make informed decisions based on data to improve end user experience.

* **Easily connect AEM Forms with Microsoft Dynamics and Salesforce.com**: The service provides out of the box data source configuration and data models for Microsoft Dynamics and Salesforce.com, making it faster and easier for developers to configure Microsoft Dynamics and Salesforce.com as data sources for an adaptive form.

## 2021.7.0 {#july-2021-07-0}

### What is new in [!DNL Forms] {#july-what-is-new-forms}

* You can now use Automated Forms Conversion service to [convert PDF Forms in French, German, and Spanish language](https://experienceleague.adobe.com/docs/aem-forms-automated-conversion-service/using/extending-the-default-meta-model.html?#language-specific-meta-model) to adaptive forms.
* Added a separate panel to template editor to display errors related to adaptive form components. It helps consolidate all adaptive form errors at one location and reduce resolution time.

### New features available in [!DNL Forms] prerelease channel {#july-prerelease-features-forms}

* **[!DNL AEM Forms as a Cloud Service - Communications]**: [Communication APIs](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/aem-forms-cloud-service-communications.html) help you combine XDP templates and XML data to generate print documents in various formats. The service allows you to generate documents in synchronous mode. The APIs enables you to create applications that let you:
  * Generate documents by populating template files with XML data.
  * Generate output forms in various formats, including non-interactive PDF print streams.
  * Generate print PDF files from an XFA form PDF and Adobe Acrobat Form.

* **Variable Data Externalizer**: You can save data of AEM Workflow variables on an external storage system managed by your organization.

* **Acroform-based Document of Record**: You can also [use Adobe Acrobat Form PDF (Acroform PDF)](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/create-an-adaptive-form/generate-document-of-record-for-non-xfa-based-adaptive-forms.html) as a template for Document of Record besides XFA-based form template.

* **Microsoft Azure data store connector**: You can now [connect Form Data Model to Microsoft Azure Storage](https://experienceleague.adobe.com/docs/experience-manager-forms-cloud-service/forms/use-form-data-model/configure-azure-storage.html). It allows you to retrieve and store adaptive form data to Microsoft Azure Storage as a BLOB.  

## 2021.6.0 {#july-2021-06-0}

### What is new in [!DNL Forms] {#june-what-is-new-forms}

* Added ability to filter custom columns in AEM Inbox.
* Added ability to use the theme editor and style layer of adaptive form editor to style the captcha component. 
* Improved speed and accuracy for automatically detecting logical sections in the source PDF forms and converting those into corresponding adaptive form panels.
* Added move action to move a PDF or XDP file from one folder to another.

### Beta feature of [!DNL Forms]  {#june-what-is-new-forms-prerelease}

* **[!DNL AEM Forms as a Cloud Service - Communications]**: Communication APIs helps you combine XDP templates and XML data to generate print documents in various formats. The service allows you to generate documents in synchronous mode. The APIs enables you to create applications that let you:
  * Generate final form documents by populating template files with XML data.
  * Generate output forms in various formats, including non-interactive PDF print streams.
  * Generate print PDFs from an XFA form PDF and Adobe Acrobat Form (AcroForm).

* **Variable Data Externalizer**: You can save data of AEM Workflow variables on an external storage system managed by your organization. 

You can write to [!DNL formscsbeta@adobe.com] to sign up for the beta program.

### Bugs fixed in [!DNL Forms] {#june-forms-bugs-fixed}

* When a field is validated before submitting data to backend service via Form Data Model (FDM), validations succeed but the Form Data Model service fail to invoke post validation.
* When you submit a form containing a standard HTML upload field from an Apple iOS device, sometimes, the content of the file is not sent and a 0-byte file is received at the other end. This is a known issue in Apple iOS. [FB9117687](https://feedbackassistant.apple.com/feedback/9117687)

## 2021.5.0 {#may-2021-05-0}

## [!DNL Adobe Experience Manager Forms] as a [!DNL Cloud Service] {#forms}

### What is new in [!DNL Forms] {#may-what-is-new-forms}

* **Contextual help**: Added contextual help for adaptive forms editor, template editor, and theme editor to help authors better understand various features of editors.
* **Error messages in Properties browser**: Added error messages for each property in the Adaptive Forms Properties browser. These messages help understand allowed values for a field.

### Upcoming beta feature of [!DNL Forms] {#may-what-is-new-forms-prerelease}

Output as a Cloud service: Output service helps you combine XDP templates and XML data to generate print documents in various formats. The service allows you to generate documents in synchronous and asynchronous batch mode. Output service enables you to create applications that let you:

* Generate final form documents by populating template files with XML data.
* Generate output forms in various formats, including non-interactive PDF print streams.
* Generate print PDFs from XFA form PDFs.

You can write to formscsbeta@adobe.com to sign up for the beta program.

### Bugs fixed in [!DNL Forms] {#may-forms-bugs-fixed}

* In an Assign Task step of AEM Forms Workflows, when you replace the default icon of the action buttons with a coral icon, the workflow stops working and logs an exception. The workflow performs as expected when default icons are used.
* In the layout layer, when you change the number of columns, open the edit layer, and drag some components in a panel, square blue boxes start appearing in the content area of the adaptive forms editor and the editor becomes unresponsive.
* Error message of a rule editor option related to providing URL of an adaptive or an external asset is too long and is not user friendly.

## 2021.4.0 {#april-2021-04-0}

### What is new in [!DNL Forms] {#april-what-is-new-forms}

* **Use Government ID identity authentication method in Adobe Sign enabled Adaptive Forms**

  Powered by advanced machine learning algorithms, Adobe Sign’s Government ID process empowers companies across the globe with the ability to secure a high-quality authentication of their recipient's identity. Now, you can use Government ID identity authentication method in Adobe Sign enabled Adaptive Forms.

  Government ID is a premium identity authentication method that instructs the recipient to [upload the image of a government-issued identity document (driver’s license, national ID, passport)](https://helpx.adobe.com/in/sign/using/adobesign-authentication-government-id.html), and then evaluates that document to ensure it's authentic.

* **Support to use in-form signing experience for asynchronous adaptive form submissions**

  You can now use the in-form signing experience for asynchronous adaptive form submissions. You can also embed an adaptive form in an [!DNL Experience Manager Sites] page and use the in-form signing experience for adaptive form submissions.

* **Support to use a variable to specify an attachment while prepopulating an Adaptive Form for an Assign Task step**

  While prepopulating an Adaptive Form for an Assign Task step, you can now use a document type variable to select an input attachment for the Adaptive Form.

* **Support to use the literal option to set value for a JSON type variable**

  You can use literal option to set value for a JSON type variable in the set variable step of an AEM Workflow. The literal option allows you to specify a JSON in the form of a string.

* **Use local development environment to create Document of Record (DoR)**

  You can use an XDP as a Document of Record template on Cloud Service instances and AEM Forms as a Cloud Service SDK (Local development environment). Previously, the support was limited to Cloud Service instances only.

### Bug fixes in [!DNL Forms] {#april-bug-fixes-forms}

* When an Adaptive Form configured to not-generate Document of Record is submitted to an AEM Workflow configured to generate Document of Record, no error message is displayed, and the task fails to submit.
