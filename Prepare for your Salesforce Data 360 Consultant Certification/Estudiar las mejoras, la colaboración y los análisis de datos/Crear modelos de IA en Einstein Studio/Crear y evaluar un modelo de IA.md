# Crear y evaluar un modelo de IA

## Objetivos de aprendizaje

Después de completar esta unidad, podrá:

*   Describir cómo crear un modelo con Model Builder.  
    
*   Describir el motivo por el que se utilizan las mediciones para conocer la calidad del modelo.  
    
*   Enumerar algunas mediciones que se utilizan para evaluar el rendimiento del modelo.  
    

## Crear y evaluar un modelo

Ya ha aprendido que los modelos de IA son ese sistema oculto que lo mejora todo. Con los modelos de IA, puede aumentar la inteligencia de su empresa, acelerar los flujos de trabajo, permitir que los usuarios tomen mejores decisiones, etc. En otras palabras, los modelos de IA le permiten obtener el máximo rendimiento de los datos pidiéndole a una máquina que los analice, aprendiendo al máximo sobre ellos y luego aplicando esos conocimientos a nuevos datos.

## Preparación de los datos

La mayoría del trabajo necesario para crear un modelo predictivo reside en la preparación de los datos. Por ello, los especialistas en datos o analistas deberían sentirse capaces de crear un modelo, ya que realmente conocen los datos. En la primera versión, Model Builder de Einstein Studio puede entrenar a un modelo basándose en un único objeto de modelo de datos (DMO) en Data 360.

Aunque nuestro objetivo principal es hacer que esto resulte más sencillo en el futuro, existen muchas herramientas en Data 360 que permiten que los usuarios [preparen y modelen los datos](https://help.salesforce.com/s/articleView?id=sf.c360_a_prepare_and_model_data.htm&type=5) para formar una tabla de datos que pueda representarse como un único DMO no normalizado. Este es un ejemplo de cómo las [transformaciones de datos por lotes](https://help.salesforce.com/s/articleView?id=sf.c360_a_batch_transform_overview.htm&type=5) pueden crear un objeto de modelo de datos para entrenar a un modelo.

## Pasos para crear un nuevo modelo

Cree un nuevo modelo de predictivo de IA con Model Builder en siete pasos haciendo clics, sin código. Para obtener más información, consulte [Steps to Create a Model (Pasos para crear un modelo)](https://help.salesforce.com/s/articleView?id=sf.c360_a_ai_ec_create_model_steps.htm&type=5) en la Ayuda de Salesforce.

Vamos a considerar este ejemplo de crear un modelo desde cero para predecir la probabilidad de abandono de los clientes. Siga los pasos utilizando los botones Next (Siguiente) y Previous (Anterior).

## Variables y observaciones

A modo de recordatorio de lo que ha aprendido en este módulo, un modelo predictivo utiliza aprendizaje automático para predecir resultados futuros. Al crear un modelo con Model Builder, Einstein no solo analiza los datos y crea un modelo predictivo, sino que también produce las mediciones de capacitación, de manera que puede evaluar el modelo.

**Variables**

Los modelos organizan los datos por variables. Una variable es una categoría de datos, como un campo en Salesforce o una columna en una hoja de cálculo. Los elementos conocidos como predicciones o variables explicativas se utilizan para generar predicciones.

**Observaciones**

Las predicciones se llevan a cabo en el nivel de observación. Una observación es un conjunto de datos estructurados, como un registro en Salesforce o una fila en una hoja de cálculo.

![En la imagen aparece un diagrama de flujo que muestra la manera en la que un modelo predictivo utiliza variables relacionadas con los contratos de los clientes para predecir el abandono de los clientes, lo que indica que la predicción se marca como "TRUE" (es decir, se cumple).](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/build-ai-models-in-einstein-studio/create-and-evaluate-an-ai-model/images/es-ES/33f333387247828e25cc239f3ef4278b_kix.6g04ixxdwbxt.png)

Para cada observación, el modelo utiliza un conjunto de variables de predicciones como entrada (1) y devuelve una predicción correspondiente (2) como salida. El modelo también puede devolver las principales variables que provocan el mayor impacto en la predicción. En esta ilustración, el resultado actual, el abandono, no se conoce aún.

## Mediciones de la capacitación

Los modelos que crea desde cero con Model Builder (conocidos como modelos creados por Einstein) ofrecen mediciones de la capacitación. Las mediciones de la capacitación le ayudan a conocer la manera en la que se ha entrenado el modelo de IA y a evaluar la calidad.

Las mediciones de la capacitación se calculan según los datos utilizados para evaluar su modelo. Para cada observación con un resultado (observado o real) conocido, se calcula una predicción y, después, se compara con el resultado real para determinar la precisión.

Importante: Hay muchas mediciones de la capacitación diferentes (de hecho, hay demasiadas como para verlas todas en este módulo). No se preocupe, no tiene por qué conocerlos todos (o incluso la mayoría). Las mediciones de la capacitación incluyen un icono de información ![](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/build-ai-models-in-einstein-studio/create-and-evaluate-an-ai-model/images/es-ES/4b25da150d008a2f05b6548fcd136f17_kix.oqbammjyqps1.jpg) para ayudarle a interpretar las mediciones sin tener que comprender todos los matices y cálculos implicados en el cálculo. Al proporcionar un conjunto completo de mediciones de la capacitación, puede evaluar el modelo según sus necesidades. De esta manera, puede evaluar la calidad del modelo mediante las mediciones que resulten más convenientes para su solución.

*   La precisión indica lo buena que son las predicciones en una escala desde suposiciones aleatorias hasta fuga de datos sobreajustados. Lo ideal es que cumplan su función.  
    
*   Los mejores pronosticadores son las entradas de datos, o variables de predicción, que causan un mayor impacto a la hora de predecir un resultado.  
    
*   La distribución de variables le muestra un histograma de los valores reales observados en los datos.  
    

![Página Model Training Quality (Calidad del entrenamiento del modelo)](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/build-ai-models-in-einstein-studio/create-and-evaluate-an-ai-model/images/es-ES/b3d1ef1bd077ce8a3eb0c6671b2c8d45_kix.jkcaqe3maxmy.png)

## ¿Qué es un buen modelo de datos?

En el caso de que vaya a basar las decisiones sobre su empresa en las predicciones que realiza su modelo, este debe ser muy bueno a la hora de predecir los resultados. Como mínimo, lo ideal es que el modelo mejore la predicción de los resultados en comparación con cuando no se dispone de un modelo, es decir, cuando se realizan suposiciones aleatorias que tienen como resultado una toma de decisiones carente de datos.

Entonces, ¿qué hace que un modelo sea bueno? En términos generales, un buen modelo cumple los requisitos de su solución al realizar predicciones lo suficientemente precisas como para ayudar a mejorar los objetivos en cuanto a los resultados. Dicho de forma sencilla, es necesario saber hasta qué punto los resultados predichos por el modelo coinciden con los resultados reales.

Para ayudarle a determinar el nivel de rendimiento de su modelo, los modelos creados por Einstein incluyen mediciones de la capacitación que visualizan mediciones comunes del rendimiento del modelo. Los científicos de datos reconocen esto como estadísticas de ajuste, que cuantifican el nivel de precisión de las predicciones del modelo en cuanto a los datos reales. Tenga en cuenta que los modelos son aproximaciones abstractas del mundo real, por lo que todos los modelos son inevitablemente imprecisos hasta cierto punto. De hecho, el modelo "perfecto" debería levantar sospechas, y no la esperanza.

Cuando pensamos en los modelos, resulta útil tener en cuenta la cita del estadístico George Box: "Todos los modelos son incorrectos, pero algunos son útiles".

Una vez que se sienta cómodo con la calidad de su modelo, puede activarlo a fin de que esté listo para su uso. Para obtener más información, consulte [Activate Your Model (Activar su modelo)](https://help.salesforce.com/s/articleView?id=sf.c360_a_ai_mm_activate_models.htm&type=5) en la Ayuda de Salesforce.

## Siguientes pasos

Una vez activado el modelo, es hora de ponerlo a trabajar. Póngase manos a la obra y aprenda a actuar en base a sus predicciones en [Resultados predictivos de Model Builder](https://trailhead.salesforce.com/content/learn/modules/predictive-outputs-from-model-builder/get-started-with-predictions).

## Recursos

*   [_Ayuda de Salesforce_: Prepare and Model Data (Preparar y modelar datos)](https://help.salesforce.com/s/articleView?id=sf.c360_a_prepare_and_model_data.htm&type=5)
*   [_Ayuda de Salesforce_: Transformaciones de datos por lotes](https://help.salesforce.com/s/articleView?id=sf.c360_a_batch_transform_overview.htm&type=5)
*   [_Ayuda de Salesforce_: Create a Model from Scratch (Crear un modelo desde cero)](https://help.salesforce.com/s/articleView?id=sf.c360_a_ai_ec_create_model_steps.htm&type=5)
*   [_Ayuda de Salesforce_: Evaluate Model Quality (Evaluar la calidad de los modelos)](https://help.salesforce.com/s/articleView?id=sf.c360_a_ai_ec_evaluate_model_quality.htm&type=5)
*   [_Ayuda de Salesforce_: Activate Your Model (Activar su modelo)](https://help.salesforce.com/s/articleView?id=sf.c360_a_ai_mm_activate_models.htm&type=5)
*   [_Publicación de blog_: Build an AI Model with Clicks In Data Cloud](https://www.salesforceblogger.com/2024/02/19/build-an-ai-model-with-clicks-in-data-cloud/)

## Preguntas

**Pregunta 1:** Verdadero o falso: ¿Puede crear un modelo predictivo basado en un objeto de modelo de datos de Data 360?

✅ **A — Verdadero**

El documento lo confirma: *"Model Builder de Einstein Studio puede entrenar a un modelo basándose en un único objeto de modelo de datos (DMO) en Data 360."*

---

**Pregunta 2:** ¿Qué le ayudan a comprender los mejores pronosticadores?

✅ **A — Las variables más importantes para el modelo**

El documento lo define claramente: *"Los mejores pronosticadores son las entradas de datos, o variables de predicción, que causan un mayor impacto a la hora de predecir un resultado."* Es decir, identifican qué variables tienen más peso en la predicción.