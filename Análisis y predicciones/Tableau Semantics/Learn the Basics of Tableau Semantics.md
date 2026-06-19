# Learn the Basics of Tableau Semantics

## Learning Objectives

After completing this unit, you’ll be able to:

*   Familiarize yourself with Tableau Semantics.  
    
*   Recognize why you should use Tableau Semantics.  
    
*   Describe how to access Tableau Semantics.  
    

## What Is Tableau Semantics?

Tableau Semantics is a semantic layer platform inside Data 360. It’s a translation layer between the raw, messy data in your spreadsheet or database and the business use cases for your data. The semantic layer lets you map complex data into standardized business terms—this lets you ask business questions of your data the way you think of it, rather than in formulas or database-isms. This layer of abstraction provides a consistent way to map complex data into familiar business terms, such as revenue, return on investment, or retention, to offer a standard and unambiguous interpretation of data across your organization.

Currently, Tableau Semantics is available in Data 360 and Tableau Next. For more information about Tableau Next, see [Create Semantic Models and Define Metrics](https://help.salesforce.com/s/articleView?id=analytics.tua_data_sdm.htm&type=5) in Salesforce Help.

You can also use the Tableau Semantics connector for Tableau Desktop, and Cloud to connect and use semantic models in Data 360 just like you can in Tableau Next. For more information, see [](https://help.tableau.com/current/pro/desktop/en-us/examples_tableau_semantics.htm)[Tableau Semantics Connector](https://help.tableau.com/current/pro/desktop/en-us/examples_tableau_semantics.htm) in Salesforce Help.

## Tableau Semantics Use Cases and Benefits

With Tableau Semantics, you use semantic models and semantic definitions on top of your data in Data 360 to serve as a single source of truth within Salesforce.

Without a semantic layer, individuals may come up with their own data models and calculated fields over and over, introducing inefficiencies and the potential for error or misalignment.

Tableau Semantics helps organizations unlock the full potential of their data by delivering:

*   **Unified, trusted data at scale:** Centralize your data and metrics in a single, governed layer for easy analysis and increased efficiency.  
    
*   **Accelerated time to insight:** Empower self-serve analytics and reduce manual effort with AI-powered features such as relationship suggestions and help writing calculations.  
    
*   **Agents aware of business context:** Get more accurate and relevant answers from your data with real-time business context.  
    

## Explore the Semantic Layer

You can create and define semantic models in the Semantic Layer tab in Data 360 or in a Tableau Next workspace.

In Data 360 you can see all the semantic models that exist in your org. You can create new semantic models, edit them, and even clone them directly from here.

![Semantic Layer Models tab.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/learn-the-basics-of-tableau-semantics/images/8af032826aa0cc35a52705fc244ca4a1_kix.34npf18ked1k.png)

When you create or edit a semantic model, you enter the Semantic Model Builder. Here you can add or edit different definitions for your semantic model. Let’s take a look.

![Semantic Model Builder with numbers for all areas.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/learn-the-basics-of-tableau-semantics/images/37d8aba7d6d887da482c22e7cb5ecd9f_kix.1whsrup1drya.png)

1.  **Model properties:** Edit the semantic model’s name, API name, and description.  
    
2.  **Suggested relationships:** Turn on or off suggested relationships so you can use Einstein to create automatic relationships between your data objects.  
    
3.  **New elements:** Create new elements for your semantic model, including metrics, calculated fields, parameters, logical views, and data objects.  
    
4.  **Search:** Search for different definitions that exist in your semantic model.  
    
5.  **Filter:** Filter the pane by different definitions.  
    
6.  **Sort:** Sort the results, for example by descending order.  
    
7.  **Model definitions pane:** View all the definitions that exist in your semantic model. Each time you create a new definition, it appears in this pane, allowing you to edit or delete it. You can also create new definitions by clicking on the plus icon.  
    
8.  **Canvas:** View all the data objects and their relationships. All of the data objects appear as icons so you can easily recognize them. If there are relationships between the objects, they appear as lines. If you hover over a relationship, you can see how they’re combined.  
    
9.  **Relationship recommendations:** If Einstein found recommended relationships, you can view them by clicking the Show Suggestions button.  
    
10.  **Test:** Click this button to test your semantic model and make sure it works as expected.  
    

If you click a data model object from inside the canvas, a preview panel appears below the canvas. Here you can view all the fields and their definitions.

![Semantic Model Builder dialog with preview pane opened at the bottom.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/learn-the-basics-of-tableau-semantics/images/2b6fa7c9bb6b99c6dc330f80f90f5bb4_kix.5mazx97o1rsf.png)

## Controlling Access to Semantic Models

In order to access the Semantic Layer and semantic models in Data 360, there are a few things you need to ensure.

1.  Data space access  
    
2.  User-level permissions  
    
3.  Explicit sharing of semantic models  
    

Let’s go over the different layers. First, make sure you can access the data space where your semantic model resides. This is done via a data space in Data 360. If users don’t have access to the data space, then they can’t view the semantic models, no matter their permissions. For more information about data spaces, see [Manage Data Spaces](https://help.salesforce.com/s/articleView?id=data.c360_a_data_spaces.htm&type=5) in Salesforce Help.

Next, make sure you have the correct user-level permissions. This controls who can create, edit, read, or delete semantic models. This is done using an object permission called Semantic Models. This permission is available in all Data 360 standard permission sets. In the example below you can see the Semantic Models object permission in the Data 360 User permission set.

![Data 360 User permission set with Semantic Models.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/learn-the-basics-of-tableau-semantics/images/5b973ae97bec4c2ccc76afd9620b9d8f_kix.ht536bvt3508.png)

You can then decide who can perform different tasks in the Semantic Layer using these permissions:

*   **Read:** Allows users to view and read semantic models.  
    
*   **Create:** Allows users to create new semantic models and semantic definitions within the same model.  
    
*   **Edit:** Allows users to edit existing semantic models.  
    
*   **Delete:** Allows users to delete semantic models that were created by the user.  
    

Additional permissions for admins:

*   **Modify All Records:** Allows users to view and edit all semantic models that are available in their workspace.  
    
*   **View All Records:** Allows users to view all semantic models that are available in their workspace.  
    

For more information about permission sets, see [Data 360 Standard Permission Sets](https://help.salesforce.com/s/articleView?id=data.c360_a_userpermissions.htm&type=5) in Salesforce Help.

Last but not least, make sure the user has access to the semantic models. By default, all semantic models are private. This means, unless you share a semantic model with a user, they won’t see it in their workspace, even if they have the correct permissions set up for their user. For more information about sharing, see [Manage Access to Semantic Models in Tableau Semantics](https://help.salesforce.com/s/articleView?id=data.c360_a_sl_data_models_access_management.htm&type=5) in Salesforce Help.

In this unit, you learned about the basics of Tableau Semantics, how to control who can access the semantic layer, and what the user interface looks like. In the next unit, learn about the different ways to create semantic models, and how to build a relationship between different objects.

Respuestas de la prueba:

---

**Pregunta 1 — What's the primary function of Tableau Semantics?**

**Respuesta: B — To define, govern, and query business metrics via the semantic layer.**

El documento explica que Tableau Semantics es una capa de traducción entre los datos crudos y los casos de uso de negocio, que mapea datos complejos en términos de negocio estandarizados como revenue, ROI o retention, proporcionando una interpretación consistente y sin ambigüedades a lo largo de la organización.

---

**Pregunta 2 — What's the name of the object permission that controls access to the semantic layer?**

**Respuesta: D — Semantic Models.**

El documento indica explícitamente que el permiso de objeto que controla quién puede crear, editar, leer o eliminar modelos semánticos se llama **Semantic Models**, y que está disponible en todos los permission sets estándar de Data 360.