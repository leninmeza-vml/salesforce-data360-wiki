# Data 360 (Data Cloud) - Preguntas y Respuestas

## INFORMACIÓN GENERAL DE DATA 360

### ¿Qué es Data 360?
Data 360 (anteriormente Data Cloud) es una plataforma de datos de clientes que:
- Unifica datos de múltiples fuentes en perfiles comprehensivos
- Procesa datos estructurados y no estructurados
- Permite análisis en tiempo real y activación de datos
- Se integra nativamente con Salesforce Platform
- Puede procesar billones de registros y petabytes de datos

### Los 5 Pilares Principales de Data 360

1. **Connect (Conectar)**
   - Conectar datos de cualquier fuente (Salesforce, sistemas externos, data lakes)
   - Más de 275 conectores preconstruidos
   - Zero Copy Data Federation (sin duplicar datos)
   - Ingesta por lotes y streaming

2. **Harmonize (Armonizar)**
   - Transformar y limpiar datos
   - Batch y Streaming Data Transforms
   - Formula Fields para ajustes
   - Mapear al Customer 360 Data Model

3. **Unify (Unificar)**
   - Identity Resolution (resolución de identidad)
   - Match Rules (reglas de coincidencia)
   - Reconciliation Rules (reglas de conciliación)
   - Crear perfiles unificados de clientes

4. **Analyze and Predict (Analizar y Predecir)**
   - Calculated Insights (perspectivas calculadas)
   - Modelos de IA/ML en Einstein Studio
   - Analytics con Tableau
   - KPIs y métricas de negocio

5. **Act (Actuar)**
   - Segmentación de audiencias
   - Activación en múltiples canales
   - Data Actions y Flows
   - Agentforce (agentes de IA)

---

## PREGUNTAS Y RESPUESTAS DEL EXAMEN

### Módulo: Fundamentos de Data 360

**P1: ¿Qué es Data 360?**
- **R: C** - Una plataforma centralizada para conectar y unificar datos de fuentes dispares para análisis y activación

**P2: ¿Qué valor aporta Data 360 a equipos de servicio con agentes de IA?**
- **R: B** - Mayor eficiencia con tasas de resolución más altas y horas de servicio reducidas, permitiendo que humanos se enfoquen en problemas más complejos

---

### Módulo: Etapas de Procesamiento de Data 360

**P1: ¿Cuál es el nombre y orden correcto de las etapas de procesamiento?**
- **R: C** - Connect Data | Harmonize and Unify | Analyze and Act

**P2: Después de conectar datos, ¿cuál es el siguiente paso?**
- **R: A** - Transformar, preparar y unificar datos

---

### Módulo: Estrategias de Datos Centradas en el Cliente

**P1: ¿Cuál es el beneficio de poner a los clientes primero al planificar arquitectura de datos?**
- **R: C** - Es posible encontrar brechas en la experiencia de cliente

**P2: ¿Qué es una trayectoria de cliente?**
- **R: B** - Una representación visual de las experiencias de un cliente con la compañía en el tiempo

**P3: ¿Qué se puede lograr al trazar un mapa de trayectoria de cliente?**
- **R: A** - Iniciar conversaciones con compañeros que tienen interés en el éxito de sus clientes

**P4: ¿Qué se puede descubrir al trazar un mapa de trayectoria de cliente?**
- **R: E** - B y C (Transferencias ineficientes Y tareas candidatas para automatización)

---

### Módulo: Investigación y Priorización

**P1: Al usar trayectoria de cliente para arquitectura de datos, ¿con qué comenzar?**
- **R: B** - Un proyecto que aborde una necesidad inmediata y proporcione una gran victoria

**P2: ¿Cómo puede la automatización mejorar la experiencia del cliente?**
- **R: C** - Es posible reducir el tiempo de llamada promedio, disminuyendo tiempos de espera

---

### Módulo: Valor de Data 360

**P1: ¿Cuál es el beneficio principal de Identity Resolution?**
- **R: B** - Crea perfiles unificados para una vista comprehensiva del cliente

**P2: ¿Qué es importante al crear un caso de uso?**
- **R: A** - Identificar requisitos de negocio y resultados deseados

---

### Módulo: Justificación de Inversión

**P1: Al calcular ROI para segmentación de marketing automatizada, ¿qué factor es MENOS probable que sea componente directo?**
- **R: D** - Lead revenue amount

**P2: ¿Qué dos cosas considerar al determinar ROI?**
- **R: A** - Cálculos de KPI y consumo de créditos

---

### Módulo: Consumo de Créditos

**P1: Armonizar 500,000 filas con multiplicador de 100,000 y unidad de 1,000,000. ¿Cuántos créditos se consumen?**
- **R: A** - 50,000 créditos
- Fórmula: (500,000/1,000,000) × 100,000 = 50,000

**P2: ¿Cómo reducir consumo de créditos para batch calculated insight?**
- **R: D** - B y C (Refrescar diariamente en vez de cada hora Y ejecutarlo con menos datos)

---

### Módulo: Datos, IA y CRM

**P1: ¿Ejemplo de uso de IA en marketing?**
- **R: D** - Crear páginas de destino personalizadas para clientes

**P2: ¿Qué establece las bases de una estrategia exitosa de IA?**
- **R: B** - Confianza

---

### Módulo: Cómo Funciona Data 360

**P1: ¿Cómo unifica Data 360 los datos para crear perfil unificado?**
- **R: C** - Con conjuntos de reglas de Resolución de identidad

**P2: ¿Cómo actuar en base a datos de Data 360 en Customer 360?**
- **R: E** - B y C (Desencadenar acciones de datos Y activar segmentos en Journey Builder)

---

### Módulo: Data 360 en Acción

**P1: ¿Ejemplo de práctica recomendada ética?**
- **R: Múltiples correctas** - A (gobernanza), B (recopilar solo lo necesario), D (respetar preferencias)

**P2: ¿Qué caso de uso aporta más información al representante de ventas?**
- **R: C** - Perspectivas en lote (o B - Resolución de identidad)

---

### Módulo: Experiencias Personalizadas con Data 360

**P1: ¿Por qué integrar Sales Cloud con Data 360?**
- **R: D** - Permite acceder a datos unificados para mejorar proyecciones de ventas e identificar oportunidades de upsell

**P2: ¿Caso de uso para Data 360 enrichment?**
- **R: B** - Copiar el lifetime value total de un cliente a un campo personalizado en Sales Cloud

---

### Módulo: Automatización con Flows y Agentes

**P1: ¿Cómo automatizar caso de soporte cuando hay alto número de devoluciones?**
- **R: D** - Desencadenar un flow desde cambio en Calculated Insight Object (CIO) cuando excede umbral

**P2: ¿Beneficio clave de construir agente sobre Data 360?**
- **R: B** - Permite al agente proporcionar respuestas altamente personalizadas usando perfil unificado de Customer 360

---

### Módulo: Conexión de Datos

**P1: ¿Cuál es el propósito de Data Federation?**
- **R: B** - Conectar metadata de una fuente externa

**P2: ¿Qué NO es un paso al conectar e ingerir datos?**
- **R: D** - Unificar perfiles (esto viene después)

---

### Módulo: Casos de Uso en Tiempo Real

**P1: ¿Cómo beneficia Data 360 en tiempo real al equipo de servicio?**
- **R: A** - Proporciona acceso inmediato a datos actualizados de clientes

**P2: ¿Cómo beneficia a marketing?**
- **R: B** - Crea segmentos dinámicos y desencadena campañas basadas en interacciones en tiempo real

**P3: ¿Qué función en tiempo real es requerida para usar otras funciones en tiempo real?**
- **R: D** - Real-time data graphs

**P4: ¿Cómo emparejar credenciales con perfil unificado en tiempo real?**
- **R: A** - Crear ruleset de identity resolution y mapear real-time data graph al unified individual DMO

---

### Módulo: Conectar y Transformar Datos

**P1: Para acceder a dataset masivo en Databricks para analytics, ¿qué usar?**
- **R: D** - Zero Copy File Federation

**P2: ¿Mejor método para limpiar datos en tiempo casi real durante ingesta?**
- **R: B** - Streaming Data Transforms

---

### Módulo: Mapear y Unificar Datos

**P1: ¿Por qué es importante mapear DLOs a DMOs?**
- **R: D** - Organiza datos dispares en estructura estandarizada, habilitando procesos downstream como segmentación e insights

**P2: ¿Qué es un perfil unificado y por qué es importante?**
- **R: B** - Una vista única y comprehensiva del cliente que vincula datos de múltiples fuentes, importante para consolidar información y entendimiento holístico

---

### Módulo: Ruta de Aprendizaje

**P1: ¿Dónde se completan los retos prácticos en la ruta Desbloquee sus datos con Data Cloud?**
- **R: C** - En una organización especial de Data 360

**P2: ¿Capacidades de Data 360?**
- **R: E** - A, B y D (Entender por qué clientes actúan, impulsar conversaciones de ventas, visualizar perfiles unificados en tiempo real)

---

### Módulo: Introducción a Data 360

**P1: ¿Cómo funciona Salesforce Data 360?**
- **R: D** - Combina datos de clientes de cualquier fuente en tiempo real en perfil unificado

**P2: ¿Data 360 permite que toda Salesforce Platform actúe en tiempo real?**
- **R: A** - Verdadero

---

### Módulo: Data 360 en Funcionamiento

**P1: ¿Cómo hace Data 360 fácil conectar todas las fuentes?**
- **R: A** - Permitiendo ingesta por lotes a través de fuentes

**P2: ¿Ventaja común que Data 360 ofrece a través de integraciones?**
- **R: D** - Insights en tiempo real basados en datos reales de su negocio

---

### Módulo: Ventas con Data 360

**P1: ¿Cómo ayuda Data 360 a automatizar procesos de ventas?**
- **R: B** - Impulsando habilitación proactiva basada en comportamiento del cliente

**P2: ¿Qué puede Data 360 predecir y analizar?**
- **R: A** - Customer Lifetime Value

---

### Módulo: Servicio con Data 360

**P1: ¿Qué workflows puede Data 360 automatizar para servicio?**
- **R: A** - Emails y alertas de clientes

**P2: ¿Ejemplos de información que Data 360 analiza?**
- **R: C** - LTV, Churn, y Effort scores

---

### Módulo: Marketing con Data 360

**P1: ¿Ejemplo de cómo rulesets ayudan a mantener vista unificada?**
- **R: B** - Un ruleset puede resolver diferencias en registros según prioridades específicas de la empresa

**P2: ¿Cómo ayuda Data 360 a obtener valor de los datos?**
- **R: A** - Ofrece acceso a insights combinados de diferentes streams en tiempo real

---

### Módulo: Espacios de Datos

**P1: ¿En qué situación tiene sentido usar espacios de datos?**
- **R: A** - Empresa tiene varias marcas/regiones y usuarios trabajan solo en contexto de su marca/región

**P2: ¿Quién puede agregar datos a un espacio de datos?**
- **R: B** - Arquitecto de Data Cloud

---

### Módulo: Plataforma de Datos de Clientes

**P1: ¿Qué producto Salesforce es una CDP diseñada para marketers?**
- **R: A** - Data 360

**P2: ¿Beneficio principal de Data 360?**
- **R: C** - Unificación de datos en un único perfil

---

### Módulo: Modelo de Datos Customer 360

**P1: ¿El modelo de datos Customer 360 es el estándar para Data 360?**
- **R: A** - Verdadero

**P2: ¿Qué es un DMO?**
- **R: D** - Un conjunto de datos creado a partir de transmisiones de datos, perspectivas y otras fuentes

---

### Módulo: Preparación para Data 360

**P1: ¿Qué caso de uso ayuda a gestionar consentimiento específico de cada canal?**
- **R: D** - Gestión de consentimiento

**P2: ¿Qué hacer antes de implementar Data 360?**
- **R: D** - A y B (Identificar fuentes de datos Y definir requisitos de negocio)

---

### Módulo: Data 360 for B2C Commerce

**P1: ¿Qué función consolida información de múltiples fuentes en vista unificada?**
- **R: B** - Perfiles de clientes unificados

**P2: ¿Cómo ayuda Data 360 a implicar compradores para promover lealtad?**
- **R: C** - Permite implicación oportuna con ofertas pertinentes en momento adecuado

---

### Módulo: Ética en Personalización

**P1: ¿Qué atributo evitar para reducir sesgo no intencionado?**
- **R: D** - Código postal (por correlaciones indirectas con demografía)

**P2: ¿Es más probable que clientes compartan información con intercambio claro de valor?**
- **R: A** - Verdadero

---

### Módulo: Mensajería Conductual

**P1: Para prácticas éticas, enviar correos que sean:**
- **R: E** - A y C (Realistas y Oportunos)

**P2: ¿Qué técnica aplicar cuando clientes se quejan de demasiados mensajes?**
- **R: C** - Limitar la frecuencia

---

## KNOWLEDGE CHECK: DATA CLOUD CORE CAPABILITIES

**Q1: ¿Cuáles son los pilares centrales de Data Cloud?**
- **R: A** - Connect, Harmonize, Unify, Analyze and Predict, Act

**Q2: ¿Beneficios de usar espacios de datos? (2)**
- **R: A y D** - Gestionar acceso con permission sets Y Segregar datos/metadata/procesos por marca/región/departamento

**Q3: ¿Casos de uso válidos para Data Cloud? (3)**
- **R: A, B, D** - Insights en tiempo real y trigger actions, Segmentos complejos de individuos unificados, Agregar datos de múltiples sistemas para lifetime value

**Q4: ¿Diferenciadores clave de Salesforce Data Cloud? (3)**
- **R: B, D, E** - Interfaz Lightning user-friendly, Integración fácil con Salesforce/AppExchange, Usa Customer 360 Data Model

**Q5: ¿Qué significa "Connect" como capacidad?**
- **R: D** - Sincronizar datos de Salesforce y fuentes externas y transformar cuando sea necesario

**Q6: ¿Declaraciones verdaderas sobre funcionalidad de Data Cloud? (3)**
- **R: A, C, E** - Plataforma abierta para integrar sistemas externos, Datos transformados/limpiados/armonizados a modelo estándar, Datos activados en Sales/Marketing/Service Cloud

**Q7: ¿Qué significa "Unify" como capacidad?**
- **R: B** - Connect, match, and reconcile customer data

**Q8: Emparejar términos con definiciones:**
- **DMO** → Data model object
- **Data lake** → A vast pool of raw data whose purpose is not yet defined
- **Attribute** → A standardized piece of information about a DMO
- **Customer 360 Data Model** → The overall system that governs a set of common data model objects
- **Data stream** → A data source brought into Data Cloud

**Q9: ¿Mejores prácticas de ética de datos? (3)**
- **R: A, B, C** - Recopilar solo lo necesario, Tratar datos sensibles cuidadosamente, Elegir partners externos cuidadosamente

**Q10: Orden correcto para transformar datos:**
1. Connect your data sources
2. Harmonize your data to a standard data model
3. Unify data with identity resolution rulesets
4. Analyze data using insights and predict behavior with AI
5. Act on your data in any channel

---

## CONCEPTOS CLAVE ADICIONALES

### Terminología Importante

**DLO (Data Lake Object)**: Contenedor para datos crudos ingresados
**DMO (Data Model Object)**: Datos organizados y mapeados al modelo estándar
**Attribute**: Campo o dato específico dentro de un DMO
**Subject Area**: Agrupación de DMOs relacionados (ej: Sales Orders, Engagement)

### Zero Copy Data Federation
- **Query Federation**: Data 360 envía query al sistema externo
- **File Federation**: Data 360 consulta directamente el storage layer (mejor para datasets masivos)

### Identity Resolution
**Match Rules**:
- Exact: coincidencia exacta
- Fuzzy: permite typos/variaciones
- Normalized: mismo contenido, diferente formato

**Reconciliation Rules**:
- Last Updated: valor más reciente
- Most Frequent: valor más común
- Source Sequence: priorizar fuente confiable

### Real-Time Capabilities
- Real-time data graphs (requerido para otras capacidades real-time)
- Real-time data ingestion
- Real-time identity resolution
- Real-time calculated insights
- Real-time segments
- Real-time data actions

### Consumo de Créditos
**Fórmula**: Credits consumed = (d/u) × m
- d = total data processed
- u = unit (siempre 1,000,000)
- m = multiplier (varía según usage type)

**Categorías de Consumo**:
- Connect (ingesta)
- Harmonize and Unify (transformaciones)
- Analyze and Predict (insights, inferencias)
- Act (queries, acciones)
- Segment and Activate
- End-to-End Real Time Processing

### Data Spaces
**Cuándo usar**:
- Múltiples marcas/regiones/departamentos
- Usuarios necesitan ver datos solo de su contexto

**Cuándo NO usar**:
- Requisitos de residencia de datos (data spaces NO resuelven esto)
- Objetivo es unificar marca y crear segmentos

### Mejores Prácticas Éticas

**Personalización**:
- Obtener consentimiento explícito
- Explicar intercambio de valor claramente
- Usar comportamiento/intención vs demografía
- Evitar atributos que introduzcan sesgo (edad, etnia, código postal)

**Mensajería Conductual**:
- Respetar preferencias
- Limitar frecuencia
- Ser transparente sobre uso de datos
- Mensajes oportunos y contextuales

### Casos de Uso Principales

**Sales Cloud**:
- Customer Lifetime Value
- Propensity to buy
- Lead qualification
- Upsell/cross-sell opportunities

**Service Cloud**:
- 360-degree customer view
- CSAT scores
- Case resolution time
- Proactive service

**Marketing Cloud**:
- Segmentación avanzada
- Campañas personalizadas
- Journey Builder con datos unificados
- Activación en plataformas publicitarias

**Commerce Cloud**:
- Recomendaciones de productos en tiempo real
- Carritos abandonados
- Personalización de sitio web
- Agente de compra guiada (Agentforce)
