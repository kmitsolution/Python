# pytest 
pytest is a popular testing framework in Python, to write and run test cases for your Python code.

### Install pytest:
Before you start using pytest, you need to install it. You can install pytest using pip by running the following command in your terminal or command prompt:

```python
pip install pytest
``

Writing Test Functions:
In pytest, you write test functions that check if specific parts of your code behave as expected. Test functions must be prefixed with "test_".

```python
# test_example.py

def add(a, b):
    return a + b

def test_addition():
    assert add(2, 3) == 5

def test_subtraction():
    assert add(5, -3) == 2
```

### Running Tests:
To run your test functions, simply execute the pytest command followed by the name of the file containing your test functions. By default, pytest will discover and run all test functions in files with names starting with "test_" or ending with "_test.py".

```
pytest test_example.py
```

If all the tests pass, you will see an output indicating the number of tests and the time taken for execution. If any test fails, pytest will display information about the failure.

### Test Output:
You can customize the output by using various options. For example, to get a more detailed output and see which test passed or failed, you can use the -v (verbose) option:

```
pytest -v test_example.py
```

