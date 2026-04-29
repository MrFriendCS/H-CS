# File handling

Reading and writing a csv or txt file can be achieved using the same code, just change the file extension.

**Note:** Anything read from a file is a string.  If the value represents another data type then it must be cast to that data type.

## Example data

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


## Reading from a file

If the number of lines to be read from a file is known then a fixed loop can be used, otherwise a conditional loop can be used.  Alternatively, the unknown number of lines can be counted, and then a fixed loop used.

File are opened in read mode (`r`).

### Fixed loop

``` python
# Make a connection to the file
file = open("people.csv" ,"r")

# Loop for each line in the file
for index in range(4):

    # Read a line
    line = file.readline()

    """Additional code goes here."""

# Close the connection to the file
file.close()
```

### Conditional loop

``` python
# Make a connection to the file
file = open("people.csv" ,"r")

# Read first line from the file
line = file.readline()

# Loop if variable not empty
while line != "":

    """Additional code goes here."""

    # Read next line
    line = file.readline()

# Close the connection to the file
file.close()
```

### Counting lines in a file

``` python
# Initialise variable
count = 0

# Make a connection to the file
file = open("people.csv" ,"r")

# Read first line from the file
line = file.readline()

# Loop if variable not empty
while line != "":

    # Read next line
    line = file.readline()

    # Incrememnt count
    count = count + 1

# Close the connection to the file
file.close()
```


## Reading parallel arrays from a file

**Note:** An assumption is that the maximum array size is known, and the file contains that number of rows or fewer.

Declare parallel arrays that are large enough to hold the data.

``` python
# Initialise data structures
names = [""] * 4
ages = [0] * 4
heights = [0.0] * 4

# Initialise variables
data = [""] * 3
line = ""

# Make a connection to the file
file = open("people.csv" ,"r")

# Loop for each line in the file
for index in range(4):

    # Read a line from the file
    line = file.readline()
    
    # Split the line at the commas
    data = line.split(",")

    # 1. Remove non-printing characters
    # 2. Cast as appropriate
    # 3. Assign to data structures
    names[index] = data[0].strip()
    ages[index] = int(data[1].strip())
    heights[index] = float(data[2].strip())

# Close the connection to the file
file.close()
```


## Reading an array of records from a file

**Note:** An assumption is that the maximum array size is known, and the file contains that number of rows or fewer.

Declare an array of records large enough to hold the data.

``` python
# Initialise data structure
people = [Person() for index in range(4)]

# Initialise variables
data = [""] * 3
line = ""

# Make a connection to the file
file = open("people.csv" ,"r" )

# Loop for each line in the file
for index in range(4):

    # Read a line from the file
    line = file.readline()
    
    # Split the line at the commas
    data = line.split(",")

    # 1. Remove non-printing characters
    # 2. Cast as appropriate
    # 3. Assign to data structure
    people[index].name = data[0].strip()
    people[index].age = int(data[1].strip())
    people[index].height = float(data[2].strip())

# Close the connection to the file
file.close()
```


## Writing parallel arrays to a file

**Notes:**

* Only strings can be written to a file, anything else must be cast to a string.
* The example will create a `csv` file.

File are opened in write mode (`w`).  If the file exists it will be overwritten, otherwise it will be created.

``` python
# Make a connection to the file
file = open("newPeople.csv", "w")

# Loop for each value
for index in range(len(names)):

    # Cast as appropriate
    file.write(names[index] + ",")
    file.write(str(ages[index]) + ",")
    file.write(str(heights[index]) + "\n")

# Close the connection to the file
file.close()
```
`\n` = new line
