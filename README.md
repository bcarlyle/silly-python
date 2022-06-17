# silly-python

A silly repo for documenting Carly's foray into Python.

## Python Best Practices
### Project structure
* Include a `setup.py` file for setting up a project in new environments
* Include a `requirements.txt` file w/ dependencies documentation
### Naming conventions
* Use underscores for long variable names (ex - `some_long_variable_name`)
* Use underscores for functions (ex - `some_function()`)
* Use CamelCase for class names (ex - `SomePythonClass`)
### Virtual environments
* Allows dependencies to be tied to a specific project
```
pip install virtualenv

python3 -m venv <env> # Create new environment
```

## Code Samples
### List comprehension
Syntax: _[ expression **for** item **in** list **if** condition ]_
```
evens = [i for i in range(20) if i%2==0]
print(evens)
# [0, 2, 4, 6, 8, 10, 12, 14, 16, 18]
```

## Helpful Tips
* Use a range object instead of a list when possible (requires MUCH less memory)
