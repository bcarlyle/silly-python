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
Largely taken from https://medium.com/pythonland/30-python-best-practices-tips-and-tricks-19172564f9c
### Return multiple values
Note - should only be used for returning up to 3 values (>3 should be put into a data object)
```
def get_user(id):
    # fetch user from database
    # ....
    return name, birthdate

name, birthdate = get_user(4)
```
### Data class
```
from dataclasses import dataclass

@dataclass
class Card:
    rank: str
    suit: str
    
card = Card("Q", "hearts")

print(card == card)
# True

print(card.rank)
# 'Q'

print(card)
Card(rank='Q', suit='hearts')
```
### List comprehension
Syntax: _[ expression **for** item **in** list **if** condition ]_
```
evens = [i for i in range(20) if i%2==0]
print(evens)
# [0, 2, 4, 6, 8, 10, 12, 14, 16, 18]
```
### List slicing
Syntax: _a[start:stop:step]_
```
first_two = [1, 2, 3, 4, 5][0:2]
print(first_two)
# [1, 2]

steps = [1, 2, 3, 4, 5][0:5:2]
print(steps)
# [1, 3, 5]

mystring = "abcdefdn nimt"[::2]
print(mystring)
# 'aced it'
```
### List/string reversal
```
revstring = "abcdefg"[::-1]
print(revstring)
# 'gfedcba'

revarray = [1, 2, 3, 4, 5][::-1]
print(revarray)
# [5, 4, 3, 2, 1]
```
### Dictionary merging
```
dict1 = { 'a': 1, 'b': 2 }
dict2 = { 'b': 3, 'c': 4 }
merged = { **dict1, **dict2 }

print (merged)
# {'a': 1, 'b': 3, 'c': 4}

# Python >= 3.9 only
merged = dict1 | dict2

print (merged)
# {'a': 1, 'b': 3, 'c': 4}
```
### Displaying images
Install Pillow w/ - `pip3 install Pillow`

```
from PIL import Image

im = Image.open("kittens.jpg")
im.show()
print(im.format, im.size, im.mode)
# JPEG (1920, 1357) RGB
```
## Helpful Tips
* Use a range object instead of a list when possible (requires MUCH less memory)
