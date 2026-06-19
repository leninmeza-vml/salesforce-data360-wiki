# Manage a Data Graph

### Learning Objectives

After completing this unit, you’ll be able to:

*   Perform key actions on a data graph, including edit, delete, clone, refresh, and schedule.  
    
*   Identify what actions are restricted for draft data graphs.  
    
*   Review a data graph’s properties and JSON structure to understand its configuration.  
    
*   Locate and explore a data graph in Data Explorer.  
    

## Manage a Data Graph

Once you’ve created a data graph, the real work begins. Managing a data graph means keeping it accurate, up to date, and ready for use across Data 360. You can refresh or schedule updates to ensure the latest data is included, clone graphs to reuse configurations, or delete graphs you no longer need.

You can also dive into the graph’s properties and JSON structure to understand its setup and troubleshoot when needed. Finally, Data Explorer gives you a central place to view and work with your data graph in action.

Once the data graph is created, you can perform several actions:

*   Edit  
    
*   Delete  
    
*   Clone  
    
*   Refresh  
    
*   Schedule  
    
*   View Refresh History  
    

To manually refresh a data graph, select **Refresh Now** from the dropdown menu next to the data graph row in a list view. Keep in mind that the refresh process can take the same amount of time as the initial creation, depending on the data volume. The Last Refreshed On column in the list view displays the timestamp of the most recent update.

Draft data graphs can’t be cloned or refreshed.

## View Data Graph Properties

After your data graph is created, you can view its properties to review the configuration and status. This helps you understand the metadata, source details, and objects involved in the data graph.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

The Last Run Status may take a few moments to update. It may show the status of Processing before changing to Active.

*   In the Data Graphs tab, navigate to the my\_test\_dg graph data graph.  
    

In the data graph editor page, you can see the DMOs and fields of the data graph.

*   In the editor, click **View Properties** to access the data graph properties.  
    
*   To review the underlying structure, click **Preview** to view the JSON representation of the data graph.  
    

If needed, click **Copy** to copy the JSON structure to your clipboard, allowing you to paste it into a file or a JSON editor for further inspection.

Alternatively, you can view the JSON structure of the data graph directly from the Data Explorer tab in Data 360.

## View Your Data Graph in Data Explorer

After you create a data graph, you can view the data graph in Data Explorer.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

You can check the data graph in the Data Explorer tab once the data graph creation process is complete.

Before you begin, make sure you have the appropriate permissions to access Data Explorer. If you don’t see it in your app list, contact your admin to enable it.

1.  In Data 360, go to the Data Explorer tab.  
    
2.  From the Data Space dropdown, select the data space in which you created the my\_test\_dg data graph.  
    
3.  From the Object Type dropdown, select **Data Graphs**.  
    
4.  In the list of available data graphs, select **my\_test\_dg**.  
    
5.  To view the JSON of the data graph, click **View** next to the record.  
    
6.  To copy the data to use elsewhere, click **Copy**.  
    

In this unit, you learned how to manage a data graph after it’s created. You explored how to edit, clone, refresh, and schedule updates. You also reviewed how to view a graph’s properties and JSON structure, and how to access and explore it in Data Explorer.

By applying these skills, you can keep your data graphs dependable and ensure they continue to provide the up-to-date insights your business needs.

## Resources

*   [_Salesforce Help_: View Your Data in Data Explorer](https://help.salesforce.com/s/articleView?id=data.c360_a_view_your_data.htm&type=5)
*   [_Trailblazer Community_: Fast and Efficient: When and Why to Use Data Graphs in Data Cloud](https://trailhead.salesforce.com/trailblazer-community/feed/0D54V00007erz1eSAA)
*   [_Trailblazer Community_: Fast and Efficient: Optimize Data graph Performance and Credit Usage](https://trailhead.salesforce.com/trailblazer-community/feed/0D5KX00000J67kj0AB)

Respuestas de la prueba:

---

**Pregunta 1 — What happens when you manually refresh a data graph?**

**Respuesta: C — The refresh can take as long as the initial creation, depending on data volume.**

El documento indica que al hacer un refresh manual, el proceso puede tomar la misma cantidad de tiempo que la creación inicial, dependiendo del volumen de datos.

---

**Pregunta 2 — Which of the following actions is restricted for a draft data graph?**

**Respuesta: C — Cloning the data graph.**

El documento especifica explícitamente que los data graphs en estado **draft** no pueden ser clonados ni actualizados (refreshed). Entre las opciones, **Clone** es la que está restringida.