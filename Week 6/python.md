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


![package](https://user-images.githubusercontent.com/15992276/160470396-9597765a-89c8-491d-b8a1-ad1c7c9c8b5f.png)


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

### File Input and Output

So far, you’ve written programs that get their input from one of two places: from the program itself or from the user.


### File and the File System

There are a multitude of types of ﬁles out there: text ﬁles, image ﬁles, audio ﬁles, and PDF ﬁles, just to name a few. Ultimately, though, a ﬁle is just a sequence of bytes called the contents of the ﬁle.


When you access a ﬁle on a computer, the contents of the ﬁle are read from the disk in the correct sequence of bytes. The important thing to know here is that there is nothing intrinsic to the ﬁle itself that dictates
how to interpret the contents.

As a programmer, it’s your job to properly interpret the contents when you open a ﬁle. This might sound diﬃcult, but Python does a lot of the hard work for you.

For example, when you open a text ﬁle, Python can convert the numerical bytes of the ﬁle into text characters for you. You do not need to know the speciﬁcs of how this conversion happens. 

There are tools in the standard library for working with all sorts of ﬁle types, including images and audio ﬁles.
In order to access a ﬁle from a storage device, a whole host of things need to happen. You need to know on which device the ﬁle is stored, how to interact with that device, and where exactly on the device the ﬁle is located.


This monumental task is managed by a ﬁle system. Python interacts with the ﬁle system on your computer in order to read, write, and manipulate ﬁles.


### The File System


The ﬁle system on a computer does two things:

1. It provides an abstract representation of the ﬁles stored on your computer and devices connected to it.
2. It interfaces with devices to control storage and retrieval ﬁle data.


### The File System Hierarchy

![File_system](https://user-images.githubusercontent.com/15992276/160470427-ca3c67b1-1c5c-4477-8da7-2e4cb16aff92.png)

File systems organize ﬁles in a hierarchy of directories, which are also known as folders. At the top of the hierarchy is a directory called the root directory. All other ﬁles and directories in the ﬁle system are contained in the root directory.

Each ﬁle in directory has a le name that must be unique from any other ﬁle in the same directory. Directories can also contain other directories, called subdirectories or subfolders.



In this ﬁle system, the root folder is called root/. It has two subdirectories: app/ and photos/. The app/ subdirectory contains a program.py ﬁle
and a data.txt ﬁle. The photos/ directory also has two subdirectories, cats/ and dogs/, that both contains two image ﬁles.

### File Paths

To locate a ﬁle in a ﬁle system, you can list the directories in order, starting with the root directory, followed by the name of the ﬁle.


A string with the ﬁle location represented in this manner is called a file path.
For example, the ﬁle path for the jack_russel.gif ﬁle in the above ﬁlessystem is root/photos/dogs/jack_russel.gif.

1. Windows: C:\Users\David\Documents\hello.txt
2. macOS: /Users/David/Documents/hello.txt
3. Ubuntu Linux: /home/David/Documents/hello.txt

All three of these ﬁle paths locate a text ﬁle named hello.txt that is stored in the Documents subfolder of the user directory for a user named David. As you can see, there are some pretty big diﬀerences between
ﬁle paths from one operating system to another.


On macOS and Ubuntu Linux, the operating system uses a virtual file system that organizes all ﬁles and directories for all devices on the system under a single root directory, usually represented by a for- ward slash symbol (/). Files and folders from external storage devices are usually located in a subdirectory called media/.


In Windows, there is no universal root directory. Each device has a separate ﬁle system with a unique root directory that is named with a drive letter followed by a colon (:) and a back slash symbol (\).


Typically, the hard drive where the operating system is installed is assigned the letter C, so the root directory of the ﬁle system for that drive is C:.


The other major diﬀerence between Windows, macOS, and Ubuntu ﬁles paths is that directories in a Windows ﬁle path are separated by back slashes (\), whereas directories in macOS and Ubuntu ﬁle paths are separated by forward slashes (/).


### Working with File Paths in Python

To work with ﬁle paths in Python, use the standard libraries pathlib module. You’ll need to import the module before you can do anything with it.

```python
import pathlib

```
The pathlib module contains a class called Path that is used to represent a ﬁle path.

### Creating Path objects

There are several ways to create a new Path object:
1. From a string
2. With Path.home() and Path.cwd() class methods
3. With the / operator
The most straightforward way to create a Path object is from a string.

### Creating Path objects from strings


For instance, the following creates a Path object representing the macOS ﬁle path "/Users/David/Documents/hello.txt":

```python
>>> path = pathlib.Path("/Users/David/Documents/hello.txt")
```


There’s problem, though, with Windows paths. On Windows, directories are separated by back slashes \. Python interprets back slashes asvthe start of an escape sequence that represent a special character invthe string, such as the newline character (\n).


Attempting to create a object with the Windows ﬁle path
"C:\Users\David\Desktop\hello.txt" raises an exception:

```python
>>> path = pathlib.Path("C:\Users\David\Desktop\hello.txt")
SyntaxError: (unicode error) 'unicodeescape' codec can't decode bytes
in position 2-3: truncated \UXXXXXXXX escape
```


There are two ways to get around this problem:
You can use a forward slash (/) instead of a back slash (\) in your Windows ﬁle paths

```python
>>> path = pathlib.Path("C:/Users/David/Desktop/hello.txt")
```

Python can interpret this just ﬁne and will translate the path appropriately and automatically when interfacing with the Windows operating system.

### Path.home() and Path.cwd()

Besides creating a Path object from a string, the Path class has class methods that return Path objects of special directories. Two of the most useful class methods are Path.home() and Path.cwd().

Every operating system has a special directory for storing data for the currently logged in user. This directory is called the user's home directory. The location of this directory depends on the operating system.

1. Windows : C:\Users<username>
2. macOS: /Users/<username>
3. Ubuntu Linux: /home/<username>

The Path.home() class method creates a Path object representing the home directory regardless of which OS the code runs on.

```python
home= pathlib.Path.home()
```

When you inspect the thing like this:
home variable on Windows,

```python
>>> home
WindowsPath("C:\\Users\\David")
```

The Path.cwd() class method returns a Path object representing the current working directory, or CWD. The current working directory is a dynamic reference to a directory that depends on where a process on the computer is currently working.

When you run IDLE, the current working directory is usually set to the Documents directory in the current user’s home directory:

```python
>>> pathlib.Path.cwd()
WindowsPath(r"C:\Users\David\Documents")
```

### Absolute vs Relative Paths

A path that begins with the root directory in a ﬁle system is called an absolute le path. Not all ﬁle paths are absolute. A ﬁle path that is not absolute is called a relative file path.


```python

>>> # Relative Windows path
>>> path = pathlib.Path(r"Photos\image.jpg")

>>> # Relative macOS or Linux path
>>> path = pathlib.Path("Photos/image.jpg")


```


Notice that the path string does not start with
C:\ on Windows, or / on MacOS and Linux.


You can check whether or not a ﬁle path is absolute using the .is_absolute() method:

```python
>>> path.is_absolute()
False
```

Relative paths only make sense when considered within the context of some other directory. They are perhaps most commonly used to describe the path to a ﬁle relative to the current working directory, or the user’s home directory.

```python
>>> home = pathlib.Path.home()
WindowsPath('C:/Users/David')
>>> home / pathlib.Path(r"Photos\image.png")
WindowsPath('C:/Users/David/Photos/image.png')


```

On the left of the forward slash (/), put an absolute path to the directory that contains the relative path. Then put the relative path on the right side of the forward slash.

### Acccessing file path components


All ﬁle paths contain a list of directories. The .parents attribute of a Path object returns an iterable containing the list of directories in the ﬁle path:

```python
>>> path = pathlib.Path.home() / "hello.txt"
>>> path
WindowsPath("C:\\Users\\David")
>>> list(path.parents)
[WindowsPath("C:\\Users\\David"), WindowsPath("C:\\Users"),
WindowsPath("C:\\")]

```

Notice that the list of the directories are returned in reverse order from how they appear in the ﬁle path. That is, the last directory in the path is the ﬁrst directory in the list of parent directories.

You can iterate over the parent directories in a for loop:

```python
for directory in path.parents:
    print(directory)


C:\Users\David
C:\Users
C:\
```

The `.parent` attribute returns the name of the ﬁrst parent directory in the ﬁle path as a string:

```python
>>> path.parent
'C:\Users\David'
```

### Checking whether or not a file path exists

You can create a Path object for a ﬁle path even if that path doesn’t actually exist. Of course, ﬁle paths that don’t represent actual ﬁles or directories aren’t very useful, unless you plan on creating them at some point.

pending on whether or not the ﬁle path exists on the machine executing the program.

For instance, if you don’t have a hello.txt ﬁle in your home directory, then the .exists() method on the Path object representing that ﬁle path returns False:

```python
path = pathlib.Path.home() / "Hello.txt"
path.exists()

False

```

Using a text editor, or some other means, create a blank file called hello.txt in your home directory. 

```python
path.is_file()
True

path.is_dir()
False

```


### Searching for files in a directory

Sometimes you only need to iterate over ﬁles of a certain type, or ﬁles with certain naming schemes. You can use the Path.glob() method on a path representing a directory to get an iterable over directory contents that meet some criteria.


A wildcard character is a special character that acts as a placeholder in a pattern. They are replaced with other characters to create a concrete ﬁle path. For example, in the pattern "*.txt", the asterisk * is a wildcard character that can be replaced with any number of other
characters.

The pattern "*.txt" matches any ﬁle path that ends with.txt. That is, if replacing the * in the pattern with everything in some ﬁle path up to the last four characters results in the original ﬁle path, then that ﬁle
path is a match for the pattern "*.txt".

```python
for path in new_dir.glob("*.txt"):
    print(path)


# C:\Users\David\new_directory\file1.txt

```

![wildcard](https://user-images.githubusercontent.com/15992276/160470476-4e251d85-e21d-4d67-9359-b25c4dbad210.png)

### The * Wildcard

The * wildcard matches any number of characters in a ﬁle path pattern.

```python
>>> list(new_dir.glob("*.py"))
# [WindowsPath('C:/Users/David/new_directory/program1.py') WindowsPath('C:/Users/David/new_directory/program2.py'), WindowsPath('C:/Users/David/new_directory/program3.py' ]

```



### The ? Wildcard

The ? wildcard character matches a single character in a pattern. For example, the pattern "program?.py" will match any ﬁle path that starts with the word program followed by a single character and then .py:


```python

>>> list(new_dir.glob("program?.py"))
[WindowsPath('C:/Users/David/new_directory/program1.py'),
WindowsPath('C:/Users/David/new_directory/program2.py')]


```
You can use multiple instances if ? in a single pattern:

```python
>>> list(new_dir.glob("?older_?"))
[WindowsPath('C:/Users/David/new_directory/folder_a'),
WindowsPath('C:/Users/David/new_directory/folder_c')]
```

### Reading and Writing Files

A le is a sequence of bytes and a byte is a number between 0 and 255.

That is, a ﬁle is a sequence of integer values.
The bytes in a ﬁle must be decoded into something meaningful in order to understand the contents of the ﬁle.
Python has standard library modules for working with text, CSV, and audio ﬁles. There are a number of third-party packages available for working with other ﬁle types.

### Path.open() method

```python
>>> from pathlib import Path
>>> path = Path.home() / "hello.txt"
>>> path.touch()
>>> file = path.open(mode="r", encoding="utf-8")

```
First, a Path object for the hello.txt ﬁle is created and assigned to the path variable. Then path.touch() creates the ﬁle in your home directory.

Finally, ```.open()``` returns a new ﬁle object representing the hello.txt ﬁle and assigns it to the file variable.


Two keyword parameters used to open the ﬁle:

1. The mode parameter determines in which mode the ﬁle should be opened. The "r" argument opens the ﬁle in read mode.
2. The encoding parameter determines the character encoding used to decode the ﬁle. The argument "utf-8" represents the UTF-8 character encoding.


```python
>>> file

<_io.TextIOWrapper name='C:\Users\David\hello.txt' mode='r' encoding='utf-8'>
```
Text ﬁle objects are instances of the TextIOWrapper class. You will never need to instantiate this class directly, since you can create them with the Path.open() method.

When you create a ﬁle object with .open(), Python maintains a link to the ﬁle resource until you either explicitly tell Python to close the ﬁle,
or the program ends.

```python
file.close()

```

### The `with` statement

When you open a ﬁle, your program is accessing data external to the program itself. The operating system must manage the connection between your program and physical ﬁle itself. When you call a ﬁle object’s .close() method, the operating system knows to close the connection.

If your program crashes between the time that a ﬁle is opened and when it is closed, the system resources maintained by the connection may continue to live on until the operating system realizes that it’s no longer needed.

To ensure that ﬁle system resources are cleaned up even if a program crashes, you can open a ﬁle in a with statement.

```python
with path.open(mode="r", encoding="utf-8") as file:
```

The with statement has two parts: a header and a body. The header always starts with the with keyword and ends with a colon (:). The return value of path.open() is assigned to the variable name after the as keyword

After the with statement header is an indented block of code. When code execution leaves the indented block, the ﬁle object assigned to file is closed automatically, even if any exception is raised during execution of code inside of the block.

### Reading Data from a file


Open the hello.txt ﬁle in your home directory that you and type the text Hello World into it. Then save the ﬁle.

```python
path = Path.home() / "hello.txt"
with path.open(mode="r", encoding="utf-8") as file:
    text=file.read()

```


The ﬁle object created by path.open() is assigned to the file variable. Inside of the with block, the ﬁle object’s .read() method reads the text from the ﬁle and assigns the result to the variable text.

```python
>>> type(text)
<class 'str'>
>>> text
'Hello World'
```

The .read() method reads all the text in the file and returns it as a string value.

If there are multiple lines of text in the ﬁle, each line in the string is separated with a newline character \n. In a text editor, open the hello.txt ﬁle again and put the text "Hello again" on the second line.

Then save the ﬁle.
```python
>>> with path.open(mode="r", encoding="utf-8") as file:
...
text = file.read()
...
>>> text
'Hello World\nHello again'
```

The text from each line has a \n character in between.
Instead of reading the entire ﬁle at once, you can process each line of the ﬁle one at a time:


```python
>>> with path.open(mode="r", encoding="utf-8") as file:
...
for line in file.readlines():
...
print(line)
...
Hello World

Hello again
```

The .readlines() method returns an iterable of lines from the ﬁle. At each step of the for loop the next line of text in the ﬁle is returned and printed.

Notice that an extra blank line is printed between the two lines of text. This doesn’t have anything to do with line endings in the ﬁle. It happens because the print() function automatically inserts a newline character at the end of every string it prints.

To print the two lines without the extra blank line, set the print() function’s optional end parameter to an empty string:

```python
>>> with path.open(mode="r", encoding="utf-8") as file:
...
for line in file.readlines():
...
print(line, end="")
...
Hello World
Hello again
```


If you try to read from a ﬁle that does not exists, both
open() raise a FileNotFoundError:

```python
>> path = Path.home() / "new_file.txt"
>>> with path.open(mode="r", encoding="utf-8") as file:
text = file.read()
Traceback (most recent call last):
File "<pyshell#197>", line 1, in <module>
with path.open(mode="r", encoding="utf-8") as file:
File "C:\Users\David\AppData\Local\Programs\Python\
Python38-32\lib\pathlib.py", line 1200, in open
return io.open(self, mode, buffering, encoding, errors, newline,
File "C:Users\David\AppData\Local\Programs\Python\
```
### Writing Data to a file

To write data to a plain text ﬁle, you pass a string to a ﬁle object’s `.write()` method. The ﬁle object must be opened in write mode by passing the value "w" to the mode parameter.

```python
>>> with path.open(mode="w", encoding="utf-8") as file:
...
file.write("Hi there!")
...
9
>>>
```

Notice that the integer 9 is displayed after executing the with block.
That’s because .write() returns the numbers of characters that are written. The string "Hi there!" has nine characters, so .write() returns the number 9.
When the text "Hi there!" is written to the hello.txt ﬁle, any existing contents are written over. It’s as if you deleted the old hello.txt ﬁle and created a new one.


```python
>>> with path.open(mode="r", encoding="utf-8") as file:
...
text = file.read()
...
>>> print(text)
Hi there!

```

You can append data to the end of a ﬁle by opening the ﬁle in append mode:

```python
>>> with path.open(mode="a", encoding="utf-8") as file:
...
file.write("\nHello")
...
6
```

When a ﬁle is opened in append mode new data is written to the end of the ﬁle and old data is left intact. The newline character is put at the beginning of the string so that the word "Hello" is printed on a new line at the end of the ﬁle.

Without a newline character at the beginning of the string, the word "Hello" would be printed on the same line as any existing text at the end of the ﬁle.

You can write multiple lines to a ﬁle at the same time using the `.writelines()` method. First, create a list of strings:

```python
lines_of_text=["Hello from line1\n","Hello from line2\n","Hello from line 3 \n"]
```

Then open the ﬁle in write mode and use the .writelines() method to write each string in the list to the ﬁle:

```python
>>> with path.open(mode="w", encoding="utf-8") as file:
        file.writelines(lines_of_text)
...
```

Each string in the lines_of_text is written to the file.
Notice that each string ends with the newline character (\n). That's because .writelines() doesn't automatically insert each string in the list on a new line.

```python
path=Path.home()
```


### Exercise

1. Write the following text to ﬁle called starships.txt in your home directory

Discovery
Enterprise
Defiant
Voyager

```python

from pathlib import Path
starships=["Discovery\n", "Enterprise\n", "Defiant\n", "Voyager"]

file_path= Path.home() / "startships.txt"

with file_path.open(mode="w", encoding="utf-8") as file:
    file.writelines(starships)

```

2. Read the ﬁle starhips.txt you created in Exercise 1 and print each
line of text in the ﬁle. The output should not have extra blank lines
between each word.

```python
with file_path.open(mode="r", encoding="utf-8") as file:
    for starship in file.readlines():
        print(starship, end="")

```

3. Read the ﬁle startships.txt and print the names of the starships
that start with the letter D.

```python
with file_path.open(mode="r", encoding="utf-8") as file:
    for starship in file.readlines():
        if starship.startswith("D"):
            print(starship,end="")


```

### Read and Write CSV Data

Suppose you had a temperature sensor in your house that records the
temperature every four hours. Over the course of a day, six tempera-
ture readings are taken.
You can store each temperature reading in a list:

```python
>>> temperature_readings = [68, 65, 68, 70, 74, 72]
```

Each day a new list of numbers is generated. To store these values to
a ﬁle, you can write the values from each day on a new line in a text
ﬁle and separate each value with a comma.


```python
from pathlib import Path

file_path=Path.home() / "temperature.txt"
with file_path.open(mode="a", encoding="utf-8") as file:
    file.write(str(temperature_readings[0]))
    for temp in temperature_readings[1:]:
        file.write(f",{temp}")
2
3
3
3
3
3

```

This creates a ﬁle called temperatures.csv in your home directory and
opens it in append mode. On a new line at the end of the ﬁle, the ﬁrst value in the temperature_readings list is written to the ﬁle. Then each remaining value in the list is written, preceded by a comma, to the same line.

```python
with file_path.open(mode="r", encoding="utf-8") as file:
    text=file.read()

>> text
'68,65,68,70,74,72'

```
The format that in which you have saved the values is called comma-
separated value, or CSV for short. The temperatures.csv ﬁle is called
a CSV ﬁle.


CSV ﬁles are a great way to store records of sequential data because you can recover each row of the CSV value as a list:

```python
>>> temperatures = text.split(",")
>>> temperatures
['68', '65', '68', '70', '74', '72']
```

The values in the temperatures list are strings, not integers like the values originally written to the ﬁle. This is because values read from a text ﬁle are always read as strings.

```python

>>> int_temperatures = [int(temp) for temp in temperatures]
>>> int_temperatures
[68, 65, 68, 70, 74, 72]
```
Reading and writing CSV ﬁles is so common that the Python standard
library has a module called csv to lessen to workload required for working with CSV ﬁles.

### The csv module

The csv module can be used to read and write CSV ﬁles.

```python
import csv
```
```python
daily_temperatures = [[68, 65, 68, 70, 74, 72],[67, 67, 70, 72, 72, 70],[68, 70, 74, 76, 74, 73],]


file_path= Path.home() / "temperatures.csv"
file= file_path.open(mode="w", encoding="utf-8")
```
Instead of using a with statement, a ﬁle object is created and assigned to the file variable so that we can inspect each step of the writing process as we go.
Now create a CSV writer object by passing the ﬁle object
to csv.writer()


```python
>>> writer = csv.writer()
```

csv.writer() return a CSV writer object with methods for writing data to the CSV file.

```python
for temp_list in daily_temperatures:
    writer.writerow(temp_list)

19
19
19
```

Just like a ﬁle object’s .write() method, .writerow() returns the number of characters written to the ﬁle.

Now close the file

```python
file.close()
```

The main advantage of using csv.writer to write to a CSV ﬁle is that you don’t need to worry about converting values to strings before writing them to the ﬁle. The csv.writer object handles this for you, which results in shorter and cleaner code.

`.writerow()` writes a single row to the CSV ﬁle, but you can write multiple rows at one using the .writerows() method. This shortens the code even more when your data is already in a list of lists:

```python
with file_path.open(mode="w", encoding="utf-8") as file:
    writer=csv.writer(file)
    writer.writerows(daily_temperatures)
    
```

```python
>>> file = file_path.open(mode="r", encoding="utf-8")
>>> reader = csv.reader(file)
```

csv.reader() returns a CSV reader object that can be used to iterate overvthe rows of the CSV ﬁle:

```python
for row in reader:
    print(row)
...

```python
['68', '65', '68', '70', '74', '72']
['67', '67', '70', '72', '72', '70']
['68', '70', '74', '76', '74', '73']
file.close()
```
Each row of the CSV ﬁle is returned as a list of strings. To recover the daily_temperatures list of lists, you’ll need to convert each list of strings to a list of integers using a list comprehension.


### Reading and Writing CSV Files with Headers

```text
name,department,salary
Lee,Operations,75000.00
Jane,Engineering,85000.00
Diego,Sales,80000.00
```

It’s possible to read CSV ﬁles such as the one above using csv.reader(), but you have to keep track of the header row, and each row is returned as a list without the ﬁeld names attached to it. It makes more sense to return each row as a dictionary whose keys are the ﬁeld names and values are the ﬁeld values in the row. This is precisely what csv.DictReater objects do!

Create a new file called employees.csv.

```python
file_path= Path.home()/"employees.csv"
file=file_path.open(mode="r", encoding="utf-8")
reader= csv.DictReader(file)
```

```python
reader.fieldnames
['name','deparment','salary']
```

Just like csv.reader objects, DictReaders objects are iterable

```python
for row in reader:
    print(row)


file.close()

#{'name': 'Lee', 'department': 'Operations', 'salary': '75000.000'}
# {'name': 'Jane', 'department': 'Engineering', 'salary': '85000.00'}
#{'name': 'Diego', 'department': 'Sales', 'salary': '80000.00'}
```


Notice that the salary ﬁeld gets read as a string. Since CSV ﬁles are plain text ﬁles, the values are always read as strings. You’ll need to convert the strings to diﬀerent data types as needed.

```python
def process_row(row):
    row["salary"]=float(row["salary"])
    return row

with file_path.open(mode="r", encoding="utf-8") as file:
    reader=csv.DictReader(file)
    for row in reader:
        print(process_row(row))


# {'name': 'Lee', 'department': 'Operations', 'salary': 75000.0}

# {'name': 'Jane', 'department': 'Engineering', 'salary': 85000.0}

# {'name': 'Diego', 'department': 'Sales', 'salary': 80000.0}
```
 You can write csv files with headers using csv.DictWriter class, which writes dictionaries with shared keys to rows in a csv file.

 ```python
 people = [{"name":"Vernoica","age":29},{"name":"Audrey","age":32}]

 file_path=Path.home() / "people.csv"

 file= file_path.open(mode="w", encoding="utf-8")
 writer = csv.DictWriter(file, fieldnames=["name","age"])
 ```

 When you instantiate a new DictWriter object, the ﬁrst parameter is the ﬁle object for writing the CSV data. The fieldnames parameter, which is required, is a list of strings of the ﬁeld names.



### Installing Third Party Packages

Python’s package manager pip is used to install and manage third party packages. It is a separate program from Python, although it’s likely that pip was installed on your computer whenever you downloaded and installed Python.


With your terminal program open, type in the following command to check whether or not pip is installed on your system:

```python
$ python3 -m pip --version
```

If pip is installed, you should see something like the following output displayed in your terminal:

```python
pip 19.3.1 from c:\users\David\appdata\local\programs\python\
python38-32\lib\site-packages\pip (python 3.8)
```

This output indicates that version 19.3.1 of and is linked to the Python 3.8 installation.

### Listing all installed packages

```python
python3 -m pip list
```

### Install a Package

```python
python3 -m pip install requests
```

Notice that pip ﬁrst tells you that it is “Collecting requests.” You will see the URL that pip is using to install the package from, as well as a progress bar indicating the progress of the download.

After that, you will see that pip installs four more packages: chardet, certifi, idna and urllib3. These packages are dependencies of requests. That means that requests requires these packages to be installed in order for it to work properly.

### Installing packages with specific versions


To install the latest version of `requests` whose version number is 2 or greater

```python
python3 -m pip install requests>=2.0
```

To install the latest version that is less than equal or equal to some number,
```python
python3 -m pip install requests<=3.0
```

The <= and >= version specifiers are inclusive because they include the version number that follows the specifier.

Exclusive versions < and > exist as well.

```python
python3 -m pip install requests<3.0
```
Finally, you can pin dependencies to a speciﬁc version with the version speciﬁer:

```python
python3 -m pip install requests==2.22.0
```


### Show Package Details

```python
python3 -m pip show requests
```

### Pitfalls of Third Party Packages

The beauty of third-party packages is that they give you the ability to add functionality to your project without having to implement everything from scratch. This oﬀers massive boosts in productivity.

But with great power comes great responsibility. As soon as you include someone else’s package in your project, you are placing an enormous amount of trust in those responsible for developing and maintaining the package. By using a package you did not develop, you lose control over certainvaspects of your project. In particular, the maintainers of a packagevmay release a new version that introduces changes that are incompatible with the version you use in your project.


By default, pip installs the latest release of a package, so if you distribute your code to someone else and they install a newer version ofva package required by your project, they may not be able to run your code. This presents a signiﬁcant challenge, for both the end user and yourself. Fortunately, Python comes with a ﬁx for this all-to-common problem: virtual environments.


```python
python3.8 -m venv env
source env/bin/activate
```
You’ve now created a folder called venv that includes a full Python install, and your shell is now set up to call this local Python version when you run the python command.

### Requirements.txt

requirements.txt is a special file that we use to tell pip, the Python package manager, which dependencies to install. The format is simple: you can create one manually by putting each dependency you import into a text file named requirements.txt, one dependency on each line.

Alternatively, you can install each dependency in your virtualenv using pip. Once you’re done (your application stops complaining about missing imports), you can run:

```python
pip freeze > requirements.txt
```
This will automatically generate a requirements.txt file for you, using the specific version of each dependency you installed in your virtualenv.

Later on, when you move your Python application to a new virtualenv, a new computer, or deploy it to the world, you can bring all your dependencies with you with requirements.txt. To install all your requirements again in a new virtual environment you can simply run:

```python
pip install -r requirments.txt
```



### I will cover virtual environments in depth at a later time.

