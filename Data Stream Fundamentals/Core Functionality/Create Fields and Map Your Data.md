### Estimación de tiempo

**15** minutos aproximadamente

### Temas

- [Create Fields and Map Your Data](#create-fields-and-map-your-data)
  - [Learning Objectives](#learning-objectives)
  - [Create a Formula Field](#create-a-formula-field)
  - [Harmonize and Map](#harmonize-and-map)
    - [Map Case to a Data Model Object](#map-case-to-a-data-model-object)
  - [Verify Your Work](#verify-your-work)
  - [Resources](#resources)
  - [Parte 1: Crear un Formula Field](#parte-1-crear-un-formula-field)
  - [Parte 2: Mapear Lead\_Home](#parte-2-mapear-lead_home)
  - [Parte 3: Mapear Case\_Home](#parte-3-mapear-case_home)
  - [Parte 4: Mapear CaseHistory2\_Home](#parte-4-mapear-casehistory2_home)

## ¿Necesita ayuda?

[Preguntar a la comunidad](/es/trailblazer-community/topics/trailheadchallenges?sort=LAST_MODIFIED_DATE_DESC&search=Create%20Fields%20and%20Map%20Your%20Data&ref=unit)

El tiempo aproximado de espera para que responda el equipo de ayuda o la comunidad es de entre **24 y 48** horas.

[Compartir comentarios](https://help.salesforce.com/services/auth/sso/trailheadlogincommunity?startURL=%2Fs%2Fcase-submission%3FtopicId%3Da6CAE0000003qPO2AY_en_US_P%26badgeName%3Dcreate-fields-and-map-your-data&language=es)

#### Recursos de Data 360

[Ver Data 360 en acción](https://salesforcedatacloud.hubs.vidyard.com/?d=701ed000001S6ujAAC)

[Más información sobre Data 360](https://www.salesforce.com/es/data/?d=701ed000001SBEVAA4)

Caduca el 14/3/2026 a las 6:00 p. m. GMT-6

### Su Playground Data Cloud está listo.

Ya puede practicar en esta insignia y con cualquier otra que requiera un Playground Data Cloud. Si el tiempo se agota, perderá el acceso a este Playground. Puede volver a solicitarlo, pero es posible que tenga que volver a empezar.

Iniciar

# Create Fields and Map Your Data

## Learning Objectives

In this step, you’ll:

- Create a formula field.
- Add a custom field to a data model object.
- Map fields to the Customer 360 Data Model.

## Create a Formula Field

When you create a Data 360 data stream, you can choose to generate more fields, called formula fields, either during data stream creation or after. These optional fields are helpful when you want to standardize data formatting, update unique identifiers, or add flags for data that meet criteria.

For this project, you create a formula field to identify leads that are located in the United States, based on the data found in the Country field of the Lead data lake object (DLO). 

1. From the Data Stream tab, locate and click the **Lead\_Home** data stream that you created.
2. From the Lead\_Home data stream record, select the **New Formula Field** from the options at the top of the screen.
3. For Field Label, name your field `Is US BasedCopiar`.
4. Confirm the Field API Name is `Is_US_BasedCopiar`.
5. For Formula Return Type, select **Text**.
6. Enter this formula in the **Transformation Formula** field:

IF(UPPER(sourceField\['Country']) == "USA" || UPPER(sourceField\['Country']) == "UNITED STATES", "TRUE" , "FALSE")

![New formula field screen](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/create-fields-and-map-your-data/images/843c9d617ef7c27d36d2971eec36cf55_kix.x5nbs91gp2ap.jpg)

7. Validate the formula using the **Tested Value** panel:

<!--THE END-->

- - Type `JapanCopiar` into the country field and then click **Test**.
  - Output will show FALSE.
  - Type `USACopiar`and then click **Test**.
  - Output will show TRUE.

<!--THE END-->

8. Once you have successful validation, click **Save**.

## Harmonize and Map

Once DLOs are created, fields from those DLOs need to map to data model objects (DMOs) found in the Customer 360 Data Model, Data 360 standard canonical data model. DMOs help organize Data 360 data. If using starter data bundles to create your data streams, many mappings are prepopulated for you. However, custom fields and some additional fields that are required for unification need to be manually mapped. Since you added a new custom formula field (and often businesses have other standard and custom objects in their data sources), this field needs to be manually mapped to the Customer 360 Data Model.

1. From the data stream, **Lead\_Home** page, click **Review** in the Data Mapping section.

On one side of the screen are the searchable data lake objects (1). On the other side, are the searchable DMOs (2) (called Data Model entities in-app). To search for a field within a DLO, use the DLO search bar (3) in this case, use Lead\_Home. 

![DLO mapping screen for the Lead data stream.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/create-fields-and-map-your-data/images/a2bc0d32acd9499d0e068027454e5a76_kix.gfcg6zkpzze1.jpg)

You need to create a new DMO field and then map it to your new formula field.

2. Under Data Model entities, scroll to the **Lead** section and under Unmapped, click **Add New Field**. You might need to scroll down to the Lead section to find the unmapped category and expand the options.

<!--THE END-->

![Add New Field link.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/create-fields-and-map-your-data/images/cdb49ea6e905b2c1d414ae9021c08559_kix.52807pdkwfot.png)

3. Name the Field, `Is US BasedCopiar` and select **Text** as the Data Type. Keep the Enable Value Suggestion box unchecked.
4. Click **Save**.
5. Now under the Data Lake Object, Lead\_Home, search for the unmapped field **Is US Based**.
6. Select **Is US Based**.
7. Under Data Model entities, scroll to the Lead section and under Unmapped select the newly created **Is US Based** custom field.
8. After a line is drawn to connect the two fields, click **Save**.

Now let’s map a field that is required for unification, formatted phone number.

1. Now locate **Phone** under the Lead\_Home search box. Notice that it’s already mapped to Telephone Number. You also need to map it to Formatted E164 Phone Number.
2. Click **Phone** to select it and then locate Formatted E164 Phone Number from the Unmapped section of Contact Point Phone.
3. Select **Formatted E164 Phone Number**.
4. After a line is drawn to connect the two fields, click **Save &amp; Close**.

### Map Case to a Data Model Object

Since you didn’t add the Case objects using a bundle, no mappings have been created. Let’s map these fields so they can be used in later insights and segments.

1. On the Case\_Home data stream, in the Data Mapping section, click **Start**.

<!--THE END-->

![Data Mapping Start button.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/create-fields-and-map-your-data/images/34f6976641e5ae24f7cbe1b6739d8ee6_kix.efjd9qan038.jpg)

2. From the Data Model entities area, click **Select Objects**. This can take some time to load.
3. Search for `CaseCopiar` in the Search field.
4. Click the **+** icon to add the Case standard object. If the **+** icon didn’t turn green, click it again.

<!--THE END-->

![Map Case objects by clicking the plus button to automatically map some fields. It becomes a green checkmark when selected.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/create-fields-and-map-your-data/images/e4b25608adc16f25005687721daf3633_kix.1tr39y7tx2m4.jpg)

5. Click **Done**.  
   This automatically maps several fields.
6. There are more fields to map. Search for these fields in Case\_Home and then map to the corresponding unmapped fields in the Case DMO.

<!--THE END-->

- - **Status** to **Case Status**
  - **Account Id** to **Account**
  - **Contact Id** to **Individual**

<!--THE END-->

7. Click **Save &amp; Close**.

**Map Case History**

Next, repeat these steps to map Case History to Case Update.

1. On the CaseHistory2\_Home data stream, in the Data Mapping section, click **Start**.
2. From the Data Model entities area, click **Select Objects**. This may take some time to load.
3. Search for `Case UpdateCopiar` in the Search field.
4. Click the **+** icon to add the Case Update standard objects and then **Done**.
5. Map these additional fields.
   
   - **CaseHistory2 ID** to **Case Update Id** (Primary Key)
   - **Case ID** to **Case**
   - **Owner ID** to **Related Owner**
   - **Last Modified By ID** to **Last Modified By**
   - **Previous Update** to **Previous Update Date**
6. Click **Save &amp; Close**.

## Verify Your Work

Now that you have completed these steps in your Developer Org, click **Verify Step** to check your work before moving to the next step in the project. This check will verify that you’ve created a custom DMO field and mapped it to your new formula field. We’ll also check that you have created the mappings for Case and Case History.

## Resources

- [*Salesforce Help*: Data Mapping](https://help.salesforce.com/s/articleView?id=data.c360_a_data_mapping.htm&type=5)
- [*Salesforce Help*: Supported Library Functions](https://help.salesforce.com/s/articleView?id=data.c360_a_supported_library_functions.htm&type=5)

---

## Parte 1: Crear un Formula Field

1. Ve a **Data Streams** → clic en **Lead_Home**
2. Clic en **New Formula Field**
3. Completa los campos:
   - **Field Label:** `Is US Based`
   - **Formula Return Type:** Text
   - **Transformation Formula:**
     ```
     IF(UPPER(sourceField['Country']) == "USA" || UPPER(sourceField['Country']) == "UNITED STATES", "TRUE" , "FALSE")
     ```
4. Prueba la fórmula:
   - Escribe `Japan` → debe mostrar **FALSE**
   - Escribe `USA` → debe mostrar **TRUE**
5. Clic en **Save**

---

## Parte 2: Mapear Lead_Home

1. En **Lead_Home** → sección Data Mapping → clic en **Review**
2. En Data Model entities, busca la sección **Lead** → Unmapped → **Add New Field**
   - Nombre: `Is US Based`, tipo: **Text** → **Save**
3. En el lado izquierdo busca **Is US Based** en Lead_Home → selecciónalo
4. En el lado derecho selecciona el campo **Is US Based** recién creado → **Save**
5. Ahora busca **Phone** en Lead_Home → ya está mapeado a Telephone Number
6. Selecciona **Phone** nuevamente → mapéalo también a **Formatted E164 Phone Number** (sección Unmapped de Contact Point Phone) → **Save & Close**

---

## Parte 3: Mapear Case_Home

1. Ve a **Case_Home** → Data Mapping → **Start**
2. Clic en **Select Objects** → busca `Case` → clic en **+** (debe volverse verde) → **Done**
3. Mapea manualmente:
   - **Status** → **Case Status**
   - **Account Id** → **Account**
   - **Contact Id** → **Individual**
4. **Save & Close**

---

## Parte 4: Mapear CaseHistory2_Home

1. Ve a **CaseHistory2_Home** → Data Mapping → **Start**
2. **Select Objects** → busca `Case Update` → clic en **+** → **Done**
3. Mapea manualmente:
   - **CaseHistory2 ID** → **Case Update Id** (Primary Key)
   - **Case ID** → **Case**
   - **Owner ID** → **Related Owner**
   - **Last Modified By ID** → **Last Modified By**
   - **Previous Update** → **Previous Update Date**
4. **Save & Close**

---
