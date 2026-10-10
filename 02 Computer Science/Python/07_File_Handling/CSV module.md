# Python CSV Module

## 1. What is the CSV Module?

The `csv` module is a built-in Python module used to read and write CSV (Comma-Separated Values) files.

CSV files store tabular data in rows and columns. They are commonly used for datasets, spreadsheets, reports, and data analysis.

**Example of a CSV file (**`students.csv`**):**

```
name,age,marks
Amit,20,85
Neha,21,92
Raj,19,78
```

The first row contains column headings, while the remaining rows contain student records.

---

## 2. Importing the CSV Module

The `csv` module is included with Python, so you do not need to install it separately.

```
import csv
```

---

## 3. Reading a CSV File

Use `csv.reader()` to read a CSV file row by row.

```
import csv

with open("students.csv", "r", newline="", encoding="utf-8") as file:
    reader = csv.reader(file)

    for row in reader:
        print(row)
```

**Output:**

```
['name', 'age', 'marks']
['Amit', '20', '85']
['Neha', '21', '92']
['Raj', '19', '78']
```

Each row is returned as a list of strings.

---

## 4. Reading CSV Files with `DictReader`

`csv.DictReader()` reads each row as a dictionary, using the column headings as keys.

```
import csv

with open("students.csv", "r", newline="", encoding="utf-8") as file:
    reader = csv.DictReader(file)

    for student in reader:
        print(student["name"], student["marks"])
```

**Output:**

```
Amit 85
Neha 92
Raj 78
```

This approach is convenient when you want to access data using column names.

**Note:** Values read from a CSV file are normally strings. Convert them to `int` or `float` when numerical operations are required.

---

## 5. Writing to a CSV File

Use `csv.writer()` to write rows to a CSV file.

```
import csv

with open("employees.csv", "w", newline="", encoding="utf-8") as file:
    writer = csv.writer(file)

    writer.writerow(["name", "department", "salary"])
    writer.writerow(["Amit", "IT", 35000])
    writer.writerow(["Neha", "HR", 32000])
```

This creates `employees.csv` with a header and two employee records.

**Important:** Opening a file in `"w"` mode overwrites its existing contents.

The `newline=""` argument is recommended when opening CSV files so the `csv` module can handle line endings correctly.

---

## 6. Writing Multiple Rows with `writerows()`

Use `writerows()` to write multiple records in one operation.

```
import csv

students = [
    ["name", "marks"],
    ["Amit", 85],
    ["Neha", 92],
    ["Raj", 78]
]

with open("students_output.csv", "w", newline="", encoding="utf-8") as file:
    writer = csv.writer(file)
    writer.writerows(students)
```

The list of rows is written to `students_output.csv`.

---

## 7. Writing Dictionaries with `DictWriter`

`csv.DictWriter()` writes dictionary data using specified column names.

```
import csv

students = [
    {"name": "Amit", "age": 20, "marks": 85},
    {"name": "Neha", "age": 21, "marks": 92},
    {"name": "Raj", "age": 19, "marks": 78}
]

fieldnames = ["name", "age", "marks"]

with open("students_dict.csv", "w", newline="", encoding="utf-8") as file:
    writer = csv.DictWriter(file, fieldnames=fieldnames)

    writer.writeheader()
    writer.writerows(students)
```

- `fieldnames` specifies the column names and their order.
    
- `writeheader()` writes the column headings.
    
- `writerows()` writes the dictionary records.
    

---

## 8. Appending Data to a CSV File

Use `"a"` mode to add new rows without replacing existing data.

```
import csv

with open("students.csv", "a", newline="", encoding="utf-8") as file:
    writer = csv.writer(file)
    writer.writerow(["Priya", 22, 88])
```

This adds a new record to the end of the file.

**Note:** Appending a header is generally unnecessary when the file already contains one. Also, `"a"` mode creates the file if it does not exist.

---

## 9. Handling CSV Data with Numeric Values

CSV readers return values as strings. Convert values before performing calculations.

```
import csv

with open("students.csv", "r", newline="", encoding="utf-8") as file:
    reader = csv.DictReader(file)

    for student in reader:
        name = student["name"]
        age = int(student["age"])
        marks = float(student["marks"])

        print(name, "Age:", age, "Marks:", marks)
```

This example assumes each record contains valid numeric values in the `age` and `marks` columns.

---

## 10. Handling Different Delimiters

CSV files do not always use commas. Some files use semicolons or tabs.

For a semicolon-separated file:

```
import csv

with open("data.csv", "r", newline="", encoding="utf-8") as file:
    reader = csv.reader(file, delimiter=";")

    for row in reader:
        print(row)
```

Set `delimiter` to match the separator used by the file.

For tab-separated data, use `delimiter="\t"`.

---

## 11. Handling CSV Exceptions

A file may be missing or inaccessible.

```
import csv

try:
    with open("missing.csv", "r", newline="", encoding="utf-8") as file:
        reader = csv.reader(file)

        for row in reader:
            print(row)

except FileNotFoundError:
    print("CSV file not found.")

except PermissionError:
    print("Permission denied.")
```

The exception handlers provide a more useful response when a file cannot be opened.

---

## 12. Important CSV Functions and Classes

|Function or class|Purpose|
|---|---|
|`csv.reader()`|Reads CSV rows as lists.|
|`csv.writer()`|Writes rows from sequences.|
|`csv.DictReader()`|Reads rows as dictionaries.|
|`csv.DictWriter()`|Writes dictionary records.|
|`writer.writerow()`|Writes one row.|
|`writer.writerows()`|Writes multiple rows.|
|`writer.writeheader()`|Writes column headings with `DictWriter`.|

---

## 13. CSV Module vs. Pandas

|`csv` module|Pandas|
|---|---|
|Built into Python.|Requires installing the `pandas` package.|
|Works directly with rows and dictionaries.|Provides DataFrames for tabular data.|
|Good for simple file operations.|Useful for data analysis and manipulation.|
|Provides explicit control over reading and writing.|Offers convenient filtering, aggregation, and cleaning operations.|

Use the `csv` module for straightforward CSV tasks. Consider Pandas when you need more advanced data analysis.

---

## 14. Key Points

- The `csv` module is built into Python.
    
- Use `csv.reader()` and `csv.writer()` for rows and lists.
    
- Use `csv.DictReader()` and `csv.DictWriter()` for dictionary-based operations.
    
- Use `newline=""` when opening CSV files for reading or writing.
    
- Use `encoding="utf-8"` for common text files.
    
- CSV values are normally read as strings.
    
- Use `"w"` to overwrite and `"a"` to append.
    
- Specify the correct delimiter when the file does not use commas.