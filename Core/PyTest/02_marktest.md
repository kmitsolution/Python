# marks in pytest
In pytest, marks are used to apply specific attributes or labels to test functions, allowing you to categorize and select tests based on certain criteria. Marks help in organizing and running tests selectively, based on the needs of your test suite. To use marks in pytest, you can apply them using the @pytest.mark decorator. Here are some commonly used pytest marks:

### Skip Test Mark:
The @pytest.mark.skip mark is used to skip the execution of a test function.
```python
import pytest

@pytest.mark.skip(reason="Skipping this test function")
def test_function_to_skip():
    assert False  # This assertion will not be checked as the test is skipped
```
### Skipif Test Mark:
The @pytest.mark.skipif mark is used to conditionally skip a test based on a specific condition.
```python
import pytest

@pytest.mark.skipif(sys.version_info < (3, 7), reason="Requires Python 3.7 or higher")
def test_python_version():
    # Test code for functionality requiring Python 3.7 or higher
    assert True
```
### Parametrize Test Mark:
The @pytest.mark.parametrize mark allows you to run a test function with different sets of input data.
```python
import pytest

def add(a, b):
    return a + b

@pytest.mark.parametrize("a, b, expected", [(1, 2, 3), (10, 20, 30), (-5, 5, 0)])
def test_addition(a, b, expected):
    assert add(a, b) == expected
```
### Custom Mark:
You can define your custom marks to group tests based on your specific criteria.
```python
import pytest

@pytest.mark.smoke
def test_smoke_test_1():
    # Test code for a smoke test 1
    assert True

@pytest.mark.smoke
def test_smoke_test_2():
    # Test code for a smoke test 2
    assert True
```

To run tests with specific marks, you can use the -m option with pytest:

```bash
pytest -m <mark_name>
```

For example, to run tests marked with smoke, you can use:

```bash
pytest -m smoke
```

Marks provide a flexible way to organize and filter tests in your test suite, making it easy to run specific groups of tests or skip certain tests based on conditions. This helps in managing large test suites and ensures that only relevant tests are executed during the testing process.
