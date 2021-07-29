---
title: Generate Document of Record for Adaptive Forms
description: Explains how you can generate a template for a Document of Record (DoR) for Adaptive Forms.

---

# Generate Document of Record for Adaptive Forms {#generate-document-of-record-for-adaptive-forms}

>[!NOTE]
>
>Using AcroForm as a template for Document of Record feature is in the Prerelease Channel for July 2021. The feature which will be generally available in the Aug 2021 release.

## Overview {#overview}

After submitting a form, your customers generally want to keep a record, in print or in document format, of the information they have filled in the form for their future reference. This is referred to as a Document of Record.

This article explains how you can generate a Document of Record for Adaptive Forms.

>[!NOTE]
>
>Auto-generation of Document of Record is not supported for XFA-based Adaptive Forms. However, you can use the XDP used to create the Adaptive Form as Document of Record.

## Adaptive Form types and their documents of record {#adaptive-form-types-and-their-documents-of-record}

When you create an Adaptive Form, you can select a form model. Your options are:

* [Form Templates](creating-adaptive-form.md#create-an-adaptive-form-based-on-an-xfa-form-template)
  Lets you select an XFA template for your Adaptive Form. When you select an XFA template, you can use the associated XDP file for Document of Record as described above.

* [XML Schema](creating-adaptive-form.md#create-an-adaptive-form-based-on-xml-or-json-schema)
  Lets you select an XML schema definition for your Adaptive Form. When you select an XML schema for your Adaptive Form, you can:

    * Associate an XFA template for Document of Record. Ensure that associated XFA template uses the same XML schema as your Adaptive Form
    * Automatically generate Document of Record

* None
  Lets you create an Adaptive Form without a form model. The Document of Record is automatically generated for your Adaptive Form.

When you select a form model, configure Document of Record using options available under Document of Record Template Configuration. See [Document of Record Template Configuration](#document-of-record-template-configuration).

## Automatically generated Document of Record {#automatically-generated-document-of-record}

A Document of Record lets your customers keep a copy of submitted form for printing purpose. When you automatically generate a Document of Record, every time you change your form, its Document of Record is updated immediately. For example, you remove age field for customers who select United States of America as their country. When such customers generate a Document of Record, the age field is not visible to them in the Document of Record.

Automatically generated Document of Record has the following advantages:

* It takes care of data binding.
* It automatically hides fields which are marked exclude from Document of Record at the time of submission. No extra effort is required.
* It saves time for designing Document of Record template.
* It lets you try different styling and appearance using different base templates and choose best style and appearance for Document of Record. Styling appearances are optional, and if you do not specify styling, system styles are set as default.
* It ensures any change in form is immediately reflected in Document of Record.

## Components to automatically generate a Document of Record {#components-to-automatically-generate-a-document-of-record}

To generate a Document of Record for Adaptive Forms, you need the following components:

**Adaptive Form** Adaptive Form for which you want to generate a Document of Record.

**Base template (recommended)** XFA template (XDP file) created in AEM Designer. Base template is used to specify styling and branding information for Document of Record template.

See [Base template of a Document of Record](#base-template-of-a-document-of-record)

>[!NOTE]
>
>Base template of a Document of Record is also called meta-template of a Document of Record.

**Document of Record template** XFA template (XDP file) generated from an Adaptive Form.

See [Document of Record Template Configuration](#document-of-record-template-configuration).

**Form data** Information filled in by a user in the Adaptive Form. It merges with the Document of Record template to generate the Document of Record.

## Mapping of Adaptive Form elements {#mapping-of-adaptive-form-elements}

The following sections describe how Adaptive Form elements appear in Document of Record.

### Fields {#fields}

<table>
 <tbody>
  <tr>
   <th>Adaptive Form component</th>
   <th>Corresponding XFA component</th>
   <th>Included by default in Document of Record Template?</th>
   <th>Notes</th>
  </tr>
  <tr>
   <td>Button</td>
   <td>Button</td>
   <td>false</td>
   <td> </td>
  </tr>
  <tr>
   <td>Check box</td>
   <td>Check Box</td>
   <td>true</td>
   <td> </td>
  </tr>
  <tr>
   <td>Date picker</td>
   <td>Date/Time Field</td>
   <td>true</td>
   <td> </td>
  </tr>
  <tr>
   <td>Drop-down list</td>
   <td>Drop-down List</td>
   <td>true</td>
   <td> </td>
  </tr>
  <tr>
   <td>Scribble Signature</td>
   <td>Signature Scribble</td>
   <td>true</td>
   <td> </td>
  </tr>
  <tr>
   <td>Numeric box</td>
   <td>Numeric Field</td>
   <td>true</td>
   <td> </td>
  </tr>
  <tr>
   <td>Password box</td>
   <td>Password Field</td>
   <td>false</td>
   <td> </td>
  </tr>
  <tr>
   <td>Radio Button</td>
   <td>Radio Button</td>
   <td>true</td>
   <td> </td>
  </tr>
  <tr>
   <td>Text box</td>
   <td>Text Field</td>
   <td>true</td>
   <td> </td>
  </tr>
  <tr>
   <td>Reset button</td>
   <td>Reset Button</td>
   <td>false</td>
   <td> </td>
  </tr>
  <tr>
   <td>Submit button</td>
   <td><p>Email Submit Button</p> <p>HTTP Submit Button</p> </td>
   <td>false</td>
   <td> </td>
  </tr>
  <tr>
   <td>Terms and conditions</td>
   <td> </td>
   <td>true</td>
   <td> </td>
  </tr>
  <tr>
   <td>File Attachment</td>
   <td> </td>
   <td>false</td>
   <td>Not available in Document of Record template. Only Available in Document of Record through attachments.</td>
  </tr>
 </tbody>
</table>

### Containers {#containers}

<table>
 <tbody>
  <tr>
   <th>Adaptive Form component</th>
   <th>Corresponding XFA component</th>
   <th>Notes</th>
  </tr>
  <tr>
   <td>Panel<br /> </td>
   <td>Subform<br /> </td>
   <td>Repeatable panel maps to repeatable subform.</td>
  </tr>
 </tbody>
</table>

### Static components {#static-components}

| Adaptive Form component |Corresponding XFA component |Notes |
|---|---|---|
| Image |Image |The TextDraw and Image components, whether bound or unbound, always appear in the Document of Record for an XSD-based Adaptive Form, unless excluded using the Document of Record settings. |
| Text |Text |

>[!NOTE]
>
>In classic UI, you get different tabs for editing field properties.

### Tables {#tables}

The Adaptive Forms table components such as header, footer, and row map to corresponding XFA components. You can map repeatable panels to tables in Document of Record.

## Base template of a Document of Record {#base-template-of-a-document-of-record}

Base template provides styling and appearance information to Document of Record. It allows you to customize default appearance of auto generated Document of Record. For example, you want to add your company logo in the header, and copyright information in the footer of the Document of Record. The master page from base template is used as a master page for Document of Record template. The master page can have information such as page header, page footer, and page number that you can apply to Document of Record. You can apply such information to Document of Record using base template for auto generation of Document of Record. Using base template enables you to change default properties of fields.

Please follow [Base template conventions](#base-template-conventions) when you design base template.

## Base template conventions {#base-template-conventions}

A base template is used to define header, footer, styling, and appearance for a Document of Record. The header and footer can include information like the company logo and copyright text. The first master page in the base template is copied and used as a master page for the Document of Record, which contains header, footer, page number, or any other information that should appear across all pages in the Document of Record. If you are using a base template which does not conform to base template conventions, the first master page from the base template is still used in Document of Record template. It is highly recommended that you design your base template as per its conventions, and use it for auto generation of Document of Record.

**Master page conventions**

* In the base template, you should name the root subform as `AF_METATEMPLATE` and the master page as `AF_MASTERPAGE`.

* The master page with the name `AF_MASTERPAGE` located under the `AF_METATEMPLATE` root subform is given preference for extracting header, footer, and styling information.

* If `AF_MASTERPAGE` is absent, the first master page present in the base template is used.

**Styling conventions for fields**

* To apply style on the fields in the Document of Record, the base template provides fields located in the `AF_FIELDSSUBFORM` subfrom under the `AF_METATEMPLATE` root subform.

* The properties of these fields are applied to the fields in the Document of Record. These fields should follow the `AF_<name of field in all caps>_XFO` naming convention. For example, the field name for check box should be `AF_CHECKBOX_XFO`.

To create a base template, do the following in AEM Designer.

1. Click **File &gt; New**.
1. Select the **Based on a template** option.

1. Select the **Forms - Document of Record** category.
1. Select **DoR Base Template**.
1. Click **Next** and provide the required information.

1. (Optional) Modify the styling and appearance of fields that you want to apply on the fields in the Document of Record.
1. Save the form.

You can now use the saved form as a base template for Document of Record.
Do not modify or remove any scripts present in the base template.

**Modifying base template**

* If you are not applying any styling over fields in base template, it is advisable to remove those fields from base template so any upgrades to base template are automatically picked up.
* While modifying base template, do not remove, add, or modify scripts.

>[!NOTE]
>
>Design base template using conventions and strictly following the steps above.

## Document of Record Template Configuration {#document-of-record-template-configuration}

Configure the Document of Record template of your form to let your customers download a print friendly copy of the submitted form. An XDP file serves as the Document of Record template. The Document of Record customers download is formatted according to the layout specified in the XDP file.

Perform the following steps to configure a Document of Record for Adaptive Forms:

1. In AEM author instance, click **Forms &gt; Forms and Documents.**
1. Select a form, and click **View Properties**.
1. In the Properties window, tap **Form Model**.
   You can also select a form model when you create a form.

   >[!NOTE]
   >
   >In the Form Model tab, ensure that you select **Schema** or **None** from the **Select From** drop-down. **[!UICONTROL Document of Record is not supported for XFA-based or Adaptive Forms with Form Template as form model.]**

1. In the Document of Record Template Configuration section of the Form Model tab, select one of the following options.

   **None** Select this option if you don't want to configure Document of Record for the form.

   **Associate Form Template as Document of Record Template** Select this option if you have an XDP file that you want to use as a template for the Document of Record. On selecting this option, all XDP files available in [!DNL AEM Forms] repository are displayed. Select the appropriate file.

   The selected XDP file gets associated with the Adaptive Form.

   **Generate Document of Record** Select this option to use an XDP file as a base template for defining the styling and appearance for the Document of Record. On selecting this option, all XDP files available in [!DNL AEM Forms] repository are displayed. Select the appropriate file.

   >[!NOTE]
   >
   >Ensure that schema used to create Adaptive Form and schema (data schema) of XFA Form are same if:
   >
   >
   >
   >    * Your Adaptive Form is schema based
   >    * You are using **Associate Form Template as the Document of Record Template** option for Document of Record
   >
   >

1. Click **Done.**

## Customize the branding information in Document of Record {#customize-the-branding-information-in-document-of-record}

While generating a Document of Record, you can change branding information for the Document of Record on the Document of Record tab. The Document of Record tab includes options such as logo, appearance, layout, header and footer, disclaimer, and whether or not you want to include unselected check box and radio button options.

To localize the branding information that you enter in the Document of Record tab, you need to ensure the locale of the browser is set appropriately. To customize the branding information of Document of Record, complete the following steps:

1. Select a panel (root panel) in the Document of Record and then tap ![configure](assets/configure.png).
1. Tap ![dortab](assets/dortab.png). The Document of Record tab appears.
1. Select either the default template or a custom template for rendering the Document of Record. If you select the default template, a thumbnail preview of the Document of Record appears below the Template drop-down.

   ![brandingtemplate](assets/brandingtemplate.png)

   If you choose to select a custom template, browse a select an XDP on your [!DNL AEM Forms] server. If you want to use a template that is not already on your [!DNL AEM Forms] server, you need to first upload the XDP to your [!DNL AEM Forms] server.

1. Based on whether you select a default or a custom template, some or all of the following properties appear in the Document of Record tab. Specify these appropriately:

    * **Logo Image**: You can either choose to use the logo image from the Adaptive Form, choose one from DAM, or upload one from your computer.
    * **Form Title**
    * **Header Text**
    * **Disclaimer Label**
    * **Disclaimer**
    * **Disclaimer Text**
    * **Accent Color**: The color in which header text and separator lines are rendered in the document or record PDF
    * **Font Family**: Font family of the text in the Document of Record PDF
    * **For Check Box and Radio Button components, show only the selected values**
    * **Separator for multiple selected value(s)**
    * **Include form objects that are not bound to data model**
    * **Exclude hidden fields from the Document of Record**
    * **Hide description of panels**

   >[!NOTE]
   >
   >If you are using an Adaptive Form template created with a verision of Designer prior to 6.3, for Accent Color and Font Family properties to work, ensure that the following is present in your Adaptive Form template under the root subform:

   ```xml
   <proto>
   <font typeface="Arial"/>
   <fill>
   <color value="4,166,203"/>
   </fill>
   <edge>
   <color value="4,166,203"/>
   </edge>
   </proto>
   ```

1. To save the branding changes, tap Done.

## Table and column layouts for panels in Document of Record {#table-and-column-layouts-for-panels-in-document-of-record}

Your Adaptive Form may be a lengthy one with several form fields. You may not want to save a Document of Record as an exact copy of the Adaptive Form. Now you can choose a table or column layout for saving one or more Adaptive Form panels in the Document of Record PDF.

Before generating a Document of Record, in a panel's settings, select Layout For The Document of Record for that panel as Table or Column. The fields in the panel get organized accordingly in the Document of Record.

![Fields in a panel rendered in a table layout in the Document of Record](assets/dortablelayout.png)

Fields in a panel rendered in a table layout in the Document of Record

![Fields in a panel rendered in a column layout in the Document of Record](assets/dorcolumnlayout.png)

Fields in a panel rendered in a column layout in the Document of Record

## Document of Record settings {#document-of-record-settings}

Document of Record settings let you choose options you want to include in the Document of Record. For example, a bank accepts name, age, social security number, and phone number in a form. The form generates a bank account number, and branch details. You can choose to display only the name, social security number, bank account, and branch details in Document of Record.

The Document of Record settings of a component are available under its properties. To access the properties a component, select the component and click ![cmppr](assets/cmppr.png) in the overlay. The properties are listed in the sidebar, and you can find the following settings in it.

**Field level settings**

* **Exclude From Document of Record**: Setting the property true excludes the field from Document of Record. This is script-able property named `excludeFromDoR`. Its behavior depends on **Exclude fields from DoR if hidden** form level property.

* **Display panel as table:** Setting the property displays panel as table in Document of Record if panel has less than 6 fields in it. Applicable for panel only.
* **Exclude title from Document of Record:** Setting the property excludes title of the panel/table from Document of Record. Applicable for panel and table only.
* **Exclude description from Document of Record:** Setting the property excludes description of the panel/table from Document of Record. Applicable for panel and table only.

**Form level settings**

* **Include unbound fields in DoR:** Setting the property includes unbound fields from Schema based Adaptive Form in Document of Record. By default it is true.
* **Exclude fields from DoR if hidden:** Setting the property overrides the behavior of “Exclude From Document of Record” field level property when it’s not true. If fields are hidden at the time of form submission, they will be excluded from Document of Record if the property is set true, provided “Exclude From Document of Record” property is not set.

## Key considerations when working with Document of Record {#key-considerations-when-working-with-document-of-record}

Keep in mind the following considerations and limitations when working on Document of Record for Adaptive Forms.

* Document of Record templates do not support rich text. Therefore, any rich text in the static Adaptive Form or in the information filled in by the end user appears as plain text in the Document of Record.
* Document fragments in an Adaptive Form do not appear in the Document of Record. However, Adaptive Form Fragments are supported.
* Content binding in Document of Record generated for XML Schema based Adaptive Form is not supported.
* Localized version of Document of Record is created on demand for a locale when the user requests the rendering of the Document of Record. Localization of Document of Record occurs along with localization of Adaptive Form. <!-- For more information on localization of Document of Record and Adaptive Forms see Using AEM translation workflow to localize Adaptive Forms and Document of Record.-->
