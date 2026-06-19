# Create a Logical View for Your Semantic Model

## Learning Objectives

After completing this unit, you’ll be able to:

*   Describe what a logical view is.  
    
*   Understand when and how to create a logical view with a join  
    
*   Understand when and how to create a logical view with a union  
    

## Explore Logical Views

Connecting tables with relationships keeps each table distinct as its own object. If you instead want to combine two or more tables into a single new object, you can use a [logical view](https://help.salesforce.com/s/articleView?language=en_US&id=data.c360_a_sl_logical_view.htm&type=5). This can be useful when the data should be more tightly coupled than with a relationship. The logical view is a separate object within the semantic model, with its own fields and it’s queried separately as its own object by the query service.

There are two ways to combine tables in a logical view: joins and unions.

*   **Join:** Combines multiple tables into a single table based on a specific join type, adding columns to widen the data.  
    
*   **Union:** Stacks multiple tables into a single table based on a shared structure, adding rows to lengthen the data  
    

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Relationships are eventually resolved into joins. A logical view with a join should only be used when you need the behavior of a specific join type.

Unions can't be created with relationships. If your data is in multiple tables that need to be appended, a logical view with a union is required.

## Create a Logical View Using a Join

If there's a reason to force a specific join type between two objects, you can use a logical view and hard-code the join type. This ensures the exact behavior of the join every time the data is queried.

*   **Left join:** A left join returns all records from the left DMO and the matched records from the right DMO.  
    
*   **Inner join:** An inner join returns all records that have matching values in two DMOs.  
    
*   **Right join:** A right join returns all records from the right DMO and the matched records from the left DMO.  
    
*   **Outer join:** An outer join, also called a full join, returns all records from both DMOs.  
    

For more information about the types of joins and examples, see [Using the Join Clause for Insights](https://help.salesforce.com/s/articleView?id=data.c360_a_calculated_insights_joins.htm&type=5) in Salesforce Help.

Joins look at the value of the fields in the join clause and bring in additional columns of data when the join clause is true. This changes the structure of the joined table by adding more columns of data across the existing rows or records.

Imagine you're interested in products that were purchased. You have a data object for Product and data object for Sales, and both contain a Product ID field. A logical view with an inner join of these tables would contain only purchased products.

1.  In the Semantic Model Builder, from the **New** dropdown menu, select **Logical View**.  
    ![Semantic Model Builder showing the New dropdown with Logical View highlighted.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-logical-view-for-your-semantic-model/images/bcf42acdeda8c571a8051101079fc0da_kix.gjta1bb98w3x.png)  
    
2.  In the **Create a Logical View** window enter a unique name, API name, and optional description.  
    ![Create a Logical View dialog.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-logical-view-for-your-semantic-model/images/90c400532392060d1be48041a0a9fe6c_kix.wf7oe93rxp5u.png)  
    
3.  Click **Save**.  
    
4.  Next, choose the first data object for the logical view (Products).  
    *   You can select a DMO, DLO, or Calculated Insight.  
        
    *   You can include all ‌of the fields, or select specific ones to include.  
        ![Select a Data Object for the Logical View dialog.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-logical-view-for-your-semantic-model/images/d09b75906e3299dbeb01f8270fd517c1_kix.j0rliv4x9iid.png)  
        
5.  Click **Save**.  
    
6.  To add a join, select the object, and then click the plus sign.  
    ![Add Join dialog highlighted.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-logical-view-for-your-semantic-model/images/6208c390c55a9e3745cdd9b57d11c383_kix.rwcyb3uwxjzm.png)  
    
7.  From the dropdown menu, select **Join Object**.  
    
8.  Select the object that you want to join and then click **Save**.  
    ![Select a Data Object for the Logical View dialog with the sales object selected.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-logical-view-for-your-semantic-model/images/ce347e2a249d314ef3fb2ace0521ec66_kix.gtsa024nz7wk.png)  
    
9.  Select the join type using the join icons. For this example, select **Inner Join**.  
    ![Join panel open at the bottom of the screen.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-logical-view-for-your-semantic-model/images/fce2f904522f56e897646b8141e7c795_kix.yn5z715xzkxk.png)  
    
10.  Under **Select Matching Data Object Fields**, click the plus sign and select which fields should be used in the join clause. In this case, connect Product and Sales, by Product ID.  
    
11.  Under the left object, search for the field name.  
    
12.  Under the right object, search for the corresponding field name.  
    ![Join dialog with Choose Data Fields dialog highlighted.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-logical-view-for-your-semantic-model/images/a3c5bcd54284af0b66181e04160eec2f_kix.in1pjtpjdlxu.png)  
    
13.  Click **Add**. After you add your fields, the bottom pane shows a preview of the logical view and a line connecting the two objects indicates that the join is successful.  
    ![Semantic Model Builder with preview of joined objects.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-logical-view-for-your-semantic-model/images/820ee74b2a573481e6edb0adb7185891_kix.etlrx48q68iy.png)  
    
14.  Click **Apply**.  
    

The logical view is added to your semantic model and appears with its own icon.![Semantic Model Builder with created logical view highlighted.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-logical-view-for-your-semantic-model/images/786ab7c74b5a812f1a4d58b7a0ed3f94_kix.ygz7tsia394x.png)

You can now use this logical view just like any other data object in the model.

## Create a Logical View Using a Union

As we just saw, joins bring together more columns of data for each record, making the data wider. This is the same final behavior as a relationship.

In contrast, [unions](https://help.salesforce.com/s/articleView?id=data.c360_a_sl_unions_create.htm&type=5) combine records by stacking the tables according to their shared column structure, essentially adding more rows to the new combined table. For example, you may have marketing data that tracks lead generation information across three different channels: email, social, and digital ads. Each channel captures the same information (the same columns) but from different systems, so there's a different table per channel. A union would append all three tables together based on their shared column structure.

1.  In the Semantic Model Builder, from the New dropdown menu, click **Logical View**.  
    
2.  In the Create a Logical View window enter a unique name, API name, and optional description. Click **Save**.  
    
3.  Next, choose the first data object for the union and then click **Save**.  
    
4.  To add a union, select the object, and then click the plus sign.  
    
5.  From the dropdown menu, select **Create Union**.  
    ![Add dropdown showing the Create Union option.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-logical-view-for-your-semantic-model/images/8da91ba6d6e1b6ec4b10dd5f62b03422_kix.78enibc7nve3.png)  
    
6.  In the **Select Data Objects for Union** dialog, select the first object for the union and then click **Save**. You can select up to nine objects. The merged fields in the union receive metadata from the first added object.  
    ![Select Data Objects for Union dialog with list of objects.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-logical-view-for-your-semantic-model/images/d02c27d054c8090cf698166002fadd10_kix.9dsrtvcr1uyu.png)  
    A preview of the selected object and fields appears.  
    ![Data Model Object preview of fields.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-logical-view-for-your-semantic-model/images/e810890280321c557329de5b6b9a9878_kix.rhd3puwojk8k.png)  
    
7.  When all data objects have been added, click **Apply** to add the new union to the logical view.  
    

The union appears in the Semantic Model Builder Canvas.

![Logical View Builder with Union highlighted in the canvas.](https://res.cloudinary.com/hy4kyit2a/f_auto,fl_lossy,q_70/learn/modules/tableau-semantics/create-a-logical-view-for-your-semantic-model/images/a93b18504571175b0eac95b1a0d862b0_kix.iyoju1glqjwy.png)

In this unit, you learned about what logical views are and their different use cases, how to create a logical view with a join, and how to create a logical view with a union. In the next unit, you learn about the different ways you can create calculated fields in your semantic model.

Respuestas de la prueba:

---

**Pregunta 1 — What is a logical view in Data 360?**

**Respuesta: B — A data object made up of multiple tables connected via specific join types.**

El documento explica que una logical view combina dos o más tablas en un único objeto nuevo dentro del semantic model, con sus propios campos, que puede construirse mediante joins o unions cuando los datos necesitan estar más estrechamente acoplados que con una simple relationship.

---

**Pregunta 2 — Which join type includes all the records from the left object and corresponding record matches from the right object?**

**Respuesta: B — Left join.**

El documento define explícitamente que un **left join** retorna todos los registros del DMO izquierdo y solo los registros coincidentes del DMO derecho, que es exactamente lo que describe la pregunta.