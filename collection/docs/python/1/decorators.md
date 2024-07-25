# Decorators

Decorators are a powerful feature in Python that allows you to modify the behavior of a function or method without changing its actual code. Decorators are often used to add functionality to existing code in a clean and readable manner.

## Simple one

```py
def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called.")
        func()
        print("Something is happening after the function is called.")
    return wrapper


@my_decorator
def say_hello():
    print("Hello!")


say_hello()
```

```sh
Something is happening before the function is called.
Hello!
Something is happening after the function is called.
```

## Arguments

```py
def log_execution(func):
    def wrapper(*args, **kwargs):
        print(f"Executing {func.__name__} with arguments {args} and {kwargs}")
        result = func(*args, **kwargs)
        print(f"{func.__name__} executed")
        return result
    return wrapper


@log_execution
def add(a, b):
    return a + b


print(add(5, 3))
```

```sh
Executing add with arguments (5, 3) and {}
add executed
8
```

Decorators are a useful tool in Python for extending the behavior of functions. They can be used for logging, timing, access control, and many other purposes. By understanding and utilizing decorators, you can write more modular, readable, and maintainable code.
