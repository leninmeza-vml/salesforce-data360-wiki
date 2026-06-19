# Aggregate Data for High-Level Insights

## Learning Objectives

After completing this unit, you’ll be able to:

*   Calculate aggregate values using functions like COUNT, SUM, and AVG.  
    
*   Group query results using the GROUP BY clause.  
    
*   Filter grouped data using the HAVING clause.  
    

## Summarize Data for Business Intelligence

After mastering the basics of selecting and filtering data, the next critical step is to turn raw data into high-level metrics and business insights. Raw data, even when filtered, can be overwhelming. Data 360 SQL’s aggregate functions allow you to compute a single result from a set of values, such as the total purchases, average age, or count of customers.

These techniques are essential for creating reports to understand macro trends and business insights for stakeholders.

## Use Aggregate Functions

Aggregate functions perform calculations on a set of rows and return a single, summary value. You typically place these functions in the SELECT clause.

Here are the most common functions.

| **Function** | **Purpose** |
| --- | --- |
| **COUNT(\*)** | Returns the number of input rows. |
| **SUM(expression)** | Returns the sum of all input values. |
| **AVG(expression)** | Returns the average (arithmetic mean) of all input values. |
| **MIN(expression)** | Returns the minimum value in a set of input values. |
| **MAX(expression)** | Returns the maximum value in a set of input values. |

For a quick, high-level summary of all customer transactions, use aggregate functions to calculate the total number of orders, the total revenue, and the average order value (AOV) from the ssot\_\_SalesOrder\_dlm DMO.

SELECT COUNT(\*) AS "Total\_Orders", SUM("OrderTotalAmount\_\_c") AS "Total\_Revenue", AVG("OrderTotalAmount\_\_c") AS "Average\_Order\_Value" FROM "ssot\_\_SalesOrder\_\_dlm"

Each function processes the entire set of records in the DMO and returns a single row containing these three calculated metrics.

## Group Results with GROUP BY

A single aggregate value, like total revenue, is useful, but analysis usually requires these metrics broken down by categories (or groups). For example, you might need the total revenue broken down by Sales Channel or the customer count broken down by Country. To see the average order value for each country, follow this example.

To perform calculations for each unique group, you use the GROUP BY clause.

*   Include the category field you want to group by in your SELECT list.  
    
*   Include that same category field in the GROUP BY clause.  
    

For example, if you need to see the average order value for each country, your query would look like:

SELECT "ssot\_\_CountryId\_\_c" AS "Country", AVG("OrderTotalAmount\_\_c") AS "Average\_Order\_Value" FROM "ssot\_\_SalesOrder\_dlm" GROUP BY "ssot\_\_CountryId\_\_c"

The query calculates the average order value (AOV) separately for every unique value found in the ssot\_\_CountryId\_\_c field.

![Note](https://res.cloudinary.com/hy4kyit2a/image/upload/doc/trailhead/en-usb473bb5ea1b7e61dfb07e6a7e547de6b.gif)

Any nonaggregated field in the SELECT clause must also be included in the GROUP BY clause.

## Filter Groups with HAVING

You already know the WHERE clause filters individual rows before they are grouped and aggregated. To apply conditions to the summary results—the groups themselves—you use the HAVING clause.

The HAVING clause filters the output of the aggregate functions. It always comes after the GROUP BY clause.

If you are only interested in countries that have a high sales volume (meaning the average order value is greater than $500), this query first groups the orders by country, calculates the AOV for each, and then filters the final list to include only those countries that meet the $500 threshold.

SELECT "ssot\_\_CountryId\_\_c" AS "Country", AVG("OrderTotalAmount\_\_c") AS "Average\_Order\_Value" FROM "ssot\_\_SalesOrder\_dlm" GROUP BY "ssot\_\_CountryId\_\_c" HAVING AVG("OrderTotalAmount\_\_c") > 500

Now that you can start turning data into metrics and business insights, the next unit helps you dive into combining data from multiple sources. Now it’s time to check your skills in this hands-on challenge!

## Reto práctico

+500 puntos

### Prepararse

Completará esta unidad en su propio Playground Data 360.

### Su reto

Expected Revenue of High Probability Opportunities

Perform an audit on high probability opportunities. Identify which opportunities have a probability over 75% and find the average expected revenue of these opportunities for reporting.  
  
**Prework**  
If you haven’t already completed unit 1, do that now. Otherwise, you won't be able to complete this challenge.

*   In the main editor window of the Customer Data Quality workspace, **create a query** with these details:
    *   Use the opportunity object: `ssot__Opportunity__dlm Copiar`
    *   Select the required field for revenue: `ssot__ExpectedRevenueAmount__c Copiar`
    *   Average the expected revenue amounts of opportunities with a probability over 75% using the `ssot__Probability__c Copiar` field.
*   Run the query and check the results
*   Save the workspace

Caduca el 11/6/2026 a las 6:00 p. m. GMT-6

### Su Playground Data 360 está listo.

Ya puede practicar en esta insignia y con cualquier otra que requiera un Playground Data 360. Si el tiempo se agota, perderá el acceso a este Playground. Puede volver a solicitarlo, pero es posible que tenga que volver a empezar.

## Guía paso a paso para resolver el reto

---

### Paso 1: Abrir el Query Editor

1. Ve a tu org de **Data Cloud** desde el App Launcher.
2. Haz clic en la pestaña **Query Editor**.
3. Abre el workspace **Customer Data Quality**.

---

### Paso 2: Escribir la Query

En el editor, pega exactamente este código:

```sql
SELECT AVG("ssot__ExpectedRevenueAmount__c") AS "Average_Expected_Revenue"
FROM "ssot__Opportunity__dlm"
WHERE "ssot__Probability__c" > 75
```

**¿Por qué cada parte?**
- `AVG(...)` → calcula el **promedio** del ingreso esperado
- `FROM ssot__Opportunity__dlm` → fuente de datos de oportunidades
- `WHERE ssot__Probability__c > 75` → filtra solo oportunidades con probabilidad **mayor al 75%**

---

### Paso 3: Ejecutar la Query

1. Haz clic en **Run Query** (esquina superior izquierda).
2. Verifica que aparezca **un solo valor** en el panel de resultados, que representa el promedio de ingresos esperados.

---

### Paso 4: Guardar la Query

1. Haz clic en **Save** (esquina superior derecha).

---

### Paso 5: Verificar el reto

1. Regresa a Trailhead.
2. Haz clic en **Check Challenge**.