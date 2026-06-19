# Implementar Data 360 para Agentforce

## Objetivos de aprendizaje

Después de completar esta unidad, podrá:

*   Explicar cómo preparar los datos para Agentforce.  
    
*   Describir cómo crear un agente basado en datos unificados y transformados desde Data 360.  
    

## Comprender los requisitos de los datos

Antes de implementar Data 360, debe conocer los requisitos de datos de su proyecto. Resulta útil revisar los pasos de preparación de los datos y las cuestiones a tener en cuenta.

| **Pasos de preparación de datos** | **Preguntas a considerar** |
| --- | --- |
| 1.  Identificar los datos necesarios para su caso de uso y definir el tipo de datos. | *   ¿Necesita registros de CRM, como candidatos o casos?  <br>    <br>*   ¿Necesita datos sin estructurar o estructurados?  <br>    <br>*   ¿Debe cargar archivos? |
| 2.  Localizar la fuente de los datos y determinar cómo conectarla a Data 360. | *   Si necesita registros de CRM, ¿en qué organización se encuentran?  <br>    <br>*   ¿Están los datos en un almacén de datos externos? En caso de ser así, debe utilizar un conector de federación de datos sin copia.  <br>    <br>*   ¿Necesita acceso en tiempo real a los datos? |
| 3.  Resaltar los requisitos de procesamiento de datos. Entre ellos se incluyen la resolución de identidad, las transformaciones o las perspectivas. | *   ¿Hay problemas de calidad en los datos? ¿Qué tipos de problemas? ¿Se han generalizado los problemas?  <br>    <br>*   ¿Debe unificar los datos? Esto implica ejecutar la resolución de identidad para vincularlos a perfiles unificados. |

Esta tabla no está completa. Obtenga más información en la unidad Preparar sus datos del módulo [IA y datos: planificación del proyecto](https://trailhead.salesforce.com/content/learn/modules/ai-data-project-planning)[](https://trailhead.salesforce.com/content/learn/modules/ai-data-project-planning).

En la siguiente sección, siga a la empresa NTO mientras identifica, conecta y procesa datos para su proyecto de Agentforce.

## Configurar Data 360 para los agentes

NTO quiere crear un agente que responda a las preguntas sobre problemas de productos. NTO tiene la intención de nutrir sus solicitudes con generación aumentada por recuperación avanzada de Data 360. Siga a Pia, la arquitecta empresarial de NTO, a medida que configura Data 360 y crea un agente, comenzando por la preparación de los datos. Estos son los pasos iniciales que tiene que seguir.

1.  Habilitar y abastecer Data 360 en una organización.  
    
2.  Configurar usuarios de Data 360.  
    
3.  Encontrar datos sobre casos de clientes e identificar las fuentes.  
    

En Service Cloud, NTO almacena datos de casos de clientes. Estos son algunos casos de ejemplo de diferentes clientes.

*   Caso 1: el modelo de pantalón 1068 es demasiado corto  
    
*   Caso 2: el modelo de pantalón 2000 es demasiado largo  
    
*   Caso 3: el reloj deportivo no se carga rápido  
    

4.  Ahora, es el momento de crear una transmisión de datos que ingiera los datos del caso de Service Cloud en Data 360. Los datos del caso se almacenan en el objeto de lago de datos (DLO) Case (Caso).  
    
5.  Pia utiliza una transformación de datos por lotes para resolver los problemas de los datos, como nombres y formatos no coherentes. Los datos transformados se almacenan en el objeto de lago de datos Cleaned Case (Caso limpio).  
    
6.  A continuación, agrega asignaciones entre el objeto de lago (DLO) de datos Cleaned Case (Caso limpio) y el objeto de modelo de datos (DMO) Case (Caso).  
    
7.  Ahora es el momento de crear y ejecutar un conjunto de reglas de resolución de identidad para vincular los casos con el perfil unificado del cliente.  
    

Ahora Pia tiene más contexto sobre cada caso. Por ejemplo, Pia ve que el Caso 1, sobre los pantalones que son demasiado cortos, proviene de Rachel Rodriguez. El perfil unificado de Rachel incluye su estatura: 1,70 metros. Pia también ve que el Caso 2, sobre los pantalones que son demasiado largos, proviene de un cliente que mide 1,65 m. Este contexto ayudará al agente a proporcionar respuestas más pertinentes y eficaces.

Una vez ingeridos, transformados y unificados los datos, Pia ya está lista para configurar la generación aumentada por recuperación.

1.  Crea un índice de búsqueda a partir del DMO Case (Caso) y un índice de búsqueda a partir del DMO Unified Individual (Perfil individual unificado).  
    

Estos índices se utilizarán para impulsar la generación aumentada por recuperación en su agente. Data 360 crea automáticamente un recuperador para cada índice, que sirve de unión entre los índices de búsqueda y las plantillas de solicitud.

De manera opcional, Pia podría crear un conjunto de recuperadores. Obtenga más información en [Crear un conjunto de recuperadores](https://help.salesforce.com/s/articleView?id=data.c360_a_ai_retriever_ensemble_create.htm&type=5).

2.  Ahora, Pia crea una plantilla de solicitud que activa el conjunto de recuperadores o ambos recuperadores individuales.  
    

El recuperador rellena la solicitud con la información más relevante. La plantilla de solicitud de Pia analiza la pregunta del cliente y utiliza su base de conocimientos (los datos y los perfiles unificados del caso existente) para crear una respuesta.

Es el momento de utilizar la plantilla de solicitud en un agente. Pia:

1.  Crea un nuevo agente a partir de una plantilla de agente de servicio de Agentforce.  
    
2.  Crea un conjunto de permisos que incluye acceso a Prompt Builder, al DMO Case (Caso) y al DMO Unified Individual (Perfil individual unificado). A continuación, asigna el conjunto de permisos al usuario agente.  
    
3.  Crea una acción de agente llamada Answer Questions with Case (Responder preguntas con el DMO Case \[Caso\]) que utiliza la plantilla de solicitud.  
    
4.  Agrega un tema al usuario agente.  
    
5.  Agrega la acción Answer Questions with Case (Responder preguntas con el DMO Case \[Caso\]) al tema.  
    
6.  Activa y prueba el agente.  
    

Por ejemplo, Pia le dice al agente "Tengo piernas largas y mido 1,70 m". ¿Qué tipo de pantalones me recomienda y cuál no? El agente responde: Los clientes con una altura similar han informado de que el modelo de pantalones 1068 es demasiado corto. Los clientes afirman que el modelo 2000 es más largo. Le recomiendo el modelo 2000 y no le recomiendo el modelo 1068.

Después de unas cuantas pruebas más para ajustar la solicitud, Pia y su equipo están satisfechos con el rendimiento. NTO implementa y el agente y hace que esté operativo agregándolo a los canales de clientes. Tras la implementación, el equipo se asegura de supervisarlo y ajustarlo de forma coherente. Recuerde que después de comenzar a utilizar su agente, debe seguir estas prácticas recomendadas.

*   Supervisar el seguimiento de auditoría y proporcionar comentarios sobre sus agentes.  
    
*   Modificar las solicitudes para abordar comentarios críticos.  
    
*   Supervisar el rendimiento con los paneles de Agentforce Analytics.  
    
*   Actualizar la implementación de la generación aumentada por recuperación para que las fuentes de datos de los agentes estén al día.  
    

## Conclusión

En este módulo, ha aprendido cómo Data 360 es compatible con las capacidades de Agentforce y la diferencia entre habilitar e implementar Data 360. Mientras que al habilitar Data 360 se desbloquean algunas capacidades, como la Capa de confianza de Einstein y la generación aumentada por recuperación con la biblioteca de datos de Agentforce, la implementación de Data 360 es el siguiente paso fundamental debido a todos los beneficios que presenta.

La implementación de Data 360 proporciona agentes con una base de datos unificada que amplía sus conocimientos sobre Salesforce y otros temas. Además, las soluciones de generación aumentada por recuperación basadas en Data 360 tienen contexto de perfiles unificados, utilizan datos transformados y procesados, y son compatibles con diversos tipos y fuentes. Cuando Data 360 se ha implementado, los agentes desbloquean capacidades en tiempo real y acceden a datos sin copia, ampliando así su potencial.

Ya visto cómo NTO prepara sus datos, implementa Data 360 para Agentforce y crea un agente de servicio que utiliza perfiles unificados para proporcionar respuestas. Ahora está listo para implementar Data 360 para Agentforce en su negocio.

## Recursos

*   [_Ayuda de Salesforce_: Gestionar índices de búsqueda](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_manage.htm&type=5)
*   [_Ayuda de Salesforce_: Transformaciones de datos por lotes](https://help.salesforce.com/s/articleView?id=data.c360_a_batch_transform_overview.htm&type=5)
*   [_Ayuda de Salesforce_: Crear un agente a partir de una plantilla de agente de servicio de Agentforce](https://help.salesforce.com/s/articleView?id=ai.service_agent_setup.htm&type=5)
*   [_Ayuda de Salesforce_: Prácticas recomendadas para los permisos de usuario agente](https://help.salesforce.com/s/articleView?id=ai.agent_user.htm&type=5)
*   [_Ayuda de Salesforce_: Implementar su agente en canales](https://help.salesforce.com/s/articleView?id=ai.agent_parent_deploy.htm&type=5)
*   [_Trailhead_: Data 360: Actuar en base a los datos](https://trailhead.salesforce.com/content/learn/modules/data-cloud-act-on-data)

Respuestas de la prueba:

---

**Pregunta 1 — ¿Cuál es el orden correcto de los pasos de preparación de datos para un proyecto de Agentforce?**

**Respuesta: D — Crear una transmisión de datos, utilizar una transformación de datos por lotes y ejecutar un conjunto de reglas de resolución de identidad.**

El documento describe exactamente este orden en el ejemplo de NTO: primero crea una transmisión de datos que ingiere los casos de Service Cloud, luego usa una transformación de datos por lotes para limpiar los datos, agrega asignaciones entre el DLO y el DMO, y finalmente ejecuta el conjunto de reglas de resolución de identidad para vincular los casos con perfiles unificados.

---

**Pregunta 2 — ¿Cuál es la secuencia correcta para crear un agente basado en datos unificados de Data 360?**

**Respuesta: C — Crear un índice de búsqueda, crear una plantilla de solicitud que active un recuperador y crear una acción de agente que utilice la plantilla de solicitud.**

El documento muestra este flujo en el ejemplo de Pia: primero crea índices de búsqueda a partir de los DMOs (Data 360 crea automáticamente recuperadores para cada índice), luego crea una plantilla de solicitud que activa los recuperadores, y finalmente crea la acción de agente **"Answer Questions with Case"** que utiliza esa plantilla de solicitud.