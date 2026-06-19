Planear la estrategia de confianza
==================================

Objetivos de aprendizaje
------------------------

Después de completar esta unidad, podrá:

*   Crear un perfil de riesgos mediante la evaluación de riesgos de IA para su proyecto.  
    
*   Implementar protecciones basadas en el perfil de riesgos.  
    

Trailcast
---------

Si desea escuchar una grabación de audio de este módulo, utilice el siguiente reproductor. Cuando termine de escuchar la grabación, recuerde volver a cada unidad, consultar los recursos y completar las tareas asociadas.

Primeros pasos con la confianza
-------------------------------

La IA tiene ciertos riesgos. ¿Cómo puede saber si su solución de IA es ética, segura y responsable? Debe crear una estrategia de confianza.

La estrategia de confianza de su proyecto es su plan para mitigar riesgos, como mantener los datos confidenciales seguros, cumplir los requisitos normativos y proteger la reputación de su empresa.

El primer paso a la hora de definir su estrategia de confianza es crear un perfil de riesgos para su proyecto. Un perfil de riesgos informa sobre la manera en que gestiona y da prioridad a los riesgos de un proyecto. Cubre el tipo y el nivel de los riesgos, la probabilidad de que tengan efectos negativos y el nivel de inestabilidad o costes para cada tipo de riesgo. Un perfil de riesgos eficaz le indica a qué riesgos debe dar prioridad.

Áreas de riesgos
----------------

Responda preguntas en las tres áreas de riesgos a fin de crear su perfil de riesgos: fugas de datos, requisitos normativos y daño de la reputación. Como ejemplo, vamos a ver cómo Becca responde estas preguntas para su proyecto.

**Área de riesgo**

**Descripción**

**Preguntas para realizar**

**Respuesta de Becca**

Fugas de datos

Las fugas de datos se producen cuando la información segura se ve expuesta de manera accidental. Puede ocurrir debido a un ciberataque, acceso no autorizado o la exposición de datos confidenciales en modelos de IA externos. Para evitar las fugas de datos, almacene los datos de manera segura y compruebe que solo los usuarios autorizados puedan acceder a ellos. Esta área de riesgo también incluye la protección de datos confidenciales, como la información de identificación personal (PII).

*   ¿Qué significa que haya oportunidades de fugas de datos en su proyecto?  
    
*   ¿Qué datos confidenciales está utilizando?  
    

Becca sabe que Coral Cloud cuenta con un sistema seguro para el almacenamiento de datos. Sin embargo, su proyecto incluye el enfoque human-in-the-loop, o interacciones humanas, en el que alguien desencadena el proceso de registro pidiéndole a Einstein que realice el registro de un huésped.

Becca ve que existe la posibilidad de que se produzca una fuga de datos, ya que el usuario que ejecuta la acción puede averiguar dónde se hospeda la persona y en qué fecha. Resulta peligroso que ese tipo de información se filtre y quede a disposición de una persona no autorizada.

El proyecto de Becca incluye datos confidenciales, como nombres completos, información de contacto e información de la tarjeta de crédito.

Requisitos normativos

Asegúrese de que su proyecto cumpla los requisitos legales de la jurisdicción y el sector en el que opera. Si no cumple todas las normativas, podría enfrentarse a multas, daño de reputación y otras repercusiones legales. El equipo legal que identificó en la primera unidad puede ayudarle a identificar y cumplir todas las normativas.

*   ¿Qué normativas debe cumplir su proyecto?  
    

Como Coral Cloud opera en la UE, el proyecto de Becca debe seguir el Reglamento General de Protección de Datos (GDPR). Becca se pone en contacto con el equipo legal para pedirle que investigue qué otras normativas debe cumplir.

Daño de la reputación

Dado que en su proyecto de IA se interactúa con clientes, este representa a la empresa. La IA puede llegar a generar respuestas dañinas o falsas debido a la toxicidad de conjuntos de datos o ataques técnicos.

*   Si su proyecto no sale bien, ¿qué impacto tiene en su reputación?  
    

Si los correos electrónicos de bienvenida generados por IA incluyen lenguaje ofensivo, las personas pensarán que los trabajadores de Coral Cloud son ofensivos y antipáticos. Como resultado, perderán clientes valiosos y potenciales. En el sector de la hostelería, Becca sabe que perder la reputación es un problema muy grave.

Crear un perfil de riesgos
--------------------------

Según la evaluación de las diferentes áreas de riesgos, Becca crea un perfil de riesgos para su proyecto. 1 representa un riesgo muy bajo y 5 representa un riesgo muy alto.

**Tipo de riesgo**

**Nivel de efectos negativos**

**Probabilidad de efectos negativos**

**Inestabilidad o costes**

Fugas de datos

4: Si hay fugas de datos, la seguridad y privacidad de los huéspedes se ve afectada.

3: Los datos de Coral Cloud se almacenan de forma segura, pero deben implantarse otros controles para abordar el riesgo.

4: Pérdida de la confianza de los clientes

Requisitos normativos

5: Coral Cloud se enfrenta a multas, otras consecuencias legales y a la pérdida de la confianza de los clientes.

5: Si el proyecto de Becca no cumple las normativas, es muy probable que Coral Cloud se enfrente a consecuencias negativas.

5: Consecuencias legales, multas y pérdida de la confianza de los clientes

Daño de la reputación

5: Si se daña la reputación de Coral Cloud, perderán posibles huéspedes y beneficios.

4: Becca debe ajustar su solicitud e implementar otras maneras de protegerse de los daños de reputación.

4: Pérdida de la confianza de los clientes

Basándose en el perfil de riesgos, Becca decide dar prioridad a los requisitos normativos en primer lugar y, después, al daño de la reputación y a las fugas de datos. Empieza a planificar la manera en la que se debe gestionar cada riesgo.

Tipos de protecciones
---------------------

Ahora que ya conoce los riesgos, implemente las protecciones de IA. Las protecciones de IA son mecanismos para garantizar que su proyecto de IA se esté ejecutando se forma legal y ética. Necesita protecciones para evitar que la IA cause daños con decisiones sesgadas, lenguaje tóxico y exposición de datos. Las protecciones son necesarias para impedir ataques técnicos.

Hay tres tipos de protecciones de IA: protecciones de seguridad, técnicas y éticas.

### Protecciones de seguridad

Estas protecciones garantizan que el proyecto cumpla las leyes y normativas, y que los datos privados y derechos humanos estén protegidos. Entre las herramientas más comunes se incluyen la recuperación de datos segura, el enmascaramiento de datos y cero retención de datos.

La recuperación de datos segura implica que su proyecto solo acceda a los datos para los que el usuario que ejecuta la acción tiene autorización. Por ejemplo, si una persona que no tiene acceso a los registros financieros desencadena una respuesta del modelo de IA, el modelo no debería recuperar los datos relacionados con los registros financieros. El enmascaramiento de datos hace que se reemplacen los datos confidenciales por datos de marcadores antes de exponerlos para los modelos externos. Así, se garantiza que los datos confidenciales no estén en peligro. Los proveedores de modelos refuerzan las políticas de cero retención de datos, lo que significa que los datos no se almacenan una vez que se satisfacen las necesidades inmediatas de la tarea. Por ello, una vez que se haya generado la respuesta, los datos utilizados desaparecerán.

### Protecciones técnicas

Estas protecciones evitan que se produzcan ataques técnicos en el proyecto llevados a cabo por un hacker, como ataques de inyección de solicitudes y fuga, u otros métodos para hacer que el modelo exponga información confidencial. Los ciberataques pueden provocar que su proyecto genere respuestas falsas o dañinas.

### Protecciones éticas

Estas protecciones hacen que su proyecto se mantenga alineado con los valores humanos. Esto incluye el análisis en busca de toxicidad y sesgo.

La toxicidad se produce cuando un modelo de IA genera contenido lleno de odio, violento, soez u obsceno. El sesgo se produce cuando la IA refleja estereotipos dañinos, como los que hacen referencia a la raza o al género. Como podrá imagina, eso sería un desastre. Dado que la IA aprende sus respuestas, la toxicidad y el sesgo podrían ser un indicio de que los datos introducen lenguaje e ideas no deseados en su modelo. La detección de la toxicidad identifica respuestas que pueden contener lenguaje tóxico, de manera que pueda revisarla de forma manual y realizar ajustes para reducirla.

Ahora ya conoce los tipos de protecciones y la manera en la que protegen su proyecto de los riesgos. A continuación, vamos a ver cómo Becca implementa protecciones en su estrategia de confianza.

Estrategia de confianza de Coral Cloud
--------------------------------------

La implementación de su estrategia de confianza será diferente según el sistema que utilice. Como Becca utiliza Salesforce, su estrategia de confianza está diseñada en la Capa de confianza de Einstein. La capa de confianza es una colección de funciones, procesos y políticas diseñados para proteger la privacidad de los datos, mejorar la precisión de la IA y promover el uso responsable de la IA en todo el ecosistema de Salesforce. Cuando crea un proyecto con las funciones de la IA generativa de Einstein, como Prompt Builder (Generador de solicitudes) en el proyecto de Becca, el proyecto pasa automáticamente pasa por la Capa de confianza.

Becca define una estrategia de confianza que aborde todas las áreas de riesgos, mediate el uso de funciones en la capa de confianza. Además, visualiza el resultado deseado. Este es un extracto de su estrategia de confianza.

![La Capa de confianza de Einstein procesa las solicitudes y genera respuestas de forma segura.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/ai-data-project-planning/plan-your-trust-strategy/images/es-ES/b7e7e25de679f0a6b881906d59a9cf00_kix.ckaki44tipkq.png)

**Área de riesgo**

**Estrategia de confianza de Becca**

**Funciones de la capa de confianza**

**Resultados**

Fugas de datos

*   Evitar que los usuarios no autorizados accedan a la información protegida.  
    
*   Proteger los nombres, la información de contacto y la información de la tarjeta de crédito de los huéspedes con el enmascaramiento de datos.  
    

*   Recuperación de datos segura y vinculación.  
    
*   Enmascaramiento de datos  
    

*   Los usuarios que no tengan acceso a los detalles de la reserva no podrán utilizar la solicitud para acceder a dichos detalles.  
    
*   La información confidencial no se introduce en los LLM de terceros.  
    

Daño de la reputación

*   Utilizar las políticas del sistema para indicar a la solución de IA cómo debe comportarse ante las solicitudes inesperadas. Esto hace que se proteja la solución de los ataques técnicos que motivan a generar respuestas incorrectas o dañinas.  
    

*   Defensa de la solicitud  
    

*   Los ataques técnicos no funcionarán debido a las políticas de defensa de la solicitud. Por ejemplo, si una persona que no pertenezca al sistema de Coral Cloud intenta hacer un registro, la solución de IA no generará ninguna respuesta.  
    

Antes de que Becca termine su estrategia de confianza, se reúne con su equipo legal y de seguridad para asegurarse de que no haya lagunas.

Siguientes pasos
----------------

Una vez diseñada la estrategia de seguridad, Becca ya ha terminado de planificar su proyecto. Ya está lista para empezar la fase de creación, en la que implementará su proyecto en Salesforce. Siga el proyecto de Becca en [Conectar Data 360 a Agentforce y Prompt Builder](https://trailhead.salesforce.com/content/learn/projects/connect-data-cloud-to-copilot-and-prompt-builder).

A medida que va creando su proyecto, tenga en cuenta que mitigar el riesgo no es una tarea que solo se lleve a cabo una vez. Tras implementar su proyecto, supervise el riesgo y lleve a cabo una auditoría de manera continua. La supervisión le ayudará a identificar tendencias problemáticas con anterioridad y podrá realizar ajustes. Revise la puntuación de toxicidad y los comentarios para identificar en qué ha fallado la solución y realice ajustes a fin de eliminar los factores de riesgo.

Resumen
-------

Este módulo explica los pasos fundamentales a la hora de prepararse para su proyecto de IA. Ahora ya sabe cómo identificar las partes interesadas del proyecto, establecer objetivos y elegir una solución técnica. Ya sabe cómo preparar datos de gran calidad y cumplir los requisitos de su proyecto. Además, ya sabe cómo una estrategia de confianza mitiga los riesgos de su proyecto y por qué es importante supervisar dichos riesgos.

Con estos conocimientos, está en el buen camino para iniciar un proyecto de IA con éxito. Antes de empezar con la implementación, asegúrese de completar el módulo [Gestión de cambios para la implementación de IA](https://trailhead.salesforce.com/content/learn/modules/change-management-for-ai-implementation).

Recursos
--------

*   [_PDF_: NIST Artificial Intelligence Risk Management Framework](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf)
*   [_Hoja de cálculo de Excel_: NIST AI Risk Assessment Template](https://airc.nist.gov/docs/Template_Google_DeepMind_gap_analysis-NIST_AIRMF_1.0.xlsx)
*   [_PDF_: Building Trust in AI with a Human at the Helm](https://www.salesforce.com/content/dam/web/en_us/www/documents/company/human-at-the-helm.pdf)
*   [_Trailhead_: Gestión de cambios para la implementación de IA](https://trailhead.salesforce.com/content/learn/modules/change-management-for-ai-implementation)
*   [_Trailhead_: Capa de confianza de Einstein](https://trailhead.salesforce.com/content/learn/modules/the-einstein-trust-layer)
*   [_Artículo_: AI-Powered Cyberattacks](https://www.crowdstrike.com/cybersecurity-101/cyberattacks/ai-powered-cyberattacks/)
*   [_Artículo_: Understanding Why AI Guardrails Are Necessary: Ensuring Ethical and Responsible AI Use](https://www.aporia.com/learn/ai-guardrails/)
*   [_PDF_: Mitigating LLM Risks Across Salesforce’s Gen AI Frontiers](https://cdn.buttercms.com/0hpTOIaRya9G15UkZ0P7)

Prueba
------

Para completar esta unidad, debe responder correctamente todas las preguntas de la prueba.

1 ¿Cuáles son las tres áreas principales de riesgo que se deben tener en cuenta a la hora de crear un perfil de riesgos?
A) Toxicidad, sesgo y ataques técnicos
B) Fugas de datos, requisitos normativos y daño de la reputación *
C) Protecciones de seguridad, protecciones éticas y protecciones técnicas
D) Enmascaramiento de datos, recuperación de datos segura y defensa de solicitudes

2 ¿Qué protecciones evitan las fugas de datos?
A) La detección de toxicidad
B) Defensa de la solicitud
C) Seguimiento de auditorías
D) Enmascaramiento de datos *
