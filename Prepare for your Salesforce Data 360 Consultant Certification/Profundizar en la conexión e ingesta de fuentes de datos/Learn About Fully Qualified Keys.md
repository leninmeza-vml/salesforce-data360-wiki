# Learn About Fully Qualified Keys

## Learning Objectives

After completing this unit, you’ll be able to:

*   Identify the purpose of keys and when to use them.  
    
*   Learn about fully qualified keys.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

As of October 14, 2025, Data Cloud has been rebranded to Data 360. During this transition, you may see references to Data Cloud in our application and documentation. While the name is new, the functionality and content remains unchanged.

## Keys to Unlock Your Data

Data 360 is a powerful tool that uses a standard data model, called the Customer 360 Data Model. To use Data 360 you must map your data to the standard data model objects (DMOs) found in the Customer 360 Data Model. When mapping your data to DMOs, you use keys to help connect your data to other data. Let’s review the types.

*   **Primary keys:** A primary key is the field or attribute that uniquely identifies each record in a dataset.  
    
*   **Foreign keys:** These are additional keys that link to the primary key of a different dataset.  
    

For example, in a sales order dataset, there’s a product ID that corresponds to the item purchased. This product ID links to a separate table with more details about that product, such as color or size. The instance of product ID on the sales order details dataset is the foreign key, and the instance of product ID on the product dataset is the primary key.

Each data stream is ingested into Data 360 with its specific keys and attributes. So if you have primary and foreign keys, what is a key qualifier? When multiple data streams are harmonized into a single data model object (DMO), the various keys can conflict and records can have the same key values. That’s where fully qualified keys come in. Fully qualified keys (FQKs) are used to avoid key conflicts when data from different sources are ingested and harmonized in Data 360. In this module, you learn what fully qualified keys are, how they’re created, and some best practices for their use.

## About Fully Qualified Keys

A fully qualified key consists of a source key (for example, the identifier-contact ID) and a key qualifier (for example, the source-CRM).

![Fully Qualified Keys are created by adding a Source Key and a Key Qualifier.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/fully-qualified-keys-in-data-cloud-quick-look/learn-about-fully-qualified-keys/images/4e1772f68fb56c035f5187227f60dcdd_kix.tfxnt0vhm4ka.png)

Configure key qualifier fields for all data lake object (DLO) fields that contain a key value. The field can be a primary key or a foreign key field.

Let’s look at an example to see how harmonized data is interpreted with and without key qualifiers.

Say you have two data streams with related data lake objects (DLO) for profile data: Contacts DLO from Salesforce CRM and Subscribers DLO from Salesforce Marketing Cloud. The records for these DLOs are mapped to the Individual DMO.

Now, you want to join the Individual DMO to the Engagement DMO to identify individuals with a minimum of two clicks. After harmonization of data, the two data streams are mapped to the Individual DMO in Data 360. The Contacts DLO has three records, and the Subscribers DLO has two records. So the Individual DMO, which contains all the records from all the mapped data streams, has five records.

Marketing Cloud uses the Contact ID from the CRM org as the primary key (Subscriber Key). So there are multiple records in the Individual DMO with the same value for Individual ID, which is the primary key field.

![Diagram for an Individual DMO with columns for Individual ID and First Name. The first 3 rows are from a Contacts DLO and the last 2 rows are from a Subscribers DLO.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/fully-qualified-keys-in-data-cloud-quick-look/learn-about-fully-qualified-keys/images/28ea783d759f0d9d99bb1aa0659b6ca4_kix.yjxtzorea2ha.png)

Next, let’s consider the Email Engagement DMO, which contains email engagement data that was ingested from Salesforce Marketing Cloud. The Individual DMO and Email Engagement DMO have a 1:N relationship through the Individual ID. When you join the Individual DMO and the Email Engagement DMO, Data 360 interprets the combined data set as the first row of Individual 2 having one click and the second row of Individual 2 having one click.

In other words, Individual 2 is assumed to have two email clicks. But in actuality, Individual 2 has only one click action, although Data 360 interprets it as two click actions. This misinterpretation can create an issue when this data is queried, including segmentation, calculated insights, and query API. If you run a query and ask for individuals who have a minimum of two click actions, Individual 2 is returned in the response. This issue occurs even when profile unification is deployed, because engagement data is always joined to the Individual DMO.

![Diagram building from previous one with two rows selected from the Individual DMO chart, pointing to a row E2 in another DMO called Email Engagement.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/fully-qualified-keys-in-data-cloud-quick-look/learn-about-fully-qualified-keys/images/b2230c98f0d66a006a814536b3ebc006_kix.vrzugqh1z2xf.png)

When you add key qualifier fields to all your DLO fields that contain a key value, either a primary key or a foreign key, Data 360 interprets the data ingested from different data sources correctly. In this example, key qualifiers are added to the DLOs from Salesforce CRM and Marketing Cloud. The Individual DMO includes the key qualifier field indicating where the record was sourced from.

![The Individual DMO with a key qualifier column added to show the data source.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/fully-qualified-keys-in-data-cloud-quick-look/learn-about-fully-qualified-keys/images/b0ba5b4a2b3f7d20d94bf7b642eb9a1e_kix.sdvxc8oer1sb.png)

When the Individual DMO and Email Engagement DMO are joined, the table join uses both the foreign key field (Individual ID) and the key qualifier field (KQ\_ID). This helps Data 360 interpret the data accurately.

## Configure a Key Qualifier

It’s advised to configure key qualifiers for all fields that contain a primary or foreign key. After creating a data stream, add key qualifiers to your data lake object (DLO) fields to create fully qualified keys (FQK). This can be done in the Data Lake Objects tab by finding the DLO and the field and selecting to add a key qualifier. You can also view existing key qualifiers from the Data Lake Object tab.

Creating fully qualified keys helps you avoid key conflicts when harmonizing data from different sources in Data 360. It ensures that each record has a unique identifier, preventing misinterpretation of data, and ensuring accurate query results. And accurate data helps you feel more confident about data-driven decisions!

## Resources

*   [_Salesforce Help_: Fully Qualified Keys](https://help.salesforce.com/s/articleView?id=data.c360_a_fully_qualified_keys.htm&type=5)
*   [_Salesforce Help_: Data 360 Glossary of Terms](https://help.salesforce.com/s/articleView?id=data.c360_a_glossary_guide.htm&type=5)
*   [_Salesforce Help_: Best Practices for Fully Qualified Keys](https://help.salesforce.com/s/articleView?id=data.c360_a_key_qualifier_best_practices.htm&type=5)

---

Preguntas:

**Pregunta 1:** ¿Cuáles son los componentes de una fully qualified key?

✅ **C — Source and key qualifier** (Fuente y calificador de clave)

El documento lo indica claramente: *"A fully qualified key consists of a source key (for example, the identifier-contact ID) and a key qualifier (for example, the source-CRM)."*

---

**Pregunta 2:** ¿Cuál es el propósito de un key qualifier en Data 360?

✅ **A — To help accurately interpret data from different sources** (Ayudar a interpretar con precisión los datos de diferentes fuentes)

El documento lo explica con el ejemplo del Individual DMO y el Email Engagement DMO: al agregar key qualifiers, Data 360 puede interpretar correctamente los datos provenientes de distintas fuentes y evitar conflictos de claves.