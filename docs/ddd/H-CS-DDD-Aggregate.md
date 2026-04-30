# Aggregate functions

Aggregate functions can be used with the `GROUP BY` clause.

## Minimum / Maximum

The `MIN` keyword is used to find the minimum value in a field, and `MAX` is used to find the maximum.  These work for both numeric and text values.

Find the `dob` of the oldest and youngest pet.

``` sql
SELECT MIN(dob), MAX(dob)
    FROM Pet;
```

## Average

``` sql
SELECT AVG(cost)
    FROM Vaccine;
```

## Sum

``` sql
SELECT SUM(cost)
    FROM Vaccination, Vaccine
    WHERE vaccination.vaxID = vaccine.vaxID
        AND pet_id = 14;
```

## Count

Count the number of records in a table that meet the condition.

``` sql
SELECT COUNT(*)
    FROM Pet
    WHERE species = "Rabbit";
```
