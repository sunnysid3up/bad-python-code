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