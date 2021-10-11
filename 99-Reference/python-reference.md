# Python Reference

[create an anchor](#anchors-in-markdown)

[Projects and Packages](##Projects-and-Packages)

[Documentation](#Documentation)

[Functions](#Functions)

[Data Structures](#Data-Structures)


# Projects and Packages
Lower case naming for scripts, libraries, packages, and modules.

script
: file.py

library
: collection of packages

package
: directory of files

module
: file.py inside package

## Project and Package Structure
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

# Documentation
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

# Functions

## Function Design Principles
1. Naming functions: use lower case and underscores between words
2. Keep functions short and with a single responsibility
   1. Keep number of arguments < 2 or else further refactor to smaller sub-functions
   2. If need more than two parameters: refactor to an object with methods or change the incoming data structure
3. Avoid repetitive function calls
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

## Useful Libraries for documentation
```buildoutcfg

functools
pandas

```

## Function Parameters, Arguments, and User Input

### Parameters and Arguments
Parameter
: Variable names used in a function definition. Holds the arguments supplied in the function invocation.

Argument
: Data supplied to function during invocation


### Type of Arugments
1. Default
2. Required and Optional
3. Flexible

#### Default Value
```buildoutcfg
    # Default Value
    def describe_pet(name, animal='dog'):
        print(name, animal)
       
    # Call Function
    describe_pet('Lucy')
    
    # Result
    'Lucy, Dog'
```

#### Optional Argument using None
```buildoutcfg
    # Default Value
    def describe_pet(name, animal=None):
        print(name, animal)
       
    # Call Function
    describe_pet('Lucy')
    
    # Result
    'Lucy'
```

#### Flexible Arguments
```buildoutcfg
    # Default Value
    def describe_pet(name, animal=None):
        print(name, animal)
       
    # Call Function
    describe_pet('Lucy')
    
    # Result
    'Lucy'
```


#### User Input
The input() function reads input data and returns a string.

```buildoutcfg
    # Get user input
    age = input("What is your age?")
    
    # Convert input to integer
    age = int(age)
```


#### Formatting Output

##### F-Strings
```buildoutcfg
    # Print Output where quantity and total are numeric values
    print(f"my test string with {variable1} and {variable2})
```

*Format Specifiers*

f
: floating point

s
: string

d
: integer

%.#f
: number of decimal places

%#
: field width
```buildoutcfg
    # Print Output where quantity and total are numeric values
    print("Quantity: %d Total: %10.2f" %(quantity,total))
```




## Error Handling
Place code with probable errors in the try block. If code successful, run the else code block.
```buildoutcfg
    try:
        # code block
    except ErrorType:
        # Error Message
    else:
        # code block
```

## Lambda
Local functions with unlimited arguments with a single expression.

```buildoutcfg
   x = lambda args:expression
   
   get_sum = lambda num1, num2: num1 + num2
   
```

# Data Structures

## Lists
```buildoutcfg
   bikes = ['trek', 'redline', 'giant']
```

### Retrieve Items
```buildoutcfg
   first = bikes[0]
   last = bikes[-1]
```
### Modify Item
```buildoutcfg
   bikes[0] = 'trek-modify'
```

### Add, Remove, delete, clear List
```buildoutcfg
   # Add
   bikes.append('salsa')
   
   # Remove specific item
   bikes.remove("trek")
   
   # Remove specified index
   bikes.pop(1)
   
   # Remove last item
   bikes.pop()
   
   # Delete list
   del bikes
   
   # Clear list
   bikes.clear()
```

### Loop a List
```buildoutcfg
    for bike in bikes:
      print(bike)
```
### List Comprehension
Creates a new list based on the values of an existing list instead of using a `for` loop.

```buildoutcfg
    # Without a condition
    [x for x in list]
    
    # With a condition
    [x for x in list if x condition]
```

### Slice a list
```buildoutcfg
   first_two = bikes[:2]
```

### Copy a list
```buildoutcfg
   copy_bikes = bikes[:]
```
### Join two lists
```buildoutcfg
   newlist = list1 + list2
   
   # using exten
   newlist.extend(list2)
```

## Dictionaries
```buildoutcfg
   bikes = ['trek', 'redline', 'giant']
```

# Conditionals
