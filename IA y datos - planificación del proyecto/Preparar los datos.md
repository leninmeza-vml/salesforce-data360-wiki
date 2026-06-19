Preparar los datos
==================

Objetivos de aprendizaje
------------------------

Después de completar esta unidad, podrá:

*   Explicar cómo identificar y resolver los retos de datos.  
    
*   Definir los requisitos de datos para su proyecto.  
    

Trailcast
---------

Si desea escuchar una grabación de audio de este módulo, utilice el siguiente reproductor. Cuando termine de escuchar la grabación, recuerde volver a cada unidad, consultar los recursos y completar las tareas asociadas.

La importancia de la disponibilidad de datos
--------------------------------------------

Su organización necesita tener los datos listos para empezar un proyecto de IA, lo que significa que los datos del proyecto deben ser precisos, estar disponibles, ser accesibles y estar gobernados de forma segura.

En muchas organizaciones, la calidad de los datos supone una gran barrera a la hora de implementar proyectos de IA. Y por una buena razón. Los datos son la base de los algoritmos de IA, ya que les permiten aprender, adaptar y tomar mejores decisiones. Los datos de gran calidad pueden mejorar la precisión, la eficacia, la fiabilidad y la equidad de los sistemas de IA.

Es fundamental abordar los problemas de calidad de los datos antes de implementar su proyecto de IA. Sin embargo, no deje que la idea de disponer de datos perfectos se interponga en el proyecto. Muchos proyectos se quedan estancados en la disponibilidad de los datos, ya que los equipos intentan conseguir la perfección. En su lugar, trabaje con su equipo para identificar objetivos razonables para que los datos estén disponibles. Puede utilizar la fase de creación para identificar y abordar cualquier brecha en los datos que afecte al resultado de la IA.

En esta unidad obtendrá una visión general sobre cómo evaluar la calidad de los datos y cómo prepararlos para un proyecto de IA.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Utilice la [hoja de cálculo: Predictive AI Data Prep Checklist](https://resources.docs.salesforce.com/rel1/doc/en-us/static/pdf/Predictive_AI_Data_Prep_Checklist.pdf) o la [hoja de cálculo: Generative AI Data Prep Checklist](https://resources.docs.salesforce.com/rel1/doc/en-us/static/pdf/Generative_AI_Data_Prep_Checklist.pdf) para planificar su estrategia de datos para un proyecto de IA.

Crear un inventario de datos
----------------------------

Becca sabe que la mejor manera de conseguir una visión completa de los datos para su proyecto es crear un inventario de datos. Un inventario de datos le ayuda a gestionar diversos activos de datos y a identificar posibles problemas.

Siga estos pasos para crear su inventario de datos.

1.  Identifique los datos que necesita para su proyecto.  
    
2.  Identifique dónde están almacenados los datos.  
    
3.  Responda algunas preguntas sobre los datos.  
    *   ¿Están los datos estructurados, no estructurados o semiestructurados? (Obtenga más información sobre la clasificación de los datos en [Aspectos fundamentales de los datos para la IA](https://trailhead.salesforce.com/content/learn/modules/data-fundamentals-for-ai)).  
        
    *   ¿Con qué frecuencia se actualizan los datos?  
        
    *   ¿Se actualizan los datos en tiempo real, cada hora, diariamente, una vez al mes, o de forma estática?  
        
    *   ¿Cómo se puede acceder a los datos?  
        
    *   ¿Se han implementado estándares de gobernanza para los datos?  
        
    *   ¿Cuáles son algunas de las consideraciones que pueden suponer un reto en su proyecto?  
        

Inventario de datos de Coral Cloud
----------------------------------

Vamos a continuar con el proyecto de IA de Becca para automatizar el proceso de registro en Coral Cloud Resorts. A modo de recordatorio, este es el plan de implementación de Becca con algunos puntos de datos clave en negrita.

1.  Utilizar un flujo para crear un registro de evento de huésped en función de los últimos **datos de reserva** de Data 360.  
    
2.  Enseñarle a Agentforce a iniciar el flujo mediante lenguaje conversacional. Por ejemplo, cuando la **huésped****Sofia Rodriguez** llegue para comenzar su estancia, el personal puede pedirle a Einstein que registre a Sofia Rodriguez y Einstein hará el resto.  
    
3.  Utilizar Prompt Builder (Generador de solicitudes) para generar un correo electrónico de bienvenida personalizado que sugiera **excursiones que pueden interesarle al huésped** y enviárselo.  
    

Becca revisa su plan para averiguar qué datos necesita para implementar la solución.

*   En el paso 1, necesita los datos de la reserva. Coral Cloud utiliza una plataforma externa que se llama Reserv-o-matic para almacenar los datos de la reserva, así que Becca utiliza Data 360 para incorporar esos datos en Salesforce.  
    
*   En el paso 2, necesita poder recuperar los datos de la reserva basándose en el nombre del cliente. Los datos de los clientes están disponibles en Salesforce.  
    
*   En el paso 3, necesita los datos de las excursiones anteriores que ha reservado el huésped. El historial de la reserva de los clientes también está disponible en Salesforce.  
    

Tras realizar un seguimiento de las fuentes de datos necesarias, Becca crea un inventario de datos.

**Nombre de los datos**

**Fuente de datos**

**Tipo de datos**

**Frecuencia de actualización**

**Consideraciones**

Registros de contacto

CRM

Estructurados

Diariamente

Las fechas se muestran en el formato MM/DD/AA

Reservas

Reserv-o-matic

Estructurados

En tiempo real

Las fechas se muestran en el formato DD/MM/AA

Excursiones

CRM

Estructurados

Diariamente

Las fechas se muestran en el formato MM/DD/AA

Requisitos de captura de los datos del proyecto
-----------------------------------------------

Los requisitos de datos de un proyecto son los requisitos básicos necesarios para que el proyecto sea un éxito. La comprensión de los requisitos de los datos reduce el trabajo innecesario.

### Evaluar la calidad de los datos

Los datos de gran calidad crean proyectos de IA eficaces y fiables. (Obtenga más información sobre la evaluación de la calidad de los datos en [Calidad de datos](https://trailhead.salesforce.com/content/learn/modules/data_quality)). A medida que evalúa la calidad de los datos, identifique dónde flaquean. Estas son las áreas para la limpieza de datos. La limpieza de datos es el proceso de corrección o eliminación de datos incorrectos, dañados, con el formato incorrecto, duplicados o incompletos en un conjunto de datos. Este proceso incluye acabar con la falta de datos.

La limpieza de datos puede suponer mucho tiempo; por ello, empiece con los datos de mayor prioridad que necesite para su proyecto. Primero, limpie los datos de alta prioridad que supongan menos esfuerzo y, después, los de mayor esfuerzo. En caso de que el tiempo y los recursos se lo permitan, limpie los datos de menos prioridad.

En el inventario de datos, Becca observa que las fechas de reserva se muestran en el formato DD/MM/AA, mientras que los registros de contacto y las excursiones se muestran en el formato MM/DD/AA. Las fechas no presentan un formato coherente, por lo que no se cumplen los criterios de calidad. Becca desarrolla un programa rápido para convertir todas las fechas de reserva al formato MM/DD/YY.

A medida que Becca va resolviendo otros problemas de datos, se da cuenta de que hay demasiados datos que arreglar. Coral Cloud es un complejo vacacional de primera clase donde se alojan miles de huéspedes al año. Becca se siente un poco desanimada hasta que se da cuenta de que ha estado sobreestimando los requisitos de datos de su proyecto y limpiando reservas de años anteriores. Solo tiene que filtrar las próximas reservas, ya que son las únicas que van a hacer uso del proceso de registro automatizado. Las reservas futuras son los datos de alta prioridad para el proyecto de Becca. Becca filtra las reservas por fechas futuras. Gracias a la comprensión de los requisitos de datos del proyecto, ahora tiene que trabajar con menos registros.

### Migrar e integrar datos

Cuando tiene datos procedentes de varias fuentes, debe migrar los datos. Esto significa que debe incorporar datos de distintas fuentes en una fuente central. Si su proyecto está integrado en Salesforce, incorpore los datos externos en Salesforce. Una vez que haya migrado los datos, intégrelos combinando los datos de diferentes fuentes en una sola vista completa y unificada. Migre e integre solo los datos que necesita para su proyecto. Esto le ayudará a que su proyecto sea manejable y a evitar llenar el sistema con datos innecesarios.

Como el proyecto de Becca implica crear un registro de evento de huésped basado en los datos de reserva de Reserv-o-matic y en el registro de contacto de Salesforce, sabe que necesita vincular los datos de la reserva con el registro de contacto. De lo contrario, el flujo no sabrá a qué contacto pertenece cada reserva. Becca no quiere integrar datos innecesarios, por lo que echa un vistazo a los registros de reservas a fin de identificar qué campos no son necesarios. Becca ve que las reservas tienen un campo Notes (Notas) para que los clientes lo rellenen con solicitudes especiales. No tiene un formato específico, y muchos clientes lo dejan en blanco. Becca no necesita este campo para crear un registro de evento de huésped, por lo que lo elimina antes de migrar las reservas a Salesforce.

Becca configura una transmisión de datos para incorporar los datos en Reserv-o-matic. A continuación, utiliza Resolución de identidad para que el registro de Sofia de Salesforce coincida con el de Reserv-o-matic. Ahora, el registro de Sofia cuenta con los detalles de su contacto de Salesforce y con los detalles de la reserva de Reserv-o-matic.

### Establecer la gobernanza de datos

Establezca una gobernanza de datos para proteger los datos. Becca utiliza la gobernanza de Data 360 para gestionar sus datos de manera segura con políticas de acceso, enmascaramiento de datos dinámico, etc. Obtenga más información en [Gobernanza de Data 360: un vistazo rápido](https://trailhead.salesforce.com/content/learn/modules/data-cloud-governance-quick-look).

### Planificar análisis

Elabore un plan de análisis para medir el éxito. Es importante para la supervisión del rendimiento y para la demostración del retorno de la inversión (ROI) de su proyecto. Demostrar el retorno de la inversión es fundamental para conseguir ayuda a la hora de desarrollar su proyecto o para futuros proyectos de IA.

El plan de análisis debería alinearse con los objetivos del proyecto que ya describió en la unidad anterior. A modo de recordatorio, estos son los objetivos del proyecto de Becca.

*   Reducir el tiempo de registro en un 50 %.  
    
*   Mantener la satisfacción del cliente al mismo nivel que antes del proyecto, o bien aumentarla.  
    

Becca decide recopilar y analizar datos para averiguar si el proyecto cumplió los objetivos.

*   Calcular el tiempo que se pasa frente al ordenador en la recepción a final del día. Comparar el tiempo medio que se pasa frente al ordenador antes y después de implementar el proceso de registro con IA.  
    
*   Ofrecer una encuesta opcional al final de la estancia del huésped en la que puedan medir su nivel de satisfacción. Comparar el nivel de satisfacción antes y después de implementar el proceso de registro con IA.  
    

Ahora, Becca tiene una manera concreta de demostrar el impacto de su proyecto.

Resolver los retos de datos
---------------------------

Después de definir los requisitos para su proyecto, Becca termina resolviendo los retos de datos más importantes; estos retos suelen incluir problemas de calidad, obstáculos, falta de datos y, a veces, una infraestructura de datos desactualizada. Becca sabe que si no resuelve estos problemas pronto, el nuevo proyecto de IA de Coral Cloud puede diseñarse con datos imprecisos o poco fiables.

Becca está progresando mucho en su proyecto. Ya es toda una profesional a la hora de lidiar con los datos. En la siguiente unidad, veremos cómo Becca evalúa los riesgos de su proyecto de IA e implementa el proyecto de forma fiable y responsable.

Recursos
--------

*   [_Artículo_: Is Your Data Good Enough for Your Machine Learning/AI Plans?](https://readwrite.com/is-your-data-good-enough-for-your-machine-learning-ai-plans/)

Prueba
------

Para completar esta unidad, debe responder correctamente todas las preguntas de la prueba.

1 Si tiene que limpiar muchos datos, ¿qué debería hacer?
A) Eliminar la mitad de los datos.
B) Empezar por los datos de mayor prioridad *
C) Limpiar únicamente los datos más recientes.
D) No limpiar los datos.

2 ¿Por qué es importante establecer la gobernanza de datos en un proyecto de IA?
A) Para aumentar la cantidad de datos del proyecto.
B) Para garantizar que todos los datos se actualicen en tiempo real.
C) Para garantizar la protección de los datos. *
D) Para determinar qué proyecto de IA debe desarrollar a continuación
