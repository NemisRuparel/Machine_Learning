# Python `pytest`

## 1. What is pytest?

`pytest` is a Python testing framework used to write and execute tests for Python programs.

It helps verify that functions and applications behave as expected.

**Key features:**

- Simple test syntax.
    
- Automatic test discovery.
    
- Detailed failure reports.
    
- Support for fixtures and parameterized tests.
    
- Useful for unit testing and integration testing.
    

---

## 2. Installing pytest

Install pytest using pip:

```
python -m pip install pytest
```

Verify the installation:

```
python -m pytest --version
```

---

## 3. Writing Your First Test

Create two files in the same directory.

**File:** `**calculator.py**`

```
def add(a, b):
    return a + b


def subtract(a, b):
    return a - b


def multiply(a, b):
    return a * b
```

**File:** `**test_calculator.py**`

```
from calculator import add, subtract, multiply


def test_add():
    assert add(2, 3) == 5


def test_subtract():
    assert subtract(10, 4) == 6


def test_multiply():
    assert multiply(3, 4) == 12
```

Run the tests:

```
python -m pytest
```

**Expected result:** Three tests pass.

`pytest` automatically discovers files named `test_*.py` or `*_test.py` and functions whose names start with `test_`.

---

## 4. Understanding `assert` in pytest

pytest uses Python's `assert` statement to check whether the actual result matches the expected result.

```
def test_square():
    result = 5 ** 2

    assert result == 25
```

If the condition is true, the test passes. If it is false, the test fails and pytest displays information about the mismatch.

Unlike ordinary program assertions that may be disabled with Python optimization, pytest rewrites test assertions to provide useful failure details.

---

## 5. Testing Different Conditions

```
def test_comparisons():
    assert 10 > 5
    assert 5 == 5
    assert 3 != 4
    assert "python".upper() == "PYTHON"
    assert 2 in [1, 2, 3]
```

Each assertion checks a different condition. If any assertion fails, the test fails.

---

## 6. Testing Exceptions

Use `pytest.raises()` to verify that code raises the expected exception.

**File:** `**test_exceptions.py**`

```
import pytest


def divide(a, b):
    if b == 0:
        raise ValueError("Cannot divide by zero.")

    return a / b


def test_divide_by_zero():
    with pytest.raises(ValueError, match="Cannot divide by zero"):
        divide(10, 0)
```

Run:

```
python -m pytest test_exceptions.py
```

The test passes when `divide(10, 0)` raises the expected `ValueError` with a matching message.

---

## 7. Using Fixtures

A fixture provides reusable setup data or resources to tests.

```
import pytest


@pytest.fixture
def numbers():
    return [10, 20, 30]


def test_sum(numbers):
    assert sum(numbers) == 60


def test_length(numbers):
    assert len(numbers) == 3
```

The `numbers` fixture supplies the list to both tests. pytest runs the fixture when a test requests it.

---

## 8. Parameterized Tests

`@pytest.mark.parametrize` lets you run the same test with multiple sets of inputs.

```
import pytest


@pytest.mark.parametrize(
    "a, b, expected",
    [
        (2, 3, 5),
        (10, 5, 15),
        (-1, 1, 0),
        (0, 0, 0),
    ],
)
def test_add(a, b, expected):
    assert a + b == expected
```

pytest runs the test once for each set of parameters, producing four test cases.

---

## 9. Running pytest Commands

|Command|Purpose|
|---|---|
|`python -m pytest`|Run discovered tests.|
|`python -m pytest -v`|Display individual test names and results.|
|`python -m pytest test_calculator.py`|Run tests from one file.|
|`python -m pytest -k add`|Run tests whose names match `add`.|
|`python -m pytest -x`|Stop after the first failure.|
|`python -m pytest --collect-only`|List tests without executing them.|
|`python -m pytest -q`|Show a more concise result.|

---

## 10. Understanding Test Results

- **PASSED:** The test completed successfully.
    
- **FAILED:** The test ran, but an assertion or other check failed.
    
- **ERROR:** A test or fixture could not execute properly.
    
- **SKIPPED:** The test was intentionally skipped.
    
- **XFAIL:** The test failed as expected because it was marked as an expected failure.
    

Example:

```
========================= test session starts =========================
collected 3 items

test_calculator.py ...                                           [100%]

========================== 3 passed ================================
```

Exact output formatting can vary by pytest version and configuration.

---

## 11. Recommended Project Structure

```
python-project/
├── calculator.py
├── test_calculator.py
├── test_exceptions.py
└── requirements.txt
```

You can list pytest as a project dependency in `requirements.txt`:

```
pytest
```

Install the dependencies using:

```
python -m pip install -r requirements.txt
```

---

## 12. Key Points

- pytest is a testing framework for Python.
    
- Test files and test functions normally use names beginning with `test_`.
    
- Use `assert` to verify expected results.
    
- Use `pytest.raises()` to test exceptions.
    
- Use fixtures to share setup data.
    
- Use parameterization to test multiple input combinations.
    
- Run tests with `python -m pytest`.
    
- Automated tests help catch bugs when code changes.