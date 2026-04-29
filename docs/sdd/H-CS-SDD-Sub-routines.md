# Sub-routines

When a sub-routine is defined it can have zero, one, or more parameters.  These are known as formal parameters.  The formal parameters will 'catch' values that are passed to the sub-routine.

``` python
def subroutineName(formalParameter1, formalParameter2, ...):
    """docstring"""
    
    <sub-routine code>
```

When a sub-routine is called it can have parameters passed to it.  These are known as actual parameters.  They must match the formal parameters in order, number, and data types.

``` python
subroutineName(actualParameter1, actualParameter2, ...)
```


## Procedures

A procedure is a type of sub-routine that ***does not*** return a value.  It must be defined before it can be used.

``` python
def square(number):
    """Display the square of number."""
    
    # Calculate result
    squared = number ** 2
    
    print(squared)
```

A procedure can be called from the main program, or from another sub-routine.

``` python
square(2)
```


## Functions

A function is another type of sub-routine that ***does*** return a value.  It must be defined before it can be used.

``` python
def toThePowerOf(number, power):
    """Return a number raised to a power."""
    
    # Calculate result
    value = number ** power
    
    return value
```

A function can be called from the main program, or from another sub-routine.  To use the value returned by the function it can be assigned to a variable or used as the a value in another operation.

__Returned value assigned__

``` python
answer = toThePowerOf(2, 5)

print(answer)
```

__Returned value used__

``` python
answer = 64 - toThePowerOf(2, 5)

print(answer)
```


### Return multiple values

Functions can return a tuple [term not part of Higher] that contains multiple values, similar to an array.  These values can be assigned to individual variables when returned.

``` python
def myData():
    """Return an integer and a string."""
    
    # Return a tuple
    return 21, "Tom"
```

``` python
# Display returned tuple
print(myData())
```

``` python
# Assign to a tuple
myTuple = myData()

# Display the tuple
print(myTuple)

# Display individual values
print(myTuple[0])
print(myTuple[1])
```

``` python
# Assign directly to variables
age, name = myData()

# Display values
print(age)
print(name)
```
