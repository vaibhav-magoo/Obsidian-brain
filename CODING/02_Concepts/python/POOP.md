[[python]] [[OOPs]] 


## Four tenets of OOP:
 - ==[[encapsulation]]== : access control , data integrity , modular and secure code
 - ==[[inheritance]]== : parent child relationship , promotes reuse and reduces duplication
 - ==[[polymorphism]]== : allows objects or functions to take on different forms
 - ==[[abstraction]]== : allowing developers to focus on what an object does rather than how it achieves its functionality.


### Defining a class:

##### ` __init__()` 
 - class is defined using the `class` keyword.
 - `_init_()` is used to declare attributes of each instance. 
 - `init` can be compared to constructors in java.

```python 
class Employee:
    def __init__(self, name, age):
        self.name =  name
        self.age = age
```

 - class names are written as "ClassName".
 - `.__init__()` initializes each new instance of the class.

#### Instance attributes vs class attributes:
 - An [[instance attributes]] value is specific to a particular instance of the class.
 - [[class attributes]] are attributes that have the same value for all class    instances. You can define a class attribute by assigning a value to a   variable name outside of .`__init__().`

#### instantiating :
 if there is a `Dog` class , it can be instantiated by using
 `Dog()`


## [[Inheritance]] :
- To create a class that inherits the functionality from another class, send the parent class as a parameter when creating the child class:

```python
class Student(Person):  
  def __init__(self, fname, lname):  
    super().__init__(fname, lname)`
```


## [[Polymorphism]] :
- Polymorphism is often used in Class methods, where we can have multiple classes with the same method name.

## [[Encapsulation]]:
- in Python, you can make properties private by using a double underscore `__` prefix:
```python
class Person:  
  def __init__(self, name, age):  
    self.name = name  
    self.__age = age # Private property  
  
p1 = Person("Emil", 25)  
print(p1.name)  
print(p1.__age) # This will cause an error
```

- Python also has a convention for protected properties using a single underscore `_` prefix:
```python
class Person:  
  def __init__(self, name, salary):  
    self.name = name  
    self._salary = salary # Protected property  
  
p1 = Person("Linus", 50000)  
print(p1.name)  
print(p1._salary) # Can access, but shouldn't
```


> [!NOTE] very important
> **Note:** A single underscore `_` is **just a convention**. It tells other programmers that the property is intended for internal use, but Python doesn't enforce this restriction.

## Accessing Inner Class from the Outside

To access the inner class, create an object of the outer class, and then create an object of the inner class:

### Example

Access the inner class and create an object:
```python
class Outer:  
  def __init__(self):  
    self.name = "Outer"  
  
  class Inner:  
    def __init__(self):  
      self.name = "Inner"  
  
    def display(self):  
      print("Hello from inner class")  
  
outer = Outer()  
inner = outer.Inner()  
inner.display()
```