# Create a Data Graph

### Learning Objectives

After completing this unit, you’ll be able to:

*   Create a data graph.  
    
*   Explain the role of the primary data model object (DMO) in building a data graph.  
    
*   Perform key actions with data graphs, such as adding related objects.  
    

## Sign Up for a Developer Edition with Data 360

Now that you’re familiar with the concepts and terms you see in this project, click **Create Playground** to receive a special, limited-time custom playground that includes Data 360 and our sample data. Once your org is created (this can take some time), look for an email entitled “Finish resetting your Salesforce password” from support@salesforce.com.

*   From the email, find and save your username (1).  
    
*   Click the link (2) to reset your password.  
    

![Reset password image with callouts on username and the link that needs to be clicked to reset.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-graphs-in-data-cloud/create-a-data-graph/images/dcd0f102c2ac274676896488eb6193d3_kix.64hrl01bkoqq.jpg)

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

This Developer Edition is designed to work with the challenges in this badge, and might not work for other badges. Always check that you’re using the Trailhead Playground or special Developer Edition org that we recommend. 

## Connect Your Developer Edition Org to Trailhead

1.  Make sure you’re logged in to your Trailhead account.  
    
2.  Click **Connect Playground**.  
    
3.  On the login screen, enter the username and password for the Developer Edition you just set up.  
    
4.  On the Allow Access? screen, click **Allow**.  
    
5.  On the _”_Want to connect this org for hands-on challenges?” screen, click **Yes! Save it.** You are redirected to the challenge page and ready to use your new Developer Edition to earn this badge.  
    

This project requires access to a special Developer Edition that includes Data 360. These Developer Editions are only available for a limited time—**be sure to complete this project before your org expires.** 

## Create a Data Stream

Before you can ingest data into Data 360, a user first needs to configure any data source that you’d like to connect. For this project, we’ve already connected a Sales Cloud and Service Cloud org to your Developer org. Since these data source connections are already established, you can now add data streams to Data 360. 

1.  After logging in to your Developer Org, go to Data Cloud from the App Launcher ![grid icon](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-graphs-in-data-cloud/create-a-data-graph/images/2c16a9f460ebab0b9baab01c8dd3be41_kix.uy2c70uc459u.jpg) and search for and select `Data CloudCopiar`.  
    

![App launcher icon with Data 360 in the Apps.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-graphs-in-data-cloud/create-a-data-graph/images/5cbf6791d6380bc327474a5f4f4c1985_kix.ms3e7nmt1gxd.png)

2.  In Data Cloud, go to the **Data Streams** tab and click **New**.  
    
3.  Click **Salesforce CRM** under Connected Sources**,** and click **Next**.  
    
4.  Note the Salesforce Org is preselected. From View Bundles, choose the **Sales** data bundle and click **Next**.  
    

![New Data Stream screen with the Sales Data Bundle selected.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-graphs-in-data-cloud/create-a-data-graph/images/6783467dd182669228b59ff5a74c2a43_kix.y6bqy9f7imln.jpg)

5.  View the associated fields and click **Next**.  
    
6.  Notice that the default Data Space is preselected and all the fields included in the bundle are listed. Leave the selections as is, and click **Deploy**.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

This can take a few moments to process. If you run into any issues, wait a few minutes and then return to these steps. 

## Create a Data Graph in Data 360

Before you begin building your data graph, you must select a primary DMO. The primary DMO acts as the core object and other related DMOs are linked to it. The primary DMO belongs to the Profile category, and you can add other related DMOs that are associated with it.

1.  In Data Cloud, under the **More** menu option, select **Data Graph**s.  
    
2.  Click **New**.  
    
3.  Click **Start from Scratch**.  
    
4.  On the New Data Graph screen, in the Data Graph Name section, enter `my_test_dgCopiar`. The Data Graph API Name section is automatically populated to my\_test\_dg.  
    
5.  From the Data Space dropdown, leave **default** as the selection.  
    
6.  From the Primary Data Model Object section, click the ![Search icon](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-graphs-in-data-cloud/create-a-data-graph/images/3fa47e4765a17c1e996c61105bf7972a_kix.u7zps0w6o7v2.png) and select **Individual** and click **Next**.  
    
7.  Select these fields from the primary DMO to include in the data graph:  
    *   **Birth Date**  
        
    *   **Created Date**  
        
    *   **First Name**  
        
    *   **Last Name**  
        
8.  To add related objects, click the **+** button next to the Individual Data Model Object. (you can also do this by using the search field) and select **Contact Point Address**.  
    

![+ icon to create a new data graph in Data 360.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-graphs-in-data-cloud/create-a-data-graph/images/896f4997bdfec83fc8dfa77adad9c6b4_kix.oepn43t54207.png)

10.  Next to Contact Point Address, click the **+** button and select **Account Contact**.  
    
11.  For Account Contact, select the following Field Label/Name:  
    *   **Account**  
        
    *   **Contact Email**  
        
    *   **Last Activity Date**  
        
12.  Click **Save and Build**.  
    
13.  From the available refresh intervals, select **Weekly**. For cost savings or if frequent updates aren’t critical, consider a less frequent refresh.  
    
14.  Click **Save and Build**.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

You can select the fields for each related object that you want to include in your graph. If multiple paths exist to reach a DMO, choose the most appropriate path. Longer paths add more levels to your graph.

That’s it! Your new data graph, my\_test\_dg is listed in the Data Graphs page. Once the Last Run Status column displays Active, you are ready to check the challenge.

If you don’t want to build your data graph from scratch, you can create a data graph using a data kit. A data kit provides prebuilt data graphs that are easy to deploy and customize. Changes to data graphs within a data kit don’t affect the original data kit, so you can deploy and modify these graphs with minimal impact.

Data graph creation can take between 15 minutes to several hours, depending on the size and complexity of the primary DMO and related objects. You can track the status of your data graph creation on the Data Graphs tab.

Now you’ve seen how to build a data graph in Data 360. You created a graph from scratch, selected a primary data model object, and added related objects and fields. You also learned how to refresh and manage your graph so it stays up to date. With these skills, you can start modeling customer data in a way that highlights key relationships and makes it easier to explore and analyze.

## Verify Your Data Graph in Data 360

Once you have completed all the above steps in your Developer org and your data graph is active (and not in Processing or Creating status), you can check your work by selecting the Check Challenge.

## Resources

*   [_Salesforce Help_: Create a Data Graph from a Data Kit](https://help.salesforce.com/s/articleView?id=data.c360_a_create_a_data_graph_data_kit.htm&type=5)

## Reto práctico

+500 puntos

### Prepararse

Completará esta unidad en su propio Playground Data Graphs in Data Cloud.

### Su reto

It’s time for you to check your work. Please make sure you have followed all the steps above and click Check Challenge to Earn 500 Points and move on the final unit.

Caduca el 3/4/2026 a las 6:00 p. m. GMT-6

### Su Playground Data Graphs in Data Cloud está listo.

Ya puede practicar en esta insignia y con cualquier otra que requiera un Playground Data Graphs in Data Cloud. Si el tiempo se agota, perderá el acceso a este Playground. Puede volver a solicitarlo, pero es posible que tenga que volver a empezar.

Iniciar

Validar reto para ganar 500 puntos

Aquí está la guía completa paso a paso:

---

# Guía: Crear un Data Graph en Data 360

## Paso 1 — Configurar el Playground

1. Haz clic en **"Create Playground"** en Trailhead
2. Revisa tu correo de `support@salesforce.com`
3. Guarda tu **nombre de usuario**
4. Haz clic en el enlace del correo para **resetear tu contraseña**
5. Regresa a Trailhead → **"Connect Playground"** → inicia sesión → **"Allow"** → **"Yes! Save it"**

---

## Paso 2 — Crear un Data Stream

1. En Salesforce, abre el **App Launcher** y busca `Data Cloud`
2. Ve a la pestaña **Data Streams** → clic en **"New"**
3. Selecciona **Salesforce CRM** → clic en **"Next"**
4. En **View Bundles**, selecciona **Sales data bundle** → clic en **"Next"**
5. Revisa los campos (déjalos por defecto) → clic en **"Next"**
6. Verifica que el **Data Space** sea `default` → clic en **"Deploy"**

> ⏳ Espera unos minutos a que procese antes de continuar.

---

## Paso 3 — Crear el Data Graph desde cero

1. En Data Cloud, haz clic en el menú **"More"** → selecciona **"Data Graphs"**
2. Haz clic en **"New"**
3. Selecciona **"Start from Scratch"**
4. En **Data Graph Name** escribe exactamente: `my_test_dg`
   - El **API Name** se llena automáticamente
5. En **Data Space** deja seleccionado: `default`
6. En **Primary Data Model Object** haz clic en el ícono de búsqueda → selecciona **"Individual"** → clic en **"Next"**

---

## Paso 4 — Seleccionar campos del DMO principal

Selecciona estos 4 campos de **Individual**:
- ✅ Birth Date
- ✅ Created Date
- ✅ First Name
- ✅ Last Name

---

## Paso 5 — Agregar objetos relacionados

**Objeto relacionado 1:**
- Haz clic en el botón **"+"** junto a *Individual*
- Selecciona **"Contact Point Address"**

**Objeto relacionado 2:**
- Haz clic en el botón **"+"** junto a *Contact Point Address*
- Selecciona **"Account Contact"**
- Selecciona estos campos de Account Contact:
  - ✅ Account
  - ✅ Contact Email
  - ✅ Last Activity Date

---

## Paso 6 — Guardar y construir

1. Haz clic en **"Save and Build"**
2. En el intervalo de actualización selecciona **"Weekly"**
3. Haz clic en **"Save and Build"** nuevamente

---

## Paso 7 — Verificar el estado

- Ve a la pestaña **Data Graphs**
- Espera a que la columna **"Last Run Status"** muestre **"Active"**

> ⚠️ Este proceso puede tardar entre **15 minutos y varias horas** dependiendo del tamaño de los datos.

---

## Paso 8 — Verificar en Trailhead

Una vez que el Data Graph esté en status **Active**, regresa a Trailhead y haz clic en **"Check Challenge"** para ganar los **500 puntos**.

---

> 💡 **Tip alternativo:** Si no quieres construirlo desde cero, puedes usar un **Data Kit** que provee data graphs preconfigurados listos para deployar y personalizar.