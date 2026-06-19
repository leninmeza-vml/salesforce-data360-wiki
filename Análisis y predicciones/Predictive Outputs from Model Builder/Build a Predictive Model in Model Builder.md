# Build a Predictive Model in Model Builder

## Learning Objectives

After completing this unit, you’ll be able to:

*   Build a no-code predictive model in Einstein Studio that predicts the conversion of a lead.  
    
*   Train and activate a model.  
    
*   Set actionable variables for a model.  
    

## Predict Lead Conversion

In this unit, you build a no-code predictive model in Einstein Studio that predicts lead conversion. Your model also provides top predictors and recommendations.

## Define Your Goals

Before you start building, it’s important to define your goals. We use the lead conversion example as we go through the questions.

| **Question** | **Description** | **Example Answer** |
| --- | --- | --- |
| What do you want to predict? | Define the purpose of your model. | The likelihood that a lead converts. Depending on the goal, you can create a binary (yes or no) or regression (percentage or numeric) prediction. |
| What’s your training dataset? | Models learn from historical data to provide predictions. Your training dataset should typically be high-quality historical data. Learn more in the [Data Quality](https://trailhead.salesforce.com/content/learn/modules/data_quality) module. | Lead Data for Training Data Model Object (DMO) |
| What field in the DMO are you predicting? | The field in the DMO that your model is predicting values for. | Status |
| What value are you maximizing or minimizing? | Define if you want to minimize or maximize the chances that the field contains a certain value. This helps a model understand your desired outcome.<br><br>For our example, you want leads to convert. You want to maximize the chances that the Status field contains the Closed - Converted value.<br><br>For an example that uses ‘minimize’, you want to minimize customer churn. Because you don’t want customers to churn, you set a goal to minimize the chances that the Churn field is True. | Maximize, Closed - Converted |

## Build Your Model

With your goals clearly defined, let’s get started and build a model. Follow these steps in your org. We’ll be checking these steps to make sure you created a model correctly.

1.  From the App Launcher, search for and select **Data Cloud**.  
    
2.  In Data Cloud, click the **Einstein Studio** tab to access Model Builder.  
    
3.  Click **Add Predictive Model**.  
    
4.  Select **Create a binary model**. Click **Next**.  
    
5.  Leave the default data space selected and select the **Lead Data for Training** DMO. This DMO contains historical lead data that your model will use for its training set. Click **Next**.  
    
6.  Select **Filtered Set of Records**.  
    
7.  Leave ‘All Conditions Are Met’ in the Use Filter When field.  
    
8.  Search for and select the **Status** field, the **In** operator, and the **Closed - Not Converted** and **Closed - Converted** values. This creates a filter that only includes closed leads in the training data. Then click **Next**.  
    
9.  To set the outcome goal of your model, search for and select the **Status** field. This is the field you want the model to predict values for.  
    
10.  Select the **Maximize** option and set its value to **Closed - Converted**. The model will predict the likelihood that leads convert to business opportunities. Then click **Next**.  
    
11.  Click the toggle in the upper right corner to disable Autopilot. Autopilot helps you quickly weed through data to identify useful variables for the outcome. For the purposes of this module, let’s select all the fields.  
    
12.  Select **Annual Revenue**, **Employees, Discount Offered**, **Positioned Product**, **Title**, **Lead Source**, and **Industry**. Then click **Next**.  
    
13.  Leave Automatic Selection enabled to automatically select the best algorithm for the lead conversion use case. Click **Next**.  
    
14.  Review your settings and click **Save**.  
    
15.  Rename the model `Predicted ConversionCopiar`. Leave the description blank.  
    
16.  Click **Save & Train**.  
    

Your model is being trained. This can take a few minutes. When training is complete, the model appears in the Predictive tab list view. This is a perfect moment to take a break and come back later.

## Evaluate Your Model

Once training is complete, you can see metrics related to the model’s performance. If you’re not already seeing the training metrics screen, follow these steps to get there.

1.  On the Einstein Studio tab, click the **Predicted Conversion** model.  
    
2.  Click **View Training Metrics**.  
    

Let’s look at some key metrics to determine if your model is performing well. Your results might vary slightly, but will still be performant.

![Training metrics page in Model Builder, including the performance, performance score, and prediction accuracy percentages.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/predictive-outputs-from-model-builder/build-a-predictive-model-in-model-builder/images/451c988729a98c63a47dfb4d143d962f_kix.6b1w5jfxp4i5.png)

*   **Performance (1):** Model Builder provides these metrics based on how the model performs against the threshold.  
    *   **Performant:** Your model is accurate and performing well. Activate when you’re ready.  
        
    *   **Too low:** Your model isn’t performing well. This can mean that your training data doesn’t have adequate patterns because the data points are too similar or different from each other.  
        
    *   **Too high:** Your model is too close to perfection. This can indicate data leakage or overfitting. Overfitting means that your model is too closely aligned with your training data. As a result, it won’t provide accurate predictions for new data.  
        

*   **Performance Score (2):** Model Builder uses mathematical formulas to give you an area under the curve (AUC) score between 0 and 1 for binary classification models. Model Builder uses R-Squared for regression models.  
    

*   **Prediction Accuracy Percentages (3):** This is how often your model predicts results correctly.  
    

Great news! Your model is performant and ready for activation.

## Activate Your Model

You must activate the model for it to begin making predictions on your leads.

1.  On the Training Metrics page, click **Activate**.  
    
2.  Click **Activate Model**.  
    
3.  Click the **back arrow** to go to the Predicted Conversion model overview page.  
    

## Set Actionable Variables

Set actionable variables. You need actionable variables to get recommendations for how to optimize those variables and improve your predicted outcome. We don’t validate this step in the challenge, so make sure you follow these steps closely.

1.  Click the **Integrations** tab.  
    
2.  Click the + icon next to Set Up Variables For Prescriptions.  
    
3.  Select **Discount Offered** and **Positioned Product.**  
    
4.  Click **Apply**.  
    

Fantastic! Your model’s working on providing predictions and recommendations for the new leads. In the next unit, you learn how to interpret the predictive outputs and process them with a prompt in Prompt Builder.

## Resources

*   [_Salesforce Help_: Create, Connect, and Activate Models](https://help.salesforce.com/s/articleView?id=data.c360_a_ai_create_connect_activate_models.htm&type=5)
*   [_Salesforce Help_: Evaluate Model Quality](https://help.salesforce.com/s/articleView?id=data.c360_a_ai_ec_evaluate_model_quality.htm&type=5)

# ¡Buen trabajo!

## ¡Evaluación completada!

### +500 puntos

![](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/predictive-outputs-from-model-builder/102e820661f3281b96bbc0c1ba201c79_badge.png)

Predictive Outputs from Model Builder

50%

Volver a realizar este reto

Siguiente unidad: [Process a Prediction with Prompt Builder](/es/content/learn/modules/predictive-outputs-from-model-builder/process-a-prediction-with-prompt-builder?trail_id=data-cloud-explore-setup-to-activation)


---

# Guía: Construir un Modelo Predictivo en Model Builder

## Paso 1 — Acceder a Einstein Studio

1. En el **App Launcher** busca y selecciona **"Data Cloud"**
2. Haz clic en la pestaña **"Einstein Studio"**
3. Haz clic en **"Add Predictive Model"**

---

## Paso 2 — Configurar el tipo de modelo

1. Selecciona **"Create a binary model"** → clic en **"Next"**
2. Deja el data space por defecto
3. Selecciona el DMO **"Lead Data for Training"** → clic en **"Next"**

---

## Paso 3 — Filtrar los datos de entrenamiento

1. Selecciona **"Filtered Set of Records"**
2. Deja **"All Conditions Are Met"** en el campo *Use Filter When*
3. Configura el filtro así:
   - **Field:** `Status`
   - **Operator:** `In`
   - **Values:** `Closed - Not Converted` y `Closed - Converted`
4. Clic en **"Next"**

---

## Paso 4 — Definir el objetivo del modelo

1. Busca y selecciona el campo **"Status"**
2. Selecciona la opción **"Maximize"**
3. Establece el valor en **"Closed - Converted"**
4. Clic en **"Next"**

---

## Paso 5 — Seleccionar variables

1. Haz clic en el **toggle** de la esquina superior derecha para **desactivar Autopilot**
2. Selecciona estos 7 campos:
   - ✅ Annual Revenue
   - ✅ Employees
   - ✅ Discount Offered
   - ✅ Positioned Product
   - ✅ Title
   - ✅ Lead Source
   - ✅ Industry
3. Clic en **"Next"**

---

## Paso 6 — Configurar el algoritmo y guardar

1. Deja **"Automatic Selection"** habilitado → clic en **"Next"**
2. Revisa la configuración → clic en **"Save"**
3. Renombra el modelo exactamente como: `Predicted Conversion`
4. Deja la descripción en blanco
5. Clic en **"Save & Train"**

> ⏳ El entrenamiento puede tardar varios minutos. Es un buen momento para tomar un descanso.

---

## Paso 7 — Evaluar el modelo

Una vez completado el entrenamiento:

1. En la pestaña **Einstein Studio**, haz clic en el modelo **"Predicted Conversion"**
2. Haz clic en **"View Training Metrics"**
3. Verifica que el status sea **"Performant"** ✅

---

## Paso 8 — Activar el modelo

1. En la página de Training Metrics, haz clic en **"Activate"**
2. Confirma haciendo clic en **"Activate Model"**
3. Haz clic en la **flecha de regreso** para volver al overview del modelo

---

## Paso 9 — Configurar variables accionables

> ⚠️ Este paso NO se valida en el reto, pero es obligatorio completarlo.

1. Haz clic en la pestaña **"Integrations"**
2. Haz clic en el ícono **"+"** junto a **"Set Up Variables For Prescriptions"**
3. Selecciona:
   - ✅ Discount Offered
   - ✅ Positioned Product
4. Clic en **"Apply"**

---
