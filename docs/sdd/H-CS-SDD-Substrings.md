# Substrings

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
