# Records

The code to produce a record needs to be imported before it can be used.

A record is defined with attributes, which can have default values.

``` python
# Get extra code
from dataclasses import dataclass

@dataclass
class Person:
    """A record to represent a person."""
    name: str = ""
    age: int = 0
    height: float = 0.0
```

Individual records can be created, either with default values, or with specified values.

``` python
person1 = Person()

person2 = Person("Beth", 23, 1.63)
```

Attribute values can be accessed using the form:

```
recordName.attributeName
```

An attribute value from a record can retrieved.

``` python
name = person2.name

print(name)
```

An attribute value can be updated.

``` python
person2.age = person2.age + 1

print(person2)
```


## Array of records

Initialising an array of records uses a loop to ensure that each element has an individual record.  If a loop is not used, each element has a copy of the same record, and that can cause problems.

``` python
# Create an array of 4 records
people = [Person() for index in range(4)]
```

``` python
# Update name in first record
people[0].name = "Alan"

# Update second record
people[1] = Person("Beth",  23,  1.63)
```

``` python
# Display array of records
print(people)

# Display second record
print(people[1])

# Display age in second record
print(people[1].age)

# Display first 2 characters of name in second record
print(people[1].name[ :2])
```

### Traverse an array of records

``` python
for index in range(len(people)):

    # Get values
    name = people[index].name
    age = people[index].age
    
    # Display name and age
    print(name + " is " + str(age) + " years old.")
```
