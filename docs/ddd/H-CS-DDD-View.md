# WHERE

It is possible to use the result from an aggregate function in a `WHERE` clause, but not directly.

A `VIEW` stores the result of a `SELECT` statement.
The view can then be queried like a table.

## Using a result in another query

This will create a temporary view that will be deleted when the database is closed.

``` sql
CREATE TEMP VIEW oldest (dob) AS
    SELECT MIN(doB)
    FROM pet;
```

Use the stored result.

``` sql
SELECT pet.name, vaccine.name, vaxDate, cost
    FROM oldest, pet, vaccination, vaccine
    WHERE pet.petID = vaccination.petID
        AND vaccination.vaxID = vaccine.vaxID
        AND oldest.dob = pet.dob;
```

## Subclause (Single query)

**Note** Using subclauses is beyond the scope of the Higher course and will not be assessed.

``` sql
SELECT pet.name, vaccine.name, vaxDate, cost
    FROM pet, vaccination, vaccine
    WHERE pet.petID = vaccination.petID
        AND vaccination.vaxID = vaccine.vaxID
        AND pet.dob = 
            (SELECT MIN(doB)
                FROM pet);
```
