# Habilitar agentes de confianza con Data 360

## Objetivos de aprendizaje

Después de completar esta unidad, podrá:

*   Describir la función de Data 360 en la generación aumentada por recuperación.  
    
*   Explicar cómo Data 360 respalda los procesos de realización de pruebas y supervisión, y las protecciones de los agentes.  
    
*   Explicar cómo Data 360 habilita Agentforce Analytics.  
    

## Explorar la importancia de los agentes de confianza

Sus agentes son la voz de su empresa para los clientes, por lo que es fundamental que estén nutridos con buenos datos, que cumplan las políticas y que sean responsables. Con Data 360, puede nutrir solicitudes con datos de la empresa mediante la generación aumentada por recuperación (RAG) y supervisar los agentes con protecciones de IA y análisis. De esta manera, se garantiza que los agentes sean más precisos y éticos. En esta unidad, aprenda cómo Data 360 potencia la generación aumentada por recuperación, las protecciones de la IA y los análisis.

## Aprender sobre la generación aumentada por recuperación

La generación aumentada por recuperación es una manera de nutrir solicitudes para los modelos de lenguaje grandes (LLM). Este proceso consiste en agregar información contextual y específica a las solicitudes a fin de mejorar la calidad, la precisión y la relevancia del resultado generado por el LLM. La generación aumentada por recuperación implica recuperar información pertinente de una base de conocimientos (con un recuperador), aumentando así la solicitud mediante la combinación de esta información con la solicitud original, y generando una respuesta. De ahí el término, generación aumentada por recuperación (RAG).

Estos son algunos términos clave para comprender qué es la generación aumentada por recuperación. Obtenga más información en [Generación aumentada por recuperación: un vistazo rápido](https://trailhead.salesforce.com/content/learn/modules/retrieval-augmented-generation-quick-look).

*   **Datos sin estructurar:** los datos que no tienen un formato específico y coherente, y que no pueden almacenarse de forma sencilla en una base de datos relacional. Tras ingerir datos sin estructurar, desglóselos de manera que pueda crear incrustaciones de vectores.  
    
*   **Incrustaciones de vectores:** representación numérica de datos sin estructurar que pueden leer las máquinas. Las incrustaciones de vectores miden la similitud semántica de diferentes fragmentos de texto, permitiendo así que los resultados sean precisos y pertinentes en solicitudes de IA generativa y búsquedas.  
    
*   **Almacenamiento de datos vectoriales****:** tipo de base de datos diseñada para almacenar incrustaciones de vectores.  
    
*   **Índice de búsqueda****:** una estructura de datos que almacena datos fragmentados y vectorizados que pueden buscarse y recuperarse desde otras aplicaciones.  
    
*   **Recuperador****:** el vínculo entre la solicitud y el índice de búsqueda. Los recuperadores buscan en fuentes de datos para encontrar información pertinente a fin de aumentar la solicitud. Los conjuntos de recuperadores son una recopilación de recuperaciones individuales que realizan búsquedas en varias fuentes de datos simultáneamente.  
    

Hay dos opciones de implementar la generación aumentada por recuperación para los agentes.

*   Inicio rápido con la biblioteca de datos de Agentforce  
    
*   Configuración avanzada en Data 360  
    

Vamos a profundizar en cada opción.

### Habilitación de Data 360: Explorar la biblioteca de datos de Agentforce

La biblioteca de datos de Agentforce (ADL) es una solución rápida de generación aumentada por recuperación preconfigurada. Se trata de la fuente de datos organizados personal de sus agentes.

Al agregar una biblioteca de datos, ya sea en Agent Builder o en la configuración, Salesforce crea automáticamente una solución impulsada por generación aumentada por recuperación con Data 360 mediante la configuración predeterminada para todos los componentes: almacenamiento de datos vectoriales, índice de búsqueda y recuperador. Puede configurar y personalizar estos componentes de forma individual.

La biblioteca de datos Agentforce solo es compatible con datos sin estructurar. Aquí tiene algunos ejemplos.

*   Artículos de Knowledge  
    
*   Archivos  
    
*   Una búsqueda en Internet  
    

Obtenga más información en [Aspectos básicos de la biblioteca de datos de Agentforce](https://trailhead.salesforce.com/content/learn/modules/agentforce-data-library-basics).

### Implementación de Data 360: Personalizar la generación aumentada por recuperación completamente con la configuración de Data 360

La implementación de la generación aumentada por recuperación directamente en Data 360 conlleva más tiempo, pero le proporciona más control sobre la ingesta de datos y el procesamiento, una mayor variedad de fuentes de datos y mecanismos de recuperación precisos más allá de la búsqueda básica (como la [búsqueda híbrida](https://trailhead.salesforce.com/content/learn/modules/hybrid-search-for-rag-quick-look)).

Gracias a la configuración avanzada, puede nutrir las solicitudes con cualquier dato que se haya incorporado a Data 360. Por ejemplo, ingiera registros de CRM con campos de texto largo sin estructurar y fragmente los datos. A continuación, cree un almacenamiento de datos vectoriales y un índice de búsqueda. Utilice el recuperador del índice de búsqueda para nutrir las solicitudes. Cuando utilice estas solicitudes en sus agentes, les proporcionará amplios conocimientos sobre sus clientes y su organización. Puede proporcionar a sus agentes acceso a datos armonizados, datos sin copia y datos en tiempo real, tanto estructurados con sin estructurar.

#### Generación aumentada por recuperación con gráficos de datos

Los registros de gráficos de datos proporcionan una vista plana de datos relacionados en forma de cadena JSON que puede recuperar rápidamente. Por ejemplo, cree un gráfico de datos que moldee relaciones entre los perfiles de los clientes y los detalles de los pedidos de venta. A continuación, utilice un gráfico de datos a fin de nutrir las solicitudes para los agentes.

Estos son los beneficios principales del uso de gráficos de datos para la generación aumentada por recuperación.

*   Integra datos de varias fuentes, entre los que se incluyen datos de CRM y datos de lagos externos sin copia, sin necesidad de crear un conjunto de recuperadores.  
    
*   Convierte los datos a un formato JSON, que mantiene los datos relacionales y los agentes pueden entenderlo fácilmente.  
    

Aprenda más en [Gráficos de datos en Data 360](https://trailhead.salesforce.com/content/learn/modules/data-graphs-in-data-cloud).

Vamos a resumir las diferencias entre la biblioteca de datos de Agentforce (ADL) y la configuración personalizable de Data 360.

| **Biblioteca de datos de Agentforce** | **Configuración personalizable de Data 360** |
| --- | --- |
| *   Es necesario que Data 360 esté habilitado  <br>    <br>*   Configuración rápida y sencilla de canalizaciones de datos complejas  <br>    <br>*   Se limita a artículos de conocimientos, archivos cargados, búsqueda web abierta o recuperadores personalizados  <br>    <br>*   No integra datos de varias fuentes; cada biblioteca contiene una sola fuente de datos  <br>    <br>*   Sin capacidades de datos en tiempo real  <br>    <br>*   Sin capacidades de datos sin copia; los datos que no sean de CRM deben estar descargados físicamente como archivo y deben haberse agregado a la biblioteca de datos | *   Es necesario que Data 360 se haya implementado  <br>    <br>*   Configuración más compleja que implica ingesta, modelado, resolución de identidad, etc.  <br>    <br>*   Compatible con la integración de varias fuentes mediante conjuntos de recuperadores o gráficos de datos  <br>    <br>*   Con las conexiones de [Data Cloud One](https://trailhead.salesforce.com/content/learn/modules/data-cloud-one-quick-look), los recuperadores se sincronizan desde la organización de inicio de Data 360 hasta organizaciones adicionales, por lo que puede utilizar el recuperador en las solicitudes y flujos de las organizaciones adicionales  <br>    <br>*   Es compatible con la transformación de datos, la asignación y la armonización, por lo que se consiguen datos más ordenados y perfiles de clientes unificados  <br>    <br>*   Se nutre a los agentes con datos de Data 360, entre los que se incluyen datos armonizados, en tiempo real y sin copia, tanto estructurados como sin estructurar |

## Habilitación de Data 360: Garantizar la seguridad con protecciones de IA

La IA necesita protecciones a fin de preservar la seguridad de los datos y mantener informados a los agentes reales. De esta manera, se garantiza que el uso de la IA cumpla con las políticas de seguridad, privacidad, normativas y de gobernanza de IA de su organización.

Entre las protecciones de Agentforce se incluyen la Capa de confianza de Einstein y las auditorías de IA generativa y comentarios. Estas funciones están potenciadas por Data 360. Además, Agentforce cuenta con sus propias protecciones. Obtenga más información en [IA de agentes de confianza](https://trailhead.salesforce.com/content/learn/modules/trusted-agentic-ai).

### Explorar la Capa de confianza de Einstein

La Capa de confianza de Einstein protege los datos de los clientes gracias a protecciones y funciones sólidas de seguridad, como la cero retención de datos, la detección de toxicidad, la recuperación de datos segura y el aprovisionamiento de datos dinámico. Mejora la seguridad y la precisión de los resultados a la vez que se garantiza el uso responsable de los agentes de IA en todo el ecosistema de Salesforce.

![Diagrama de la Capa de confianza de Einstein.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-powered-agentforce/enable-trusted-agents-with-data-cloud/images/es-ES/faa628ff197d15a3fbb6181ea6849384_kix.9m9o3qie40yt.png)

### Auditoría y seguimiento de comentarios de la IA generativa

El seguimiento de auditoría proporciona los datos que necesita para rastrear las acciones y los resultados de los agentes de IA. Estos datos se almacenan y analizan en Data 360.

*   Id. de solicitud y datos del usuario  
    
*   Texto de la solicitud y solicitud de información de identificación personal enmascarada  
    
*   Seguridad y puntuación de toxicidad  
    

Puede registrar comentarios en las respuestas de los agentes mediante la API de comentarios.

*   Reacciones de aprobación o desaprobación y texto de motivos  
    
*   Acciones de aceptación, regeneración, modificación y rechazo o ignorancia  
    
*   Respuesta final modificada utilizada  
    

## Habilitación de Data 360: Explorar Agentforce Analytics

Después de que los agentes se hayan implementado, supervise el rendimiento de los mismos con Agentforce Analytics. Los datos se almacenan y se procesan en Data 360. Muestre los resultados con paneles e informes de Data 360.

Los paneles preconfigurados incluyen los siguientes datos.

*   Enmascaramiento de datos  
    
*   Toxicidad en las respuestas  
    
*   Tendencias de los usuarios  
    
*   índices de aceptación  
    

También puede crear sus propios paneles personalizados.

![Ejemplo de un panel de Agentforce Analytics predeterminado.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/data-cloud-powered-agentforce/enable-trusted-agents-with-data-cloud/images/es-ES/a424a6e5ee1a0cc9c98c8eb6481f8c3a_kix.rj6jma9m1ozv.png)

## Diferencias entre la habilitación y la implementación de Data 360

Vamos a resumir las funciones de la habilitación y la implementación de Data 360.

| **Habilitación de Data 360** | **Habilitación e implementación de Data 360** |
| --- | --- |
| *   Vista limitada del cliente  <br>    <br>*   Fuentes de datos fragmentadas  <br>    <br>*   Solicitudes con generación aumentada por recuperación mediante la biblioteca de datos de Agentforce  <br>    <br>*   IA fiable y segura con la Capa de confianza de Einstein  <br>    <br>*   IA fiable y supervisada por personas con auditoría y seguimiento de comentarios de la IA generativa  <br>    <br>*   Perspectivas de Agentforce Analytics | *   Todos los beneficios de haber habilitado Data 360  <br>    <br>*   Los agentes tienen acceso a lo siguiente:  <br>    *   Datos transformados y unificados en todas las fuentes de datos  <br>        <br>    *   Datos en tiempo real  <br>        <br>    *   Datos sin copia almacenados en sistemas externos, como lagos de datos  <br>        <br>    *   Datos mejorados con perspectivas calculadas e IA predictiva de Einstein Studio  <br>        <br>*   Solicitudes con generación aumentada por recuperación con amplias capacidades mediante la configuración avanzada de Data 360 |

## Lo próximo será lo siguiente

Ahora ya conoce las diferentes ventajas de haber habilitado o implementado Data 360 para Agentforce. También sabe cómo Data 360 potencia las capacidades de Agentforce con datos unificados, generación aumentada por recuperación, protecciones de IA y análisis. A continuación aprenderá a implementar Data 360 para Agentforce.

## Recursos

*   [_Ayuda de Salesforce_: Uso de la generación aumentada por recuperación](https://help.salesforce.com/s/articleView?id=data.c360_a_rag_overview.htm&type=5)
*   [_Ayuda de Salesforce_: Biblioteca de datos de Agentforce](https://help.salesforce.com/s/articleView?id=ai.data_library_parent.htm&type=5)
*   [_Ayuda de Salesforce_: Gráficos de datos](https://help.salesforce.com/s/articleView?id=data.c360_a_data_graphs.htm&type=5)
*   [_Ayuda de Salesforce_: Capa de confianza de Einstein](https://help.salesforce.com/s/articleView?id=ai.generative_ai_trust_layer.htm&type=5)
*   [_Ayuda de Salesforce_: Auditorías de IA generativa y datos de comentarios](https://help.salesforce.com/s/articleView?id=ai.generative_ai_feedback_about.htm&type=5)
*   [_Ayuda de Salesforce_: Agentforce Analytics](https://help.salesforce.com/s/articleView?id=ai.copilot_analytics.htm&type=5)
*   [_Trailhead_: Introducción a los informes de Data 360](https://trailhead.salesforce.com/content/learn/modules/introduction-to-data-cloud-reports)

Respuestas de la prueba:

---

**Pregunta 1 — ¿Cuál es la diferencia principal entre la biblioteca de datos de Agentforce (ADL) y la configuración totalmente personalizada de Data 360 para RAG?**

**Respuesta: A — La biblioteca de datos de Agentforce es una solución de inicio rápido preconfigurada, mientras que la configuración personalizada proporciona un mayor control sobre la ingesta y el procesamiento de datos.**

El documento describe la ADL como una "solución rápida de RAG preconfigurada" limitada a datos sin estructurar de una sola fuente, mientras que la configuración avanzada de Data 360 ofrece más control, mayor variedad de fuentes de datos y mecanismos de recuperación más precisos como la búsqueda híbrida.

---

**Pregunta 2 — ¿Cuál es una función clave de la auditoría y seguimiento de comentarios de la IA generativa impulsada por Data 360?**

**Respuesta: B — Registra datos de comentarios, como reacciones de aprobación o desaprobación, y una puntuación de seguridad para cada respuesta.**

El documento especifica que el seguimiento de auditoría almacena datos como el texto de la solicitud, la seguridad y puntuación de toxicidad, y permite registrar comentarios con reacciones de aprobación/desaprobación, acciones de aceptación/rechazo y la respuesta final modificada. Todos estos datos se almacenan y analizan en Data 360.
