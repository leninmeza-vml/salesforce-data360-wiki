# Filter, Order, and Limit Your Query Results

## Learning Objectives

After completing this unit, you’ll be able to:

*   Filter query results using the WHERE clause with logical operators.  
    
*   Search for patterns in string data using the LIKE operator.  
    
*   Sort query results in ascending or descending order using ORDER BY.  
    
*   Limit the number of returned rows with the LIMIT and OFFSET clauses.  
    

## Filter Query Results with WHERE

In the previous unit, you learned how to write a simple query using SELECT and FROM. It's a good idea to focus your analysis on a specific subset of data to limit the results and hone in on what is useful. To do this, use the WHERE clause to filter the results.

The WHERE clause always comes after the FROM clause and allows you to specify conditions that must be met for a record to be included in your final result set.

### Use Comparison and Logical Operators

You can use standard comparison operators (like =, >, <, !=) and logical operators (AND, OR) to define your criteria.

Let’s say you need to conduct a data quality check to find records that are missing a birth date, and you're only interested in records created after a specific date in 2024. To do this, you would use the following query.

SELECT "ssot\_\_FirstName\_\_c", "ssot\_\_LastName\_\_c", "ssot\_\_CreatedDate\_\_c" FROM "ssot\_\_Individual\_\_dlm" WHERE "ssot\_\_createdDate\_\_c" > DATE '2024-01-01' AND "ssot\_\_BirthDate\_\_c" IS NULL

In this example:

*   \> is a comparison operator.  
    
*   AND is a logical operator that requires both conditions to be true.  
    
*   IS NULL is used to specifically check for records where the field is empty or undefined. You would use IS NOT NULL to exclude records where a value is missing.  
    

You can also use the OR operator to return a record if _either_ of the specified conditions is met. You can use parentheses () to group conditions for complex logic and clarity.

## Search for Patterns with LIKE

Sometimes you don't know the exact value you're looking for, or you want to match a group of related text values (strings). The LIKE operator is used for pattern matching against text fields.

The LIKE operator is used with wildcards.

*   **Percent sign (** **%** **):** Matches any sequence of zero or more characters.  
    
*   **Underscore (** **\_** **):** Matches any single character.  
    

For example, if you want to see all last names that begin with the letter 'S' for a focused segment, you can use the % wildcard. Here’s what that looks like.

SELECT "ssot\_\_FirstName\_\_c", "ssot\_\_LastName\_\_c" FROM "ssot\_\_Individual\_\_dlm" WHERE "ssot\_\_LastName\_\_c" LIKE 'S%'

## Order and Limit Your Results

Even after filtering with WHERE, a query can still return thousands of records. To make the results manageable for review and to target specific records, you use the ORDER BY and LIMIT clauses.

### Sort Data with ORDER BY

The ORDER BY clause sorts your result set based on one or more specified fields. This is crucial because, without it, the order of the results can be inconsistent.

*   **Ascending order:** To sort in ascending order (A-Z, 1–100), use the ASC keyword.  
    
*   **Descending order:** To sort in the reverse order (Z-A, 100–1), use the DESC keyword.  
    

If you wanted to find the 20 newest individuals (sorted by the date they were created in the source system), you would sort by the ssot\_\_createdDate\_\_c field in descending order.

SELECT "ssot\_\_FirstName\_\_c", "ssot\_\_CreatedDate\_\_c" FROM "ssot\_\_Individual\_\_dlm" ORDER BY "ssot\_\_CreatedDate\_\_c" DESC

### Control the Row Count with LIMIT and OFFSET

The LIMIT clause controls exactly how many rows are returned in the final result set. This is most often used with ORDER BY to find the "top N" records, such as the 10 most recent records or the 5 lowest prices.

To find the 20 most recent individuals, you combine the previous query with LIMIT.

SELECT "ssot\_\_FirstName\_\_c", "ssot\_\_CreatedDate\_\_c" FROM "ssot\_\_Individual\_\_dlm" ORDER BY "ssot\_\_CreatedDate\_\_c" DESC LIMIT 20

The OFFSET clause is used in conjunction with LIMIT to skip a specified number of rows before starting to return the result set. For example, to retrieve the second page of 20 results, you would skip the first 20: LIMIT 20 OFFSET 20.

Now that you can effectively find the data you are looking for, you can start turning that data into metrics and business insights in the next unit. But before moving on, put what you learned into practice by following the instructions to complete the challenge in this unit.

## Reto práctico

+500 puntos

### Prepararse

Completará esta unidad en su propio Playground Data 360.

### Su reto

Extract Targeted Customer List for AW Computing

Using what you learned in this unit and the previous unit, write, run, and save a query to find the 5 customers with the oldest age who have a valid photo and whose last name begins with 'P'.  
  
**Prework**  
If you haven’t already completed unit 1, do that now. Otherwise, you won't be able to complete this challenge.

*   In the main editor window of the Customer Data Quality workspace, **create a query** with these details:
    *   Select the `ssot__LastName__c Copiar` , `ssot__PhotoURL__c Copiar` , and `ssot__BirthDate__c Copiar` fields from the `ssot__Individual__dlm Copiar` object
    *   Filter the results:
        *   All records with `ssot__LastName__c Copiar` starting with the letter `P Copiar` .
        *   The `ssot__PhotoURL__c Copiar` must not be `NULL Copiar` .
    *   Sort the results with the oldest `ssot__BirthDate__c Copiar` first
    *   Limit the query to `5 Copiar` records

Caduca el 11/6/2026 a las 6:00 p. m. GMT-6

### Su Playground Data 360 está listo.

Ya puede practicar en esta insignia y con cualquier otra que requiera un Playground Data 360. Si el tiempo se agota, perderá el acceso a este Playground. Puede volver a solicitarlo, pero es posible que tenga que volver a empezar.

## Guía paso a paso para resolver el reto

---

### Paso 1: Abrir el Query Editor

1. Ve a tu org de **Data Cloud** desde el App Launcher.
2. Haz clic en la pestaña **Query Editor**.
3. Abre el workspace **Customer Data Quality** que creaste en la unidad anterior.

---

### Paso 2: Escribir la Query

En el editor, pega exactamente este código:

```sql
SELECT "ssot__LastName__c",
       "ssot__PhotoURL__c",
       "ssot__BirthDate__c"
FROM "ssot__Individual__dlm"
WHERE "ssot__LastName__c" LIKE 'P%'
AND "ssot__PhotoURL__c" IS NOT NULL
ORDER BY "ssot__BirthDate__c" ASC
LIMIT 5
```

**¿Por qué cada parte?**
- `LIKE 'P%'` → apellidos que empiezan con la letra **P**
- `IS NOT NULL` → solo registros que **tienen** foto válida
- `ORDER BY ... ASC` → los más viejos primero (fecha de nacimiento más antigua = ASC)
- `LIMIT 5` → solo los **5** resultados

---

### Paso 3: Ejecutar la Query

1. Haz clic en **Run Query** (esquina superior izquierda del editor).
2. Verifica que aparezcan resultados en el panel inferior con 5 registros.

---

### Paso 4: Guardar la Query

1. Haz clic en **Save** (esquina superior derecha).

---

### Paso 5: Verificar el reto

1. Regresa a Trailhead.
2. Haz clic en **Check Challenge**.