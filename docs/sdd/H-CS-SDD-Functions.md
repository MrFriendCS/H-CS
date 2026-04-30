# Functions

A function is a type of sub-routine that ***does*** return a value.
It must be defined before it can be used.

When a function is defined it can have zero, one, or more parameters.
These are known as formal parameters.
The formal parameters will 'catch' values that are passed to the function when it is 'called'.

The returned value is normally assigned to a variable, or it can be used in another sub-routine.


## Example - General

``` python
def functionName(formalParameter1, formalParameter2, ...):
    """docstring"""
    
    <function code>
    
    return <result>
```

A function can be called from the main program, or from another sub-routine.

``` python
functionResult = functionName(actualParameter1, actualParameter2, ...)
```


## Example - No formal parameters

``` python
def pickRandom():
    """Picks a random number from 1 to 10."""
    
    # Get extra code
    import random
    
    # Intialise local variable
    randomNumber = 0
    
    # Pick random number
    randomNumber = random.randint(1, 10)
    
    # Return random number
    return(randomNumber)
```

This function can be called from the main program, or from another sub-routine.

``` python
myNumber = pickRandom()

print("Random number: " + str(myNumber))
```


## Example - One formal parameter

``` python
def square(number):
    """Calculates the square of a number."""
    
    # Intialise local variable
    squared = 0
    
    # Calculate result
    squared = number ** 2
    
    # Return the result
    return squared
```

This function can be called from the main program, or from another sub-routine.

``` python
result = square(2)

print("Result: " + str(result))
```


## Example - Multiple formal parameters

``` python
def powerOf(number, power):
    """Calculates a number raised to a power."""
    
    # Intialise local variable
    result = 0
    
    # Calculate result
    result = number ** power
    
    # Return the result
    return result
```

This function can be called from the main program, or from another sub-routine.

``` python
result = powerOf(5, 3)

print("Result: " + str(result))
```


## Return multiple values

Functions can return a tuple [term not part of Higher] that contains multiple values, similar to an array.  These values can be assigned to individual variables when returned.

``` python
def myData():
    """Return an integer and a string."""
    
    # Return a tuple
    return 21, "Tom"
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
print(name + " is " + str(age) + " years old.")
```
