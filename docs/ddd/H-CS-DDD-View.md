# WHERE

It is possible to use the result from an aggregate function in a `WHERE` clause, but not directly.

A `VIEW` stores the result of a `SELECT` statement.
The view can then be queried like a table.

## Using a result in another query

This will create a temporary view that will be deleted when the database is closed.

``` sql
CREATE TEMP VIEW YoungPet AS
    SELECT MIN(doB) AS dob
        FROM Pet;
```

Use the stored result.

``` sql
SELECT Pet.name,
       Vaccine.name,
       vaxDate,
       cost
    FROM YoungPet,
         Pet,
         Vaccination,
         Vaccine
    WHERE Pet.petID = Vaccination.petID
      AND Vaccination.vaxID = Vaccine.vaxID
      AND YoungPet.dob = Pet.dob;
```

## Subclause (Single query)

**Note** Using subclauses is beyond the scope of the Higher course and will not be assessed.

``` sql
SELECT Pet.name,
       Vaccine.name,
       vaxDate,
       cost
    FROM Pet,
         Vaccination,
         Vaccine
    WHERE Pet.petID = Vaccination.petID
      AND Vaccination.vaxID = Vaccine.vaxID
      AND Pet.dob = (
            SELECT MIN(doB)
                FROM Pet);
```
