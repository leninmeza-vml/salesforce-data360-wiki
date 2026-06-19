# Aumentar agentes y solicitudes con el conocimiento empresarial pertinente

## Objetivos de aprendizaje

Después de completar esta unidad, podrá:

*   Explicar por qué la generación aumentada por recuperación (RAG) mejora la precisión y la importancia de las respuestas del LLM en las plantillas de agentes y de solicitud.  
    
*   Describir cómo configurar y utilizar la generación aumentada por recuperación en su organización de Salesforce.  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

**¡Nueva experiencia de creación de agentes muy pronto!**

¡Agentforce se actualiza! En Dreamforce 2025, anunciamos la nueva experiencia de creación de agentes que puede ser diferente del proceso y las funciones que se aprenden en esta insignia. Esperamos que la nueva experiencia esté disponible en versión beta unas semanas después de la Dreamforce. La disponibilidad general será un poco después. La experiencia de creación actual sigue estando disponible para admitir los agentes que se hayan creado previamente. Permanezca atento para mantenerse informado.

## ¿Qué es la generación aumentada por recuperación?

La generación aumentada por recuperación (RAG) es una manera popular de nutrir solicitudes para los modelos de lenguaje grandes (LLM). Con el aprovisionamiento de datos se agregan conocimientos o información del cliente a la solicitud, proporcionando al LLM el contexto que necesita para responder a una pregunta o tarea de una forma más precisa.

![Flujo de tiempo de ejecución de la generación aumentada por recuperación: la solicitud del LLM aumentada con información pertinente a fin de ordenar al LLM la generación de una respuesta.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/retrieval-augmented-generation-quick-look/augment-prompts-with-relevant-knowledge/images/es-ES/1c6bea0309f0497da032e820853bca5f_kix.pc023llbylg.png)

Vamos a desglosar el proceso de generación aumentada por recuperación:

1.  _Se recupera_ información importante de un almacén de conocimientos que contenga datos estructurados y sin estructurar.  
    
2.  _Se aumenta_ la solicitud mediante la combinación de esta información con la solicitud original.  
    
3.  Con la solicitud aumentada, el LLM _genera_ una respuesta.  
    

Muchos LLM se entrenan, de forma general, en internet con contenido estático y disponible públicamente. La generación aumentada por recuperación agrega información específica de un dominio para ayudar a los LLM a proporcionar mejores respuestas para las solicitudes. Con la generación aumentada por recuperación, puede extraer información de gran valor de todo tipo de contenido, como respuestas de servicio, casos, artículos de conocimiento, transcripciones de conversaciones, respuestas a solicitudes de propuestas, correos electrónicos, notas de reuniones, preguntas frecuentes (FAQ), etc.

## Soluciones rápidas de Agentforce con Agentforce Builder y la biblioteca de datos de Agentforce

Agentforce Builder permite seleccionar artículos de conocimiento o cargar archivos para que los agentes los recuperen con tan solo unos clics. Puede hacerlo seleccionando o creando una [biblioteca de datos de Agentforce](https://help.salesforce.com/s/articleView?id=ai.data_library_parent.htm), que abarca el contenido que utiliza el agente para responder preguntas. Seleccione la fuente de la que la biblioteca de datos extrae la información pertinente: base de conocimientos de Salesforce, archivos que haya cargado (de texto, HTML y PDF) o una búsqueda web. En el tiempo de ejecución, su agente utiliza esta información para nutrir las solicitudes del LLM y que este genere respuestas mejores, más precisas y relevantes.

Al agregar una biblioteca de datos, se crearán automáticamente todos los elementos necesarios para una solución impulsada por generación aumentada por recuperación que funcione. Si lo desea, puede personalizar estos elementos para ajustar las soluciones de generación aumentada por recuperación para sus casos de uso. Esto lo veremos más adelante.

## Obtener conocimientos empresariales pertinentes en los agentes

Los agentes obtienen conocimientos pertinentes de una biblioteca de datos con la acción estándar [Answer Questions with Knowledge (Responder preguntas con Knowledge)](https://help.salesforce.com/s/articleView?id=sf.copilot_actions_ref_answer_questions_with_knowledge.htm). Esta acción recupera información de forma dinámica del contenido del archivo que haya especificado a la hora de crear o seleccionar una biblioteca.

![Flujo detallado de tiempo en ejecución de la generación aumentada por recuperación para agentes: responda preguntas con acciones de Knowledge, solicitudes y respuestas de consultas, solicitudes aumentadas y reenvío de respuestas del LLM al agente.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/retrieval-augmented-generation-quick-look/augment-prompts-with-relevant-knowledge/images/es-ES/95a2f06b40168dff587fab1ced23fe43_kix.grpqnua87xdz.png)

Cada vez que se ejecute la acción Answer Questions with Knowledge (Responder preguntas con Knowledge):

1.  La acción ejecuta la plantilla de solicitud asociada. El recuperador se activa con una consulta dinámica.  
    
2.  La consulta busca en la biblioteca de datos.  
    
3.  La consulta recupera el contenido pertinente.  
    
4.  La solicitud original se rellena con información recuperada de la biblioteca de datos y, a continuación, se envía al LLM.  
    
5.  La respuesta generada por el LLM se envía al agente.  
    

## Obtener conocimientos empresariales pertinentes en las solicitudes

En el tiempo de ejecución, las plantillas de solicitud extraen información pertinente de la biblioteca de datos para nutrir las solicitudes del LLM, a fin de conseguir respuestas más precisas. Si utiliza una plantilla de solicitud personalizada, en Prompt Builder, integre un recuperador de búsqueda de Einstein que seleccione al insertar una fuente. También puede utilizar un recuperador personalizado que ajuste la configuración de la búsqueda para cada solicitud proporcionada.

![Flujo detallado de tiempo en ejecución de la generación aumentada por recuperación: consulte, vectorice, recupere contenido relevante, aumente y envíe contenido al LLM.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/retrieval-augmented-generation-quick-look/augment-prompts-with-relevant-knowledge/images/es-ES/1a14376292ee9e05a1389558560e7294_kix.ur2xzk5e75xe.png)

Cada vez que se ejecute una plantilla de solicitud con un recuperador:

1.  El recuperador se activa con una consulta dinámica iniciada a partir de la plantilla de solicitud.  
    
2.  La consulta se vectoriza (se convierte en representaciones numéricas). La vectorización habilita la búsqueda de coincidencias semánticas en el índice de búsqueda (que ya se ha vectorizado).  
    
3.  La consulta recupera el contenido pertinente de los datos indexados en el índice de búsqueda.  
    
4.  La solicitud original se rellena con la información recuperada del índice de búsqueda.  
    
5.  La solicitud se envía al LLM, que genera y devuelve la respuesta de la solicitud.  
    

## Personalización avanzada en Data 360

Al agregar una biblioteca de datos, ya sea en Agentforce Builder o en la configuración, Salesforce crea automáticamente una solución impulsada por generación aumentada por recuperación con la configuración predeterminada de todos los componentes: almacenamiento de datos vectoriales, índice de búsqueda, recuperador, plantilla de solicitud y acción estándar. Puede configurar y personalizar estos componentes de forma individual.

![Pasos de preparación de los datos: ingerir, fragmentar, vectorizar e indexar.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/retrieval-augmented-generation-quick-look/augment-prompts-with-relevant-knowledge/images/es-ES/2c2a876a132293ac5b8fb860930d2a18_kix.5gv0v4t35wbj.png)

La preparación de los datos implica estas tareas en Data 360.

1.  Conecte (ingiera) sus datos sin estructurar.  
    
2.  Cree una configuración de índice de búsqueda que fragmente y vectorice el contenido. Data 360 utiliza un índice de búsqueda para gestionar contenido estructurado y sin estructurar de manera que se optimice la búsqueda. Tiene dos opciones de búsqueda: búsqueda vectorial y búsqueda híbrida. La búsqueda híbrida combina la búsqueda vectorial y la búsqueda de palabras clave.  
    *   En el proceso de fragmentación se desglosa el texto en unidades más pequeñas, reflejando así las partes del contenido original, como frases o párrafos.  
        
    *   En el proceso de vectorización se convierten los fragmentos en representaciones numéricas del texto que capturan similitudes semánticas.  
        
3.  Almacene y gestione el índice de búsqueda.  
    

Después de crear un índice de búsqueda, cree un recuperador en Einstein Studio que busque información pertinente en el índice de búsqueda para un caso de uso específico. Un recuperador es un recurso que se inserta en una plantilla de solicitud para buscar y devolver información relevante del almacén de conocimientos. Para buscar la compatibilidad con una variedad de casos de uso, puede crear diferentes recuperadores que centren la búsqueda en el subconjunto de información pertinente a fin de agregarla a la solicitud.

## Ver la generación aumentada por recuperación en acción

En este vídeo se muestra lo sencillo que resulta aumentar una plantilla de solicitud mediante este proceso.

## Conclusión

La biblioteca de datos de Agentforce y la generación aumentada por recuperación en Data 360 se integran con la plataforma de IA generativa de Einstein. Se incorpora la funcionalidad de la generación aumentada por recuperación en aplicaciones listas para usar, como Agentforce Builder y Prompt Builder. Con la generación aumentada por recuperación, puede nutrir y mejorar las soluciones de Agentforce de forma segura con los datos adecuados a partir de un modelo de datos armonizados.

## Recursos

*   [_Ayuda de Salesforce_: Datos sin estructurar en Data 360](https://help.salesforce.com/s/articleView?id=sf.c360_a_unstructured_data_about.htm&type=5)
*   [_Ayuda de Salesforce_: Data 360: datos fragmentados y vectorizados](https://help.salesforce.com/s/articleView?id=sf.c360_a_search_index_grounding.htm&type=5)
*   [_Ayuda de Salesforce Help_: Data 360: búsqueda vectorial](https://help.salesforce.com/s/articleView?id=sf.c360_a_search_index_vector_index.htm&type=5)
*   [_Ayuda de Salesforce_: Data 360: Búsqueda híbrida](https://help.salesforce.com/s/articleView?id=data.c360_a_hybridsearch_index.htm&type=5)
*   [_Ayuda de Salesforce_: Ejemplo: Generación aumentada por recuperación de agentes con la configuración avanzada de Data 360](https://help.salesforce.com/s/articleView?id=ai.generative_ai_rag_example.htm&type=5)
*   [_Trailhead_: Aspectos básicos de la biblioteca de datos de Agentforce](https://trailhead.salesforce.com/content/learn/modules/agentforce-data-library-basics)
*   [_Trailhead_: Datos no estructurados en Data 360](https://trailhead.salesforce.com/content/learn/projects/unstructured-data-in-data-cloud)
*   [_Trailhead_: Tipos de índices de búsqueda en Data 360: un vistazo rápido](https://trailhead.salesforce.com/content/learn/modules/search-index-types-data-cloud-quick-look)
*   [_Trailhead_: Búsqueda híbrida para la generación aumentada por recuperación: un vistazo rápido](https://trailhead.salesforce.com/content/learn/modules/hybrid-search-for-rag-quick-look)
*   [_Salesforce Blog_: RAG – The Hottest 3 Letters in Generative AI Right Now](https://www.salesforce.com/blog/what-is-retrieval-augmented-generation/)
*   [_Salesforce Blog_: Agentforce and RAG: Best Practices for Better Agents](https://www.salesforce.com/content/dam/web/en_us/www/documents/article/agentforce_and_rag_best_practices_for_better_agents.pdf)

¡Aquí están las respuestas de la prueba!

---

**Pregunta 1 — ¿Por qué utilizaría la generación aumentada por recuperación (RAG) en sus solicitudes?**

**Respuesta: A — Porque mejora la precisión y la importancia de las respuestas del LLM.**

El documento explica que RAG agrega información específica de un dominio para ayudar a los LLM a proporcionar respuestas más precisas y relevantes, combinando la solicitud original con información recuperada de un almacén de conocimientos.

---

**Pregunta 2 — En una plantilla de solicitud, ¿qué debe agregar para activar la generación aumentada por recuperación?**

**Respuesta: B — Un recuperador de búsqueda de Einstein.**

El documento indica que en Prompt Builder debes integrar un **recuperador de búsqueda de Einstein** al insertar una fuente, el cual busca y devuelve información relevante del almacén de conocimientos para nutrir la solicitud enviada al LLM.