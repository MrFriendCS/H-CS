# Type Hinting

Type hinting is used to show what data type or data structure is passed to a subprogram or returned from a function.


## Single Data Type / Data Structure

| SQA       | Python Data Type |
| ---       | ---------------- |
| Character | str |
| String    | str |
| Integer   | int |
| Real      | float |
| Boolean   | bool |
| Array     | list |


``` python
def myFunction() -> str:
    """Example of returning a single value."""
    
    "Hello"
```


``` python
def myFunction() -> list[int]:
    """Example of returning an array of integers."""
    
    return [1, 2, 4, 9, 16, 25]
```


## Multiple Data Types / Data Structures

When multiple values are returned, they are returned as a __tuple__.

A tuple can be thought of as similar to an array.
Tuples are not part of Higher CS, but are used when working with Python.


``` python
def myFunction() -> tuple[int, str]:
    """Example of returning multiple values."""
    
    return 7, "Hello"
```


``` python
def myFunction() -> tuple[list[int], list[str]]:
    """Example of returning multiple arrays."""
    
    return [65, 66, 67], ["A", "B", "C"]
```
