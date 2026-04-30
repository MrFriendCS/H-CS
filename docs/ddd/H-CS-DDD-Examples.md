# Examples

``` sql
SELECT species, COUNT(*) as jags
    FROM Pet, Vaccination
    WHERE Pet.petID = Vaccination.vaxID
        AND vaxDate >= "2020-01-01"
        AND vaxDate <= "2020-12-31"
    GROUP BY species
    ORDER BY jags DESC;
```

``` sql
SELECT Pet.petID, Pet.name, species, SUM(cost * 1.2) as [inc VAT]
    FROM Pet, Vaccination, Vaccine
    WHERE Pet.petID = Vaccination.vaxID
        AND Vaccination.vaxID = Vaccine.vaxID
        AND paid = FALSE
    GROUP BY Pet.petID
    ORDER BY [inc VAT] DESC;
```
