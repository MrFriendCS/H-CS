# Software Design and Development

## Notes

All the code examples use Python.

These notes are focused on Higher Computing Science so some terms are used differently.  Any reference to an `array` will actually use a `list`.  Any reference to a `procedure` will be a `function` that does not explicitly return a value. 


## Sub-routines

When a sub-routine is defined it can have zero, one, or more parameters.  These are known as formal parameters.  The formal parameters will 'catch' values that are passed to the sub-routine.

``` python
def subroutineName(formalParameter1, formalParameter2, ...):
	"""docstring"""
    <sub-routine code>
```

When a sub-routine is called it can have parameters passed to it.  These are known as actual parameters.

``` python
subroutineName(actualParameter1, actualParameter2, ...)
```


### Procedures

A procedure is a type of sub-routine that ***does not*** return a value.  It must be defined before it can be used.

``` python
def square(number):
    """Display the square of number."""
    
    squared = number ** 2
    
    print(squared)
```

A procedure can be called from the main program, or from another sub-routine.

``` python
square(2)
```


### Functions

A function is another type of sub-routine that ***does*** return a value.  It must be defined before it can be used.

``` python
def toThePowerOf(number, power):
    """Return a number raised to a power."""

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


#### Return multiple values

Functions can return a tuple [term not part of Higher] that contains multiple values, similar to an array.  These values can be assigned to individual variables when returned.

``` python
def myData():
    """Return an integer and a string."""
    
    # Returns a tuple
    return 21, "Tom"
```

``` python
# Display returned tuple
print(myData())
```

``` python
# Assign to a tuple
myTuple = myData()

# Access values
print(myTuple[0])
print(myTuple[1])
```

``` python
# Assign to variables
age, name = myData()

print(age)
print(name)
```


## Predefine functions

### Character to ASCII

``` python
myCharacter = "A"

myASCII = ord(myCharacter)

print(myASCII)
```


### ASCII to character

``` python
myASCII = 97

myCharacter = chr(myASCII)

print(myCharacter)
```


### Floating-point numbers to integers

This removes the decimal part of the value.  It does not round.

``` python
myFloat = 13 / 5

myInt = int(myFloat)

print(myInt)
```


### Modulus

The modulus is the remainder when doing division.

13 &divide; 5 = 2 remainder 3

``` python
myModulus = 13 % 5

print(myModulus)
```


## Substrings

Python does not have pre-defined functions for creating substrings.  Strings can be treated as an array of characters.  Python starts counting from zero.

### Index values

#### Positive index

Positive index values, with `0` being the first element.
```
Index: 0  1  2  3  4  5  6  7  8  9  10
Value: H  e  l  l  o     W  o  r  l  d
```

#### Negative index

Negative index values, with `-1` being the last element.

```
Index: -11  -10  -9  -8  -7  -6  -5  -4  -3  -2  -1
Value:   H    e   l   l   o       W   o   r   l   d
```


### Individual character

``` python
# Positive index
print("Hello World"[6])
```

``` python
# Negative index
print("Hello World"[-5])
```

``` python
myString = "Hello World"
myCharacter = myString[1]
print(myCharacter)
```


### Multiple characters

To extract more than a single character a second parameter is used.

```
string[start : stop]
```

**Notes:**
* The `stop` value is always one more than the last character to be included.
* The number of characters selected can be calculated using `stop`-`start`

``` python
print("Hello World"[0:4])
```

``` python
myString = "Hello World"
mySubstring = myString[6:11]
print(mySubstring)
```


### Left substring

If the first character is included in a substring then the `start` parameter can be omitted.

``` python
myString = "Hello World"
mySubstring = myString[ :4]
print(mySubstring)
```


### Right substring

If the last character is included in a substring then the `stop` parameter can be omitted.

``` python
myString = "Hello World"
mySubstring = myString[6: ]
print(mySubstring)
```

Using negative index values can be easier.

``` python
myString = "Hello World"
mySubstring = myString[-5: ]
print(mySubstring)
```


### Mid substring

``` python
myString = "Hello World"
mySubstring = myString[3:8]
print(mySubstring)
```


## Parallel 1D arrays

Parallel arrays have the same number of elements in each array.

``` python
names = [""] * 4
ages = [0] * 4
heights = [0.0] * 4
```


## Records

The code to produce a record needs to be imported before it can be used.

A record is defined with attributes, which can have default values.

``` python
from dataclasses import dataclass

@dataclass
class person:
    name: str = ""
    age: int = 0
    height: float = 0.0
```

Individual records can be created, either with default values, or with specified values.

``` python
person1 = person()

person2 = person("Beth", 23, 1.63)
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


### Array of records

Using default values.

``` python
# Create an array of records
people = [person() for index in range(4)]
```

```
# Update second record
people[1] = person("Beth",  23,  1.63)

# Update name in third record
people[2].name = "Carl"
```

``` python
# Display array of records
print(people)

# Display second record
print(people[1])

# Display name in second record
print(people[1].name)

# Display first 2 character of name in second record
print(people[1].name[ :2])
```


## File handling

Reading and writing a csv or txt file can be achieved using the same code, just change the file extension.

**Note:** Anything read from a file is a string.  If the value represents another data type then it must be cast to that data type.

### Example Data

The data used in the examples can be represented in a table:

| Name | Age | Height |
| ---- | --- | ------ |
| Alan | 24  | 1.78 |
| Beth | 23  | 1.63 |
| Carl | 22  | 1.89 |
| Dina | 21  | 1.59 |

It can also be represented as a text file, e.g. `people.csv` or `people.txt`.

```
Alan,24,1.78
Beth,23,1.63
Carl,22,1.89
Dina,21,1.59
```


### Reading parallel arrays from a file

**Note:** An assumption is that the maximum array size is known, and the file contains that number of rows or fewer.

Declare parallel arrays that are large enough to hold the data.

``` python
names = [""] * 4
ages = [0] * 4
heights = [0.0] * 4
```

Declare other variables

``` python
tempData = [""] * 3
line = ""
index = 0
```

Open the file that holds the data, in read only mode.

``` python
file = open("people.csv" ,"r" )
```

Read the first line of the file.

``` python
line = file.readline()
```

Start / continue the conditional loop if the variable `line` is not empty.

``` python
while line != "":
```

Split the content of the variable `line` at the commas.  Assign the elements to `tempArray`.

``` python
    tempData = line.split(",")
```

Remove leading and trailing spaces from `tempData`, cast appropriately, and assign to parallel arrays.

``` python
    names[index] = tempData[0].strip()
    ages[index] = int(tempData[1].strip())
    heights[index] = float(tempData[2].strip())
```

Read the next line of the file.

``` python
    line = file.readline()
```

Increase the index of where the next element will be stored, and back to `while` statement.

``` python
    index = index + 1
```

Close the file.

``` python
file.close()
```


### Reading an array of records from a file

**Note:** An assumption is that the maximum array size is known, and the file contains that number of rows or fewer.

Declare an array of records large enough to hold the data.

``` python
people = [person()] * 4
```

Declare all other variables.

``` python
tempData = [""] * 3
name = ""
age = 0
height = 0.0
line = ""
index = 0
```

Open the file that holds the data, in read only mode.

``` python
file = open("people.csv" ,"r" )
```

Read the first line of the file.

``` python
line = file.readline()
```

Start / continue the conditional loop if the variable `line` is not empty.

``` python
while line != "":
```

Split the content of the variable `line` at the commas and assign the elements to `tempArray`.

``` python
    tempData = line.split(",")
```

Retrieve the individual attributes from `tempData`, remove leading and trailing spaces, and cast appropriately.

``` python
    name = tempData[0].strip()
    age = int(tempData[1].strip())
    height = float(tempData[2].strip())
```

Assign a new record to appropriate element in the array.

``` python
    people[index] = person(name, age, height)
```

Read the next line of the file.

``` python
    line = file.readline()
```

Increase the index of where the next record will be stored.

``` python
    index = index + 1
```

Close the file.

``` python
file.close()
```

### Count number of lines in a file

If the size of the required array(s) is unknown then it is possible to to find out how many lines are in the file.

``` python
count = 0

file = open("people.csv", "r")
line = file.readline()

while line != "":
    count = count + 1
    line = file.readline()

file.close()

# Display result
print("Rows: " + str(count)")
```


### Writing parallel arrays to a file

**Notes:**
* Only strings can be written to a file, anything else must be cast to a string.
* The example will create a `csv` file.

Open the file that will hold the data, in write mode.  If the file exists it will be overwritten, otherwise it will be created.

``` python
file = open("newPeople.csv", "w")
```

Loop for each element in the arrays to be written to the file.

``` python
for index in range(len(names)):
```

Write the elements to the file, separated with commas, and finish with a newline `\n`.

``` python
    file.write(names[index] + ",")
    file.write(str(ages[index]) + ",")
    file.write(str(heights[index]) + "\n")
```

Close the file.

``` python
file.close()
```


### Count number of lines in a file

If the size of the required array(s) is unknown then it is possible to to find out how many lines are in the file.

``` python
count = 0

file = open("people.csv", "r")
line = file.readline()

while line != "":
    count = count + 1
    line = file.readline()

file.close()

# Display result
print("Rows: " + str(count)")
```


## Standard algorithms

### Linear search - array

Finds the first occurrence and then ___stops___ searching.

``` python
names = ["Alan", "Beth", "Carl", "Dina"]
found = False
index = 0

# Repeat for each value, or until target value found
while not found and index < len(names):

    # Compare current value with target value
    if names[index] == "Carl":
        found = True
    else:
        # Increment index
        index = index + 1

# Display result
if found:
    print("Found at index " + str(index))
else:
    print("Not found")
```


### Find minimum (or maximum) - array

Assign the value in the ___first___ element as the minimum, or maximum.  Loop from the ___second___ element to the end of the array.

``` python
heights = [1.78, 1.63, 1.89, 1.59]

# Assign first element as minimum
minimum = heights[0]

# Repeat for remaining values
for index in range(1, len(heights)):

    # Compare current value with minimim
    if heights[index] < minimum:
    
        # Update minimum value
        minimum = heights[index]

# Display result
print("Minimum: " + str(minimum))
```


### Count occurrences - array

Counts all occurrences.

``` python
names = ["Alan", "Beth", "Carl", "Dina"]
count = 0

# Repeat for each value
for index in range(len(names)):

    # Compare current value with target value
    if names[index] == "Carl":
        
        # Increment count
        count = count + 1

# Display result
print("Found " + str(count) + " occurence(s)")
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbOTQ3NTY3ODc1LDE5NDQ5ODI2MzgsMTg0Nz
g1MDg1MywtOTYwOTIwNzYzLC04MzIwODY1MzksLTM0NDgwOTI1
MCw4MjQ5MjExMDgsMjAwODQyOTcwMCwxOTA0NTgxOTU3LDE2MT
A5NjgwODcsLTg1MDYyOTM3OCw0ODgyNTM1MjYsLTEyOTY5NzAw
MzksMjAzNTg0OTg3NiwtMTU3OTM2Nzg5NiwxNDMwMzMzNjExLD
E5MzE5MDQzNCwxNjg0OTgzMjc0XX0=
-->