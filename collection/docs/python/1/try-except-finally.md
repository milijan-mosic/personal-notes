# Try/Except/Finally

The try/except/finally construct in Python is used to handle exceptions (errors) that occur during the execution of a program. This construct allows you to manage errors gracefully without crashing the program and to execute cleanup code regardless of whether an error occurred.

## Basic Structure

- try block: Contains the code that might throw an exception.
- except block: Contains the code that runs if an exception occurs in the try block.
- finally block: Contains the code that always runs, regardless of whether an exception occurred or not.

Example:

```py
try:
    # Code that may raise an exception
    result = 10 / 0
except ZeroDivisionError as e:
    # Code that runs if a ZeroDivisionError occurs
    print(f"Error: {e}")
finally:
    # Code that runs no matter what
    print("This will always run")
```

```sh
Error: division by zero
This will always run
```

Using `else` with try/except

The else block can be used after the except block. It runs only if no exceptions were raised in the try block.

```py
try:
    result = 10 / 2
except ZeroDivisionError:
    print("You can't divide by zero!")
else:
    print(f"Result is {result}")
finally:
    print("This will always run")
```

```sh
Result is 5.0
This will always run
```
