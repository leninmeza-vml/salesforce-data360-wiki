# Process a Prediction with Prompt Builder

## Learning Objectives

After completing this unit, you’ll be able to:

*   View predictive outputs from a model.  
    
*   Create a prompt in Prompt Builder that processes the raw predictive output into readable text.  
    

## View Predictive Outputs

In this unit, you learn why and how to use Prompt Builder to transform predictive outputs from Model Builder into a readable and conversational paragraph.

First, to understand why you need to use Prompt Builder, let’s look at the predictive output for the lead Andy Doe from Unit 1.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Access the unprocessed predictive output with [Data 360 Connect REST API](https://developer.salesforce.com/docs/platform/connectapi/overview), or print it using a screen flow.

![Unprocessed predictive output for lead conversion.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/predictive-outputs-from-model-builder/process-a-prediction-with-prompt-builder/images/830ffca3f14aa60ef421cc9e654d9ee9_kix.5tncerakqtdw.png)

### Predictive Score

This is the predicted likelihood to convert. For Andy, we got 43.478, meaning he has a 43% likelihood to convert.

### Top Predictors

Here’s a top predictor for Andy.

*   `nameCopiar`: The field name, `Positioned_Product_c__cCopiar`.  
    
*   `inputValueCopiar`: The current value of the field, `GC5000 SeriesCopiar`.  
    
*   `valueCopiar`: How many percentage points this field contributed to the predicted outcome, `-7.27Copiar`.  
    

The GC5000 Series positioned product decreased Andy’s likelihood to convert by 7%.

### Recommendations

Here’s a recommendation for Andy.

*   `nameCopiar`: The field name, `Positioned_Product_c__cCopiar`.  
    
*   `prescribedValueCopiar`: The prescribed value of the field, or what you should change the value to, `GC1000 SeriesCopiar`.  
    
*   `valueCopiar`: How many percentage points the change could contribute to the outcome, `24.2Copiar`.  
    

Changing Andy’s positioned product to GC1000 Series can increase his likelihood to convert by 24%.

We know how powerful this prediction is but it’s certainly not easy to understand. Remember how readable Andy’s prediction was in Unit 1? With an unprocessed output from Model Builder, it can feel like we’re doing rocket science to glean the same insights. That’s where Prompt Builder comes in. Follow along with the following steps to ensure you can pass the challenge at the end of this unit.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Learn more about Prompt Builder in [Prompt Builder Basics](https://trailhead.salesforce.com/content/learn/modules/prompt-builder-basics).

## Turn on Einstein Generative AI

To use Prompt Builder, Einstein Generative AI must be on. Follow these steps to ensure it’s turned on.

1.  Click the gear icon and launch **Setup**.  
    
2.  In the Quick Find box, search for and select **Einstein Setup**.  
    
3.  Ensure the Turn On Einstein toggle is set to **On**.  
    
4.  Refresh your browser to reload Setup.  
    

## Create a Prompt Template

Next, you’ll create a prompt template that takes the prediction result from Model Builder and formats it into an easy-to-read list.

The prompt template should describe how to interpret unprocessed predictions from Model Builder. For example, the template should explain how to identify the field name, value, and percentage points for top predictors and top recommendations. The prompt template should also specify a friendly and conversational tone and a list format. This ensures that you don’t give your sales agents a paragraph full of technical jargon.

1.  From Setup, in the Quick Find box, search for and select **Prompt Builder**. If you can’t find Prompt Builder, refresh the page.  
    
2.  Click **New Prompt Template.**  
    
3.  Select **Flex** for the Prompt Template Type.  
    
4.  Name the prompt template: `Explain Conversion and Give RecommendationsCopiar`.  
    
5.  Make sure the API name is `Explain_Conversion_and_Give_RecommendationsCopiar`. Leave the description blank.  
    
6.  Define three inputs for your template.  
    1.  Under Inputs, click **Add**.  
        1.  Name the source: `Predicted OutcomeCopiar`. Make sure the API name is `Predicted_OutcomeCopiar`.  
            
        2.  Select **Free Text** for the source type.  
            
        3.  Leave the Require when template runs checkbox checked.  
            
    2.  Click **Add**.  
        1.  Name the source: `Top PredictorsCopiar`. Make sure the API name is `Top_PredictorsCopiar`.  
            
        2.  Select **Free Text** for the source type.  
            
        3.  Leave the Require when template runs checkbox checked.  
            
    3.  Click **Add**.  
        1.  Name the source: `Top RecommendationsCopiar`. Make sure the API name is `Top_RecommendationsCopiar`.  
            
        2.  Select **Free Text** for the source type.  
            
        3.  Leave the Require when template runs checkbox checked.  
            
7.  Click **Next**.  
    
8.  The following prompt template explains how to transform the JSON input into a readable format. Review the prompt template, then copy and paste the template into the Prompt Template Workspace.  
    

You are a data analyst trying to help a seller convert a lead. {!$Input:Predicted\_Outcome} is the likelihood of converting this lead. A moderate likelihood has a score between 50 and 70. A high likelihood has a score above 70. Anything with a score less than 50 requires attention. {!$Input:Top\_Predictors} are the key drivers of the conversion likelihood. Positive values increase the likelihood to convert which is good and negative values indicate less likelihood of conversion which is bad. {!$Input:Top\_Recommendations} are the actions the user can take to improve the likelihood of converting. An example of a JSON response for predictors is: \[{ "fields" : \[ { "customText" : null, "inputValue" : "3", "label" : null, "name" : "fare\_\_c", "prescribedValue" : "" } \], "value" : 6.680652684719895 }\] This means that having a fare of 3 increases the predicted value by 6.68 percentage points. If any values have No, make sure to interpret those. For example, if you get { "customText" : null, "inputValue" : "No", "label" : null, "name" : "Streaming TV", "prescribedValue" : "" }, respond that not having streaming TV affects the prediction, NOT Streaming TV is No. If any values have False, make sure to interpret those. For example, if you get { "customText" : null, "inputValue" : "False", "label" : null, "name" : "Partner", "prescribedValue" : "" }, respond that not being a Partner affects the prediction, NOT Partner is No. Sometimes you might have something like "fields" : \[ {"customText" : null, "inputValue" : "3.0", "label" : null, "name" : "sibsp\_\_c", "prescribedValue" : "" }, {"customText" : null,"inputValue" : "3.0", "label" : null, "name" : "pclass\_\_c", "prescribedValue" : ""} \], "value" : -6.326304223287199 This means that having a sibsp value of 3 AND a pclass value of 3 decreases the predicted value by 6.36 percentage points. Drop the \_\_c from any variables that have them. An example of a JSON response for prescriptions is: \[{ "fields" : \[ { "customText" : null, "inputValue" : "", "label" : null, "name" : "Response\_Time\_From\_Assignment\_c\_\_c", "prescribedValue" : "0 to 0.12" } \], "value" : 6.680652684719895 }\] In the above example, "name" refers to the name of the field that can be changed and the "prescribedValue" is what should be done to improve the outcome. The data type of the field is number, the "prescribedValue" will be a number range in the format lower value "to" upper value. "Value" represents how much the score will be improved if the field is changed to the prescribedValue. First, state the {!$Input:Predicted\_Outcome}. Now, given {!$Input:Top\_Predictors} and {!$Input:Top\_Recommendations}, explain conversationally to the user what their top predictors are and what recommendations you have for improving. If there are more than two predictors or recommendations, format in list form by numbering them. DO NOT mix up top predictors and recommendations. Don’t end with a question. DO NOT use quotation marks. Be friendly and conversational.

8.  Click **Save**.  
    
9.  Click **Activate**.  
    

You now have a prompt template that’s ready to transform your predictions!

It’s time to check your work to double-check that you’ve set up Einstein and created your prompt template successfully to move on to the next unit. There, you’ll wrap up all the work you’ve done and display your prediction on a lead record.

## Resources

*   [_Salesforce Help_: Set Up Einstein Generative AI](https://help.salesforce.com/s/articleView?id=ai.generative_ai_enable.htm&type=5)
*   [_Salesforce Help_: Prompt Builder](https://help.salesforce.com/s/articleView?id=ai.prompt_builder_about.htm&type=5)
*   [_Salesforce Developers_: Data 360 Connect REST API](https://developer.salesforce.com/docs/platform/connectapi/overview)

---

# Guía: Procesar una Predicción con Prompt Builder

## Paso 1 — Activar Einstein Generative AI

1. Haz clic en el ícono de **engranaje** ⚙️ → **"Setup"**
2. En el Quick Find busca y selecciona **"Einstein Setup"**
3. Verifica que el toggle **"Turn On Einstein"** esté en **On**
4. **Refresca** el navegador

---

## Paso 2 — Crear el Prompt Template

1. En Setup, busca y selecciona **"Prompt Builder"**
2. Haz clic en **"New Prompt Template"**
3. Selecciona **"Flex"** como Prompt Template Type
4. Configura los detalles:
   - **Name:** `Explain Conversion and Give Recommendations`
   - **API Name:** `Explain_Conversion_and_Give_Recommendations`
   - **Description:** dejar en blanco

---

## Paso 3 — Definir los 3 Inputs

Haz clic en **"Add"** tres veces, configurando cada input así:

**Input 1:**
- Name: `Predicted Outcome`
- API Name: `Predicted_Outcome`
- Source Type: **Free Text**
- ✅ Deja marcado "Require when template runs"

**Input 2:**
- Name: `Top Predictors`
- API Name: `Top_Predictors`
- Source Type: **Free Text**
- ✅ Deja marcado "Require when template runs"

**Input 3:**
- Name: `Top Recommendations`
- API Name: `Top_Recommendations`
- Source Type: **Free Text**
- ✅ Deja marcado "Require when template runs"

Haz clic en **"Next"**

---

## Paso 4 — Pegar el Prompt Template

Copia y pega exactamente este texto en el **Prompt Template Workspace**:

```
You are a data analyst trying to help a seller convert a lead. {!$Input:Predicted_Outcome} is the likelihood of converting this lead. A moderate likelihood has a score between 50 and 70. A high likelihood has a score above 70. Anything with a score less than 50 requires attention. {!$Input:Top_Predictors} are the key drivers of the conversion likelihood. Positive values increase the likelihood to convert which is good and negative values indicate less likelihood of conversion which is bad. {!$Input:Top_Recommendations} are the actions the user can take to improve the likelihood of converting. An example of a JSON response for predictors is: [{ "fields" : [ { "customText" : null, "inputValue" : "3", "label" : null, "name" : "fare__c", "prescribedValue" : "" } ], "value" : 6.680652684719895 }] This means that having a fare of 3 increases the predicted value by 6.68 percentage points. If any values have No, make sure to interpret those. For example, if you get { "customText" : null, "inputValue" : "No", "label" : null, "name" : "Streaming TV", "prescribedValue" : "" }, respond that not having streaming TV affects the prediction, NOT Streaming TV is No. If any values have False, make sure to interpret those. For example, if you get { "customText" : null, "inputValue" : "False", "label" : null, "name" : "Partner", "prescribedValue" : "" }, respond that not being a Partner affects the prediction, NOT Partner is No. Sometimes you might have something like "fields" : [ {"customText" : null, "inputValue" : "3.0", "label" : null, "name" : "sibsp__c", "prescribedValue" : "" }, {"customText" : null,"inputValue" : "3.0", "label" : null, "name" : "pclass__c", "prescribedValue" : ""} ], "value" : -6.326304223287199 This means that having a sibsp value of 3 AND a pclass value of 3 decreases the predicted value by 6.36 percentage points. Drop the __c from any variables that have them. An example of a JSON response for prescriptions is: [{ "fields" : [ { "customText" : null, "inputValue" : "", "label" : null, "name" : "Response_Time_From_Assignment_c__c", "prescribedValue" : "0 to 0.12" } ], "value" : 6.680652684719895 }] In the above example, "name" refers to the name of the field that can be changed and the "prescribedValue" is what should be done to improve the outcome. The data type of the field is number, the "prescribedValue" will be a number range in the format lower value "to" upper value. "Value" represents how much the score will be improved if the field is changed to the prescribedValue. First, state the {!$Input:Predicted_Outcome}. Now, given {!$Input:Top_Predictors} and {!$Input:Top_Recommendations}, explain conversationally to the user what their top predictors are and what recommendations you have for improving. If there are more than two predictors or recommendations, format in list form by numbering them. DO NOT mix up top predictors and recommendations. Don't end with a question. DO NOT use quotation marks. Be friendly and conversational.
```

---

## Paso 5 — Guardar y Activar

1. Haz clic en **"Save"**
2. Haz clic en **"Activate"**

---

## Paso 6 — Verificar en Trailhead

Con el prompt template activo, regresa a Trailhead y haz clic en **"Validar reto"** para ganar los **500 puntos**. 🎉

---

> ⚠️ **Puntos críticos a verificar:**
> - Los API Names deben ser exactos con guiones bajos
> - Einstein debe estar **On** antes de crear el template
> - El template debe estar en estado **Active**, no Draft