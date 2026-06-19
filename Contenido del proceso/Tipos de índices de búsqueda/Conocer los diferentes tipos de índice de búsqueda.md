# Conocer los diferentes tipos de índice de búsqueda en Data 360

## Objetivos de aprendizaje

Después de completar esta unidad, podrá:

*   Describir los índices de búsqueda compatibles con Data 360.  
    
*   Identificar el índice de búsqueda que se debe crear para su caso de uso.  
    

## Utilizar la búsqueda en Data 360 para nutrir a la IA

Al proporcionar a la IA datos específicos de los clientes, se mejora el valor de la IA generativa en aplicaciones, análisis y herramientas de automatización en la Salesforce Platform. A la IA se le pueden proporcionar datos sin estructurar, semiestructurados o estructurados. Al utilizar la solicitud del usuario para recuperar los datos de CRM pertinentes para nutrir al modelo de IA, aplicaciones como Agentforce, Tableau y Flow Builder, se garantiza que los resultados se ajusten con precisión al propósito de los usuarios. Utilice la búsqueda en Data 360 para garantizar contenido generado por IA preciso pertinente, perspectivas más profundas a partir de análisis y flujos de trabajo automatizados más eficaces para sus equipos y clientes.

En Data 360 puede crear índices de búsqueda para cualquier dato, incluidos los datos sin estructurar de las bases de conocimientos. Data 360 es compatible con los siguientes tipos de índice de búsqueda.

*   Búsqueda vectorial  
    
*   Búsqueda híbrida  
    

Para crear índices de búsqueda en Data 360, incorpore sus datos a Data 360. Data 360 ingiere datos sin estructurar, los asigna a objetos de modelo de datos (DMO) estándar o a objetos de modelo de datos sin estructurar (UDMO) y crea contenido significativo y fragmentado a partir de esos datos. A continuación, Data 360 crea incrustaciones de vectores para generar un índice de búsqueda que ayude a las aplicaciones a conocer las similitudes semánticas y léxicas con los datos.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Para conocer la definición de incrustaciones de vectores y otros términos de Data 360, consulte [Glosario de términos de Data 360](https://help.salesforce.com/s/articleView?id=sf.c360_a_glossary_guide.htm&language=en_US&type=5).

## Seleccionar un tipo de búsqueda

Antes de decidir qué tipo de búsqueda es más adecuada para su caso de uso y conjunto de datos específicos, vamos a profundizar primero en las diferencias entre ellos y en el tipo de resultado de solicitudes de búsqueda en la respuesta más pertinente.

### Búsqueda vectorial

La búsqueda vectorial, también conocida como búsqueda semántica, implica recuperar datos (o fragmentos de datos) que se parecen semánticamente para una consulta de búsqueda. Entre estos datos pueden incluirse vídeos, audios y transcripciones de llamadas. La recuperación de la búsqueda vectorial se realiza mediante la fragmentación de los datos, creando así incrustaciones de vectores y buscando incrustaciones de vectores que tengan similitudes semánticas con la consulta de búsqueda.

![Datos de varias fuentes de datos incluidos en Data 360. Data 360 fragmenta los datos y crea incrustaciones de vectores para crear un índice vectorial. Aplicaciones de C360 como Tableau, Agentforce, etc.; a continuación se consulta el índice vectorial y se obtienen resultados relevantes.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/search-index-types-data-cloud-quick-look/get-to-know-search-index-types-in-data-cloud/images/es-ES/20ca4f02377c38cbd3055996e512b270_kix.3o0nkw9edc84.png)

La búsqueda vectorial es apropiada para consultas de búsqueda extensas en las que los usuarios buscan información general. La consulta de búsqueda recupera datos con una puntuación de búsqueda vectorial alta que se correlacionan con las coincidencias semánticas más cercanas.

Por ejemplo, esta es una consulta que busca información sobre cómo funciona el navegador Google Chrome. La solicitud de búsqueda recupera fragmentos con la puntuación de búsqueda vectorial más alta, que se relacionan con la coincidencia semántica más cercana de la solicitud de búsqueda.

**Consulta:**

select c.Chunk\_c, v.score\_c from vector\_search(table(WikiArticle\_c\_vector\_search\_2\_index\_\_dlm), 'how does Google Chrome internet browser work', '', 100) as v join WikiArticle\_c\_vector\_search\_2\_ chunk\_dlm as c on v.SourceRecordId\_c=c.RecordId\_c ORDER by v.score\_c desc limit 3;

**Resultado:**

![La imagen muestra resultados de la consulta para una búsqueda vectorial en orden descendente en cuanto a la puntuación de búsqueda vectorial. Los fragmentos de datos que tienen la coincidencia semántica más cercana a la consulta de búsqueda son los resultados que aparecen más arriba.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/search-index-types-data-cloud-quick-look/get-to-know-search-index-types-in-data-cloud/images/es-ES/d9dd68da75973da706daaaad7de6f566_kix.xm1tluyx8z1c.png)

### Búsqueda híbrida

La búsqueda híbrida combina el potencial de la búsqueda vectorial semánticamente consciente con la capacidad de la búsqueda de palabras clave de gestionar el vocabulario del dominio. La búsqueda híbrida combina la información recuperada de ambos tipos de búsqueda y, a continuación, clasifica los resultados con una función de clasificación combinada a fin de mostrar la información más relevante**.**

La función de clasificación combinada de la búsqueda híbrida predeterminada se optimiza con marcadores internos para una variedad de tareas basadas en la búsqueda. Los datos de formación y evaluación se basan en solicitudes capturadas de la búsqueda de Einstein y aplicaciones de IA generativa, como Einstein Search Answers.

![Datos de varias fuentes de datos incluidos en Data 360. Data 360 fragmenta los datos y crea incrustaciones vectoriales. A partir de los datos fragmentados y vectorizados, Data 360 crea un índice de búsqueda vectorial y un índice de búsqueda de palabras clave. A continuación, la función de clasificación combinada de la búsqueda híbrida clasifica los resultados recuperados y proporciona la respuesta más relevante a las aplicaciones de C360 que solicitan los datos.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/search-index-types-data-cloud-quick-look/get-to-know-search-index-types-in-data-cloud/images/es-ES/2d533dec91ab8bd77d531f0ccfb9f4c0_kix.m0p5ypa3319g.png)

La búsqueda híbrida es una buena opción para solicitudes de búsqueda extensas en las que se incluyen términos de búsqueda específicos. La solicitud de búsqueda recupera datos con una puntuación de búsqueda de palabras clave alta que se correlacionan con las coincidencias de palabras clave exactas y una puntuación de búsqueda vectorial alta que se correlacionan con las coincidencias semánticas más cercanas. De esta manera, se recuperan datos con una puntuación de búsqueda híbrida alta que se correlacionan con los resultados de la búsqueda más relevantes.

Para el mismo ejemplo de solicitud que se ha utilizado para la búsqueda vectorial, la búsqueda de palabras clave promueve posiciones más altas de la clasificación para que el contenido sea más relevante y, por consiguiente, el LLM cuente con información más detallada.

**Consulta:**

select c.Chunk\_\_c, h.hybrid\_score\_\_c, h.keyword\_score\_\_c, h.vector\_score\_\_c from hybrid\_search(table(WikiArticle\_c\_hybrid\_search\_2\_index\_\_dlm), 'how does Google Chrome internet browser work ?', '', 100) as h join WikiArticle\_c\_hybrid\_search\_2\_chunk\_\_dlm as c on h.SourceRecordId\_\_c=c.RecordId\_\_c ORDER by h.hybrid\_score\_\_c desc limit 2;

**Resultado:**

![La imagen muestra resultados de la consulta para una búsqueda híbrida en orden descendente en cuanto a la puntuación de búsqueda híbrida. Los fragmentos de datos que tienen la coincidencia semántica y la coincidencia de palabra clave más cercanas a la consulta de búsqueda son los resultados que aparecen más arriba.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/search-index-types-data-cloud-quick-look/get-to-know-search-index-types-in-data-cloud/images/es-ES/d4e709195b114a0d63489ce2ab0a82dd_kix.g2cm395vq1ug.png)

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Para la misma consulta del ejemplo de Google Chrome, la búsqueda híbrida es mucho más potente que una búsqueda vectorial, ya que devuelve fragmentos que incluyen información sobre cómo funcionan los navegadores con detalles específicos sobre el navegador Google Chrome.

## Resumen

Cree índice de búsqueda en Data 360 para nutrir a la IA con datos sin estructurar, semiestructurados y estructurados de su organización.

Seleccione el tipo de búsqueda que le venga mejor para las solicitudes de búsqueda de sus usuarios finales y aplicaciones. Si las consultas de los usuarios son principalmente sobre información general o contienen más de cinco palabras, una búsqueda vectorial sería suficiente para esta situación. La búsqueda vectorial proporciona resultados pertinentes cuando una consulta de un usuario tiene contenido contextual, que son normalmente solicitudes más extensas.

Para conseguir los resultados más precisos y pertinentes que combinen coincidencias de búsqueda semántica y coincidencias de búsqueda de palabras clave para una solicitud, cree un índice de búsqueda híbrida.

## Recursos

*   [_Ayuda de Salesforce_: Datos sin estructurar en Data 360](https://help.salesforce.com/s/articleView?id=data.c360_a_unstructured_data_about.htm&type=5)
*   [_Ayuda de Salesforce_: Búsqueda vectorial](https://help.salesforce.com/s/articleView?id=data.c360_a_search_index_vector_index.htm&type=5)
*   [_Ayuda de Salesforce_: Búsqueda híbrida](https://help.salesforce.com/s/articleView?id=data.c360_a_hybridsearch_index.htm&type=5)
*   [_Publicación del blog Salesforce Engineering_ : How Data Cloud Hybrid Search Combines Keyword and Vector Retrieval to Elevate the Search Experience](https://engineering.salesforce.com/how-data-cloud-hybrid-search-combines-keyword-and-vector-retrieval-to-elevate-the-search-experience/)

## Preguntas de la prueba:

**Pregunta 1 — Verdadero o falso: ¿Se pueden crear índices de búsqueda en datos estructurados, semiestructurados y sin estructurar?**

**Verdadero (A).** El documento indica claramente que en Data 360 se pueden crear índices de búsqueda para cualquier dato, incluyendo los tres tipos mencionados.

---

**Pregunta 2 — ¿Qué tipo de búsqueda es más adecuado para combinar coincidencia semántica y coincidencia de palabras clave?**

**Búsqueda híbrida (B).** El documento lo explica así: la búsqueda híbrida combina lo mejor de ambos mundos — la capacidad semántica de la búsqueda vectorial con la precisión léxica de la búsqueda de palabras clave — y luego clasifica los resultados con una función de clasificación combinada para ofrecer la información más relevante.
