# Procedures

A procedure is a type of sub-routine that ***does not*** return a value.
It must be defined before it can be used.

When a procedure is defined it can have zero, one, or more parameters.
These are known as formal parameters.
The formal parameters will 'catch' values that are passed to the procedure when it is 'called'.


## Example - General

``` python
def procedureName(formalParameter1: dataType, formalParameter2: dataType, ...) -> None:
    """docstring"""
    
    <procedure code>
```

A procedure can be called from the main program, or from another sub-routine.
The procedure call can pass zero, one, or more actual parameters to the procedure.

``` python
procedureName(actualParameter1, actualParameter2, ...)
```


## Example - No formal parameters

``` python
def pickRandom() -> None:
    """Displays a random number from 1 to 10."""
    
    # Get extra code
    import random
    
    # Intialise local variable
    randomNumber = 0
    
    # Pick random number
    randomNumber = random.randint(1, 10)
    
    # Display random number
    print("Random number: " + str(randomNumber))
```

This procedure can be called from the main program, or from another sub-routine.

``` python
pickRandom()
```


## Example - One formal parameter



``` python
def square(number: int) -> None:
    """Displays the square of a number."""
    
    # Intialise local variable
    squared = 0
    
    # Calculate result
    squared = number ** 2
    
    # Display the result
    print("The square of " + str(number) + " is " + str(squared))
```

This procedure can be called from the main program, or from another sub-routine.

``` python
square(2)
```


## Example - Multiple formal parameters

``` python
def powerOf(number: int, power: int) -> None:
    """Displays a number raised to a power."""
    
    # Intialise local variable
    result = 0
    
    # Calculate result
    result = number ** power
    
    # Display the result
    print(str(number) + " raised to the power of " + str(power) + " is " + str(result))
```

This procedure can be called from the main program, or from another sub-routine.

``` python
powerOf(5, 3)
```
