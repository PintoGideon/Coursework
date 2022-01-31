### What is a programming language ?

Programming in lay man terms is a way for us to give instructions to the computer. Computers don't understand human language for that matter. Computer's speak in ones and zeros. But writing ones and zeros would be difficult for us. It's hard for us to communicate like that.

Humans have developed programming languages that are between the human language and machine language.


Let's say you want to book a flight through a website. As a user , you want to pull up a list of flights for a particular destination on the screen. The web page is usually coded in Python or Javascript by a developer. We will call it source code. 

How does the source code in a file convert into zeros and one's so that our machines can understand. We need to translate the source code into machine level language and for that we need a translator.

### What is a translator? 

Well, the translator is another program written by a user. It can either be a compiler or an interpreter.
Python usually uses an interpreter. An interpreter goes line by line through your source code and executes it on our machine. Compilers on the other hand take your code all at once and translates it into machine code. The differences between these two are a bit complicated and can be covered at a later point.

![Compilers](https://user-images.githubusercontent.com/15992276/151667882-3478dca0-3510-4adc-b223-4911936b9efd.png)


In order for us to be able to write Python code, we can't do it anywhere. If you opened up a text file in your computer and started writing python code, you wouldn't be able to make your machine function accordingly. Why? We need to have a translation service.

### Python Interpreter

How do I get the translation service? Well, you download it on your machine.
Download Python on your machine: (https://www.python.org/downloads/)

When you click on Downloads, and dowload python on your machine, you are actually downloading this.
(https://github.com/python/cpython)

It's important that you install python correctly (https://techsviewer.com/how-to-install-python-on-mac/)

![Python_Installer](https://user-images.githubusercontent.com/15992276/151674132-aafddc21-d4af-458f-9ac7-5325664c4137.png)

Press Continue a few times until you are asked to agree to the software license agreement. Then click Agree. You’ll be shown a window that tells you where Python will be installed and how much space it will take. You most likely don’t want to change the default location, so go ahead and click Install to start the installation.


![shell_window](https://user-images.githubusercontent.com/15992276/151674144-a49d24f4-6809-49cc-969a-46f86f737cad.png)




### Open IDLE
You can open IDLE in three steps:
1. Open Finder and click Applications.
2. Double-click the Python 3.8 folder.
3. Double-click the IDLE icon.
IDLE opens a Python shell in a new window. The Python shell is an
interactive environment that allows you to type in Python code and
execute it immediately. It’s a great way to get started with Python!

The ```>>>``` symbol that you see is called a prompt. Whenever you see
this, it means that Python is waiting for you to give it some instructions.

You just downloaded a translation service called as `cypthon`. Remember, I told you that the translation service (cypthon) is a layer of software that works between your program and your computer hardware to get your code running.. There are other translation services out there written in different langauges that achieve the same result. When you download from Python, you are actually downloading the translation service (The interpreter).

*Advanced*
Reference Article: https://faun.pub/the-right-way-to-set-up-python-on-your-mac-e923ffe8cf8e


![Python_Interpreter](https://user-images.githubusercontent.com/15992276/151667884-2efa50c7-3ca5-4f0e-940e-01f2916afece.png)

Just to come full circle, You write python code in a file, the interpreter takes it and converts it into byte code that is close to machine readable code, it then uses the CPython Virtual Machine which runs the byte code to convert it into zeroes and ones. The CVM is not an isolated component of Python. It’s just part of the Python system you’ve installed on your machine. Technically, the PVM is the last step of what is called the Python interpreter.

The whole process to run Python scripts is known as the Python Execution Mode


### How do we finally run Python code ?

The interpreter is able to run Python code in two different ways:

1. A script or module
2. A piece of code typed in an interactive session.

A widely used way to run python code is through an interactive session. To start a Python interactive session, just open a command-line or terminal and then type in python or python3 depending on your
python installation. On a Mac system, it is very straight-forward. All you need to do is open Launchpad and search for Terminal, and in the terminal, type Python and boom, it will give you an output with the Python version.

![Python_Program](https://user-images.githubusercontent.com/15992276/151667886-eafd6102-92b1-4f87-bc52-6d39353e56a0.png)

When you work interactively, every expression and statement you type in is evaluated and executed immediately:

![Python_Program](https://user-images.githubusercontent.com/15992276/151667886-eafd6102-92b1-4f87-bc52-6d39353e56a0.png)


An interactive session will allow you to test every piece of code you write, which makes it an awesome development tool and an excellent place to experiment with the language and test Python code on the fly.

To exit interactive mode, you can use one of the following options:

- quit() or exit(), which are built-in functions
- The Ctrl+Z and Enter key combination on Windows, or just Ctrl+D on Unix-like systems


### REPL (A great alternative environment to get started)

In the python world, it's easy to get overwhelmed by the different developer tools out there. We will learn each of them as we go. Right now, I want to take the path of least resistance and get you'll up and running.

![REPL](https://user-images.githubusercontent.com/15992276/151670703-552c1fff-49e2-4998-afa5-db554cd0f034.png)

You should see this dashboard when you sign in.

![Step_1](https://user-images.githubusercontent.com/15992276/151670852-1b978290-a81d-44cf-bf7d-723874e88c96.png)

Click on the + icon and choose python as your official programming language.

![step_2](https://user-images.githubusercontent.com/15992276/151670850-10bca37b-233e-426a-ba9e-fca2b54d2410.png)

Once, you see your python setup, the world is your oyster. If you have reached this step, you are officially ready to code.

![step_3](https://user-images.githubusercontent.com/15992276/151670851-e0e6a0ef-574b-419a-866a-8b1Add41abadd.png)




### Learning Python

Let's start with our first python code.

![Hello_World](https://user-images.githubusercontent.com/15992276/151672026-086d18bc-0092-47a4-9495-45665b0f9b89.png)


A function is code that performs some task and can be called by a name. Here we used the print() function
with the text "Hello, World" as input.

```python
print("Hello World")
```
The paranthesis tells Python that it is a function (print in our example) and python has to call it with the input "Hello World".
The quotation marks indicate that "Hello World" is just text and not something else.

### Mess Things up

Everybody makes mistakes—especially while programming! In case you haven’t made any mistakes yet, let’s get a head start and mess something up on purpose to see what happens. Mistakes in programs are called errors. You’ll experience two main types of errors: syntax errors and runtime errors.

### Syntax Errors

A syntax error occurs when you write code that isn’t allowed in the Python language.
Let’s create a syntax error by removing the last quotation mark from the code in the hello_world.py ﬁle that you created in the last section:

![Syntax_Error](https://user-images.githubusercontent.com/15992276/151674721-7158e7e3-cc62-40d1-bc51-c95fb683d324.png)


```python
EOL while scanning string literal.
```
There are two terms in this message that may be unfamiliar:
1. A string literal is text enclosed in quotation marks.
World" is a string literal.
"Hello,
2. EOL stands for end of line.

So, the message tells you that Python got to the end of a line while reading a string literal. String literals must be terminated with a quo-tation mark before the end of a line.

### Runtime Errors

In contrast, runtime errors only occur while a program is runnig. If you used REPT.it, the code editor might have caught the syntax error by showing you a squiggly line.

![Runtime_Error](https://user-images.githubusercontent.com/15992276/151674712-c66f644d-945f-4cac-a029-2a3c9eda538a.png)


Whenever an error occurs, Python stops executing the program and displays several lines of text called a `traceback`. The traceback shows useful information about the error

![RuntimeError_2](https://user-images.githubusercontent.com/15992276/151674713-fe426e91-6517-43c0-9abc-16b346dcc3bd.png)

Tracebacks are best read from the bottom up:

- The last line of the traceback tells you the name of the error and
the error message. In this case, a `NameError` occurred because the name `Hello` is not deﬁned anywhere.

- The second to last line shows you the code that produced the error. There’s only one line of code in `hello_world.py`, so it’s not hard to guess where the problem is. This information is more helpful for
larger files.

- The third to last line tells you the name of the ﬁle and the line number so you can go to the exact spot in your code where the error occurred.


### Create a variable


In python, `variables` are names that can be assigned a value and then used to refer to that value throughout your code

1. Variables keep values accessible: For example, you can assign the result of some time-consuming operation to a variable so that your program doesn’t have to perform the operation each time
you need to use the result.

2. Variables give values context: The number 28 could mean lots of diﬀerent things, such as the number of students in a class, the number of times a user has accessed a website, and so on. Giving the value 28 a name like `num_students` makes the meaning of the value clear.

It's important to learn how to use variables in your code, as well as some of the conventions Python programmers follow when choosing names for variables.

### The Assignment Operator

An operator is a symbol, such as +, that performs an operation on one or more values. For example, the + operator takes two numbers, one to the left of the operator and one to the right, and adds them
together. Values are assigned to variable names using a special symbol called
the assignment operator (=) . The = operator takes the value to the right of the operator and assigns it to the name on the left.



![Hello_World](https://user-images.githubusercontent.com/15992276/151675412-f5b8a1a8-5044-4bf4-b68f-d12d8775d1dd.png)



On the ﬁrst line, you create a variable named greeting and assign it the value "Hello, World" using the = operator. `print(greeting)` displays the output Hello, World because Python looks for the name greeting, ﬁnds that it’s been assigned the value "Hello,World", and replaces the variable name with its value before calling the function. `

If you hadn’t executed `greeting = "Hello, World"` before executing then you would have seen a `NameError` like you did when you tried to execute `print(Hello,World)` in the previous section.

***Note***:
Although `=` looks like the equals sign from mathematics, it has a diﬀerent meaning in Python. This distinction is important and can be a source of frustration for beginner programmers.
Just remember, whenever you see the = operator, whatever is to the right of it is being assigned to a variable on the left.


Variable names are case sensitive, so a variable named greeting is not the same as a variable named Greeting. For instance, the following
code produces a `NameError:`

```python
>>> greeting = "Hello, World"
>>> print(Greeting)
Traceback (most recent call last):
File "<stdin>", line 1, in <module>
NameError: name 'Greeting' is not defined
```

### Rules for valid variable names

Variable names can be as long or as short as you like, but there are a few rules that you must follow. Variable names may contain upper-case and lowercase letters (A–Z, a–z), digits (0–9), and underscores
(_), but they cannot begin with a digit.

For example, each of the following is a valid Python variable name:

- string1
- _a1p4a
- list_of_names (Most preferred way)

The following aren’t valid variable names because they start with a
digit:

- 9lives
- 99_balloons
- 2beOrNot2Be1

Just because a variable name is valid doesn’t necessarily mean that it’s a good name. Choosing a good name for a variable can be surprisingly diﬃcult. For-tunately, there are some guidelines that you can follow to help you choose better names.

### Descriptive Names Are Better Than Short Names
Descriptive variable names are essential, especially for complex programs. Writing descriptive names often requires using multiple words. Don’t be afraid to use long variable names.

In the following example, the value 3600 is assigned to the variable s:

```python
s = 3600
```

The name s is totally ambiguous. Using a full word makes it a lot easier to understand what the code means:
```python
seconds = 3600
```

seconds is a better name than s because it provides more context. But it still doesn’t convey the full meaning of the code. Is 3600 the number of seconds it takes for a process to ﬁnish, or is it the length of a movie? There’s no way to tell.

The following name leaves no doubt about what the code means:

```python
seconds_per_hour = 3600
```

When you read the above code, there’s no question that 3600 is the number of seconds in an hour. seconds_per_hour takes longer to type than both the single letter s and the word seconds, but the payoﬀ in
clarity is massive.

Although naming variables descriptively means using longer variable names, you should avoid using excessively long names. A good rule of thumb is to limit variable names to three or four words maximum.

***Note***: In Python, however, it’s common to write variable names in lower_case_with_underscores. In this system, you leave every letter in lowercase and separate each word with an underscore. For
instance, num_students and list_of_names are written in lower_case_-with_underscores.



### Bored ?

If at this point, you are bored and wish to motivate yourself, watch this video from David Malan, a professor at Harvard.

https://www.youtube.com/watch?v=ZEQh45W_UDo

This will give you a glimpse into what's coming next even if you don't understand all of it yet.


### Variable Inspection

Before, we dive deep, let's learn to inspect values in the terminal.

```python
>>> greeting = "Hello, World"
>>> greeting
'Hello, World'
```
When you press `Enter` after typing greeting a second time, Python prints the string literal assigned to greeting even though you didn’t use the print() function. This is called variable inspection.

Now print the string assigned to greeting using the print() function:

```python
>>> print(greeting)
Hello, World
```

Are you seeing the difference?
When you type the variable name greeting and press Enter , Python prints the value assigned to the variable as it appears in your code.

You assigned the string literal "Hello, World" to greeting, which is why 'Hello, World' is displayed with quotation marks.

On the other hand, `print()` displays a more human-readable representation of the variable’s value which, for string literals, means displaying the text without quotation marks.

```python
>>> x = 2
>>> x
2
>>> print(x)
2
```
Here, you assign the number 2 to x. Both using print(x) and inspecting x display output without quotation marks because 2 is a number and not text. In most cases, though, variable inspection gives you more
useful information than `print()`.

```python
>>> x = 2
>>> y = "2"
>>> print(x)
2
>>> print(y)
2

```
However, inspecting x and y shows the diﬀerence between each vari-
able’s value:

```python
>>> x
2
>>> y
'2'

```

The key takeaway here is that `print()` displays a readable representation of a variable’s value, while variable inspection displays the value as it appears in the code.
Keep in mind that variable inspection only works in the interactive window (More on this later).


### String and String Methods (A gentle Introduction)


Strings are one of the fundamental Python data types. The term data type refers to what kind of data a value represents. Strings are used to represent text.

We say that strings are a *fundamental* data type because they can’t be broken down into smaller values of a diﬀerent type. Not all data types are fundamental. You’ll learn about compound data types later.

The string data type has a special abbreviated name in Python: ```python str```. You can see this by using `type()`, which is a function used to determine the data type of a given value.

Type the following into IDLE’s interactive window:
```python
>>> type("Hello, World")
<class 'str'>
```

The output <class 'str'> indicates that the value `"Hello, World"` is an instance of the `str` data type. That is, `"Hello, World"` is a string.


***Note:*** For now, you can think of the word ``class`` as a synonym for data type, although it actually refers to something more speciﬁc (More on this later).

`type()` also works for values that have been assigned to a variable:

```python
>>> phrase = "Hello, World"
>>> type(phrase)
<class 'str'>

```

### Three important things to remember about strings.

1. Strings contain individual letters or symbols called characters.
2. Strings have a length, deﬁned as the number of characters the string contains.
3. Characters in a string appear in a sequence, which means that each character has a numbered position in the string.
As you’ve already seen, you can create a string by surrounding some text with quotation marks:

```python
string1 = 'Hello, World'
string2 = "1234"
```
You can use either single quotes (string1) or double quotes (string2) to create a string as long as you use the same type at the beginning and end of the string.

***Important to note:***

The quotes surrounding a string are called `delimiters` because they tell Python where a string begins and where it ends. When one type of quotes is used as the delimiter, the other type can be used inside the string:

```python
string3 = "We're #1!"
string4 = 'I said, "Put it over by the llama."'
```

After Python reads the ﬁrst delimiter, it considers all the characters after it part of the string until it reaches a second matching delimiter. This is why you can use a single quote in a string delimited by double
quotes, and vice versa. If you try to use double quotes inside a string delimited by double
quotes, you’ll get an error:

```python
>>> text = "She said, "What time is it?""
File "<stdin>", line 1
text = "She said, "What time is it?""
^
SyntaxError: invalid syntax
```


Python throws a `SyntaxError` because it thinks the string ends after the second ", and it doesn’t know how to interpret the rest of the line. If you need to include a quotation mark that matches the delimiter in-
side a string, then you can escape the character using a backslash:
```python
>>> text = "She said, "What time is it?""
>>> print(text)
She said, "What time is it?"

```
### Last, but not least

The number of characters contained in a string, including spaces, is called the length of the string. For example, the string ```"abc"``` has a length of 3, and the string ```"Don't Panic"``` has a length of 11.
Python has a built-in len() function that you can use to determine the length of a string. To see how it works, type the following into IDLE’s interactive window:

```python
>>> len("abc")
3
You can also use len() to get the length of a string that’s assigned to a
variable:
>>> letters = "abc"
>>> len(letters)
3
```

First, you assign the string ```"abc"``` to the variable letters. Then you use `len()` to get the length of letters, which is 3.



