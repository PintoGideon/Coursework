### Object Oriented Programming

OOP, or object-oriented programming, is a method of structuring a program by bundling related properties and behaviors into individual objects.

Conceptually, objects are like the components of a system.

Think of a program as a factory assembly line of sorts. At each step of the assembly line a system component processes some material, ultimately transforming raw material into a ﬁnished product.

Primitive data structures—like numbers, strings, and lists—are
designed to represent simple pieces of information, such as the cost of an apple, the name of a poem, or your favorite colors, respectively. What if you want to represent something more complex?

For example, let’s say you want to track employees in an organization.
You need to store some basic information about each employee, such as their name, age, position, and the year they started working.
One way to do this is to represent each employee as a list:

```python
kirk = ["James Kirk", 34, "Captain", 2265]
spock = ["Spock", 35, "Science Officer", 2254]
mccoy = ["Leonard McCoy", "Chief Medical Officer", 2266]
```

First, it can make larger code ﬁles more diﬃcult to manage. If you reference `kirk[0]` several lines away from where the kirk list is declared,

Will you remember that the element with index 0 is the employee’s name?
Second, it can introduce errors if not every employee has the same number of elements in the list. In the mccoy list above, the age is missing, so `mccoy[1]` will return "Chief Medical Officer" instead of Dr. McCoy’s age.

### Classes

Classes are used to create user-deﬁned data structures. Classes deﬁne functions called methods, which identify the behaviors and actions that an object created from the class can perform with its data.

A class is a blueprint for how something should be deﬁned.
While the class is the blueprint, an instance is an object that is built from a class and contains real data. An instance of the Dog class is not a blueprint anymore. It’s an actual dog with a name, like Miles, who’s four years old.

All class deﬁnitions start with the class keyword, which is followed by the name of the class and a colon. Any code that is indented below the class deﬁnition is considered part of the class’s body.

```python
class Dog:
    pass
```

The body of the Dog class consists of a single statement: the pass keyword. pass is often used as a placeholder indicating where code will eventually go. It allows you to run this code without Python throwing an error.

The properties that all Dog objects must have are deﬁned in a method called `.__init__().` Every time a new Dog object is created, `.__init_-_()` sets the initial state of the object by assigning the values of the object’s properties. That is, `.__init__()` initializes each new instance of the class.

```python
class Dog:
    def __init__(self, name, age):
        self.name=name
        self.age=age

```

Notice that the `.__init__()` method’s signature is indented four spaces. The body of the method is indented by eight spaces. This indentation is vitally important. It tells Python that the `.__init__()` method belongs to the Dog class.

In the body of .**init**(), there are two statements using the self variable:

1. `self.name = name` creates an attribute called `name` and assigns to it the value of the name parameter.

2. `self.age = age` creates an attribute called age and assigns it to the value of the `age` parameter.

Attributes created in `.__init__()` are called instance attributes. On the other hand, class attributes are attributes that have the same value for all class instances. You can deﬁne a class attribute by assigning a value to a variable name outside of `.__init__()`

```python
class Dog:
    species="Canis Familiaris"

    def __init__(self, name, age):
        self.name=name
        self.age=age

```

Class attributes are deﬁned directly beneath the ﬁrst line of the class name and are indented by four spaces. They must always be assigned an initial value. When an instance of the class is created, class attributes are automatically created and assigned to their initial values.

### Instantiate an Object

```python
class Dog:
    pass
```

```python
Dog()
<__main__.Dog object at 0x106702d30>

```

You now have a new Dog object at 0x106702d30. This funny-looking string of letters and numbers is a memory address that indicates where the Dog object is stored in your computer’s memory.

```python
Dog()
<__main__.Dog object at 0x0004ccc90>

```

The new Dog instance is located at a diﬀerent memory address. That’s because it’s an entirely new instance and is completely unique from the ﬁrst Dog object that you instantiated.

```python
>>> a = Dog()
>>> b = Dog()
>>> a == b #false


```


### Putting it together

Here is a new Dog class with a class attribute called
two instance attributes called .name and .age:

```python
class Dog:
    species="Canis familiaris"
    def __init__(self, name, age):
        self.name=name
        self.age=age


```

To instantiate objects of this Dog class, you need to provide values for the name and age. If you don’t, then Python raises a TypeError:


```python
>> Dog()

Traceback (most recent call last):
File "<pyshell#6>", line 1, in <module>
Dog()
TypeError: __init__() missing 2 required positional
arguments: 'name' and 'age'

```

```python
>>> buddy = Dog("Buddy", 9)
>>> miles = Dog("Miles", 4)


```
This creates two new Dog instances—one for a nine-year-old dog
named Buddy and one for a four-year-old dog named Miles.

When you instantiate a Dog object, Python creates a new instance and passes it to the ﬁrst parameter of .__init__(). This essentially removes the self parameter, so you only need to worry about the name and age parameters.
After you create the Dog instances, you can access their instance attributes using dot notation:

```python
buddy.name
'Buddy'

buddy.age
# 9
```

You can access class attributes the same way

```python
buddy.species # 'Canis Familiaris'

```
All Dog instances have .species, .name, and .age attributes, so you can use those attributes with conﬁdence knowing that they will always return a value.

```python
>>> buddy.age = 10
>>> buddy.age
# 10
```

### Instance Methods

```python

class Dog:
    speciies = "Canis Familiaris"

    def __init__(self, name, age):
        self.name=name
        self.age=age
    

    def description(self):
        return f"{self.name} is {self.age} years old"

    def speak(self, sound):
        return f"{self.name} says {sound}"

```

The `Dog` class has two instance methods:

1. .description() returns a string displaying the name and age of the dog.

2. .speak() has one parameter called sound and returns a string containing the dog's name and the sound the dog makes


```python
miles = Dog("Miles",4)

miles.description()

miles.speak("Woof")


```

### Inhertiance


Inheritance is the process by which one class takes on the attributes and methods of another. Newly formed classes are called child classes, and the classes that child classes are derived from are called parent classes.

Child classes inherit all of the parent’s
attributes and methods but can also specify attributes and methods that are unique to themselves.


```python


class Dog:
    species = 'Canis Familiaris'

    def __init__(self, name, age, breed):
        self.name=name
        self.age=age
        self.breed=breed
```


```python

miles = Dog("Miles", 4, "Jack Russell Peter")
buddy = Dog("Buddy", 9, "Dachshund")

```
Each breed of dog has slightly diﬀerent behaviors. For example, bulldogs have a low bark that sounds like “woof,” but dachshunds have a higher-pitched bark that sounds more like “yap.”

Using just the Dog class, you must supply a string for the
ment of .speak() every time you call it on a Dog instance:
sound argument of `.speak().`

```python

class Dog:
    species= 'Canis Familiaris'

    def __init__(self, name, age):
        self.name=name
        self.age=age

    def __str__(self):
        return f"{self.name} is {self.age} years old"
    
    def speak(self, sound):
        return f"{self.name} says {sound}

```

Since diﬀerent breeds of dogs have slightly diﬀerent barks, you want to provide a default value for the sound argument of their respective `.speak()` methods. To do this, you need to override `.speak()` in the class deﬁnition for each breed.

```python

class JackRussellTerrier(Dog):
    def speak(self, sound='Arf'):
        return f"{self.name} says {sound}"


```

Now .speak() is defined on the JackRussellTerrier class with the default argument for sound set to "Arf". 

```python
miles = JackRussellTerrier("Miles",4)
miles.speak()
# Miles says "Arg"

miles.speak("Grr")
'Miles says Grr'
```

Sometimes it makes sense to completely override a method from a parent class. But in this instance, we don’t want the JackRussellTerrier class to lose any changes that might be made to the formatting of the
output string of Dog.speak().

To do this, you still need to deﬁne a `.speak()` method on the child JackRussellTerrier class. But instead of explicitly deﬁning the output string, you need to call the Dog class’s `.speak()` inside of the child class’s `.speak()` using the same arguments that you passed to
`JackRussellTerrier.speak()`.

You can access the parent class from inside a method of a child class by using super():

```python
class JackRussellTerrier(Dog):
    def speak(self, sound='Arf'):
        return super().speak(sound)

```

When you call `super().speak(sound)` inside of JackRussellTerrier, Python searches the parent class, Dog, for a `.speak()` method and calls it with the variable sound. Now when you call miles.speak(), you’ll see output reflecting the new formatting in the Dog class:

One thing to keep in mind about class inheritance is that changes to the parent class automatically propogate to child classes.


### More on Classes later (Please refer better tutorials online on this topic)


### Sample Task


Write a Rectangle class that must be instantiated with two attributes: .length and .width. Add an .area() method to the class that returns the area (length * width) of the rectangle.

```python

class Rectangle:
    def __init__(self, length, width):
        self.length=length
        self.width=width

    def area(self):
        return self.length * self.width
    

```



Then write a Square class that inherits from the Rectangle class and is instantiated with a single attribute called .side_length. Test your Square class by instantiating a Square with a .side_length of 4. Calling .area() should return 16

```python
class Square(Rectangle):
    def __init__(self, side_length):
        super().__init__(side_length, side_length)


square=Square(4)
print(square.area)
```

