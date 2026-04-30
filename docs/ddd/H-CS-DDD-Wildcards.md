# Wildcards

Wildcards use the `LIKE` keyword, and are used with `WHERE`.  There are two wildcards:

| Symbol | Name       | Meaning |
| :----: | ----       | ------- |
| %      | Percent    | Zero, one, or more characters |
| _      | Underscore | A single character |

Zero, one, or more characters, after the first character.

``` sql
SELECT *
    FROM Pet
    WHERE name LIKE "G%";
```
Zero, one, or more characters, before the last character.

``` sql
SELECT *
    FROM Pet
    WHERE name LIKE "%n";
```

Zero, one, or more characters in the middle.

``` sql
SELECT *
    FROM Pet
    WHERE species LIKE "R%t";
```

A single character.

``` sql
SELECT *
    FROM Pet
    WHERE species LIKE "_at";
```
