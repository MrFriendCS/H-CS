# Writing parallel arrays to a file

**Notes:**

* Only strings can be written to a file, anything else must be cast to a string.
* The example will create a `csv` file.

File are opened in write mode (`w`).
If the file exists it will be overwritten, otherwise it will be created.

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
