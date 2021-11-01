---
title: Experience Manager [!DNL Forms] as a Cloud Service Communications batch processing 
description: How to create brand-oriented and personalized communications?
---

# Forms as a Cloud Service Communications - batch processing 

Communications allows you to create, assemble, and deliver brand-oriented and personalized communications such as business correspondences, documents, statements, claim processing letters, benefit notices, claim processing letters, monthly bills, and welcome kits. You can use Communications APIs to combine a template (XFA or PDF) with customer data to generate documents in PDF, PS, PCL, and ZPL formats.

Communications provide APIs for on-demand and scheduled document generation. You can use synchronous APIs for on-demand and batch APIs (asynchronous APIs) for scheduled document generation:

* Synchronous APIs are suitable for on-demand, low latency, and single record document generation use cases. These APIs are more suitable for user-action based use cases. For example, generating a document after a user fill a form. 

* Batch APIs (Asynchronous APIs) are suitable for scheduled high throughput multiple document generation use cases. These APIs generate documents in batches. For example, phone bills, credit card statements, and benefits statements generated every month.

<!-- The following skills are required to create templates and use HTTP APIs: 

* Understanding of Adobe Forms Designer or Acrobat Forms to create templates

* Understanding of HTTP APIs and experience of using HTTP APIs

* Basic understanding of Adobe Experience Manager -->


## Batch operations {#batch-operations}

A batch operation is a process of generating multiple documents of similar type for a set of records at scheduled intervals. A batch operation has two parts: Configuration (definition) and execution. 

* **Configuration (definition)**: A batch configuration stores information about various assets and properties to set for generated documents. For example, it provides details about the XDP or PDF template and location of customer data to use along with specifying various properties for output PDF documents.

* **Execution**: To start a batch operation, run and pass on the batch configuration to an Asynchronous API.

### Components of a batch operation {#components-of-a-batch-operations}

**Cloud configuration**: Experience Manger Cloud configuration helps you connect an Experience Manager instance to customer owned Microsoft Azure Storage.

**Batch Data Store configuration (USC)**: Batch data configuration helps you configure a specific instance of Blob storage for Batch APIs.

**Batch APIs**: Use these APIs to create and execute a batch operation to merge a PDF or XDP template with data and generate output in PDF, PS, PCL, and ZPL formats.

![data-merge-table](assets/communications-batch-structure.png)

**Storage**: Communication APIs use customer owned Microsoft Azure Cloud storage to fetch customer records and store generated documents. You configure Microsoft Azure Storage in Experience Manager Cloud Service Configuration.

**App**: Your custom application to use the Batch APIs to generate and consume documents.

## Generate multiple documents using batch operations {#generate-multiple-documents-using-batch-operations}

You can use batch operations to generate multiple documents at scheduled intervals.

>[!VIDEO](https://video.tv.adobe.com/v/337425)

You can watch the video or perform the instructions below to learn how to generate documents using batch operations.  

### Pre-requisites {#pre-requisites}

To use Batch API, the following is required: 

* [Microsoft Azure Storage account](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-create)
* PDF or XDP templates 
* [Data to be merged with templates](#form-data)
* Users with Experience Manager administrator privileges

### Setup your environment {#setup-your-environment}

Before using a batch operation:

* Upload customer data (XML files) to Azure Storage
* Create a Cloud configuration
* Create Batch Data Store configuration
* Upload templates and other assets to your Experience Manager Forms Cloud Service instance

### Upload customer data (XML files) to Azure Storage {#upload-customer-data-to-Azure-Storage}

On your Microsoft Azure Storage, create [containers](https://docs.microsoft.com/en-us/azure/vs-azure-tools-storage-explorer-blobs) and [upload customer data (XML)](https://docs.microsoft.com/en-us/azure/vs-azure-tools-storage-explorer-blobs#managing-blobs-in-a-blob-container) to the [folders](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-quickstart-blobs-portal) inside the containers.  
Note: You can configure Microsoft Azure storage to automatically clean input folder or move content of output folder to a different location at scheduled intervals.

### Create a Cloud configuration {#create-a-cloud-configuration}

The Cloud configuration connects your Experience Manager instance to Microsoft Azure Storage. To create a Cloud configuration:

1. Go to Tools > Cloud Services > Azure Storage
1. Open a folder to host the configuration and click Create. You use the Global folder or create a new folder.
1. Specify name of the configuration and credentials to connect to the service. You can [retrieve these credentials from your Microsoft Azure Storage portal](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-keys-manage?tabs=azure-portal#view-account-access-keys).  
1. Click Create.

Your Experience Manager instance is now connected to Microsoft Azure Storage.

### Create Batch Data Store configuration {#create-batch-data-store-configuration}

Batch data configuration helps you configure containers and folders for input and output. You keep your customer records in Source Folder and generated documents are placed in the Destination Folder.

Before creating the Batch Data Store configuration, create source and destination folders on your Microsoft Azure Storage. To create the configuration:

1. Go to Tools > Forms > Output Batch – Unified Storage Connector.
1. Open a folder to host the configuration and click Create. You use the Global folder or create a new folder.
1. Specify Title and Name of the configuration. In Storage select Microsoft Azure Storage.
1. In Storage Configuration Path, browse and select the Cloud Configuration for connecting to Microsoft Azure Storage.  
1. In the Source Folder, specify path of Azure Storage container and folder containing records. 
1. In the Destination Folder, specify path of Azure Storage container and folder to store the generated documents.
1. Click Create.

Your Experience Manager instance is now connected to Microsoft Azure Storage and configured to retrieve and send data to specific locations on Microsoft Azure Storage.


### Upload templates and other assets to your Experience Manager instance {#upload-templates-and-other-assets-to-your-AEM-instance}

An organization typically has multiple templates. For example, one template each for credit card statements, benefits statements, and claim applications. Upload all such XDP and PDF templates to your Experience Manager instance. To upload a template:

1. Open you Experience Manager instance. 
1. Go to Forms > Forms and Documents 
1. Click Create > Folder and create a folder. Open the folder.
1. Click Create > File Upload and upload the templates.

## Use batch API to generate documents {#use-batch-API-to-generate-documents}

To use a batch API, create a batch job and run it. The API documentation provides information about APIs to create and run a batch, corresponding parameters, and possible errors. You can download the API definition file (.yaml file) and upload it to Postman or similar software to test the APIs to create and run a batch operation.

### Create a batch {#create-a-batch}

To create a batch, use the /config API. Include the following mandatory properties in the body of the HTTP request:

* **configName**: Specify Unique name of the batch. For example, `wknd-job`
* **dataSourceConfigUri**: Specify location of the Batch Data Store configuration. It can be relative or absolute path of the configuration. For example: `/conf/global/settings/forms/usc/batch/wknd-batch`
* **outputTypes**: Specify output formats: PDF or Print. If you us the Print output type, use the renderType property to specify the format of print output. The supported formats are PCL, PS, ZPL. 
* **template**: Specify absolute or relative path of the template. For example, `crx:///content/dam/formsanddocuments/wknd/statements.xdp`

For example, you include the following JSON in the body of HTTP APIs to create a batch named wknd-job:

Once you create a batch, you can use the /config/[configName] to see details of the batch.

### Run a batch {#run-a-batch}

To create a batch, use the `/config /[configName]/execution`. For example, to run a batch named wknd-demo, use /config/wknd-demo/execution. The server returns HTTP response code 202 on accepting the request.  The API does not return any payload except a unique code in header of HTTTP response for the batch job running on the server. You can use the unique code (Batch-Job-ID) to retrieve the status of the batch.

>[!NOTE]
>
>While the batch is running, do not make any changes to source and destination folders.

### Check status of a batch {#status-of-a-batch}

To retrieve status of a batch, use the /config /[configName]/execution/[Batch Job ID]. The (Batch-Job-ID) is included in the header of HTTTP response for the batch execution request.  For example, the following image displays unique code for a batch job.

The response of the status request contains the status section. It provides details about status of the batch job, number of records, and status of each output type specified in the job. It also includes start and end time of batch job along with information about errors, if any.

### View generated documents {#view-generated-documents}

On completion of job, the generated documents are stored to the `success` folder at the destination location specified in the Batch Data Store configuration. If there are any errors, the service creates a `failure` folder. It provides information about the type and reason of errors.

Processing a batch can take some time depending on the number of input records and complexity of the template. It is advised to wait for a few minutes before checking destination folders for output files.

## Considerations  {#considerations-for-communications-apis}

### Form data {#form-data}

Communications APIs accept both a form design that is typically created in Designer and XML form data as input. To populate a document with data, an XML element must exist in the XML form data for every form field that you want to populate. The XML element name must match the field name. An XML element is ignored if it does not correspond to a form field or if the XML element name does not match the field name. It is not necessary to match the order in which the XML elements are displayed. The important factor is that the XML elements are specified with corresponding values.

Consider the following example loan application form:

![Loan application Form](assets/loanFormData.png)

To merge data into this form design, create an XML data source that corresponds to the form. The following XML represents an XML data source that corresponds to the example mortgage application form.

```XML

<?xml version="1.0" encoding="UTF-8" ?>
- <xfa:datasets xmlns:xfa="http://www.xfa.org/schema/xfa-data/1.0/">
- <xfa:data>
- <data>
    - <Layer>
        <closeDate>1/26/2007</closeDate>
        <lastName>Johnson</lastName>
        <firstName>Jerry</firstName>
        <mailingAddress>JJohnson@NoMailServer.com</mailingAddress>
        <city>New York</city>
        <zipCode>00501</zipCode>
        <state>NY</state>
        <dateBirth>26/08/1973</dateBirth>
        <middleInitials>D</middleInitials>
        <socialSecurityNumber>(555) 555-5555</socialSecurityNumber>
        <phoneNumber>5555550000</phoneNumber>
    </Layer>
    - <Mortgage>
        <mortgageAmount>295000.00</mortgageAmount>
        <monthlyMortgagePayment>1724.54</monthlyMortgagePayment>
        <purchasePrice>300000</purchasePrice>
        <downPayment>5000</downPayment>
        <term>25</term>
        <interestRate>5.00</interestRate>
    </Mortgage>
</data>
</xfa:data>
</xfa:datasets>


```

### Supported document types {#supported-document-types}

For complete access to the rendering capabilities of the Communications APIs, it is recommended that you use an XDP file as input. Sometimes, a PDF file can be used. However, using a PDF file as input has the limitations:

A PDF document that does not contain an XFA stream cannot be rendered as PostScript, PCL, or ZPL. Communications APIs can render PDF documents with XFA streams (that is, forms created in Designer) into laser and label formats. If the PDF document is signed, certified, or contains usage rights (applied using AEM Forms Reader Extensions service), it cannot be rendered to these print formats.

## Known issues {#known-issues}

* Ensure that the size of the template and XCI configuration files is larger than 16KB.

* Ensure that the data xml file does not contain the XML declaration header. For example, `<?xml version="1.0" encoding="UTF-8"?>`

* For a batch configuration, only one instance of combination of values of OutputType(PDF, PRINT) and RenderType(PostScript, PCL, IPL, ZPL, and so on) is allowed.

* Do not modify the Data Source USC Configuration/Azure Cloud Configuration used in a batch configuration while the batch is being run. Even after execution, if any update is required, create a copy of configuration instead of updating the one used in an existing batch configuration.

## Best Practices {#best-practices}

* Adobe recommends hosting data files blob container store in the cloud region used by Experience Manager Cloud Service.

## Frequently asked questions {#faq}

**Can I use a watched folder or other storage mechanisms to store input and output?**

At the moment, you can use Microsoft Azure Storage to save input data and generated documents. Microsoft Azure storage provides various options to [automate data movement operations](https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy-v10).

**Is a Microsoft Azure Storage account included with Experience Manager Forms Cloud Service licence?**

Microsoft Azure Storage account is independent of Experience Manager Forms Cloud Service licence.

**Does Communication APIs store data on Experience Manager Forms Cloud Service servers?**

Input and output data is saved only on Microsoft Azure Storage.

**Are Communication APIs available only for Experience Manager Forms Cloud Service? Can I get similar functionality on on-premise environment?**

You can use AEM Forms Output service to combine a template (XFA or PDF) with customer data to generate documents in PDF, PS, PCL, and ZPL formats.

In comparison to on-premise environment,  the Cloud Service provides additional benefits of auto-scaling and cost effectiveness.

<!--**Where is data processed?**

**Who has access to data?**

**Is data encrypted?**

**Where is data hosted?** -->

**Can I run multiple batch operations simultaneously?**
Yes, you can run multiple batch operations simuntabously. It is advised to use different source and destination folders for every operation to avoid any conflicts.
