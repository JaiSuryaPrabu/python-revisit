# Advanced Topics

## OOP

### Basic Definition

> In python , OOP concept is implemented with the `class` and `objects`

### Syntax

Class structure

```
class class_name:
    
    # constructor
    def __init__(self,*args):
        pass
    
    # method
    def method(self,*args):
        pass
```

Object initialization

``` 
object = class_name(arguments)
```

### Example

1. Basic example :
``` py linenums="1"
class sample:

    def __init__(self,name):
        self.name = name

    def get_name(self):
        return self.name
```

2. Inheritance
``` py linenums="1"
class parent:

    def __init__(self,value):
        self.value = value

    def multiply(self,value):
        return self.value * value

class child(parent):
    
    def __init__(self,value):
        super().__init__(value)
        self.value = value
```

## Lambda

### Basic Definition
> Lambda is a anonymous function that contains only the expression in the body of the function
### Syntax
```
variable = lambda function_name args* : expression 
```
### Example
``` py linenums="1"
anonymous = lambda multiply x,y : x*y
anonymous(5,4)
```
The Output is :
``` 20 ```

## Decorators

### Basic Definition
> A function that *describes* another function, denoted by `@`
### Syntax
Syntax for decorator
```
def decorator_function(function):
    def wrapper(*args):
        # code
        return function(args)
    return wrapper
```
Syntax to use the decorator for a function
```
@decorator_function
def function(*args):
    # code for function
```
### Example
Code
``` py linenums="1"
# decorator
def decorator(function):
    def wrapper(*args):
        print(f"The function name : {function.__name__}")
        print(f"The arguments are : {args}")
        return function(*args)
    return wrapper

@decorator
def func(x):
    print(f"Printing the {x}")
func(5)
```
Output
```
The function name : func
The arguments are : (5,)
Printing the 5
```
## Iterators & Iterables

### Basic Definition
* Iterator and Iterables are `class` that contains `__next__()` dunder in it
* Iterator needs an additional **dunder** named `__iter__()`

> 💡 All `iterators` are `iterables` but all `iterables` are not `iterators`
### Syntax
1. Iterator
```
class iterator_name:
    # constructor

    # iter() method
    def __iter__(self):
        return self

    # next() method
    def __next__(self):
        # logic for producing the each elements
        # StopIteration is an exception that is used to stop the iteration 
```
2. Iterator with `collections.abc.Iterator` doesn't needs `__iter__()` method in the class definition

3. Iterables
```
class iterable_names:
    # constructor

    # iter() method
    def __iter__(self):
        return iterable_names(self)
```
### Example
Code for `Iterator` class definition
``` py linenums="1"
class iterator:
    def __init__(self,sequence):
        self.sequence = sequence
        self.index = 0

    def __iter__(self):
        return self
    
    # __iter__() needs __next__() method
    def __next__(self):
        if self.index < len(self.sequence):
            value = self.sequence[self.index]
            self.index += 1
            return value
        else:
            # stop iteration is must
            raise StopIteration
```
Code for executing the *iterator*
``` py linenums="1"
for i in iterator([1,2,3,4,5]):
    print(i,end="\t")
```
Output
```
1	2	3	4	5
```
Code for `Iterables` structure
``` py linenums="1"
class iterables:
    def __init__(self,sequence):
        self.sequence = sequence

    def __iter__(self):
        return iterables(self)
    
    # no need of next() in iterables
```
Code for executing the iterables
``` py linenums="1"
i = iterables([1,2,3,4,5])
i.sequence
```
Output
```
[1, 2, 3, 4, 5]
```

## Generators

### Basic definition
* There are two types of generators:
    * Generator function
    * Generator Item
> `yield` is used in generator

### Syntax
1. Generator function
``` 
def generator_function(sequence):
    for i in sequence:
        yield i
```
2. Generative expression
```
# parenthesis denotes generator expression
varible = (i for i in [1,2,3,4,5])
```
### Example
1. Generator function structure
``` py linenums="1"
def generator(sequence):
    for item in sequence:
        yield item
```
Execution
``` py linenums="1"
for n in generator([1,3,4,5,6]):
    print(n,end = "\t")
```
Output
```
1	3	4	5	6
```
2. Generator Expression structure
``` py linenums="1"
gen = (item for item in [1,2,3,4,5])
```
Execution
``` py linenums="1"
for i in gen:
    print(i,end="\t")
```
Output
```
1	2	3	4	5
```

## Resource
1. Real python docs:
    * [OOP](https://realpython.com/python3-object-oriented-programming/)
    * [Lambda](https://realpython.com/python-lambda/)
    * [Decorator](https://realpython.com/primer-on-python-decorators/)
    * [Iterators and Iterables](https://realpython.com/python-iterators-iterables/)
    * [Generators](https://realpython.com/python-iterators-iterables/#creating-generator-iterators)