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

A class is a blueprint for how something should be deﬁned. It doesn’t actually contain any data. A class is a blueprint for how something should be deﬁned. It doesn’t actually contain any data.

