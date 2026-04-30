# Alias

To display search results with a different column heading instead of the field name the `AS` keyword is used.

``` sql
SELECT name AS Jag, cost
    FROM Vaccine;
```

The alias can be used within the `ORDER BY` clause.

``` sql
SELECT name AS Jag, cost
    FROM Vaccine
    WHERE Jag LIKE "F%"
    ORDER BY Jag DESC;
```

Aliases are not restricted to single words.  Due to the space, square brackets are used.

``` sql
SELECT petID, name, species, dob AS [Date of Birth]
    FROM Pet
    ORDER BY [Date of Birth] ASC;
```
