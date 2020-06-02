# bad-python-code

#### If-Elif Hell
```python
def func_x(num):
    if num == 1:
        return a()
    elif num == 2:
        return b()
    elif num == 3:
        return c()
    elif num == 4:
        return d()
    elif num == 5:
        return e()


# Better
def func_y(num):
    mapper = {
        1: a,
        2: b,
        3: c,
        4: d,
        5: e
    }
    return mapper[num]()
```

#### Unnecessary If-Else Boolean
```python
def func_x(is_chubby):
    if is_chubby is True:
        return a()
    elif is_chubby is False:
        return b()


# Better
def func_y(is_chubby):
    return a() if is_chubby else b()
```

#### Less Pythonic Loop
```python
def func_x(array):
    for i in range(len(array)):
        print(array[i])


# Better
def func_y(array):
    for item in array:
        print(item)
```

#### Returning boolean
```python
def func_x(num):
    if num > 10:
        return True
    else:
        return False


# Better
def func_y(num):
    return num > 10
```

#### Too Many Variable Declarations
```python
a = 1
b = 2
c = 3


# Better
a, b, c, = 1, 2, 3
```

#### Unpacking
```python
x = [10, 20, 30]

a = x[0]
b = x[1]
c = x[2]


# Better
a, b, c, = x
```

#### If/Else Loop Without a Break
```python
def func_x(breeds, pet):
    for breed in breeds:
        if breed == pet:
            print("I have a dog.")
    else:
        print("I don't have a dog")


func_x(["chihuahua", "jack russell"], "chihuahua")

# => I have a dog.
# => I don't have a dog


# Better
def func_y(breeds, pet):
    for breed in breeds:
        if breed == pet:
            print("I have a dog.")
            break
    else:
        print("I don't have a dog")


func_x(["chihuahua", "jack russell"], "chihuahua")
# => I have a dog.
```

#### Wildcard Imports
```python
from typing import *


# Better
from typing import Union, Optional, OrderedDict
```

#### Context Manager
```python
f = open("file.text", "r")
try:
    content = f.read()
finally:
    f.close()


# Better
with open("file.text", "r") as f:
    content = f.read()
```

# Returning More than One Variable Type from Function
```python
def func_x(param):
    if param:
        return 200, {"message": f"{param}"}
    else:
        return 400, "A useful error message"


# Better
def func_y(param):
    if param:
        return 200, {"message": f"{param}"}
    else:
        return 400, {"message": "A useful error message"}    
```