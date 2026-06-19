# Combine Data from Multiple Objects with Joins

## Learning Objectives

After completing this unit, you’ll be able to:

*   Describe the purpose and mechanics of a join query.  
    
*   Write a query to perform an INNER JOIN between two DMOs.  
    
*   Combine data using LEFT, RIGHT, and FULL OUTER JOINS.  
    
*   Ensure accurate join results by joining on both the ID and the key qualifier fields.  
    

## Explore the Use of Joins

So far, you’ve queried data from single data model objects (DMOs) and data lake objects (DLOs). But in Data 360, customer information is naturally spread across multiple objects. For example, a customer's profile is in the Individual DMO, while their email addresses are in the ContactPointEmail DMO.

To create a single, unified view of a customer, you need to use joins. A join combines data from two or more DMOs or DLOs based on a related field that they share. This allows you to bring together separate pieces of information, such as an individual's name and their corresponding email address, into one result set.

### Inner Join

The INNER JOIN is the most common type of join. It returns only the rows that have matching values in the specified join fields in both tables. Records that only exist in one of the tables are excluded.

To perform an INNER JOIN:

*   List the first table in the FROM clause.  
    
*   Use the INNER JOIN keyword, followed by the second table.  
    
*   Specify the join condition using the ON keyword.  
    

To see the first name, last name, and email address for all individuals who have a recorded email contact point, use an INNER JOIN to ensure you only get records where both pieces of data exist.

In this query, the Individual DMO is joined to the ContactPointEmail DMO using the common key, ssot\_\_IndividualId\_\_c. Records are only included if the Individual ID exists in both DMOs. Notice that aliases (i. and e.) are used to clearly specify which table each field is coming from.

SELECT i."ssot\_\_FirstName\_\_c", i."ssot\_\_LastName\_\_c", e."ssot\_\_EmailAddress\_\_c" FROM "ssot\_\_Individual\_\_dlm" i INNER JOIN "ssot\_\_ContactPointEmail\_\_dlm" e ON i."ssot\_\_Id\_\_c" = e."ssot\_\_IndividualId\_\_c"

### Outer Joins

While the INNER JOIN is useful for matching records, you sometimes need to include records that don't have a match in the other table. This is where outer joins come in.

#### LEFT OUTER JOIN

A LEFT OUTER JOIN (often shortened to LEFT JOIN) returns:

*   All rows from the left table (the one listed first in the FROM clause).  
    
*   Any matching rows from the right table.  
    
*   If no match is found for a row in the left table, the fields from the right table are returned as NULL.  
    

To get a full list of all individuals, including those who have no email address on file, this query is the same as the INNER JOIN, but using LEFT JOIN ensures all individuals are kept.

SELECT i."ssot\_\_FirstName\_\_c", i."ssot\_\_LastName\_\_c", e."ssot\_\_EmailAddress\_\_c" FROM "ssot\_\_Individual\_\_dlm" i LEFT JOIN "ssot\_\_ContactPointEmail\_\_dlm" e ON i."ssot\_\_Id\_\_c" = e."ssot\_\_IndividualId\_\_c"

#### RIGHT and FULL OUTER JOIN

*   **RIGHT OUTER JOIN** (or **RIGHT JOIN** ) **:** Returns all rows from the right table, and the matched rows from the left table.  
    
*   **FULL OUTER JOIN** (or **FULL JOIN** ) **:** Returns all rows from both tables. Where there is no match, the columns from the non-matching side return NULL.  
    

For simplicity and portability, LEFT JOIN is generally preferred. If you need a RIGHT JOIN, you can typically achieve the same result by swapping the order of the tables and using a LEFT JOIN.

## Joining Best Practices: Use the Key Qualifier (KQ\_Id\_\_c)

In Unit 1, you learned about the key qualifier (KQ\_Id\_\_c) field. For most queries, especially those that involve one-to-many relationships (like one Individual having many Contact Points), Data 360 often requires you to join on both the primary ID and the KQ\_Id\_\_c for the most accurate and unique results.

A more robust join for your email list would look like this:

ON i."ssot\_\_Id\_\_c" = e."ssot\_\_IndividualId\_\_c" AND i."KQ\_Id\_\_c" = e."KQ\_Id\_\_c"

Joining on both fields is the best practice in Data 360 SQL to ensure you correctly link the specific, qualified version of a record.

You learned how to bring together complex data and filter, in the next unit you learn how to handle incorrect or mismatched data on the fly in your queries.

Practice what you learned by completing the challenge below before moving on to the next unit.

## Reto práctico

+500 puntos

### Prepararse

Completará esta unidad en su propio Playground Data 360.

### Su reto

Unify Customer Profile and Sales Data

Start a new project to determine which customers have a high revenue value in their account. To do this link individuals with their sales accounts.

*   Create a workspace.
    *   Data space: Default
    *   Name: `High Value Customers Copiar`
*   Write, run, and save a query that joins individuals to their sales accounts and filters for individuals with annual revenue values greater than `500000000 Copiar` :
    *   Use the individual object ( `ssot__individual__dlm Copiar` , alias `individual Copiar` )
    *   Join the account object ( `ssot__Account__dlm Copiar` , alias `account Copiar` ) to the individual object using the individual ID ( `individual.ssot__PrimaryAccountId__c Copiar` ) and the account ID ( `account.ssot__Id__c Copiar` ).
    *   Select the individual's first name ( `ssot__FirstName__c Copiar` ) to easily identify them.
    *   Filter for accounts with revenue (ssot\_\_AnnualRevenueAmount\_\_c) values over `500000000 Copiar` .
*   Run the query and check the results
*   Save the workspace

Caduca el 11/6/2026 a las 6:00 p. m. GMT-6

### Su Playground Data 360 está listo.

Ya puede practicar en esta insignia y con cualquier otra que requiera un Playground Data 360. Si el tiempo se agota, perderá el acceso a este Playground. Puede volver a solicitarlo, pero es posible que tenga que volver a empezar.

## Guía paso a paso para resolver el reto

---

### Paso 1: Abrir el Query Editor y crear un nuevo Workspace

1. Ve a tu org de **Data Cloud** desde el App Launcher.
2. Haz clic en la pestaña **Query Editor** → clic en **New**.
3. Completa los campos:
   - **Workspace Name:** `High Value Customers`
   - **Data Space:** `Default`
4. Haz clic en **Save**.

---

### Paso 2: Escribir la Query

En el editor, pega exactamente este código:

```sql
SELECT individual."ssot__FirstName__c"
FROM "ssot__individual__dlm" individual
INNER JOIN "ssot__Account__dlm" account
  ON individual."ssot__PrimaryAccountId__c" = account."ssot__Id__c"
WHERE account."ssot__AnnualRevenueAmount__c" > 500000000
```

**¿Por qué cada parte?**
- `FROM ssot__individual__dlm individual` → tabla de individuos con alias `individual`
- `INNER JOIN ssot__Account__dlm account` → une la tabla de cuentas con alias `account`
- `ON individual.ssot__PrimaryAccountId__c = account.ssot__Id__c` → condición de unión entre ambas tablas
- `WHERE ... > 500000000` → filtra solo cuentas con ingresos anuales **mayores a 500,000,000**

---

### Paso 3: Ejecutar la Query

1. Haz clic en **Run Query** (esquina superior izquierda).
2. Verifica que aparezcan resultados en el panel inferior con nombres de individuos.

---

### Paso 4: Guardar la Query

1. Haz clic en **Save** (esquina superior derecha).

---

### Paso 5: Verificar el reto

1. Regresa a Trailhead.
2. Haz clic en **Check Challenge**.