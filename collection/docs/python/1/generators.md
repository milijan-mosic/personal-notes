# Generators

Generators are a special type of iterator in Python that allow you to iterate over a sequence of values lazily, meaning they generate values on the fly and only when required. This is memory efficient and can improve performance, especially when working with large datasets.

There are two main ways to create generators in Python:

- Generator Functions
- Generator Expressions

## Generator Functions

```py
def count_up_to(max):
    count = 1
    while count <= max:
        yield count
        count += 1


# Using the generator function
counter = count_up_to(5)
for num in counter:
    print(num)
```

```sh
1
2
3
4
5
```

## Generator Expressions

Generator expressions provide a compact way to create generators. They are similar to list comprehensions but use parentheses instead of square brackets.

```py
# List comprehension
squares_list = [x * x for x in range(5)]
print(squares_list)


# Generator expression
squares_generator = (x * x for x in range(5))


for square in squares_generator:
    print(square)
```

```sh
[0, 1, 4, 9, 16]
0
1
4
9
16
```

## Combining Generators

```py
def generator1():
    for i in range(3):
        yield i


def generator2(gen):
    for value in gen:
        yield value * 2


# Combining generators
gen1 = generator1()
gen2 = generator2(gen1)


for value in gen2:
    print(value)
```

```sh
0
2
4
```
