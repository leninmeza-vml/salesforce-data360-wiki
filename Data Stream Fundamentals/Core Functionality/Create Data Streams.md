# Create Data Streams

## Learning Objectives

In this project, you’ll:

*   Learn how to connect data using data streams.  
    
*   Define data lake objects.  
    
*   Create data streams.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

As of October 14, 2025, Data Cloud has been rebranded to Data 360. During this transition, you may see references to Data Cloud in our application and documentation. While the name is new, the functionality and content remains unchanged.

## Everything Begins with Data

Data is the foundation of our world and work. It can help you make discoveries, answer questions, drive decisions, and connect. To do this, you need data in the right place at the right time. But just having mountains of information isn’t what sets you up for success. What really matters is being able to easily, accurately, and quickly categorize that data. Salesforce Data 360 makes it possible to quickly bring data to your fingertips using the power of the Salesforce Platform and a scalable infrastructure.

So, how exactly does your data get into Data 360? And what do you do after you get data into Data 360? In this project, you explore bringing data into Data 360, mapping and unification of that data, and then querying and acting on that data.

## Sign Up for a Developer Edition with Data 360

Now that you’re familiar with the concepts and terms in this project,click **Create Playground** to receive a special, limited-time custom playground that includes Data 360 and our sample data. Once your org has been created (this can take some time), look for an email entitled “Finish resetting your Salesforce password” from support@salesforce.com.

*   From the email, find and save your username (1).  
    
*   Click the link (2) to reset your password.  
    

![Reset password image with callouts on username and the link that needs to be clicked to reset.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/create-data-streams-1/images/dcd0f102c2ac274676896488eb6193d3_kix.fvi7sc1g1xr5.jpg)

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

This Developer Edition is designed to work with the challenges in this badge, and might not work for other badges. Always check that you’re using the recommended Trailhead Playground or special Developer Edition org. 

## Connect Your Developer Edition Org to Trailhead

1.  Make sure you’re logged in to your Trailhead account.  
    
2.  Click **Connect Playground**.  
    
3.  On the login screen, enter the username and password for the Developer Edition you just set up.  
    
4.  On the Allow Access? screen, click **Allow**.  
    
5.  On the _"_Want to connect this org for hands-on challenges?" screen, click **Yes! Save it.** You are redirected to the challenge page and ready to use your new Developer Edition to earn this badge.  
    

This project requires access to a special Developer Edition that includes Data 360. These Developer Editions are only available for a limited time—be sure to complete this project before your org expires. 

## Connect Your Data

Connections in Data 360 are started by setting up data streams, which are data sources either connected or ingested into Data 360. The data from those data sources are stored in data lake objects (DLOs), which are basically storage containers for data stream data. If data needs manipulation, formula fields can be created to normalize your data or to create basic calculations.

## Create a Data Stream

Before you can ingest data into Data 360, you need to configure any data source that you’d like to connect. Data sources can be other Salesforce orgs, Marketing Cloud Engagement business units, external platforms, CSV files, and more! For this project, we’ve already connected a Sales Cloud and Service Cloud org to your Developer org. Since these data source connections are already established, you can now add data streams to Data 360. 

1.  After logging back into your Developer Org, go to Data Cloud from the App Launcher and search for and select **Data Cloud**.  
    

![App launcher icon with Data Cloud in the Apps.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/create-data-streams-1/images/5cbf6791d6380bc327474a5f4f4c1985_kix.vlpygkiszpj3.png)

2.  In **Data Cloud**, go to the **Data Streams** tab and click **New**.  
    
3.  Click **Salesforce CRM** under Connected Sources**,** and click **Next**.  
    
4.  Note the Salesforce Org is preselected. From View Bundles, choose the **Sales** data bundle and click **Next**.  
    

![New Data Stream screen with the Sales Data Bundle selected.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/create-data-streams-1/images/6783467dd182669228b59ff5a74c2a43_kix.cf0h36cp67n7.jpg)

5.  View the associated fields and click **Next**. It may take a few minutes for the fields to appear.  
    
6.  Notice that the default Data Space is preselected and all the fields included in the bundle are listed. Leave the selections as is, and click **Deploy**.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Deployment may take a few minutes. If you run into any issues, wait a few minutes and then retry the deployment again. 

Six new data streams are now created. Next, add some additional data streams to connect Service Cloud case data to Data 360.

1.  From the **Data Streams** window, click **New**.  
    
2.  Select **Salesforce CRM** and click **Next**.  
    
3.  Select **View Objects** (1) and search for `CaseCopiar` (2).  
    
4.  Select both **Case** and **Case History** and click **Next**.  
    

![New Data Stream window with Case and Case History selected.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/explore-data-cloud-core-functionality/create-data-streams-1/images/323861caae329b21ce78e5a81fb801d2_kix.bz7k6c11p5ru.jpg)

5.  Under Objects starting with Case, keep the name the same (Case\_Home) and select **Engagement** from the Object Category dropdown.  
    
6.  Then select **Created Date** from the dropdown for Event Time Field.  
    
7.  Click **CaseHistory2**. Keep the same name (CaseHistory2\_Home) and select **Other** for the Object Category.  
    
8.  Click **Next**.  
    
9.  Check that the default data space is selected and click **Deploy**.  
    

## Verify Your Data Streams

Great, you’ve created data streams to start the flow of data from Sales and Service cloud objects into Data 360. Now that you have created these data streams in your Developer Org, click **Verify Step** to check your work before moving to the next step in the project. In the next step, you add formula fields and map data to the Customer 360 Data Model.  

## Resources

*   [_Salesforce Help_: About Salesforce Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_data_cloud.htm)
*   [_Salesforce Help_: Data 360 Glossary of Terms](https://help.salesforce.com/s/articleView?id=data.c360_a_glossary_guide.htm)
*   [_Salesforce Help_: Data360 Editions and Licenses](https://help.salesforce.com/s/articleView?id=data.c360_a_dc_editions.htm)

## Verificar paso

+100 puntos

Completará esta unidad en su propio Playground Data Cloud.

### Restablecer la contraseña del Playground Data Cloud

Siga estos pasos:

*   En este correo electrónico, copie el nombre de usuario y siga los pasos para restablecer la contraseña.
*   Vuelva aquí y haga clic en **Conectar un Playground**.
*   Inicie sesión con el nombre de usuario `epic.21b21773155292371@orgfarm.salesforce.comCopiar` y su contraseña nueva.
*   Otorgue permiso de Trailhead para acceder al Playground.
*   Nota: Es posible que el restablecimiento de contraseña tarde unos minutos. Si se produce algún error, espere un momento y vuelva a intentarlo con las mismas credenciales.

Conectar un Playground

notification

Hemos enviado un correo electrónico a lenin.meza@vml.com desde support@salesforce.com. ¿No encuentra el correo electrónico? [Obtener ayuda](https://trailhead.salesforce.com/help?article=Trailhead-Account-Email)

Verificar paso para ganar 100 puntos

Aquí te explico paso a paso cómo completar el playground de **Create Data Streams** en Salesforce Data 360:

**1. Configura tu cuenta**

- Revisa tu correo de support@salesforce.com con el asunto "Finish resetting your Salesforce password"
- Guarda tu nombre de usuario y resetea tu contraseña usando el enlace del correo

**2. Conecta tu org a Trailhead**

- Haz clic en **Connect Playground** en Trailhead
- Ingresa tus credenciales del Developer Edition
- Acepta en la pantalla "Allow Access?" y luego "Yes! Save it"

**3. Crea el primer Data Stream (Sales Cloud)**

- Ve al **App Launcher** → busca y selecciona **Data Cloud**
- Ve a la pestaña **Data Streams** → clic en **New**
- Selecciona **Salesforce CRM** → Next
- En "View Bundles" elige **Sales data bundle** → Next
- Deja todo por defecto → clic en **Deploy**

**4. Crea el segundo Data Stream (Service Cloud - Cases)**

- Desde Data Streams → clic en **New**
- Selecciona **Salesforce CRM** → Next
- Selecciona **View Objects** y busca **Case**
- Selecciona **Case** y **Case History** → Next
- Para **Case_Home**: categoría = **Engagement**, Event Time Field = **Created Date**
- Para **CaseHistory2_Home**: categoría = **Other**
- Clic en **Deploy**

**5. Verifica**

- Una vez desplegados los streams, haz clic en **Verify Step**

**Consejos importantes:**
- El deployment puede tardar varios minutos, ten paciencia
- Si hay errores, espera unos minutos y vuelve a intentarlo
- Asegúrate de usar exactamente el Developer Edition especial de este badge, no otro playground

¿Tienes algún problema en algún paso específico?