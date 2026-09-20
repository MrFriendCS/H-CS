# main()

A sub-program called `main()` is used as a specific entry point to the program, and to allow procedures and functions to be tested individually.
All the code that calls the sub-programs goes inside `main()


## main() 

``` python
def main() -> None:
    """Code that calls other functions goes here."""
    
    print("Hello world!")    
```


# Calling main()

The following code is added at the end of the program.
It only calls `main()` if the code is run directly.
It does not call `main()` if the code is imported by another program.

``` python
# Run program
if __name__ == "__main__":

    main()   
```
