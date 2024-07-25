# Package and Module

In Python, the terms "module" and "package" refer to different levels of organization for Python code, allowing for a clear and maintainable structure, especially in larger projects.

## Module

A module is a single Python file containing Python code. It can define functions, classes, and variables. Additionally, a module can include runnable code. Modules help in organizing code into manageable sections and facilitate code reuse.

```py
# my_module.py
def greet(name):
    return f"Hello, {name}!"


class Animal:
    def __init__(self, name):
        self.name = name

    def speak(self):
        raise NotImplementedError("Subclass must implement abstract method")
```

```py
# main.py

import my_module

print(my_module.greet("Alice"))  # Output: Hello, Alice!

dog = my_module.Animal("Buddy")
# dog.speak()  # This will raise NotImplementedError
```

```py
from my_module import greet, Animal

print(greet("Bob"))  # Output: Hello, Bob!
```

## Package

A package is a collection of related modules grouped together within a directory. It helps organize related modules under a common namespace. To be recognized as a package, a directory must contain a special file named `__init__.py`.

Contents of my_package/module1.py:

```py
# my_package/module1.py

def foo():
    return "foo from module1"
```

Contents of my_package/module2.py:

```py
# my_package/module2.py

def bar():
    return "bar from module2"
```

Directory structure for a package named my_package:

```py
my_package/
    __init__.py
    module1.py
    module2.py
```

Contents of my_package/`__init__`.py:

```py
# my_package/__init__.py

from .module1 import foo
from .module2 import bar

__all__ = ["foo", "bar"]
```

The `__init__`.py file can be empty, but it can also execute initialization code for the package or set the `__all__` variable to control what is imported when `from package import *` is used.

You can import and use the package and its modules:

```py
# main.py

from my_package import foo, bar


print(foo())  # Output: foo from module1
print(bar())  # Output: bar from module2
```

## Summary

- Module: A single Python file containing code, which can define functions, classes, and variables.
- Package: A collection of related modules grouped in a directory with an `__init__.py` file.

Using packages and modules effectively organizes code, making it more modular, maintainable, and scalable.
