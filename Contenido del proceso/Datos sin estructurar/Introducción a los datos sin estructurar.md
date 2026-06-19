# Introducción a los datos sin estructurar en Data 360

## Objetivos de aprendizaje

Después de este paso, podrá hacer lo siguiente:

*   Definir datos sin estructurar en Data 360.  
    
*   Explicar cómo los datos sin estructurar mejoran sus estrategias de IA y de automatización.  
    
*   Describir cómo conectar datos a partir de un almacén de "blobs" externo (por ejemplo, Amazon S3).  
    

![Nota](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

#### Nota

¿Su idioma de aprendizaje es español? Comience el reto en un Trailhead Playground en español y utilice las traducciones proporcionadas entre paréntesis para navegar. Copie y pegue **solo los valores en inglés**, ya que las validaciones del reto se basan en los datos en inglés. Si no aprueba el reto en su organización en español, le recomendamos que (1) cambie la configuración regional a Estados Unidos, (2) cambie el idioma a inglés, siga las instrucciones [descritas aquí](https://help.salesforce.com/s/articleView?id=sf.usersetup_lang_time_zone.htm&type=5) y, a continuación, (3) vuelva a hacer clic en el botón Check Challenge (Comprobar el reto).

Consulte la insignia [Trailhead en su idioma](https://trailhead.salesforce.com/content/learn/modules/trailhead-in-your-language) para obtener más información sobre cómo aprovechar la experiencia de Trailhead en otros idiomas.

## ¿Qué son los datos sin estructurar?

Los datos que recopila su organización suelen ser de tres tipos: estructurados, semiestructurados y sin estructurar. Las organizaciones recopilan una gran cantidad de datos sin estructurar (cada vez más), pero solo utilizan de manera eficaz una pequeña parte de ellos. La integración de grandes cantidades de datos en flujos de trabajo puede suponer todo un reto, especialmente cuando hay que realizar búsquedas y recuperar información. Como Data 360 es compatible con los datos sin estructurar, podemos cambiar eso.

Los datos sin estructurar son datos que no tienen un formato específico y coherente, y que no pueden almacenarse de forma sencilla en una base de datos relacional. Su falta de estructura hace que resulte particularmente difícil realizar búsquedas o analizar información. Sin embargo, las tecnologías de IA, como los modelos de lenguaje grandes (LLM), pueden procesar datos sin estructurar de manera eficaz. Esta capacidad hace que muchas empresas incorporen cada vez más datos sin estructurar en sus estrategias basadas en datos.

Entre las formas más comunes de datos sin estructurar se encuentran las transcripciones de chats, archivos de vídeo y audio, correos electrónicos, documentos legales y otros tipos de textos extensos, como libros. En Salesforce, algunos ejemplo de datos sin estructurar son artículos de Knowledge o transcripciones de llamadas de ventas.

## Utilizar datos sin estructurar para mejorar sus estrategias de IA y de automatización

Al conectar sus datos sin estructurar en Data 360, puede crear resultados centrados en los clientes en su IA generativa de Einstein (Prompt Builder y Agentforce), en la automatización (Flow Builder) y en aplicaciones de análisis (Tebleau y CRM Analytics). Por ejemplo, puede mejorar las recomendaciones de respuesta del servicio mediante la generación de respuestas para los clientes con datos de artículos de Knowledge o la creación de plantilla de solicitud que utilicen correos electrónicos anteriores para generar mensajes personalizados. Si lo prefiere, puede utilizar Flow Builder y Agentforce para mostrar a los agentes de servicio datos de casos similares a fin de ayudarles en la resolución de los casos o a registrar otros nuevos.

## Conectar datos sin estructurar a partir de almacenes de "blobs" externos

Data 360 puede consultar datos sin estructurar en formato HTML, TXT y PDF (en futuras versiones habrá otros formatos adicionales). Dado que Data 360 ya es compatible con conexiones de Amazon S3, Azure Blob Storage y Google Cloud Storage, la configuración puede llevarse a cabo con tan solo unos clics y podrá incorporar sus datos sin estructurar si ya ha establecido esas conexiones.

Tras establecer una conexión entre su almacén de "blobs" externo y Data 360, podrá consultar datos sin estructurar en Data 360 mediante la creación de un objeto de lago de datos (UDLO) y la asignación del mismo a un objeto de modelo datos (UDMO).

Data 360 crea asignaciones a nivel de campo automáticamente entre los UDLL y los UDMO, ya que los esquemas de ambos objetos son idénticos. En la [Ayuda de Salesforce](https://help.salesforce.com/s/articleView?id=data.c360_a_unstructured_data_about.htm&type=5) podrá obtener más información sobre los esquemas.

La relación entre los UDLO y los UDMO puede ser 1:1 o N:1. Esto significa que cada UDLO puede asignarse, como máximo, a un UDMO; por otra parte, se pueden asignar varios UDLO a un único UDMO. Observemos un ejemplo.

Vamos a suponer que usted va a consultar datos de registros de casos de varios almacenes de "blobs" externos. Los diferentes UDLO consultan datos de estas tres fuentes: CaseRecordingsFromAWSBucket1, CaseRecordingsFromAWSBucket2, y CaseRecordingsfromGCS. Como estas fuentes son lógicamente el mismo objeto, los UDLO individuales se asignan a un UDMO: CaseRecordings.

Al conectar datos sin estructurar desde sus almacenes de "blobs" externos a Data 360, proporciona a sus administradores y usuarios un contexto más relevante a fin de ayudarles a resolver problemas, gestionar casos y crear solicitudes eficaces para las aplicaciones de IA generativa de Einstein.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Data 360 no importa datos sin estructurar; los UDMO consultan estos datos desde el almacén de "blobs" externo.

## Registrarse para conseguir un Playground personalizado con Data 360

Para completar este proyecto, necesita un Playground personalizado que contenga Data 360 y nuestros datos de ejemplo. Si todavía no ha hecho clic en el botón **Create Playground (Crear Playground)** que aparece en la parte superior de esta página, hágalo ahora. Siga los pasos para crear un Playground personalizado y conéctelo a Trailhead.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Este Playground personalizado está diseñado para trabajar con los retos de esta insignia y es posible que no funcione con otras. Compruebe siempre que está usando el Trailhead Playground o la organización de Developer Edition que le recomendamos.

Una vez que haya iniciado su Playground personalizad, estará listo para introducir el contenido desde un artículo de Knowledge como datos sin estructurar. Haga clic en el paso Verify (Comprobar) **para obtener 100 puntos** en la sección Challenge (Reto) a fin de ir al siguiente paso en el proyecto.

# Guía paso a paso: Datos sin estructurar en Data 360

## 1. Configurar el Playground

1. Haz clic en **"Create Playground"** en la parte superior de la página de Trailhead
2. Revisa tu correo de `support@salesforce.com` con las credenciales
3. Copia tu nombre de usuario y restablece tu contraseña
4. Regresa a Trailhead y haz clic en **"Conectar un Playground"**
5. Inicia sesión con tus credenciales y otorga permisos a Trailhead

---

## 2. Comprender los conceptos clave antes de practicar

Antes de entrar al Playground, asegúrate de entender estos tres puntos:

**¿Qué son los datos sin estructurar?**
Datos sin formato fijo (transcripciones, PDFs, correos, audios) que no caben fácilmente en una base de datos relacional. Ejemplos en Salesforce: artículos de Knowledge y transcripciones de llamadas.

**¿Para qué sirven en Data 360?**
Para alimentar aplicaciones como Agentforce, Prompt Builder, Flow Builder y Tableau con contexto real de tus clientes.

**¿Qué formatos soporta Data 360?**
HTML, TXT y PDF (con más formatos en versiones futuras).

---

## 3. Conectar datos sin estructurar desde un almacén externo

El flujo de conexión es el siguiente:

```
Amazon S3 / Azure Blob / Google Cloud Storage
            ↓
     Crear conexión en Data 360
            ↓
  Crear un UDLO (Unstructured Data Lake Object)
            ↓
  Asignarlo a un UDMO (Unstructured Data Model Object)
            ↓
     ¡Datos listos para consultar!
```

Puntos importantes a recordar:
- Data 360 **no importa** los datos, solo los **consulta** desde el almacén externo
- Un UDLO → máximo un UDMO (relación N:1 permitida)
- Varios UDLO pueden apuntar al mismo UDMO

---

Veo que ya estás en tu Playground de Salesforce. El error al verificar indica que aún falta completar la tarea en Data Cloud. Vamos a buscar los pasos exactos para cargar el artículo de Knowledge.¡Encontré los pasos exactos! Aquí está la guía para completar el reto:

---

## Cómo ingestar el artículo de Knowledge en Data 360

Sigue estos pasos para completar el reto y ganar los 100 puntos:

**1.** Haz clic en el **App Launcher** (el cuadro de 9 puntos, arriba a la izquierda), escribe `data` y selecciona la app **Data Cloud**.

**2.** Dentro de Data Cloud, ve a la pestaña **Data Streams** y haz clic en **New**.

**3.** Selecciona **Salesforce CRM** como fuente de datos → clic en **Next**.

**4.** Deja seleccionada la org de Salesforce por defecto. Selecciona el bundle **Knowledge** → clic en **Next**.

**5.** Revisa los campos incluidos en el data stream (la selección por defecto está bien para este reto) → clic en **Next**.

**6.** Revisa los nuevos data streams y objetos que se desplegarán → clic en **Deploy**.

**7.** Espera a que el Status cambie a **Active**.

---

## Para verificar que funcionó

Selecciona un objeto de Knowledge y revisa los mapeos de datos entre el **Data Lake Object** y el **Data Model Object** en la pestaña **Data Lake Objects**.

---

## ¿Qué sigue?

Una vez completado esto, el siguiente paso del proyecto es **crear un índice de búsqueda vectorial** para el objeto de artículo de Knowledge. ¡Ya casi terminas!