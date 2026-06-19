# Create a Semantic Model

## Learning Objectives

After completing this unit, you’ll be able to:

*   Describe a semantic model.  
    
*   Describe the types of semantic models.  
    
*   Create a semantic model.  
    

## Explore Semantic Models

Before you learn how to build a semantic model, you should first understand what semantic models are and how they’re structured. Semantic models are first-class Salesforce metadata, integrated throughout Data 360 to power analytical and data-driven experiences.

A semantic model consists of one or more data objects and their relationships and semantic definitions tailored for a specific analytical use case. For example, renaming a field from COGS to Cost of Goods, or setting the default aggregation to median.

There are a few ways to create semantic models, including from scratch, extending an existing model, and more.

If you’re using Tableau Next to create semantic models, see [Add Semantic Models](https://help.salesforce.com/s/articleView?id=analytics.tua_data_sdm_add_models.htm&type=5) in Salesforce Help.

## Create Your Semantic Model

To better understand how Tableau Semantics can help you with your business, let's create a model using the data model objects (DMOs) Account, Individual, and Case. This model can then be consumed by business analysts and users later on to answer questions such as how many escalated cases occurred this past quarter for a specific customer profile.

Before you begin, check the available data objects in Data 360 to make sure you have all the required data.

1.  From Data Cloud, select the **Data Model** tab.  
    

![Data Model screen showing all the data model objects that exist.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-semantic-model/images/304c9955012251444bb0cfa416e8c6a7_kix.duv3d6h92jsw.png)

Here you can see you have the data model objects (DMOs) you need for your semantic model: accounts, sales, product, category, case, and case representative data objects. For more information about data model objects, see [Data Model Objects (DMOs)](https://help.salesforce.com/s/articleView?id=data.c360_a_data_model_objects.htm&type=5) in Salesforce Help.

After verifying that you have all the data you need, you're ready to create a semantic model.

1.  In Data 360, select the **Semantic Layer** tab.  
    
2.  Click **New Model**.  
    ![Semantic Layer dialog with new model highlighted.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-semantic-model/images/b9ce843bdca0445de06a0ad72d192242_kix.byzhj9tfokho.png)  
    

There are several options to create a new model, including starting from scratch, extending an additional model, and working from a data kit.

3.  Select **Start with a New Model**.  
    ![New Semantic Model dialog with Start with New Model highlighted.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-semantic-model/images/31e97e995384fc224974a4111d64f2e3_kix.44ehcj4tw04v.png)  
    
4.  Click **Next**.  
    
5.  (Optional) Select the data space for your data objects. You can only use one data space per model.  
    
6.  Select the data objects you want to use in your semantic model. You can select data model objects (DMOs), data lake objects (DLOs), and calculated insights (CIs). In this case, select **Account**, **Sales**, **Product**, **Product Category, Case**, and **Case Representative**.  
    ![Select Data Objects for Semantic Model dialog.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-semantic-model/images/1f1ed75c8d6f5cce0cf3fe498ae5e274_kix.752myovrqxma.png)  
    
7.  Click **Next**.  
    
8.  In the **New Semantic Model** dialog, enter these details:  
    *   Enter a unique name for the semantic model.  
        
    *   Define the API name of the semantic model. The API name can’t be edited after the model is created.  
        
    *   Enter an optional description.  
        ![New Semantic Model dialog](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-semantic-model/images/f9fe5d92edb7abd1468afd71d153feaf_kix.nf8b021od3wl.png)  
        
9.  Click **Create**.  
    

The Semantic Model Builder appears and you can see the selected data objects in the middle of the Semantic Model Builder Canvas:![Semantic Model Builder with Data Objects and canvas highlighted.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-semantic-model/images/291ef0f701471edee4795a45d04e1921_kix.hvd1wo7bzvum.png)

Now that you've added data objects to your semantic model, the next step is to set up the relationships between those objects.

## Add Relationships Between Your Data Objects

Relationships are flexible connections between different data objects based on common fields. Use the Semantic Layer to establish relationships between your data objects to enrich your data model without the need to predefine the join type. Think of a relationship as a contract between two DMOs. When you build a visualization with fields from those DMOs, the Semantic Layer uses the contract to decide what join type is necessary for the analysis.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

We recommend using relationships as your first approach to combining your data—rather than manual joins—because it makes data preparation and analysis easier and more intuitive.

By default, any relationships that were mapped between DMOs in Data 360 are automatically transferred into the model. Any existing relationships that can create circular relationships (relationships that reference the same object multiple times) are automatically removed. You can also remove any relationships you don't want.

If no relationships exist or you need to create new ones, you can do so manually or by using Semantics AI.

### Create a Manual Relationship

1.  To create a relationship manually, click the plus sign next to a data object then select the object to connect to, such as Account to Individual.  
    ![Semantic Model Builder with data object selected and Add Relationship dialog displayed.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-semantic-model/images/2ba2e882e8c0114e2b70f583600f9c29_kix.p7b9ot3kbs2m.png)  
    
2.  Next, choose the fields from each DMO that the relationship is built on, such as Account.Account = Individual.Account. If you need additional fields, click the plus icon and add more fields to the relationship.  
    

![Semantic Model Builder with the relationship UI visible.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-semantic-model/images/551e1cc311fe22747499ece7effd0807_kix.m9op8gtreeqz.png)

3.  When you have all the fields needed to define the relationship, select **Apply**. The Semantic Model Builder shows a straight black line, indicating that the relationship is configured correctly.  
    ![Semantic Model Builder with three DMOs and a relationship between two of them.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-semantic-model/images/a85f86437e4d09d3f74d5524f77b499a_kix.x9hqadzagh37.png)  
    

### Use Semantics AI to Create Relationships

You can also use Semantics AI to help create a relationship, such as between the Account and Case data objects.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

To use Suggest Relationships in Semantics AI, you must first perform some setup. For more information, see \[Create a Relationship with Suggest Relationships\] [https://help.salesforce.com/s/articleView?id=analytics.tua\_data\_sdm\_suggest\_rel.htm&type=5](https://help.salesforce.com/s/articleView?id=analytics.tua_data_sdm_suggest_rel.htm&type=5) in Salesforce Help.

You must turn on Semantics AI in the Feature Manager. For more information, see [Enable Data 360 Features](https://help.salesforce.com/s/articleView?id=data.c360_a_feature_manager.htm&type=5) in Salesforce Help.

1.  In the Semantic Model Builder, click **Show Suggestions**.  
    ![Semantic Model Builder with Relationship Recommendations highlighted.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-semantic-model/images/b867312a4ad68b4721651ba9251cafff_kix.5h52bey1l1ey.png)  
    Here you can see that Semantics AIfound a relationship between Account and Case using the Account ID.  
    ![Recommended relationship highlighted.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-semantic-model/images/80a176d279fa335cd22d768bccd94032_kix.devurixog1lv.png)  
    
2.  You want to make sure this is what you’re looking for, so click **Review**.  
    
3.  Once everything looks good, select **Apply**.  
    
4.  The Semantic Model Builder shows a straight black line, indicating that the relationship is configured correctly.  
    ![Semantic Model Builder with defined relationships in the canvas.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-semantic-model/images/76518ad42db7201a306d55e13c8cd72b_kix.cr07phx7kzk4.png)  
    

Now your semantic model has three objects and two relationships—a relationship between Account and Individual, and between Account and Case.

In this unit, you learned about the different ways to create semantic models, how to create a semantic model from scratch, and how to add relationships between your data model objects. Head over to the next unit to see how to create a logical view when you have multiple tables and need one single view of your data.

Respuestas de la prueba:

---

**Pregunta 1 — What are semantic models in Data 360?**

**Respuesta: B — First-class Salesforce metadata integrated throughout Data 360 to power analytical and data-driven experiences.**

El documento define explícitamente que los semantic models son "first-class Salesforce metadata, integrated throughout Data 360 to power analytical and data-driven experiences", consistiendo en objetos de datos, sus relaciones y definiciones semánticas adaptadas a un caso de uso analítico específico.

---

**Pregunta 2 — What's the recommended first approach to combining data objects in the Semantic Layer?**

**Respuesta: B — Use relationships.**

El documento indica explícitamente que se recomienda usar **relationships** como primer enfoque para combinar datos, en lugar de joins manuales, porque hace la preparación y el análisis de datos más fácil e intuitivo.