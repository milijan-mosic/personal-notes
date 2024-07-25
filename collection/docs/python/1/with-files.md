# `with` and files

The with statement in Python is used to wrap the execution of a block of code. It is most commonly used when dealing with file operations to ensure proper resource management. When you use the with statement for file operations, it automatically takes care of opening and closing the file, even if an error occurs during file operations. This makes your code cleaner and more robust.

```py
with open("example.txt", "r") as file:
    content = file.read()
    print(content)
# No need to explicitly close the file, it is automatically done when the block is exited
```

## Reading from a File

There are several methods to read from a file:

- file.read(size): Reads the entire file or up to `size` bytes.
- file.readline(): Reads one line from the file.
- file.readlines(): Reads all lines from the file and returns them as a list of strings.

## Summary

- with statement: Used to wrap file operations, ensuring that the file is properly opened and closed, even if an error occurs.
- File modes: "r" for read, "w" for write, "a" for append, "b" for binary mode, etc.
- Reading methods: read(), readline(), readlines().
- Writing method: write().
