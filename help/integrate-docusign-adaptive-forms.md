---
title: Integrate DocuSign with an adaptive form
seo-title: Learn how to use DocuSign with an adaptive form to collect e-signatures.
---

# Using DocSign with an adaptive form {#integrate-aem-forms-with-DocuSign}

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

1.
