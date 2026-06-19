# Use Advanced SQL Techniques

## Learning Objectives

After completing this unit, you’ll be able to:

*   Transform data values using the CASE conditional expression.  
    
*   Apply string manipulation functions, such as SUBSTRING(), to reformat data.  
    
*   Check for related data using subqueries with EXISTS and NOT EXISTS.  
    
*   Simplify complex queries using Common Table Expressions (CTEs).  
    

## Unlock the Full Potential of Queries

In the previous units, you reviewed the fundamental tools to select, filter, group, and join data. In this unit, you'll learn the techniques that elevate your queries from basic reports to sophisticated, reusable data logic.

These advanced techniques are essential for building multi-step analysis or quickly identifying relationships within massive datasets.

## Data Transformation with CASE and String Functions

Raw data rarely arrives perfectly formatted for reporting. You often need to change values, categorize numbers, or clean up text before analysis.

### Apply Conditional Logic with CASE

The CASE expression allows you to implement if/then/else logic directly in your SELECT statement. It checks a field's value against one or more conditions and returns a corresponding result, which is perfect for creating business categories.

The CASE expression has the following structure:

CASE WHEN condition\_1 THEN result\_1 WHEN condition\_2 THEN result\_2 ... ELSE result\_default END AS "New\_Column\_Alias"

To quickly segment accounts into 'High-Value' or 'Standard' based on a revenue field, use the following query to create the segment:

SELECT "ssot\_\_AccountId\_\_c", "ssot\_\_AnnualRevenue\_\_c", CASE WHEN "ssot\_\_AnnualRevenue\_\_c" > 100000 THEN 'High-Value' WHEN "ssot\_\_AnnualRevenue\_\_c" IS NULL THEN 'Unqualified' ELSE 'Standard' END AS "Account\_Segment" FROM "ssot\_\_Account\_\_dlm"

### Manipulate Text with String Functions

String manipulation functions are crucial for normalizing and cleaning text data, which ensures accuracy when filtering or grouping.

Use functions like UPPER() and TRIM() to standardize text fields for quality checks:

SELECT TRIM(UPPER("ssot\_\_FirstName\_\_c")) AS "Clean\_FirstName" FROM "ssot\_\_Individual\_\_dlm"

Another powerful function is SUBSTRING(), which extracts a specific sequence of characters from a string.

If you need to pull only the first three characters of a product code to identify its product family, use this query:

SELECT "ProductCode\_\_c", SUBSTRING("ProductCode\_\_c", 1, 3) AS "Product\_Family" FROM "ssot\_\_Product\_\_dlm"

The arguments are: the field, the starting position (1 in this case), and the length of the string to extract (3).

## Simplify and Optimize Queries

As your analysis becomes more complex, requiring multiple steps of filtering and calculation, your queries can become long and difficult to read. CTEs and subqueries help organize and optimize this complex logic.

### Simplify Complex Queries with CTEs

A Common Table Expression (CTE) is a temporary, named result set defined within the execution scope of a single SELECT statement. You define a CTE using the WITH clause.

CTEs are perfect for breaking down a multi-step query into logical, readable parts. They act as temporary virtual tables that you can reference immediately after they are defined.

To find the average order size for high-value accounts (revenue > 100000), first identify those accounts and then find their average order size using a CTE.

WITH HighValueAccounts AS ( SELECT "ssot\_\_AccountId\_\_c" FROM "ssot\_\_Account\_\_dlm" WHERE "ssot\_\_AnnualRevenue\_\_c" > 100000 ) SELECT AVG(o."OrderTotalAmount\_\_c") AS "Avg\_HighValue\_Order\_Amount" FROM "ssot\_\_SalesOrder\_\_dlm" o INNER JOIN HighValueAccounts h ON o."ssot\_\_AccountId\_\_c" = h."ssot\_\_AccountId\_\_c"

In this example, the HighValueAccounts CTE is calculated first and then treated like a standard DMO in the final SELECT statement.

### Check Related Data with Subqueries

A subquery (or inner query) is a query nested inside another SELECT statement. Subqueries are often used in the WHERE clause to filter the main query based on data from a related DMO without performing a full join.

The EXISTS operator checks if a subquery returns any rows. It is highly efficient because the subquery stops running as soon as it finds the first match. Use EXISTS to find all individuals who have _at least one_ related sales order:

SELECT "ssot\_\_FirstName\_\_c", "ssot\_\_LastName\_\_c" FROM "ssot\_\_Individual\_\_dlm" i WHERE EXISTS ( SELECT 1 FROM "ssot\_\_SalesOrder\_\_dlm" o WHERE o."ssot\_\_IndividualId\_\_c" = i."ssot\_\_Id\_\_c" )

Conversely, the NOT EXISTS operator returns TRUE if the subquery returns no rows. Use NOT EXISTS to identify at-risk customers—individuals who have no recorded sales orders:

WHERE NOT EXISTS ( SELECT 1 FROM "ssot\_\_SalesOrder\_\_dlm" o WHERE o."ssot\_\_IndividualId\_\_c" = i."ssot\_\_Id\_\_c" )

You’ve successfully navigated creating complex SQL queries in Data 360! Time to get started querying your own data.

Now that you've learned about data manipulation and common table expressions, it's time to check your knowledge in this unit and earn this badge.

## Reto práctico

+500 puntos

### Prepararse

Completará esta unidad en su propio Playground Data 360.

### Su reto

Analyze the Performance of Recent, High-Value Customers

Perform a final, complex analysis for the executive team. Retrieve a list of the individuals with accounts with opportunities at risk, which can be used to reach out to customers to avoid opportunity loss.  
  
**Prework**  
If you haven’t already completed unit 4, do that now. Otherwise, you won't be able to complete this challenge.

*   Write, run, and save a complex Data 360 SQL query using a CTE and a subquery. Use the object fields table to view available fields and their data types while creating this query.
    *   Create a CTE named `account_risk Copiar` .
        *   Use `ssot__Account__dlm Copiar` .
        *   Set the alias to `account Copiar` .
    *   In the CTE, filter for accounts that have an open opportunity with a probability less than or equal to 50%.
        *   Account ID: `account."ssot__Id__c" Copiar`
        *   Opportunity object: `"ssot__Opportunity__dlm" Copiar`
        *   Open opportunity field: `opportunity."ssot__IsClosed__c" Copiar`
        *   Probability field: `opportunity."ssot__Probability__c" Copiar`
    *   Set the opportunity alias to `opportunity Copiar` .
    *   Use the CTE and the individual object to find personal details.
        *   CTE name: `account_risk Copiar`
        *   CTE alias: `risk Copiar`
        *   Join using `risk."ssot__Id__c" Copiar` and `"ssot__PrimaryAccountId__c" Copiar`
    *   Use the individual object.
        *   Object: `ssot__Individual__dlm Copiar`
        *   Alias: `individual Copiar`
    *   Join the result with email contact point information to return the customer’s email address.
        *   Object: `"ssot__ContactPointEmail__dlm" Copiar`
        *   Alias: `email Copiar`
        *   Join using `individual."ssot__Id__c" Copiar` and `email."ssot__PartyId__c" Copiar`
    *   Return these fields.
        *   First name: `individual."ssot__FirstName__c" Copiar`
        *   Last name: `individual."ssot__LastName__c" Copiar`
        *   Email: `email."ssot__EmailAddress__c" Copiar`
        *   Company: `risk."ssot__Name__c" Copiar`
*   Run the query and check the results
*   Save the workspace

Caduca el 11/6/2026 a las 6:00 p. m. GMT-6

### Su Playground Data 360 está listo.

Ya puede practicar en esta insignia y con cualquier otra que requiera un Playground Data 360. Si el tiempo se agota, perderá el acceso a este Playground. Puede volver a solicitarlo, pero es posible que tenga que volver a empezar.

## Guía paso a paso para resolver el reto

---

### Paso 1: Abrir el workspace correcto

1. Ve a tu org de **Data Cloud** desde el App Launcher.
2. Haz clic en la pestaña **Query Editor**.
3. Abre el workspace **High Value Customers**.

---

### Paso 2: Escribir la Query

En el editor, pega exactamente este código:

```sql
WITH account_risk AS (
  SELECT account."ssot__Id__c",
         account."ssot__Name__c"
  FROM "ssot__Account__dlm" account
  WHERE EXISTS (
    SELECT 1
    FROM "ssot__Opportunity__dlm" opportunity
    WHERE opportunity."ssot__CustomerAccountId__c" = account."ssot__Id__c"
      AND opportunity."ssot__IsClosed__c" = 'false'
      AND opportunity."ssot__Probability__c" <= 50
  )
)
SELECT individual."ssot__FirstName__c",
       individual."ssot__LastName__c",
       email."ssot__EmailAddress__c",
       risk."ssot__Name__c"
FROM "ssot__Individual__dlm" individual
INNER JOIN account_risk risk
  ON individual."ssot__PrimaryAccountId__c" = risk."ssot__Id__c"
INNER JOIN "ssot__ContactPointEmail__dlm" email
  ON individual."ssot__Id__c" = email."ssot__PartyId__c"
```

**Estructura de la query:**

- **CTE `account_risk`**: usa `ssot__Account__dlm` con alias `account` y filtra con `EXISTS` las cuentas que tienen oportunidades abiertas (`IsClosed = false`) con probabilidad `<= 50%`, usando el alias `opportunity`.
- **Query principal**: une el CTE (`risk`) con `ssot__Individual__dlm` (`individual`) mediante `ssot__PrimaryAccountId__c`, luego une con `ssot__ContactPointEmail__dlm` (`email`) mediante `ssot__PartyId__c`.
- **Campos devueltos**: nombre, apellido, email y nombre de la empresa.

---

### Paso 3: Ejecutar la Query

1. Haz clic en **Run Query**.
2. Verifica que aparezcan resultados con las 4 columnas: nombre, apellido, email y empresa.

---

### Paso 4: Guardar la Query

1. Haz clic en **Save**.

---

### Paso 5: Verificar el reto

1. Regresa a Trailhead.
2. Haz clic en **Check Challenge**.

---

> **Tip:** Si el reto no pasa a la primera, revisa que `ssot__IsClosed__c = false` esté en minúsculas y que todos los aliases coincidan exactamente: `account_risk`, `account`, `opportunity`, `risk`, `individual`, `email`.