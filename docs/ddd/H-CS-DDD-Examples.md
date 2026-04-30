# Examples

``` sql
SELECT species, COUNT(*) as jags
    FROM pet, vaccination
    WHERE pet.petID = vaccination.vaxID
        AND vaxDate >= "2020-01-01"
        AND vaxDate <= "2020-12-31"
    GROUP BY species
    ORDER BY jags DESC;
```

``` sql
SELECT pet.petID, pet.name, species, SUM(cost * 1.2) as [inc VAT]
    FROM pet, vaccination, vaccine
    WHERE pet.petID = vaccination.vaxID
        AND vaccination.vaxID = vaccine.vaxID
        AND paid = FALSE
    GROUP BY pet.petID
    ORDER BY [inc VAT] DESC;
```
