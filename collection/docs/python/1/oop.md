# Object-Oriented Programming

Object-Oriented Programming (OOP) is a programming paradigm that uses objects and classes to structure software in a way that is modular, reusable, and organized. Python supports OOP and provides various features to implement it effectively.
Key Concepts of OOP

- Class: A blueprint for creating objects (instances). It defines a set of attributes and methods that the created objects will have.
- Object: An instance of a class. It represents a specific entity with attributes and behavior defined by its class.
- Inheritance: A mechanism to create a new class using the properties and methods of an existing class. This promotes code reusability.
- Encapsulation: The bundling of data and methods that operate on the data within one unit, and restricting access to some of the object's components.
- Polymorphism: The ability to use a single interface to represent different data types or classes. It allows methods to do different things based on the object it is acting upon.

## Class

```py
class Dog:
    # Class attribute
    species = "Canis familiaris"

    # Initializer / Instance attributes
    def __init__(self, name, age):
        self.name = name
        self.age = age

    # Instance method
    def description(self):
        return f"{self.name} is {self.age} years old."

    # Another instance method
    def speak(self, sound):
        return f"{self.name} says {sound}"
```

## Object

```py
# Creating an instance of the Dog class
my_dog = Dog("Buddy", 3)

# Accessing class attributes and methods
print(my_dog.species)  # Output: Canis familiaris
print(my_dog.description())  # Output: Buddy is 3 years old.
print(my_dog.speak("Woof"))  # Output: Buddy says Woof
```

## Inheritance

Inheritance allows a class to inherit attributes and methods from another class. The class being inherited from is called the parent or base class, and the class that inherits is called the child or derived class.

```py
# Parent class
class Animal:
    def __init__(self, name):
        self.name = name

    def move(self):
        print(f"{self.name} is moving")


# Child class
class Dog(Animal):
    def __init__(self, name, breed):
        super().__init__(name)
        self.breed = breed

    def bark(self):
        print(f"{self.name} says Woof!")


# Creating an instance of the Dog class
dog = Dog("Buddy", "Golden Retriever")
dog.move()  # Output: Buddy is moving
dog.bark()  # Output: Buddy says Woof!
```

## Encapsulation

Encapsulation restricts direct access to some of an object’s attributes and methods. This is achieved using private and protected access modifiers.

```py
class Person:
    def __init__(self, name, age):
        self.name = name  # Public attribute
        self._age = age  # Protected attribute

    def display(self):
        print(f"Name: {self.name}, Age: {self._age}")

    def _update_age(self, new_age):  # Protected method
        if new_age > 0:
            self._age = new_age


# Creating an instance of the Person class
person = Person("Alice", 30)
person.display()  # Output: Name: Alice, Age: 30

# Accessing protected attribute and method
person._update_age(31)
person.display()  # Output: Name: Alice, Age: 31
```

## Polymorphism

Polymorphism allows methods to do different things based on the object it is acting upon. This is often achieved using method overriding in inheritance.

```py
class Animal:
    def make_sound(self):
        raise NotImplementedError("Subclass must implement this method")


class Dog(Animal):
    def make_sound(self):
        return "Woof!"


class Cat(Animal):
    def make_sound(self):
        return "Meow!"


# Using polymorphism
animals = [Dog(), Cat()]

for animal in animals:
    print(animal.make_sound())
```

```sh
Woof!
Meow!
```
