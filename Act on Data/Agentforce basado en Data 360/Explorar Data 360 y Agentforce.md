# Explorar Data 360 y Agentforce

## Objetivos de aprendizaje

Después de completar esta unidad, podrá:

*   Explicar por qué es necesario Data 360 para Agentforce.  
    
*   Identificar los beneficios de la creación de agentes que utilicen datos unificados de Customer 360 desde Data 360.  
    

## Antes de empezar

Antes de empezar este módulo, considere completar este contenido recomendado.

*   [Experiencias basadas en Data 360](https://trailhead.salesforce.com/content/learn/modules/data-cloud-powered-experiences)  
    
*   [Fundamentos de Agentforce](https://trailhead.salesforce.com/content/learn/modules/einstein-copilot-basics)  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Todas las funciones que se describen en este módulo consumen créditos de Data 360. Obtenga más información en [Consumo de créditos de Data 360: un vistazo rápido](https://trailhead.salesforce.com/content/learn/modules/data-cloud-credit-consumption-quick-look) y en [Cartera digital de Salesforce: un vistazo rápido](https://trailhead.salesforce.com/content/learn/modules/salesforce-digital-wallet-quick-look).

## Explorar cómo interactúan Data 360 y Agentforce

Ha dado el salto y ya tiene Agentforce en su organización de Salesforce. Está deseando crear agentes de IA que conozca a sus clientes y su empresa. Vamos a ver cómo se relaciona Data 360 con Agentforce para que pueda comprender la conexión y cómo se usan en conjunto.

Hay dos capas de Data 360 para Agentforce: habilitación e implementación.

*   **Habilitar** significa que abastece y habilita Data 360 en su organización.  
    
*   **Implementar** significa que habilita Data 360 en su organización, conecta los datos y los asigna a modelos de datos. Probablemente también los combine con conjuntos de reglas de resolución de identidad y configure otras funciones de Data 360.  
    

La habilitación e implementación de Data 360 afecta a las capacidades de Agentforce.

*   **Habilitación de Data 360****:** Data 360 debe abastecerse y habilitarse para todos los usos de Agentforce. Las funciones de Agentforce, como la biblioteca de datos de Agentforce y la Capa de seguridad de Einstein, no funcionan sin Data 360.  
    
*   **Implementación de Data 360:** al implementar Data 360, obtiene beneficios como diversos datos de Customer 360, capacidades potentes de limpieza y transformación de datos, y generación aumentada por recuperación totalmente personalizable. Para crear una plantilla de agentes sólida y ayudar con los requisitos complejos, debe implementar Data 360.  
    

En este módulo, conocerá la manera en la que la habilitación y la implementación de Data 360 afecta a sus agentes. Data 360 y Agentforce trabajan en conjunto para proporcionar agentes de confianza y eficaces nutridos con sus datos empresariales. Para conocer el motivo por el que necesita Data 360, explore la manera en la que las capacidades de Agentforce se potencian con Data 360. Aprenderá si debe habilitar o implementar Data 360 para cada una de las capacidades. También aprenderá a implementar Data 360 para Agentforce siguiendo un caso de uso.

Comenzará por explorar la manera en la que Data 360 proporciona la base para conseguir agentes eficaces y personalizados.

## Implementación de Data 360: agentes basados en datos de Customer 360

Una vez que se haya implementado Data 360 por completo, ofrece una base de datos sólida y segura que proporciona a los agentes acceso a datos unificados de Customer 360, transformados, en tiempo y sin copia. En la tabla, explore algunos aspectos clave de una base de Data 360 y la manera en la que afecta a los agentes.

En la columna Ejemplo de NTO, siga el ejemplo de Northern Trail Outfitters (NTO). una empresa ficticia de prendas de ropa. NTO ha creado un agente de servicio que gestiona las consultas de los clientes, entre las que se incluyen recomendaciones de productos, reembolsos de pedidos y promociones.

| **Base de Data 360** | **Descripción** | **Cómo afecta a Agentforce** | **Ejemplo de NTO** |
| --- | --- | --- | --- |
| Customer 360 unificado | Incorpore datos de Salesforce y otras fuentes, ejecute conjuntos de reglas de resolución de identidad y cree un perfil unificado de cada cliente con contexto histórico en fuentes de datos. | Los agentes basados en datos de Data 360 conocen a sus clientes por completo, desde sus compras en Sales Cloud hasta su implicación en Marketing Cloud.<br><br>En lugar de proporcionar respuestas genéricas o inconexas, los agentes ofrecen respuestas personalizadas que tienen en cuenta las acciones del cliente en la empresa. | 1.  Un cliente le pide al agente de NTO una recomendación de producto.  <br>    <br>2.  Con los perfiles unificados, el agente puede ver la compra más reciente del cliente: una nueva línea de zapatos de NTO. El agente también ve que el cliente ha interactuado con la campaña de marketing de la línea, específicamente haciendo clic en la chaqueta y en los zapatos.  <br>    <br>3.  Como el cliente ya ha comprado zapatos, el agente le recomienda la chaqueta. |
| Transformaciones de datos | Limpie y transforme los datos. Resuelva los problemas de calidad de los datos, como nombres o formatos incoherentes. | La limpieza de datos mejora la precisión, la coherencia y la fiabilidad del agente. Si no se realiza una limpieza de datos, es más probable que el agente proporcione respuestas ambiguas o incorrectas, o puede que ni siquiera responda. | NTO ha ingerido registros de pedidos de Commerce Cloud en Data 360. NTO aún no ha tenido tiempo de realizar una limpieza de datos.<br><br>1.  Un cliente le pide al agente de NTO que le reembolse su pedido.  <br>    <br>2.  El agente de NTO busca el número de pedido en Data 360. Sin embargo, la fecha que aparece en el registro del pedido está en el formato DD/MM/AA. En la política de NTO se indica que las devoluciones deben procesarse en un plazo de 30 días, pero la fórmula solo funciona con fechas en el formato MM/DD/AA.  <br>    <br>3.  El agente de NTO no puede procesar el reembolso.  <br>    <br><br>NTO ejecuta una transformación de datos para convertir todas las fechas al formato MM/DD/AA. Ahora, los agentes pueden procesar los reembolsos correctamente. |
| Datos en tiempo real | Ingiera, unifique y analice datos en tiempo real y actúe en base a ellos. | Cree agentes que conozcan las acciones actuales de los clientes y reaccionen en unos segundos. | 1.  Un cliente navega por el sitio web de NTO, abre la ventana de chat del agente y le pregunta si hay alguna promoción.  <br>    <br>2.  El agente ve las interacciones del cliente en tiempo real e identifica que el cliente ha hecho clic en mochilas.  <br>    <br>3.  En lugar de recomendar todas las promociones activas, el agente le indica al cliente las promociones más relevantes: dos por uno en una selección de mochilas. |
| Sin copia | Conecte datos almacenados fuera de Salesforce sin copia. La conexión sin copia le permite crear comunicaciones bidireccionales entre Data 360 y sistemas externos, de manera que pueda acceder a los datos libremente sin duplicarlos. | Expanda el alcance de sus agentes más allá de Salesforce. | NTO almacena los datos del programa de fidelidad en Databricks. Se utiliza la conexión sin copia para incorporar los datos en Data 360 y enriquecer los perfiles unificados.<br><br>1.  Un cliente le pregunta al agente de NTO si hay alguna promoción disponible.  <br>    <br>2.  El agente busca el perfil unificado del cliente, que se ha enriquecido con los datos del programa de fidelidad.  <br>    <br>3.  El agente ve que el cliente es socio platino, lo cual le concede el derecho a una promoción exclusiva.  <br>    <br>4.  El agente de NTO recomienda la promoción exclusiva. |

Aunque hay otras opciones para ingerir datos a fin de que Agentforce los utilice, Data 360 es la única plataforma compatible con una estrategia integral con datos unificados.

*   Datos de CRM mediante Fileforce: solo se ingieren datos de CRM sin estructurar, no se unifican los datos.  
    
*   Agentforce mediante la biblioteca de datos de Agentforce (utiliza el almacenamiento de Data 360): solo se ingieren datos sin estructurar, no se unifican los datos.  
    

## Lo próximo será lo siguiente

En esta unidad, ha descubierto cómo los agentes basados en Data 360 se benefician del acceso a datos unificados, transformados, en tiempo real y sin copia. Tras conectar fuentes y transformar datos en Data 360, ya está listo para configurar la generación aumentada por recuperación (RAG).

## Recursos

*   [_Ayuda de Salesforce_: Mejor juntos: datos e IA](https://help.salesforce.com/s/articleView?language=en_US&id=data.c360_a_dc_ai.htm&type=5)
*   [_Salesforce Blog_: The Force Behind Agentforce: How Data Cloud Fuels Agent-First Enterprises](https://www.salesforce.com/news/stories/how-data-cloud-powers-agentforce/)
*   [_Ayuda de Salesforce_: Set Up and Maintain (Configuración y mantenimiento)](https://help.salesforce.com/s/articleView?id=data.c360_a_set_up.htm&type=5)
*   [_Trailhead_: Datos e identidad en Data 360](https://trailhead.salesforce.com/content/learn/modules/data-and-identity-in-salesforce-cdp)
*   [_Ayuda de Salesforce_: Unificar perfiles de origen](https://help.salesforce.com/s/articleView?id=data.c360_a_identity_resolution_unify_source_profiles.htm&type=5)
*   [_Trailhead_: Transformaciones de datos de transmisión en Data 360: un vistazo rápido](https://trailhead.salesforce.com/content/learn/modules/batch-data-transforms-in-data-cloud-quick-look)
*   [_Trailhead_: Transformaciones de datos de transmisión en Data 360: Un vistazo rápido](https://trailhead.salesforce.com/content/learn/modules/streaming-data-transforms-quick-look)
*   [_Ayuda de Salesforce_: Limpieza y preparación de datos](https://help.salesforce.com/s/articleView?id=data.c360_a_cleansing_data.htm&type=5)
*   [_Trailhead_: Casos de uso en tiempo real en Data 360](https://trailhead.salesforce.com/content/learn/modules/real-time-use-cases-in-data-cloud)
*   [_Ayuda de Salesforce_: Capacidades en tiempo real en Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_real_time_capabilities.htm&type=5)
*   [_Trailhead_: Data 360 con conexión sin copia](https://trailhead.salesforce.com/content/learn/modules/data-cloud-with-zero-copy)
*   [_Ayuda de Salesforce_: Federación de datos sin copia](https://help.salesforce.com/s/articleView?id=data.c360_a_byol_data_federation.htm&type=5)

Respuestas de la prueba:

---

**Pregunta 1 — ¿Qué pasos debe seguir para tener acceso a la base de datos sólida de Data 360?**

**Respuesta: D — Implementar Data 360, abastecerlo y habilitarlo; a continuación, conectar, transformar y asignar los datos.**

El documento distingue entre **habilitar** (abastecer y habilitar Data 360 en la organización) e **implementar** (conectar datos, asignarlos a modelos de datos, configurar resolución de identidad y otras funciones). Para obtener la base de datos sólida completa se requiere la implementación completa, no solo la habilitación.

---

**Pregunta 2 — ¿Por qué los datos unificados de Customer 360 en Data 360 son beneficiosos para los agentes?**

**Respuesta: B — Porque se habilita a los agentes para que proporcionen respuestas personalizadas que tengan en cuenta las acciones del cliente y el contexto completo.**

El documento ilustra esto con el ejemplo de NTO: gracias a los perfiles unificados, el agente puede ver tanto las compras recientes del cliente en Sales Cloud como sus interacciones en Marketing Cloud, permitiéndole dar recomendaciones personalizadas en lugar de respuestas genéricas.