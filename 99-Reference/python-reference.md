# Python Reference

## Projects and Packages

script
: file.py

library
: collection of packages

package
: directory of files

module
: file.py inside package

### Project and Package Structure
````
|- main.py
|- requirements.txt
|- setup.py
|- license
|- src
    |- data
    |- features
    |- modules
    |- visualization
    |- package1
    |   |- __init__.py
    |   |- module.py
    |- package2
    |   |- __init__.py
    |   |- module.py
|- tests
    |- data
    |- features
    |- modules
    |- visualization
    |- test_package1
    |   |- __init__.py
    |   |- test_module.py
    |- test_package2
    |   |- __init__.py
    |   |- test_module.py

````

## Documentation
Python uses `docstrings` to document and comment code. `docstring` has two types of comments:

1. one-line
```buildoutcfg
def square(a):
    '''one-line docstring to describe the function'''
    return a**a
```

2. multi-line
- In multi-line documentation, we follow the first line with a blank line before continuing the documentation.

```buildoutcfg
def square(a):
    '''multi-line docstring to describe the function
    
    Parameters:
    argument1(int): description of argument1

    Returns:
    int: Returning value
    '''

    return a**a
```

### Useful Libraries for documentation
```buildoutcfg

pydoc
sphinx

```

## Function Design Principles

1. Keep functions short and with a single responsibility
   1. Keep number of arguments < 2 or else further refactor to smaller sub-functions
   2. If need more than two parameters: refactor to an object with methods or change the incoming data structure
2. Avoid repetitive function calls
```buildoutcfg
    # Open three files
    
    # List of file names
    file_names = ['f1.txt', `f2.txt`, `f3.txt`]
    
    file_list = [myReadFileFunc(f) for f in filenames]
```
3. Use multiple assignment to unpack variables in data structures
```buildoutcfg
    x,y,z = [myReadFileFunc(f) for f in filenames]
```



