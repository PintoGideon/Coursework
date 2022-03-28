### Modules and Packages

As you gain experience writing code, you will eventually work on projects that are so large that keeping all of the code in a single ﬁle becomes cumbersome.
Instead of writing a single ﬁle, you can put related code into separate ﬁles called `modules`. Individual modules can be put together like building blocks to create a larger application.


### Working with Modules

A module is a ﬁle containing Python code that can be re-used in other Python code ﬁles.


Technically, every Python script ﬁle that you have created while reading this book is a module, but you haven’t seen how to use code from one module inside of another.

### Creating Modules

Start a new script window by selecting File > New File
or by pressing Ctrl + N . In the script window, deﬁne a function add() that returns the sum of its two parameters:

```python
def add(x,y):
    return x+y

```

Save the file as adder.py in a new directory called myproject/somewhere on your computer. adder.py is a python module. Now open a new file and type the following code.

```python
# main.py

value=add(2,2)
print(value)

```
Save the ﬁle as main.py in the same myproject/ folder you just created. Then press F5 to run the module.

When the module runs you’ll see a NameError displayed in IDLE’s inter-
active window:
```python
Traceback (most recent call last):
File "//Documents/myproject/main.py", line 1, in <module>
value = add(2, 2)
NameError: name 'add' is not defined
```

It makes sense that a NameError occurs because add() is deﬁned in adder.py and not in main.py. In order to use add() in main.py, you must ﬁrst import the adder module.

```python

# main.py

import adder

value=add(2,2)
print(value)
```
When you import one module into another, the contents of the imported module become available in the other. The module with the import statement is called the calling module. In this example, adder.py is the imported module and main.py is the calling module.

Press Ctrl + S to save main.py and press F5 to run the module. The NameError exception is still raised. That’s because add() can only be accessed from the adder namespace.

A namespace is a collection of names, such as variable names, function names, and class names. Every Python module has its own namespace.
Variables, functions, and classes in a module can be accessed from within the same module by just typing their name. That’s how you’ve been doing it throughout this book so far. However, this doesn’t work for imported modules.

To access a name in an imported module from the calling module, type the imported module’s name followed by a dot (.) and the name you want to use:

For instance, to use the `add()` function in the adder module, you need to type `adder.add().`

```python
# main.py
import adder
value = adder.add(2, 2)
# <-- Change this line
print(value)
```

There are two import variations you should know about.

1. import <module> as <other_name>
2. from <module> import <name>

```python 
import adder as a

value= a.add(2,2)

```


```python
from adder import add 
value = add(2,2)
```


### Working with Packages
Modules allow you to divide a program in to individual ﬁles that can be reused as needed. Related code can be organized into a single module and kept separate from other code.

Package take this organizational structure one step further by allowing you to group related modules under a single namespace.

### Creating Packages

A package is a folder that contains one or more Python modules. It must also contain a special module called __init__.py. Here is an example of a package so that you can see this structure:

The __init__.py module doesn’t need to contain any code! It only needs to exist so that Python recognizes the mypackage/ folder as a Python package.

Using your computers ﬁle explorer, or whatever tool you are comfortable with, create a new folder somewhere on your computer called packages_example/. Inside of that folder, create another folder called mypackage/.

The packages_example/ folder is called the project folder, or project root folder, because it contains all of the ﬁles or folders in the packages_examples project. The mypackage/ folder will eventually become a Python package. It isn’t one right now because it doesn’t
contain any modules.

Creat a new script and add the following comment, save the file as main.py

```python
#main.py
```

Open another script, and type the commment

```python
# __init__.py
```

Then save the ﬁle as __init__.py in the mypackage/ subfolder of your packages_example folder.

Finally, create two more script windows. Save these ﬁles as module1.py and module2.py, respectively, in your mypackages/ folder, and insert comments at the top of each ﬁle containing the ﬁle name.

Now that we’ve created the package structure, let’s add some code. In the module1.py ﬁle, add the following function:

```python
#module1.py

def greet(name):
    print(f"Hello, {name}")


```

In the module2.py ﬁle add the following:

```python
def depart(name):
print(f"Goodbye, {name}!")

```
Make sure you save both of the module1.py and module2.py ﬁles! You’re now ready to import and use these modules in the main.py module.


### Importing Modules From Packages


```python
# main.py
import mypackage
mypackage.module1.greet("Pythonista")
mypackage.module2.depart("Pythonista")

```

Save main.py and press F5 to run the module. In the interactive window, an AttributeError is raised:

```python

Traceback (most recent call last):
File "\MacHomeDocumentspackages_examplemain.py", line 5, in <module>
mypackage.module1.greet("Pythonista")
AttributeError: module 'mypackage' has no attribute 'module1
```

When you import the mypackage module, the module1 and module2 namespaces are not imported automatically. In order to use them, you need to import them as well.

```python

import mypackage.module1
import mypackage.module2
# <-- Add this line
# Leave the below code unchanged
mypackage.module1.greet("Pythonista")
mypackage.module2.depart("Pythonista")
```

Now when you save and run called:
main.py, both greet() and depart() get
```python
Hello, Pythonista!
Goodbye, Pythonista!
```

In general, modules are imported from packages using dotted module names with the following format:

### Import Statement Variations for Packages


1. import <package>
2. import <package> as <other_name>
3. from <package> import <module>
4. from <package> import <module> as <other_name>

These variations work much the same was as the counterparts for modules.

For instance, instead of importing mypackage.module1 on one line and on another, you can import both modules from the package on the same line.

```python
# main.py

from mypackage import module1, module2
module1.greet("Pythonista")
module2.depart("Pythonista")


```

You can change the name of an imported module using as the
word:


```python
# main.py
from mypackage import module1 as m1, module2 as m2
m1.greet("Pythonista")
m2.depart("Pythonista")

```

You can also import individual names from a package module. For instance, you can rewrite your main.py to the following without changing what gets printed when you save and run the module:

```python
# main.py
from mypackage.module1 import greet
from mypackage.module2 import depart
greet("Pythonista")
depart("Pythonista")
```





