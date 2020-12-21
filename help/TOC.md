---
sub-product: Experience Manager Forms 
user-guide-title: AEM Forms as a Cloud Service Guide
description: AEM Forms as a Cloud Service Help
breadcrumb-title: Forms as a Cloud Service Guide
user-guide-description: AEM Forms as a Cloud Service is a platform to create, manage, publish enterprise-class forms and business processes.
---

# AEM Forms as a Cloud Service Guide {#forms}

+ [AEM Forms as a Cloud Service Guide](home.md)
+ Introduction {#introduction-to-forms-cloud-service}
  + [Introduction to Forms as a Cloud Service](introduction.md)
  + [Notable changes](noteable-changes.md)
  + [Frequently asked questions](faq.md)
+ Setup and configure the service {#setup-environment}
  + [Setup a Cloud Service environment](setup-forms-cloud-service.md)
  + [Setup a local development environment](setup-local-development-environment.md)
  + [Configure Automated Forms Conversion service](https://docs.adobe.com/content/help/en/aem-forms-automated-conversion-service/using/configure-service.html)
  + [Configure dispatcher cache](configure-adaptive-forms-cache.md)
  + [Harden your environment](harden-your-forms-as-a-cloud-service-environment.md)
+ [Migrate from AEM 6.5 Forms](migrate-to-forms-as-a-cloud-service.md)
+ Create and publish adaptive forms {#create-an-adaptive-form}
  + Before you start {#before-you-start}
    + [Create a template](template-editor.md)
    + [Create a theme](themes.md)
    + [Convert existing PDF Forms to adaptive forms](https://experienceleague.adobe.com/docs/aem-forms-automated-conversion-service/using/convert-existing-forms-to-adaptive-forms.html?lang=en)
    + [Connect various data sources to exchange business data](data-integration.md)
  + Create an adaptive form {#create-an-adaptive-form-on-forms-cs}
    + [Design JSON Schema for an adaptive form](adaptive-form-json-schema-form-model.md)
    + [Design an XML Schema for an adaptive form](adaptive-form-xml-schema-form-model.md)
    + [Create an adaptive form](creating-adaptive-form.md)
  + Add components to an adaptive form {#add-components-to-an-adaptive-form}
    + [Understand adaptive forms editor](introduction-forms-authoring.md)
    + [Best practices for working with components](best-practices-for-working-with-components.md)
    + [Add tables to an adaptive form](adaptive-forms-tables.md)
    + [Add placeholder text to an adaptive form component](placeholder-text-in-aem-forms.md)
    + [Use the separator component](separator-component-in-adaptive-forms.md)
    + [Author in-context help for adaptive form fields](authoring-in-field-help.md)
    + [Apply electronic signatures to a form using scribble signatures](signing-forms-using-scribble.md)
    + [Use core components](https://github.com/adobe/aem-core-wcm-components)
    + [Create repeatable sections in an adaptive form](creating-forms-repeatable-sections.md)
    + [Create and use reusable form fragments](adaptive-form-fragments.md)
    + [Download and import sample form fragments](reference-adaptive-form-fragments.md)
    + [Generate Document of Record](generate-document-of-record-for-non-xfa-based-adaptive-forms.md)
    + [Synchronize an adaptive form with an XFA form](synchronizing-adaptive-forms-xfa.md)
  + Configure layout and apply style to an adaptive form{#configure-layout-of-an-adaptive-form}
    + [Set layout of an adaptive form](layout-capabilities-adaptive-forms.md)
    + [Use Layout mode to resize components](resize-using-layout-mode.md)
    + [Create multi-step data capture experience](introduction-form-sequence.md)
    + [Apply inline CSS styles to individual adaptive form components](inline-style-adaptive-forms.md)
  + Add rules and use expressions in an adaptive form {#add-rules-and-use-expressions-in-an-adaptive-form}
    + [Add rules to an adaptive form](rule-editor.md)
    + [Grant rule editor access to select user groups](rule-editor-access-user-groups.md)
    + [Use expressions in an adaptive form](adaptive-form-expressions.md)
  + Use Form data model {#use-form-data-model}
    + [Configure data sources](configure-data-sources.md)
    + [Configure Microsoft Dynamics OData](ms-dynamics-odata-configuration.md)
    + [Create form data model](create-form-data-models.md)
    + [Work with form data model](work-with-form-data-model.md)
    + [Use form data model](using-form-data-model.md)
  + Use Adobe Sign {#use-adobe-sign}
    + [Configure Adobe Sign](adobe-sign-integration-adaptive-forms.md)
    + [Use Adobe Sign to e-sign an adaptive form](working-with-adobe-sign.md)
  + Configure submit actions and metadata submission {#configure-submit-actions-and-metadata-submission}
    + [Set submit action for an adaptive form](configuring-submit-actions.md)
    + [Configure redirect page](configuring-redirect-page.md)
    + [Configure asynchronous submission for an adaptive form](asynchronous-submissions-adaptive-forms.md)
    + [Add information from user data to form submission metadata](form-submission-metadata.md)
    + [Create a custom submit action](custom-submit-action-form.md)
  + Localize an adaptive form {#localize-an-adaptive-form}
    + [Use AEM translation workflow to localize adaptive forms and document of record](using-aem-translation-workflow-to-localize-adaptive-forms.md)
    + [Support new locales for an adaptive form](supporting-new-language-localization.md)
  + Preview, publish, or embed an adaptive form {#preview-prefill-publish-an-adaptive-form}
    + [Preview an adaptive form](previewing-forms.md)
    + [Publish or unpublish adaptive forms](publishing-unpublishing-forms.md)
    + [Embed adaptive forms to an AEM Sites page](https://github.com/adobe/aem-core-forms-components)
  + Prepopulate fields or prefill an adaptive form {#prefill-and-prepopulate}
    + [Dynamically populate drop-down lists](dynamically-populate-dropdowns.md)
    + [Prefill adaptive form fields](prepopulate-adaptive-form-fields.md)
  + Review an adaptive form and related assets {#review-adaptive-forms-and-related-assets}
    + [Create and manage reviews for assets in forms](create-reviews-forms.md)
    + [Associating submission reviewers with a form](adding-reviewers-form.md)
  + Improve performance and make an adaptive form accessible {#improve-performance-and-make-forms-accessible}
    + [Improve performance of large forms with lazy loading](lazy-loading-adaptive-forms.md)
    + [Make your adaptive forms accessible](creating-accessible-adaptive-forms.md)
+ Manage users, forms, and metadata  {#manage-forms-and-related-assets}
  + [Configure user, roles, and groups](forms-groups-privileges-tasks.md)
  + Import export forms and related assets {import-export-forms-and-related-assets}
    + [Import and export assets](import-export-forms-templates.md)
    + [Import XDP and PDF documents](get-xdp-pdf-documents-aem.md)
    + [Download an XFA or a PDF form template](download-xfa-or-pdf-form.md)
  + Manage metadata{#manage-metadata}
    + [Add, remove, or edit metadata of an adaptive form](manage-form-metadata.md)
    + [Reuse metadata properties of an adaptive form](reusing-adaptive-forms.md)
+ Create and use workflows {#create-form-centric-workflows}
  + [Create a forms-centric workflow model](aem-forms-workflow.md)
  + [Use forms-centric steps in workflow - step reference](aem-forms-workflow-step-reference.md)
  + [Use variables in a forms-centric workflow model](variable-in-aem-workflows.md)
  + [Dynamically select a user or group for AEM Forms-centric workflow steps](dynamically-select-a-user-or-group-for-aem-workflow.md)
  + [Manage Forms applications and tasks in AEM Inbox](manage-applications-inbox.md)
  + [Share and request access to Inbox items of a user](configure-shared-queues-osgi.md)
  + [Use the Out of Office option](configure-out-of-office-settings.md)
+ Handling user data {#}
  + [Forms-centric workflows on OSGi](forms-workflow-osgi-handling-user-data.md)
+ Troubleshoot the service{#troubleshooting-aem-forms-cloud-service}
  + [Installation and Configuration](troubleshooting-installation-and-configuration.md)
  + [Caching performance](troubleshooting-caching-performance.md)
+ Developer reference {#developer-reference}
  + [API to invoke form data model service from adaptive forms](invoke-form-data-model-services.md)
