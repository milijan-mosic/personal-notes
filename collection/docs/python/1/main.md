# if `__name__` == `__main__`:

In Python, the `__main__` module is a special built-in module that serves as the entry point for program execution. When a Python file is run directly, Python sets the `__name__` variable to `__main__` within that module. This feature is commonly used to differentiate between code that should be executed when a module is run as a script versus when it is imported as a module in another script.

```py
def greet():
    print("Hello, World!")


if __name__ == "__main__":
    greet()
```

## When this script is executed directly:

```sh
$ python script.py
Hello, World!
```

## When this script is imported as a module:

```py
import script

# Nothing happens automatically
# You would need to call script.greet() to execute the greet function
```
