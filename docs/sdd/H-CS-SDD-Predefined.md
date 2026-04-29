# Predefine Functions

## Character to ASCII

``` python
myCharacter = "A"

myASCII = ord(myCharacter)

print(myASCII)
```


## ASCII to character

``` python
myASCII = 97

myCharacter = chr(myASCII)

print(myCharacter)
```


## Floating-point numbers to integers

This removes the decimal part of the value.  It does not round.

*Note*: 13 &divide; 5 = 2.6

``` python
myFloat = 13 / 5

myInt = int(myFloat)

print(myInt)
```


## Modulus

The modulus is the remainder when doing division.

*Note*: 13 &divide; 5 = 2 remainder 3

``` python
myModulus = 13 % 5

print(myModulus)
```
