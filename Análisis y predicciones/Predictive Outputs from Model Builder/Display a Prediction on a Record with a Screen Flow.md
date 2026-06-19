# Display a Prediction on a Record with a Screen Flow

## Learning Objectives

After completing this unit, you’ll be able to:

*   Create a screen flow that displays a prediction on a record page.  
    
*   View predictions and recommendations on a record page.  
    

In this unit, you create a screen flow to run the lead conversion prediction, process it with the prompt template, and display the prediction on a lead record. Then, you create a new lead and run the flow on the new lead. And, you view predictions and recommendations on the record.

## Create a Screen Flow

Screen flows are flows in Flow Builder that you can use to add information to a screen. For the lead conversion example, the information is the predicted conversion and recommendations and the screen is a lead record. Learn more about [Screen Flows](https://trailhead.salesforce.com/content/learn/modules/screen-flows) and [Flow Builder.](https://trailhead.salesforce.com/content/learn/modules/flow-basics)

### Link Record ID to Your Flow

Continue to use the special developer org you've been using for previous units as you follow along with the steps outlined below.

1.  From the App Launcher, search for and select **Flows**.  
    
2.  Click **New** to open Flow Builder.  
    
3.  Click **Screen Automations**, then click **Screen Flow**.  
    
4.  Click ![toolbox](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/predictive-outputs-from-model-builder/display-a-prediction-on-a-record-with-a-screen-flow/images/8e67318f28d8630b7bf7c64317ecfefc_kix.l580svgdk1ze.png) to open the Toolbox.  
    
5.  Create a variable that stores the record ID.  
    *   Click **New Resource**.  
        
    *   For the Resource Type, select **Variable**.  
        
    *   Name the resource: `recordIdCopiar`. Leave the description blank.  
        
    *   For the Data Type, select **Text**.  
        
    *   Leave the default value blank.  
        
    *   Select **Available for input**.  
        
    *   Click **Done**.  
        
6.  Add a Get Records element that pulls lead records into the flow.  
    *   Click the + icon in the Canvas.  
        
    *   Search for and select **Get Records**.  
        
    *   Name the element: `Get Lead DataCopiar`.  
        
    *   Make sure the API name is `Get_Lead_DataCopiar`. Leave the description blank.  
        
    *   Make sure the Data Source field is **Salesforce Object**.  
        
    *   For the Object, search for and select **Lead**.  
        
    *   Under Filter Lead Records, leave ‘All Conditions Are Met (AND)’ in the Condition Requirements.  
        
    *   Search for and select **Lead** **ID** as the field, **Equals** as the operator, and **recordId** as the value.  
        
    *   Leave the default values in sort order and record storing.  
        

Now your flow can find the corresponding lead given a record ID. Next, bring in your predictive model.

### Add Predictive Model to the Flow

1.  Add an Action element that pulls your predictive model into the flow.  
    *   Click the + icon in the Canvas below Get Lead Data.  
        
    *   Search for and select the **Predicted Conversion** action.  
        
    *   Name the element: `Predict ConversionCopiar`.  
        
    *   Make sure the API name is `Predict_ConversionCopiar`. Leave the description blank.  
        
    *   Map each field to the corresponding field in the Lead from Get Lead Data.  
        *   Click **Lead from Get Lead Data**.  
            
        *   Search for and select the corresponding field. For example, select **Annual Revenue** for Annual Revenue. Repeat for each field.  
            
    *   Turn on recommendations. Enter `3Copiar` for the number of recommendations.  
        
    *   Turn on top predictors. Enter `3Copiar`for the number of top predictors.  
        
2.  Create a text template that stores the top recommendations from the model output.  
    *   Under Toolbox, click **New Resource**.  
        
    *   For the Resource Type, select **Text Template**.  
        
    *   In the API Name field, name the resource: `JSONRecommendationsCopiar`. Leave the description blank.  
        
    *   Click the **View as Rich Text** dropdown and select **View as Plain Text**.  
        
    *   Enter `{!Predict_Conversion.prescriptions}Copiar` in the Body.  
        
    *   Click **Done**.  
        
3.  Create a text template that stores the top predictors from the model output.  
    *   Under Toolbox, click **New Resource**.  
        
    *   For the Resource Type, select **Text Template**.  
        
    *   In the API Name field, name the resource: `JSONPredictorsCopiar`. Leave the description blank.  
        
    *   Click the **View as Rich Text** dropdown and select **View as Plain Text**.  
        
    *   Enter `{!Predict_Conversion.factors}Copiar` in the Body.  
        
    *   Click **Done**.  
        

Now your flow can input the lead into your predictive model and get the predicted conversion. Then, you stored the recommendations and predictors in text templates. Next, bring in your prompt template.

### Add Prompt Template to the Flow

1.  Click the + icon in the Canvas below Predict Conversion.  
    
2.  Search for and select the first result for the **Explain Conversion and Give Recommendations** action.  
    
3.  Name the element: `Explain Conversion and Give RecommendationsCopiar`.  
    
4.  Make sure the API name is `Explain_Conversion_and_Give_RecommendationsCopiar`. Leave the description blank.  
    
5.  For the Predicted Outcome, select **Outputs from Predict Conversion**, then click **Prediction**.  
    
6.  For the Top Predictors, select **JSONPredictors**.  
    
7.  For the Top Recommendations, select **JSONRecommendations**.  
    

### Display the Prediction on the Record Page

1.  Add a Screen element.  
    *   Click the + icon in the Canvas below Explain Conversion and Give Recommendations.  
        
    *   Search for and select **Screen**.  
        
    *   Name the element: `Show PredictionCopiar`.  
        
    *   Make sure the API name is `Show_PredictionCopiar`. Leave the description blank.  
        
    *   In the Components tab on the left side of the screen, search for and select **Display Text**.  
        *   In the API Name field, name the component: `Output_From_PromptCopiar`.  
            
        *   In the “Insert a resource…” field, click **Outputs from Explain\_Conversion\_and\_Give\_Recommendations**, then click **promptResponse**.  
            
        *   Click **Done**.  
            
2.  Click **Save**.  
    
3.  Name the flow: `Lead Conversion Predictions and RecommendationsCopiar`.  
    
4.  Make sure the API name is `Lead_Conversion_Predictions_and_RecommendationsCopiar`. Leave the description blank.  
    
5.  Click **Save**.  
    
6.  Click **Activate**.  
    

## Add Flow to Lead Record Page Layout

Add the flow to the lead record page layout. This will run the flow on every lead and display the prediction on each record page.

1.  From the App Launcher, search for and select **Leads**.  
    
2.  Click the **Recently Viewed** dropdown and select **All Open Leads**.  
    
3.  Click on **Andy Doe**.  
    
4.  Click the gear icon, then click **Edit Page**. This opens the lead record page layout in the Lightning App Builder.  
    
5.  From the Components tab, search for `FlowCopiar`. Drag the Flow component to the Related tab on the right side of the page. Make sure the Flow component is the first item in the Related tab.  
    
6.  In the Flow field, search for and select **Lead Conversion Predictions and Recommendations**.  
    
7.  Check the box for Pass record ID into this variable.  
    
8.  Click **Save**.  
    
9.  In the window, click **Activate**.  
    
10.  Click **Assign as Org Default**.  
    
11.  Leave Desktop selected and click **Next**.  
    
12.  Click **Save**.  
    
13.  Click the back button to exit the Lightning App Builder and go back to Andy’s record page. You should see the prediction on the right side of the screen.  
    

Well done! Now predictions from your model are available on every lead record. Your sales agents can quickly see which leads are likely to convert, as well as get recommendations for how to maximize lead conversion directly on a record page.

## Wrap Up

Predictive models in Model Builder provide more than just a prediction. They teach you how to adjust your course to get the best outcome. In this module, you learned how to turn your predictions into tangible results. You built a model that predicted lead conversion, processed the output with Prompt Builder, and displayed it on lead record pages with a screen flow. By providing actionable predictions to your sales agents, they can now adjust their strategies to improve conversion for every lead. You’ll see higher conversion rates, increased efficiency from your sales agents, and increased revenue. Now, it’s time for you to build and act on your predictive outputs from Model Builder to reap all the benefits!

Click the Check Challenge below to earn 500 Points button and complete this badge.

## Resources

*   [_Salesforce Help_: Automate Your Business Processes with Salesforce Flow](https://help.salesforce.com/s/articleView?id=platform.platform_automation.htm&type=5)
*   [_Salesforce Help_: Add a Flow to a Lightning Page](https://help.salesforce.com/s/articleView?id=platform.flow_distribute_internal_lab.htm&type=5)

Aquí está la guía completa para el reto final:

---

# Guía: Mostrar una Predicción en un Record con Screen Flow

## Paso 1 — Crear el Screen Flow

1. En el **App Launcher** busca y selecciona **"Flows"**
2. Haz clic en **"New"**
3. Selecciona **"Screen Automations"** → **"Screen Flow"**
4. Haz clic en el ícono 🧰 **Toolbox** para abrirlo

---

## Paso 2 — Crear la variable recordId

1. En Toolbox haz clic en **"New Resource"**
2. Configura así:
   - Resource Type: **Variable**
   - Name: `recordId`
   - Data Type: **Text**
   - Default value: en blanco
   - ✅ Marca **"Available for input"**
3. Clic en **"Done"**

---

## Paso 3 — Agregar elemento Get Records

1. Haz clic en el ícono **"+"** en el Canvas
2. Busca y selecciona **"Get Records"**
3. Configura así:
   - Name: `Get Lead Data`
   - API Name: `Get_Lead_Data`
   - Data Source: **Salesforce Object**
   - Object: **Lead**
   - Condition Requirements: **All Conditions Are Met (AND)**
   - Field: `Lead ID` | Operator: `Equals` | Value: `recordId`
4. Deja los valores por defecto en sort order y record storing

---

## Paso 4 — Agregar el Modelo Predictivo

1. Haz clic en **"+"** debajo de Get Lead Data
2. Busca y selecciona la acción **"Predicted Conversion"**
3. Configura así:
   - Name: `Predict Conversion`
   - API Name: `Predict_Conversion`
4. Mapea cada campo con el correspondiente de **"Lead from Get Lead Data"**:
   - Annual Revenue → Annual Revenue
   - Discount Offered → Discount Offered
   - Employees → Employees
   - Industry → Industry
   - Lead Source → Lead Source
   - Positioned Product → Positioned Product
   - Title → Title
5. Activa **recommendations** → ingresa `3`
6. Activa **top predictors** → ingresa `3`

---

## Paso 5 — Crear Text Templates

**Template 1 — Recommendations:**
1. En Toolbox → **"New Resource"**
2. Resource Type: **Text Template**
3. API Name: `JSONRecommendations`
4. Cambia a **"View as Plain Text"**
5. Body: `{!Predict_Conversion.prescriptions}`
6. Clic en **"Done"**

**Template 2 — Predictors:**
1. En Toolbox → **"New Resource"**
2. Resource Type: **Text Template**
3. API Name: `JSONPredictors`
4. Cambia a **"View as Plain Text"**
5. Body: `{!Predict_Conversion.factors}`
6. Clic en **"Done"**

---

## Paso 6 — Agregar el Prompt Template al Flow

1. Haz clic en **"+"** debajo de Predict Conversion
2. Busca y selecciona **"Explain Conversion and Give Recommendations"** (primer resultado)
3. Configura:
   - Name: `Explain Conversion and Give Recommendations`
   - API Name: `Explain_Conversion_and_Give_Recommendations`
4. Mapea los inputs:
   - **Predicted Outcome** → Outputs from Predict Conversion → **Prediction**
   - **Top Predictors** → **JSONPredictors**
   - **Top Recommendations** → **JSONRecommendations**

---

## Paso 7 — Mostrar la predicción en pantalla

1. Haz clic en **"+"** debajo del paso anterior
2. Busca y selecciona **"Screen"**
3. Configura:
   - Name: `Show Prediction`
   - API Name: `Show_Prediction`
4. En el tab Components busca y selecciona **"Display Text"**:
   - API Name: `Output_From_Prompt`
   - En "Insert a resource…" selecciona → **Outputs from Explain_Conversion_and_Give_Recommendations** → **promptResponse**
   - Clic en **"Done"**

---

## Paso 8 — Guardar y Activar el Flow

1. Haz clic en **"Save"**
2. Name: `Lead Conversion Predictions and Recommendations`
3. API Name: `Lead_Conversion_Predictions_and_Recommendations`
4. Description: en blanco
5. Clic en **"Save"**
6. Clic en **"Activate"**

---

## Paso 9 — Agregar el Flow al Lead Record Page

1. En App Launcher busca **"Leads"**
2. Cambia la vista a **"All Open Leads"**
3. Haz clic en **"Andy Doe"**
4. Haz clic en el ícono ⚙️ → **"Edit Page"**
5. En Components busca `Flow`
6. **Arrastra** el componente Flow a la pestaña **"Related"** como **primer elemento**
7. En el campo Flow selecciona **"Lead Conversion Predictions and Recommendations"**
8. ✅ Marca **"Pass record ID into this variable"**
9. Clic en **"Save"** → **"Activate"** → **"Assign as Org Default"**
10. Deja **Desktop** seleccionado → **"Next"** → **"Save"**
11. Haz clic en el **botón de regreso** para volver al record de Andy

> ✅ Deberías ver la predicción en el lado derecho del record page.

---

## Paso 10 — Verificar en Trailhead

Regresa a Trailhead y haz clic en **"Validar reto"** para ganar los **500 puntos finales** y completar la insignia. 🎉