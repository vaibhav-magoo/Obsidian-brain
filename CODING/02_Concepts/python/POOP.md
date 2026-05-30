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