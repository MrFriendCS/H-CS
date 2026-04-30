# GROUP BY

`GROUP BY` places results of a query into logical groups and removes duplicates.  Aggregate functions can be used with each group.

The following example will return the `species` field from every record.  Values will be repeated if they are repeated in the table.

``` sql
SELECT species
    FROM Pet;
```

The following example will group together `species` field from every record.  Values will not be repeated, i.e. one row for each group.

``` sql
SELECT species
    FROM Pet
    GROUP BY species;
```

**Note:** If fields and aggregate functions are both displayed then the fields must be in the `GROUP BY` clause, otherwise the result is meaningless.

``` sql
SELECT species, MIN(dob), MAX(dob)
    FROM Pet
    GROUP BY species;
```


## ORDER BY

`ORDER BY`, if used, must follow `GROUP BY`.

``` sql
SELECT species, COUNT(species)
    FROM Pet
    GROUP BY species
    ORDER BY COUNT(species) DESC;
```
