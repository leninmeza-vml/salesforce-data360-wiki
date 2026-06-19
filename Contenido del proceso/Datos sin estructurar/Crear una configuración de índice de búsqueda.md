# Crear una configuración de índice de búsqueda

## Objetivos de aprendizaje

Después de esta unidad, podrá:

*   Explicar cómo funcionan las configuraciones de índice de búsqueda y la integración de datos en Data 360.  
    
*   Crear una configuración de índice de búsqueda vectorial.  
    

![Nota](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

#### Nota

¿Su idioma de aprendizaje es español? Comience el reto en un Trailhead Playground en español y utilice las traducciones proporcionadas entre paréntesis para navegar. Copie y pegue **solo los valores en inglés**, ya que las validaciones del reto se basan en los datos en inglés. Si no aprueba el reto en su organización en español, le recomendamos que (1) cambie la configuración regional a Estados Unidos, (2) cambie el idioma a inglés, siga las instrucciones [descritas aquí](https://help.salesforce.com/s/articleView?id=sf.usersetup_lang_time_zone.htm&type=5) y, a continuación, (3) vuelva a hacer clic en el botón Check Challenge (Comprobar el reto).

Consulte la insignia [Trailhead en su idioma](https://trailhead.salesforce.com/content/learn/modules/trailhead-in-your-language) para obtener más información sobre cómo aprovechar la experiencia de Trailhead en otros idiomas.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

A partir del 14 de octubre de 2025, Data Cloud ha pasado a ser Data 360. Durante esta transición, es posible que vea referencias a Data Cloud en nuestra aplicación y documentación. Aunque el nombre sea nuevo, la funcionalidad y el contenido siguen siendo los mismos.

## Nutrir la búsqueda de datos sin estructurar mediante configuraciones de índices de búsqueda

Nutrir la búsqueda de datos sin estructurar y estructurados mejora el uso de la IA generativa, los análisis y las herramientas de automatización en Salesforce Platform. Contar con una búsqueda bien nutrida permite integrar datos específicos de clientes en aplicaciones como Agentforce, Tableau y Flow Builder para garantizar que los resultados estén bien ajustados a las intenciones y los contextos de los usuarios. Esta alineación permite obtener contenido más preciso y relevante generado por IA, información más detallada a partir de análisis y flujos de trabajo de automatización más eficientes para sus equipos y clientes.

Para nutrir una búsqueda, debe desglosar los datos sin estructurar en fragmentos correctos desde el punto de vista semántico y, a partir de esos fragmentos, crear incrustaciones de vectores, es decir, representaciones numéricas de los datos fragmentados. El contenido fragmentado y almacenado en el índice de búsqueda de Data 360 permite búsquedas y se puede usar en aplicaciones con IA generativa de Einstein (como Prompt Builder y Agentforce), así como en aplicaciones de automatización (Flow Builder) y análisis (Tableau).

![Un diagrama gráfico donde se muestra el flujo para crear y usar un índice vectorial.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/projects/unstructured-data-in-data-cloud/create-a-search-index-configuration/images/es-ES/f46c79f6b3a08b50d5eb7f12f91d5cd2_kix.bbqya6exd64m.png)

## Datos sin estructurar en fragmentos

En la unidad anterior, hemos visto cómo Data 360 hace referencia a datos sin estructurar mediante objetos de modelos de datos sin estructurar (UDMO). También puede fragmentar los UDMO o cualquier objeto de modelo de datos (DMO) con campos de texto, como artículos de Knowledge de Salesforce. Esto es lo que haremos en esta unidad.

Al fragmentar UDMO o DMO, se desglosan en fragmentos procesables con significado semántico. Estas unidades de texto se almacenan en Data 360 en objetos de modelos de datos fragmentados (CDMO), que se crean a partir de objetos de modelos de datos u objetos de modelos de datos sin estructurar.

## Funcionamiento de la fragmentación

Data 360 admite distintas estrategias de segmentación.

La extracción de pasajes semánticos utiliza el significado semántico inherente a las etiquetas HTML para fragmentar un documento en pasajes. Los elementos HTML como encabezados (<h1>, <h2>), listas (<ul>, <ol>) o texto en negrita (<strong>) que actúa a modo de encabezado se consideran los límites lógicos de los pasajes.

La estrategia de extracción de pasajes basada en ventanas emplea elementos de nivel de texto como etiquetas <div> y <p>, o texto sin formato separado por saltos de línea, para fragmentar documentos en pasajes. Si un párrafo no contiene HTML, la extracción se realiza a nivel de oración.

Hay más información sobre las estrategias de fragmentación en la [Ayuda de Salesforce](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_supported_chunking_strategies.htm&type=5).

Por ahora, veamos lo que ocurre después de fragmentar los datos.

## Crear incrustaciones de vectores a partir de contenido fragmentado

Después de que Data 360 fragmente el contenido, se crea una incrustación de vector, es decir, una representación numérica de contenido fragmentado que se puede recuperar o utilizar en aplicaciones de IA generativa, automatización o análisis de Salesforce.

Las incrustaciones de vectores son representaciones numéricas de texto que almacenan relaciones entre palabras o frases. La incrustación captura el significado semántico del contenido, por lo que los fragmentos de contenido similares desde el punto de vista semántico tienen incrustaciones de vectores similares. Estas representaciones ayudan a que las máquinas procesen y comprendan el lenguaje de forma eficaz.

En Data 360, se hace referencia a las incrustaciones de vectores en los objetos de modelos de datos de índice (IDMO), que veremos con más detalle luego en esta unidad.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Hay más información sobre las incrustaciones de vectores y el contenido fragmentado en la [Ayuda de Salesforce](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_grounding.htm&type=5).

## Crear configuraciones de índice de búsqueda vectorial

A fin de preparar los datos sin estructurar para la búsqueda, debe fragmentarlos y vectorizarlos. Para ello, debe crear una configuración de índice de búsqueda. La configuración de índice de búsqueda se crea para cualquier tipo de objeto de datos con campos de texto que contienen los conceptos informativos, narrativos o descripciones detalladas que buscan sus usuarios a fin de encontrar resultados relevantes. Un ejemplo de estos datos son los artículos de Salesforce Knowledge u otros documentos de texto (por ejemplo, transcripciones de chat) que se guardan en un almacén de "blobs", como Amazon S3.

## Crear una configuración de índice de búsqueda vectorial a partir de artículos de Knowledge

En la unidad anterior, ha creado una transmisión de datos y un objeto de lago de datos a partir del paquete de Knowledge en el conector de CRM de Salesforce, que proporciona varios artículos de Knowledge.

El objeto Knowledge Article Version (Versión del artículos de Knowledge) resulta útil para indexar, ya que puede utilizar este objeto para consultar, recuperar o buscar información en todos los tipos de artículos según su versión. El objeto Knowledge Article Version (Versión del artículos de Knowledge) incluye estos campos que se deberían indexar para realizar búsquedas.

*   **Name (Nombre)**: el nombre o el título del artículo de Knowledge  
    
*   **Description (Descripción)**: la descripción o el resumen del artículo de Knowledge, asignada a partir de Summary (Resumen)  
    
*   **Campos de texto personalizado**: cualquier campo de texto enriquecido (límite de 131 K) que contenga datos sin estructurar  
    

## Crear una configuración para el índice de búsqueda vectorial para el DMO Knowledge Article Version

Completará estos pasos en su organización de Data 360 a fin de superar el reto al final de esta unidad.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

La **configuración avanzada** le proporciona más control sobre las elecciones de fragmentación y vectorización; sin embargo, para este reto, utilizará principalmente la configuración predeterminada.

1.  Si aún no lo ha hecho, inicie su Playground de Data Cloud.  
    
2.  En App Launcher, seleccione **Data Cloud**.  
    
3.  Haga clic en **Search Index (Buscar índice)** | **New (Nuevo)**.  
    Si no ve la opción Search Index (Buscar índice) en la navegación Data Cloud, haga clic en el menú desplegable **More (Más)** y seleccione **Search Index (Buscar índice)**.  
    
4.  Haga clic en **Advanced Setup (Configuración avanzada)** | **Next (Siguiente)**.  
    
5.  En la página Select Source Object (Seleccionar objeto de origen), seleccione **Vector Search (Búsqueda vectorial)**, el DMO **Knowledge Article Version (Versión del artículo de Knowledge)** y haga clic en **Next (Siguiente)**.  
    
6.  En la página Select Fields to Chunk (Seleccionar campos para fragmentar), haga clic en **Manage Fields (Gestionar campos)**.  
    
7.  Haga clic en **Select All Fields (Seleccionar todos los campos)** y en **Save (Guardar)**.  
    
8.  Deje la estrategia de fragmentación predeterminada y **haga clic en Next (Siguiente)**.  
    
9.  En la página Select a Vectorization Strategy (Seleccionar una estrategia de vectorización), deje la estrategia de vectorización predeterminada tal y haga clic en **Next (Siguiente)**.  
    
10.  En la página Select Related Fields for Search Filtering (Seleccionar campos relacionados para filtrar la búsqueda), no agregue ningún campo y haga clic en **Next (Siguiente)**.  
    
11.  En la página Search Index Configuration Details (Detalles de la configuración del índice de búsqueda), reemplace el nombre de la configuración del índice de búsqueda generado automáticamente por `My_kavCopiar`. (El nombre de API de la configuración del índice de búsqueda se completa automáticamente).  
    
12.  Haga clic en **Save (Guardar)**.  
    

¡Eso es todo! Su nueva configuración de índice de búsqueda, My\_kav, aparece debajo de la ficha Search Index (Buscar índice).

## Ver los CDMO e IDMO Knowledge Article Version

Tras crear una configuración de índice de búsqueda, el estado cambia a Submitted (Enviado) y después a In-progress (En curso) a medida que se procesan los datos del objeto de modelo de datos (DMO) o el objeto de modelo de datos sin estructurar (UDMO) de origen. Si no se produce ningún error, el estado cambia de Submitted (Enviado) a In progress (En curso) y, posteriormente, a Ready (Listo). No verá ningún registro en Data Explorer hasta que el estado del índice de búsqueda sea Ready (Listo).

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Data 360 puede tardar unos minutos en procesar los datos en el índice de búsqueda; sin embargo, el tiempo puede variar, así que puede tomarse algo o ir a estirar las piernas tranquilamente. Cuando vuelva, haga clic en Refresh (Actualizar) y compruebe si el estado del índice de búsqueda es Ready (Listo).

El contenido más útil de un artículo de Knowledge se encuentra en el campo Description (Descripción). Normalmente, los artículos de muestra son muy pequeños y solo hay un fragmento. Esto significa que para cada registro del CDMO y el IDMO Knowledge Article Version (Versión del artículos de Knowledge) hay un fragmento y un vector respectivamente, pero el contenido más extenso podría tener más registros en cada DMO.

Vamos a echar un vistazo rápido al CDMO y al IDMO que hemos creado para el DMO Knowledge Article Version (Versión del artículos de Knowledge).

1.  Confirme que el estado del índice de búsqueda sea Ready (Listo).  
    
2.  En Data Cloud, haga clic en **Data Explorer**.  
    
3.  En el menú desplegable Object (Objeto), seleccione **Data Model Object (Objeto de modelo de datos)**.  
    
4.  En el campo Select an Object (Seleccionar un objeto), seleccione **My\_kav** **chunk (Fragmento My\_kav)**.  
    Ahora, debería poder ver una lista de todos los fragmentos que ha creado Data 360 a partir de los artículos de Knowledge de muestra.  
    
5.  En el campo Select an Object (Seleccionar un objeto), seleccione **My\_kav** **index (Índice My\_kav)**  
    Ahora, debería poder ver una lista de todos los registros de vector que ha creado Data 360 a partir de los artículos de Knowledge de muestra.  
    

Puede utilizar los CDMO e IDMO del índice de búsqueda en Salesforce en aplicaciones como Flow Builder, Agentforce, Prompt Builder e incluso Tableau. Si lo prefiere, consulte los documentos de búsqueda vectorial para obtener más información sobre la [ejecución de consultas de búsqueda vectorial](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_query.htm&type=5).

Al conectar datos sin estructurar a Data 360, podrá nutrir los resultados de la búsqueda con una gran cantidad de datos para una gran variedad de casos de uso centrados en los clientes. Al fragmentar y vectorizar los datos, podrá utilizar la búsqueda vectorial en aplicaciones de IA generativa de Einstein, Flow Builder e incluso Tableau a fin de mejorar las capacidades, los análisis y la automatización de la IA.

## Recursos

*   [_Ayuda de Salesforce_: Data 360: Utilizar la búsqueda para la IA, la automatización y los análisis](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_ground_ai.htm&type=5)
*   [_Ayuda de Salesforce_: Data Cloud: Búsqueda vectorial](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_vector_index.htm&type=5)

