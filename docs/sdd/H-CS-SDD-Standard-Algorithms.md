# Standard Algorithms

**Note:** The standard algorithms are shown working with a single array but they could equally work with parallel arrays or an array of records.

## Linear search - array

Finds the first occurrence and then ___stops___ searching.

``` python
names = ["Alan", "Beth", "Carl", "Dina"]
found = False
index = 0

# Repeat for each value, or until target value found
while not found and index < len(names):

    # Compare current value with target value
    if names[index] == "Carl":
        # Set flag to true
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


## Find minimum (or maximum) - array

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


## Count occurrences - array

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
