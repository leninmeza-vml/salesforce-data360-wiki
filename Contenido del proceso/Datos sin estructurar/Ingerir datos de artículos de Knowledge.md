# Ingerir datos de artículos de Knowledge

## Objetivos de aprendizaje

Después de este paso, podrá hacer lo siguiente:

*   Describir cómo los artículo de Salesforce Knowledge contienen datos sin estructurar.  
    
*   Explicar cómo se ingieren datos de artículos de Knowledge a partir de CRM.  
    

![Nota](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

#### Nota

¿Su idioma de aprendizaje es español? Comience el reto en un Trailhead Playground en español y utilice las traducciones proporcionadas entre paréntesis para navegar. Copie y pegue **solo los valores en inglés**, ya que las validaciones del reto se basan en los datos en inglés. Si no aprueba el reto en su organización en español, le recomendamos que (1) cambie la configuración regional a Estados Unidos, (2) cambie el idioma a inglés, siga las instrucciones [descritas aquí](https://help.salesforce.com/s/articleView?id=sf.usersetup_lang_time_zone.htm&type=5) y, a continuación, (3) vuelva a hacer clic en el botón Check Challenge (Comprobar el reto).

Consulte la insignia [Trailhead en su idioma](https://trailhead.salesforce.com/content/learn/modules/trailhead-in-your-language) para obtener más información sobre cómo aprovechar la experiencia de Trailhead en otros idiomas.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

A partir del 14 de octubre de 2025, Data Cloud ha pasado a ser Data 360. Durante esta transición, es posible que vea referencias a Data Cloud en nuestra aplicación y documentación. Aunque el nombre sea nuevo, la funcionalidad y el contenido siguen siendo los mismos.

## Utilizar datos de productos a partir de artículos de Knowledge

Los artículos de Knowledge de la base de datos de Salesforce, redactados por agentes de servicio expertos y escritores internos, son documentos que pueden incluir información sobre procesos, como la manera de restablecer el producto a los valores predeterminados, o sobre preguntas frecuentes, como la cantidad de almacenamiento de los productos.

Los artículos de Knowledge contienen datos estructurados y sin estructurar en campos de texto personalizados. Estos datos son útiles para nutrir las respuestas y las solicitudes de servicio contextualizadas para el caso de uso de un cliente.

Veamos cómo se ingieren estos datos tan valiosos.

## Ingerir datos de artículos de Knowledge desde Salesforce CRM

En Data 360, puede utilizar el paquete de artículos de Knowledge para ingerir datos de artículos de Knowledge desde su organización de Salesforce. El paquete incluye asignaciones predeterminadas para los objetos de modelo de datos pertinentes (DMO) en Data 360.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Los objetos de Knowledge se agregaron en la versión 3.0 del paquete de datos de Service Cloud.

Complete estos pasos a fin de obtener puntos para esta unidad.

1.  Si aún no lo ha hecho, inicie su Playground personalizado de Data Cloud.  
    
2.  Haga clic en App Launcher (Iniciador de aplicación), introduzca `dataCopiar` y, a continuación, haga clic en la aplicación Data Cloud.  
    
3.  En Data Cloud, vaya a la ficha **Data Streams (Transmisiones de datos)** y haga clic en **New (Nueva)**.  
    
4.  Seleccione la fuente de datos **Salesforce CRM** y haga clic en **Next (Siguiente)**.  
    
5.  Deje seleccionada la organización de Salesforce predeterminada. Seleccione el paquete de datos **Knowledge** y haga clic en **Next (Siguiente)**.  
    
6.  Revise los campos incluidos en su transmisión de datos (la selección predeterminada es perfecta para este reto) y haga clic en **Next (Siguiente)**.  
    
7.  Revise los nuevos objetos y transmisiones de datos que se van a implementar desde el kit de transmisiones de datos y haga clic en **Deploy (Implementar)**.  
    

Cuando la transmisión de datos esté lista, el estado cambiará a Active (Activa).

Para comprobar su trabajo, puede ver los DLO del artículo de knowledge junto con los UDLO en la ficha Data Lake Objects (Objetos de lago de datos) en Data 360.

## ¿Qué viene a continuación?

En la siguiente unidad, creará la configuración de un índice de búsqueda vectorial para el objeto del artículo de Knowledge.
