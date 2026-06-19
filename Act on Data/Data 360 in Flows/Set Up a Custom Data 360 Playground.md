# Set Up a Custom Data 360 Playground

## Learning Objectives

After completing this unit, you’ll be able to:

*   Sign up for a custom Data 360 Playground.  
    
*   Configure the playground for use with this badge.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

We highly recommend that you have a good level of knowledge of flows and Data 360 before you work on this badge. To learn about flows, complete the [Build Flows with Flow Builder](https://trailhead.salesforce.com/content/learn/trails/build-flows-with-flow-builder) trail. To learn about Data 360, complete the [Unlock Your Data with Data Cloud](https://trailhead.salesforce.com/users/strailhead/trailmixes/unlock-your-data-with-data-cloud) trailmix.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

As of October 14, 2025, Data Cloud has been rebranded to Data 360. During this transition, you may see references to Data Cloud in our application and documentation. While the name is new, the functionality and content remains unchanged.

Data 360 connects and harmonizes all your data in one place. This includes external data such as your company website, mobile app, end-user products, and internal data from your Salesforce org.

But that data, even if it’s been cleaned, mapped, and harmonized, isn’t useful if you can’t do anything with it. Fortunately, the Salesforce declarative automation tool, Flow Builder, can access your Data 360 data. This access gives you the ability to create powerful interactive or triggered automation that uses that data. You can even trigger a flow from changes made to the data in Data 360.

## Get Ready to Get Hands-On

Before you start creating flows that interact with Data 360, complete the following three steps to set up your playground.

### Sign Up for a Custom Playground with Data 360

To complete this module, you need a custom playground that contains Data 360 and our sample data.

1.  Click **Create Playground**.  
    
2.  Your new org is automatically attached to your Trailhead account!  
    
3.  Make note of your org's expiration date and complete this badge before then.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

This custom playground is designed to work with the challenges in this badge, and may not work for other badges. Always check that you’re using the playground or special Developer Edition org that we recommend.

### Create Data Streams from a Data Kit

The custom playground has a lot of configuration already done for you, but there’s a few steps you need to complete before you can proceed. First, let’s create the data streams and their mappings.

1.  If you haven’t already launched your Data 360 playground, do that now.  
    
2.  Click the **App Launcher** ![](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-in-flows/set-up-a-custom-data-cloud-playground/images/5716869dd86823e5674ad95141e7f2f5_kix.1xun7hsd1c6n.png), type `dataCopiar`, then click the **Data Cloud** app.  
    
3.  Click the **Data Streams** tab.  
    
4.  Click **New**.  
    
5.  Click **Salesforce CRM**.  
    

![The Salesforce CRM button reads: Import objects from Salesforce CRM.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-in-flows/set-up-a-custom-data-cloud-playground/images/b801e098a271c8d6d4e7a898f18f05f4_kix.jr5s6mncslj.png)

6.  Click **Next**.  
    
7.  Click the **DataCloudFlows** Custom Data Bundle.  
    
8.  Click **Next**.  
    Notice that the default Data Space is pre-selected and all the fields included in the bundle are listed.  
    
9.  Leave the current selections and click **Next**.  
    
10.  Click **Deploy**.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

If you get an error when you click Deploy, it’s likely that the data streams were actually created successfully. Close the New Data Stream window and refresh the page to see your new data streams.

You may notice that all of your dev org’s Data 360 data comes from a Salesforce CRM source, connected to the same org. Unfortunately, we can’t set up external data sources for you. Instead, we created Salesforce objects that simulate external objects, with data streams and mappings to make these data structures appear as data model objects (DMOs) in Data 360. The steps in these exercises work with data streaming from truly external databases as well.

### Create a Calculated Insight

Next, create a calculated insight that counts the records in one of the org’s external objects.

1.  Click the **Calculated Insights** tab.  
    
2.  Click **New**.  
    
3.  Select **From a Data Kit** and click **Next**.  
    
4.  Select **Number of Abandoned Carts** and click **Next**.  
    
5.  Click **Activate**.  
    
6.  For Schedule, select **Not Scheduled**, and click **Enable**.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

If you get an error when you click Enable, it’s likely that the calculated insight was actually created successfully. Close the Select a Data Kit window and the New Insight window, then refresh the page to see your new calculated insight.

7.  On the new Number of Abandoned Carts calculated insight page, click ![](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-in-flows/set-up-a-custom-data-cloud-playground/images/72397ddf05b5e75cf961575144ef3986_kix.a2uvuh8ikh0.png), then click **Publish Now**.  
    You may have to refresh the page to see the Publish Now option.  
    

![The Publish Now option on a calculated insight page.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-in-flows/set-up-a-custom-data-cloud-playground/images/a4e19a7bcc94931ab670b6dc59b25ff0_kix.ggwz2uecgp74.png)

Your special Data 360 org is now ready to go! Before we start building flows in this org, let’s review some Data 360 concepts that are key to working with flows.

## How Flows Interact with Data 360

Let’s talk about some important parts of Data 360, what they do, and how they interact with flows.

### Data Lake Objects

Data lake objects (DLOs) are storage containers for the raw data that data streams bring into Data 360. In these objects, the data remains in unaltered form but can be referenced by the rest of Data 360. Flows can’t access data in DLOs.

### Data Model Objects

After Data 360 maps, harmonizes, or transforms your DLO data, it makes the data available through data model objects (DMOs). In other words, data in DMOs has gone through all the processes that you’ve defined to make that data useful. Most of the data that’s accessible in flows is found in DMOs. Here are some examples of what a DMO might contain.

*   Data from a Salesforce org  
    
*   Data from an external database  
    
*   Transformed, filtered, or aggregated data  
    
*   Formula fields based on source data  
    
*   Unified identity information compiled from multiple sources  
    

### Calculated Insights and Calculated Insight Objects

Calculated insights consist of a SQL (Structured Query Language) query and the complex metrics that the query returns. When you activate a calculated insight, Data 360 creates a calculated insight object (CIO) to store the values returned by the SQL query. Data 360 runs the query on a schedule and updates the CIO’s records when the query’s results change. For most Data 360 purposes, the CIO isn’t very visible. But when you access calculated insight results with Flow Builder, you interact with the CIO just like you do with any other object.

![“Data 360 diagram corresponding to the preceding descriptions. Flows can access the data in DMOs and calculated insights.”](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-in-flows/set-up-a-custom-data-cloud-playground/images/c1ae11704262aa82b99e7232b5104511_kix.132ekfvym8cc.png)

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

For more information on creating calculated insights, check out the [Enhance Data in Data Cloud](https://trailhead.salesforce.com/content/learn/trails/enhance-data-in-customer-data-platform) trail in Trailhead.

## Resources

*   [_Salesforce Help_: Data 360 Glossary of Terms](https://help.salesforce.com/s/articleView?id=data.c360_a_glossary_guide.htm&type=5)
*   [_Trailhead_: Build Flows with Flow Builder](https://trailhead.salesforce.com/content/learn/trails/build-flows-with-flow-builder)
*   [_Trailhead_: Unlock Your Data with Data Cloud](https://trailhead.salesforce.com/users/strailhead/trailmixes/unlock-your-data-with-data-cloud)

## Reto práctico
Aquí está la guía completa para resolver el reto:

---

# Guía: Configurar el Playground de Data 360 para Flows

## Paso 1 — Crear el Playground

1. Haz clic en **"Create Playground"** en Trailhead
2. Tu org se adjunta automáticamente a tu cuenta
3. Anota la **fecha de expiración** y completa la insignia antes de esa fecha
4. Haz clic en **"Launch"** para abrir el org

---

## Paso 2 — Crear los Data Streams desde un Data Kit

1. En el **App Launcher** busca y selecciona `data` → haz clic en **"Data Cloud"**
2. Ve a la pestaña **"Data Streams"** → clic en **"New"**
3. Selecciona **"Salesforce CRM"** → clic en **"Next"**
4. Selecciona el bundle **"DataCloudFlows Custom Data Bundle"** → clic en **"Next"**
5. Verifica que el **Data Space** por defecto esté preseleccionado
6. Deja todas las selecciones como están → clic en **"Next"**
7. Clic en **"Deploy"**

> ⚠️ Si aparece un error al hacer Deploy, es probable que los data streams **sí se crearon**. Cierra la ventana y refresca la página para verificarlo.

---

## Paso 3 — Crear el Calculated Insight

1. Ve a la pestaña **"Calculated Insights"** → clic en **"New"**
2. Selecciona **"From a Data Kit"** → clic en **"Next"**
3. Selecciona **"Number of Abandoned Carts"** → clic en **"Next"**
4. Clic en **"Activate"**
5. En Schedule selecciona **"Not Scheduled"** → clic en **"Enable"**

> ⚠️ Si aparece un error al hacer Enable, el calculated insight probablemente **sí se creó**. Cierra las ventanas y refresca la página.

---

## Paso 4 — Publicar el Calculated Insight

1. En la página del calculated insight **"Number of Abandoned Carts"**
2. Haz clic en la **flecha desplegable ↓**
3. Selecciona **"Publish Now"**

> 💡 Si no ves la opción "Publish Now", **refresca la página** primero.

---

## Paso 5 — Verificar la configuración

Confirma que tienes:
- ✅ Data Streams creados y en status **Active**
- ✅ Calculated Insight **"Number of Abandoned Carts"** creado y publicado

---

## Paso 6 — Verificar en Trailhead

Regresa a Trailhead y haz clic en **"Check Challenge"** para ganar los **500 puntos**. 🎉

---

> 💡 **Conceptos clave a recordar para los siguientes pasos:**
> - Los **Flows NO pueden acceder** a Data Lake Objects (DLOs)
> - Los **Flows SÍ pueden acceder** a Data Model Objects (DMOs) y Calculated Insights
> - Los Calculated Insight Objects (CIOs) se comportan como cualquier otro objeto en Flow Builder

Veo que los Data Streams ya están creados y activos. Ahora necesitas crear el Calculated Insight. Aquí te muestro cómo acceder:

---

## Cómo crear "Number of Abandoned Carts"

### 1. Ve a Calculated Insights
Haz clic en **"Calculated Insights"** en el menú superior de Data Cloud

### 2. Crear nuevo
Haz clic en **"New"**

### 3. Seleccionar From a Data Kit
- Selecciona **"From a Data Kit"** → clic en **"Next"**

### 4. Buscar el insight
- Busca y selecciona **"Number of Abandoned Carts"**
- Clic en **"Next"**

### 5. Activar
- Clic en **"Activate"**
- En Schedule selecciona **"Not Scheduled"**
- Clic en **"Enable"**

### 6. Publicar
- En la página del calculated insight
- Haz clic en la **flecha ↓**
- Selecciona **"Publish Now"**

---

## Si no ves "Calculated Insights" en el menú

Puede estar oculto en **"More"** (el menú desplegable al final de la barra de navegación). Haz clic ahí y búscalo.

---

¿Puedes ver la opción **"Calculated Insights"** en tu menú de navegación? Comparte una captura si no aparece. 🔍

El error "Unable to create DataKitComponentTemplateMap record" es común en este paso. Según el documento del módulo, este error generalmente significa que el calculated insight **sí se creó correctamente** a pesar del mensaje.

---

## Pasos a seguir

### 1. Cierra las ventanas de error
- Haz clic en la **X** del error
- Haz clic en **"Previous"** o cierra la ventana del Data Kit

### 2. Refresca la página
- Presiona **F5** o **Cmd+R**

### 3. Ve a Calculated Insights
- Haz clic en **"Calculated Insights"** en el menú
- Busca **"Number of Abandoned Carts"**
- Si aparece en la lista, ¡el insight sí se creó! ✅

### 4. Publicar el insight
Si el insight existe:
1. Haz clic en él para abrirlo
2. Haz clic en la **flecha ↓** (dropdown)
3. Selecciona **"Publish Now"**
4. Espera a que complete

### 5. Verificar en Trailhead
Una vez publicado, regresa a Trailhead y haz clic en **"Check Challenge"**

---

> 💡 El documento indica explícitamente: *"If you get an error when you click Enable, it's likely that the calculated insight was actually created successfully."*

¿Aparece **"Number of Abandoned Carts"** en tu lista de Calculated Insights? 🔍

