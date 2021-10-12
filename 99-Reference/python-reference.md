# Python Reference

[create an anchor](#anchors-in-markdown)

[Projects and Packages](##Projects-and-Packages)

[Documentation](#Documentation)

[Functions](#Functions)

[Data Structures](#Data-Structures)


## Projects and Packages
Lower case naming for scripts, libraries, packages, and modules.

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

## Functions

### Function Design Principles
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

### Useful Libraries for data processing
```buildoutcfg

functools
collections
pandas
random
datetime

```

### Function Parameters, Arguments, and User Input

#### Parameters and Arguments
Parameter
: Variable names used in a function definition. Holds the arguments supplied in the function invocation.

Argument
: Data supplied to function during invocation


#### Type of Arugments
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
*args:
Use as parameter to send `non-keyworded` argument list to a function.

```buildoutcfg
   # args example
   def multiply(*args):
    z = 1
    for num in args:
        z*=num
    
    return z
```

**kwargs:
Use as parameter to send keyword dictionary as argument list to a function.

```buildoutcfg
   # kwargs example
   def print_values(**kwargs):
    for k,v in kwargs.items():
        print(f'The value of {k} is {v}')
```

#### User Input
The input() function reads input data and returns a string.

```buildoutcfg
    # Get user input
    age = input("What is your age?")
    
    # Convert input to integer
    age = int(age)
```


### Formatting Output

##### F-Strings
```buildoutcfg
    # Print Output where quantity and total are numeric values
    print(f"my test string with {variable1} and {variable2})
```

##### Format Specifiers

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

### Error Handling
Place code with probable errors in the try block. If code successful, run the else code block.
```buildoutcfg
    try:
        # code block with probable errors
    except [ErrorType, Exception]:
        # Error Message or
        pass # continue running
    else:
        # code block if no errors
```

### Lambda
Local functions with unlimited arguments with a single expression.

```buildoutcfg
   x = lambda args:expression
   
   get_sum = lambda num1, num2: num1 + num2
   
```

## Data Structures

### Lists
```buildoutcfg
   bikes = ['trek', 'redline', 'giant']
```

#### Retrieve Items
```buildoutcfg
   first = bikes[0]
   last = bikes[-1]
```
### Modify Item
```buildoutcfg
   bikes[0] = 'trek-modify'
```

#### Add, Remove, delete, clear List
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

#### Loop a List
```buildoutcfg
    for bike in bikes:
      print(bike)
```
#### List Comprehension
Creates a new list based on the values of an existing list instead of using a `for` loop.

```buildoutcfg
    # Without a condition
    [x for x in list]
    
    # With a condition
    [x for x in list if x condition]
```

####  Slice a list
```buildoutcfg
   first_two = bikes[:2]
```

#### Copy a list
```buildoutcfg
   copy_bikes = bikes[:]
```
####  Join two lists
```buildoutcfg
   newlist = list1 + list2
   
   # using exten
   newlist.extend(list2)
```
####  Remove duplicates
```buildoutcfg
   # Convert list to a set()
   set_list = set(bikes)
```

####  Sort
```buildoutcfg
   # ascending
   bikes.sort(reverse=true)
   
   # descending
   bikes.sort()
   
```

#### Count Common Items
```buildoutcfg
   from collections import Counter
   
   c = Count(bikes)
   
   c.most_common(3) # three most common items in bikes
   
```

#### Tests for values and emptiness
```buildoutcfg
    bikes = ['trek', 'redline', 'giant']
    
    # value in list
    if 'trek' in bikes:
    
    # value not in
    if 'salsa' not in bikes:
    
    # list is empty
    if not bikes:
        print("list is empty")
```

####  Summary Stats
```buildoutcfg
   # length
   len(bikes)
   
   # sum
   sum(bikes)
   
   # min
   min(bikes)
   
   # max
   max(bikes)

```

### Dictionaries
Key-value pair data structure.

```buildoutcfg
   bike = {'color': 'green', 'price': 100}
```
#### Retrieve Item, keys, values
```buildoutcfg
    # item value
   get_color = bike['color']
   
   # keys
   keys = bike.keys()
   
   # value
   values = bike.values()
```
#### Modify Item
```buildoutcfg
   bike['color'] = 'blue'
```

#### Add key-value pair to dictionary
```buildoutcfg
   # add item
   bike['new_key'] = new_value
   
   # add item
   bike = {'new_key': new_value}
```

#### Delete key-value pair
```buildoutcfg
   del bike['color']
```


#### Min and Max Values

```buildoutcfg
    # return key with largest value
    max(bikes, key=bikes.get)
    
     # return key with smallest value
    min(bikes, key=bikes.get)
```

#### Loop a dictionary
```buildoutcfg
    # loop keys
    for x in bike.keys():
        print(x)


    # loop values
    for v in bike.values():
        print(x)
```

#### Ordered Dictionary
Preserves the key-value order when modifying the dictionary.
```buildoutcfg
    # import OrdedDict
    from collections import OrderedDict
    
    bikes = OrderedDict()
```

### Strings

#### String length
```buildoutcfg    
   s = 'hello'
   
   str_len = len(s)
```

#### String case
```buildoutcfg    
   # upper
   s.upper()
   
   # lower
   s.lower()
   
   # title return capitalized first letter
   s.title()
```

#### Substrings
```buildoutcfg    
   # string starts with
   s.startswith('hel')
   
   # string ends with
   s.endwith('lo')

   # replace a substring
   s.replace('e','z')
```

#### Split String
```buildoutcfg    
   # split string on the character x
   s.split(x)
```

#### Fill string
```buildoutcfg    
   # left fill string with zeros and make a lenght of 10
   s.zfill(10)
```


## Conditionals
```buildoutcfg
   if condition:
     # code block
   elif:
     # code block
   else:
     # code block
```

#### Tests for multiple conditions
```buildoutcfg
    # and    
    if age > 21 and age < 35:
    
    # or
    if age < 21 or age < 35:
    
    # not(A and B)
    if not a or not b:

    # not(A or B)
    if not a and not b:
```

## Files

#### Read file
```buildoutcfg    
    
    # read entire file
    with open(filename) as f:
      contents = f.read()

    # read line by line
    with open(filename) as f:
      for line in f
         print(line.rstrip())  

```

#### Write file
```buildoutcfg    
    # write single line
    with open(filename, 'w') as f:
      f.write('line 1')

    # write multiple lines
    with open(filename, 'w') as f:
      f.write('line 1')
      f.write('line 2')
```


#### Append to file
```buildoutcfg    
    # write single line
    with open(filename, 'a') as f:
      f.write('line 1')

```


#### File Paths
```buildoutcfg    
   ######## ADD NOTES

```

#### JSON
```buildoutcfg    
   import json
   
   # read json
   with open(filename) as j:
      contents = json.load(j)

   # write json
   with open(filename, 'w') as j:
      json.dump(data,j)

```

## Loops


### For Loops
Use to iterate over a sequence: list, tuple, dictionary, set, or string

```buildoutcfg    
   
   fruits = ["apple", "banana", "cherry"]
   
   for x in fruits:
     print(x)

```
#### Range(start,end,increment) function
Returns a sequence of numbers, starting from 0 and increments by 1 as teh default. The sequence ends at the specified user input number.

```buildoutcfg    
   
   for x in range(6):
     print(x)

```

#### Continue and Break
```buildoutcfg   
 
   fruits = ["apple", "banana", "cherry"]
   
   for x in fruits:
      if x == "banana":
         continue
      elif x == "apple":
         break
      else:
         print("complete")
     
```

### While Loops

```buildoutcfg    
   
   # simple
   x = 1
   while x <=5:
      print(x)
      x += 1

```

#### Continue and Break
```buildoutcfg    
   active = True
   while active:
      if x == 1:
         break
      elif x in my_list:
         continue
      else:
         print(x)
```

## Classes
Classes the foundation of OOP and provide a blueprint for the properties and methods of an object.

### Concepts
Object(instance):
distinct instance of a class with self-contained data and methods.

Method:
function of a class and takes `self` as the first parameter

Constructor:
Defines the class attributes and invoked on object creation.

Attribute:
Property of an object.

Encapsulation:
Hides the class implementation from the user.

Inheritance:
Extends a class to a new class. The new class inherits all the properties and methods of the parent class.

Composition:
Uses multiple classes to create a new class.

Polymorphism:
Provides an interface for different classes to use an object.

### Class Components
Class Variable:
Belong to the class, not the object. Declared before the constructor or any methods. Used for increment/decrement as well as constant variables.

Class Method:
Used with the class instead of the object instance.

Instance Variables:
Defined at the object level.

Methods:
Defined at the object level.

Public Methods:
Defined at the object level and the method available to the interface.

```buildoutcfg    
   def public_method(self):
      print(self.x)
```

Private Methods:
Defined at the object level and the method `NOT AVAILABLE` to the interface. Called automatically.

```buildoutcfg    
   def _private_method(self, val):
      return val - self.x
```

#### Creating a Class
```buildoutcfg  
   # class module
     
   class Car():
   
   # constructor
   def __init__(self, make, model, year):
      self.make = make
      self.model = model
      self.year = year
      fuel_level = 0
      fuel_capacity = 15
   
   def fill_tank(self):
      self.fuel_level = self.fuel_capacity
   
   def drive(self):
      print('Car is moving')
      
```

```buildoutcfg    
   # object creation
   
   my_car = Car('audi', 'a4', 2016)
```
#### Accessing methods, attribute values, and modifying attributes
```buildoutcfg    
   # Access attributes
   
   make = my_car.make
   model = my_car.model
   
```

```buildoutcfg    
   # Call methods
   
   my_car.fill_tank()
   my_car.drive()
   
```

```buildoutcfg    
   # Modify Attribute
   
   my_car.fuel_level = 10
   
```


#### Patterns for Object Data
```buildoutcfg    
   # Running Total
   
   def addItem(self,x):
      self.total += x
```

```buildoutcfg    
   # Counting Events
   
   def countItem(self,x):
      self.count += 1
```

```buildoutcfg    
   # Collecting values
   
   def collectItem(self,x):
      self.items.append(x)
```

#### Instances as attributes
Allows classes to work together to model complex situations.

```buildoutcfg    
   # Class Battery():
   """ Battery for Car""
   
   def __init__(self,size=70):
      self.size = size
      self.charge_level = 0
   
   def get_range(self):
      if self.size == 70:
         return 240
      elif self.size == 85:
         return 270
```

```buildoutcfg    
   # Class ElectricCar(Car):
   
   def __init__(self,make, model, year):
      self.battery = Battery() # Use battery object

```

```buildoutcfg    
   # Use the instance
   
   my_car.battery.get_range()

```

#### Inheritance

```buildoutcfg    
   # Parent Class

   class Dog():
   
      def __init__(self,name):
         self.name = name
      
      def sit(self):
         print(self.name + " is sitting.")
```

```buildoutcfg    
   # Child Class

   class Beagle():
   
      def __init__(self,name):
         super().__init__(name)
      
      def bark(self):
         print("Beagle is barking")
```