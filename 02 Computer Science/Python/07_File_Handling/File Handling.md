# Python File Handling

## 1. What is File Handling?

File handling in Python allows you to create, open, read, write, append, and manage files.

It is useful for storing data permanently so that it remains available even after a program finishes running.

### Common File Operations

- **Create:** Create a new file.
    
- **Read:** Retrieve data from a file.
    
- **Write:** Write data to a file, replacing existing content.
    
- **Append:** Add data to the end of a file.
    
- **Close:** Release the file resource after use.
    

---

## 2. Opening a File

Python uses the built-in `open()` function to open files.

### Syntax

```
open("filename", "mode")
```

### File Modes

| Mode   | Description                                                             |
| ------ | ----------------------------------------------------------------------- |
| `"r"`  | Read an existing file. Raises `FileNotFoundError` if it does not exist. |
| `"w"`  | Write to a file. Creates it if needed or overwrites existing content.   |
| `"a"`  | Append content to a file. Creates it if needed.                         |
| `"x"`  | Create a new file. Raises `FileExistsError` if it already exists.       |
| `"r+"` | Read and write without initially truncating the file.                   |
| `"b"`  | Binary mode modifier, such as `"rb"` or `"wb"`.                         |
| `"t"`  | Text mode modifier, which is the default.                               |

---

## 3. Reading a File

The `"r"` mode opens a file for reading.

Suppose `notes.txt` contains:

```
Hello, Python!
Learning file handling.
```

### Using `read()`

Reads the entire remaining content of the file.

```
file = open("notes.txt", "r", encoding="utf-8")

content = file.read()
print(content)

file.close()
```

**Output:**

```
Hello, Python!
Learning file handling.
```

### Using `readline()`

Reads one line at a time.

```
with open("notes.txt", "r", encoding="utf-8") as file:
    print(file.readline())
    print(file.readline())
```

**Output:**

```
Hello, Python!

Learning file handling.
```

The extra blank line appears because each returned line normally includes its newline character, and `print()` adds another newline.

### Using `readlines()`

Reads all lines and returns them as a list.

```
with open("notes.txt", "r", encoding="utf-8") as file:
    lines = file.readlines()

print(lines)
```

**Output:**

```
['Hello, Python!\n', 'Learning file handling.\n']
```

The exact list depends on the file's contents and line endings.

---

## 4. Writing to a File

Use `"w"` mode to write content.

```
with open("notes.txt", "w", encoding="utf-8") as file:
    file.write("Welcome to Python!\n")
    file.write("File handling is useful.")
```

This creates `notes.txt` if it does not exist. If it already exists, its previous contents are overwritten.

**Important:** Use `"w"` carefully because it replaces the existing content.

---

## 5. Appending to a File

Use `"a"` mode to add content to the end of a file without replacing its existing contents.

```
with open("notes.txt", "a", encoding="utf-8") as file:
    file.write("\nThis line was appended.")
```

Appending is useful for logs, records, and maintaining a history of entries.

---

## 6. Creating a New File

Use `"x"` mode when you want to create a file only if it does not already exist.

```
with open("new_file.txt", "x", encoding="utf-8") as file:
    file.write("This is a new file.")
```

If `new_file.txt` already exists, Python raises `FileExistsError` rather than overwriting it.

---

## 7. Using `with` to Open Files

The `with` statement is the recommended way to work with files.

```
with open("notes.txt", "r", encoding="utf-8") as file:
    content = file.read()
    print(content)
```

**Advantages:**

- Automatically closes the file when the block exits.
    
- Works even if an exception occurs inside the block.
    
- Makes file-handling code cleaner and safer.
    

You generally do not need to call `file.close()` when using `with`.

---

## 8. Reading a File Line by Line

For large files, iterating over the file is usually more memory-efficient than loading the entire file into memory.

```
with open("notes.txt", "r", encoding="utf-8") as file:
    for line in file:
        print(line, end="")
```

This processes one line at a time.

---

## 9. Checking Whether a File Exists

The `pathlib` module provides a convenient way to work with file paths.

```
from pathlib import Path

file_path = Path("notes.txt")

if file_path.exists() and file_path.is_file():
    print("File exists.")
else:
    print("File does not exist.")
```

**Output when the file exists:**

```
File exists.
```

`exists()` checks whether a path exists, while `is_file()` checks whether it refers to a regular file.

---

## 10. Handling File Exceptions

File operations may fail because a file is missing, access is denied, or another I/O error occurs.

```
try:
    with open("missing.txt", "r", encoding="utf-8") as file:
        print(file.read())

except FileNotFoundError:
    print("The file was not found.")

except PermissionError:
    print("Permission denied.")
```

**Output if the file is missing:**

```
The file was not found.
```

Handle specific exceptions when you can respond to them appropriately.

---

## 11. Working with File Paths

Use `pathlib.Path` to create and manage paths across operating systems.

```
from pathlib import Path

folder = Path("data")
folder.mkdir(exist_ok=True)

file_path = folder / "example.txt"

file_path.write_text("Hello from pathlib!", encoding="utf-8")

content = file_path.read_text(encoding="utf-8")
print(content)
```

**Output:**

```
Hello from pathlib!
```

The example creates a `data` directory if necessary and writes a file inside it.

---

## 12. File Pointer Methods

Python maintains a file position when reading or writing.

### `tell()`

Returns the current file position.

### `seek()`

Moves the file position to a specified location.

```
with open("notes.txt", "r", encoding="utf-8") as file:
    print(file.tell())

    file.read(5)
    print(file.tell())

    file.seek(0)
    print(file.read(5))
```

For ordinary text files, `tell()` returns an opaque position value that can be used with `seek()` to return to a previously recorded position. Do not assume every position corresponds directly to a character index.

---

## 13. Text Files vs. Binary Files

|Text mode|Binary mode|
|---|---|
|Uses `"r"`, `"w"`, or `"a"`.|Uses `"rb"`, `"wb"`, or `"ab"`.|
|Reads and writes strings.|Reads and writes bytes.|
|Can decode and encode text.|Does not perform text decoding or encoding.|
|Suitable for `.txt`, `.csv`, and source files.|Suitable for images, PDFs, audio, and other binary data.|

### Binary Example

```
with open("image.png", "rb") as file:
    data = file.read()

print(type(data))
```

**Output:**

```
<class 'bytes'>
```

This example reads the image as bytes; it does not display the image.

---

## 14. Key Points

- Use `open()` to access files.
    
- Use `"r"` to read, `"w"` to overwrite, and `"a"` to append.
    
- Use `"x"` to create a file without overwriting an existing one.
    
- Prefer `with open(...)` for automatic resource management.
    
- Specify `encoding="utf-8"` for text files when appropriate.
    
- Use `pathlib` for readable, cross-platform path handling.
    
- Handle expected file exceptions.
    
- Use binary mode for non-text data.
    
- Be careful with `"w"` mode because it truncates existing files.