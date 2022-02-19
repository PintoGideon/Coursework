### Strings are Immutable

Strings are immutable, which means that you can’t change
them once you’ve created them. For instance, see what happens when you try to assign a new letter to one particular character of a string:

```python

>>> word = "goal"
>>> word[0] = "f"
Traceback (most recent call last):
File "<pyshell#16>", line 1, in <module>
word[0] = "f"
TypeError: 'str' object does not support item assignment

```
Python throws a TypeError and tells you that str objects don’t support item assignment.

If you want to alter a string, then you must create an entirely new string. To change the string "goal" to the string "foal", you can use a string slice to concatenate the letter "f" with everything but the ﬁrst
letter of the word "goal":

```python
>>> word = "goal"
>>> word = "f" + word[1:]
>>> word
'foal'
```

### Manipulate Strings with Methods

Strings come bundled with special functions called string methods that you can use to work with and manipulate strings. There are numerous string methods available, but we’ll focus on some of the most commonly used ones.

### Converting String Case

To convert a string to all lowercase letters, you use the string’s .lower() method. This is done by tacking .lower() onto the end of the string
itself:

```python
>>> "Jean-Luc Picard".lower()
'jean-luc picard'

```

The dot (.) tells Python that what follows is the name of a method—the `lower()` method in this case.

String methods don’t just work on string literals. You can also use `.lower()` on a string assigned to a variable:

```python
>>> name.upper()
'JEAN-LUC PICARD'
```

Compare the .upper() and .lower() string methods to the len() function you saw in the last section. Aside from the diﬀerent results of these functions, the important distinction here is how they’re used.
`len()` is a stand-alone function. If you want to determine the length of the name string, then you call the len() function directly:

```python
>>> len(name)
15
```

### Removing Whitespace from a String

cludes things like spaces and line feeds, which are special characters that move output to a new line.
Sometimes you need to remove whitespace from the beginning or end of a string. This is especially useful when working with strings that come from user input, which may include extra whitespace characters by accident.

There are three string methods that you can use to remove whitespace
from a string:
1. rstrip()
2. lstrip()
3. .strip()


`.rstrip()` removes whitespace from the right side of a string:

```python
>>> name = "Jean-Luc Picard
"
>>> name
'Jean-Luc Picard
'
>>> name.rstrip()
'Jean-Luc Picard'
```

You use .rstrip() to remove trailing spaces from the right-hand side of the string. This returns the new string "Jean-Luc Picard", which no longer has the spaces at the end. works just like .rstrip(), except that it removes whitespace from the left-hand side of the string:

To remove whitespace from both the left and the right sides of the string at the same time, use `.strip()`:

```python
>>> name = "
Jean-Luc Picard
"
>>> name
'
Jean-Luc Picard
'
>>> name.strip()
'Jean-Luc Picard'
```


It’s important to note that none of .rstrip(), .lstrip(), or .strip() re-moves whitespace from the middle of the string. In each of the previous examples, the space between “Jean-Luc” and “Picard” was always
preserved.

### Determine If a String Starts or Ends With a Particular String

When you work with text, sometimes you need to determine if a given string starts with or ends with certain characters. You can use two string methods to solve this problem: `.startswith()` and `.endswith()`.

Let’s look at an example. Consider the string "Enterprise". Here’s how you use .startswith() to determine if the string starts with the letters
e and n:

```python
>>> starship = "Enterprise"
>>> starship.startswith("en")
False
```

You tell .startswith() which characters to search for by providing a string containing those characters. So, to determine if "Enterprise" starts with the letters e and n, you call .startswith("en"). This returns False. Why do you think that is? If you guessed that .startswith("en") returns False because "Enterprise" starts with a capital E, then you’re absolutely right! The `.startswith()` method is case sensitive. To get `.startswith()` to
return True, you need to provide it with the string "En":

```python
>>> starship.startswith("En")
True
```

You can use `.endswith()` to determine if a string ends with certain characters:

```python
>>> starship.endswith("rise")
True
```
Just like `.startswith()`, the `.endswith()` method is case sensitive:

```python
>>> starship.endswith("risE")
False
```

### String Methods and Immutability

Most string methods that alter a string, like `.upper()` and `.lower()`, actually return copies of the original string with the appropriate modiﬁcations.

Try this out in IDLE’s interactive window:

```python
>>> name = "Picard"
>>> name.upper()
'PICARD'
>>> name
'Picard'
```
When you call name.upper(), nothing about name actually changes. If you need to keep the result, then you need to assign it to a variable:

```python
>>> name = "Picard"
>>> name = name.upper()
>>> name
'PICARD'
```

`name.upper()` return a new string "PICARD", which is reassigned to the `name` variable. This overrides the original string "Picard" that you ﬁrst assigned to `name`.


### Use IDLE to Discover Additional String Methods

Strings have lots of methods associated with them, and the methods introduced in this section barely scratch the surface. IDLE can help you ﬁnd new string methods. To see how, ﬁrst assign a string literal to a variable in the interactive window:

```python
>>> starship = "Enterprise"
```

Next, type starship followed by a period, but do not hit `Enter` . You should see the following in the interactive window:

```python
>>> starship.

```
Now wait for a couple of seconds. IDLE displays a list of every string method, which you can scroll through using the arrow keys.
A related shortcut in IDLE is the ability to use Tab to automatically ﬁll in text without having to type long names. For instance, if you type only starship.u and hit Tab , then IDLE automatically ﬁlls in starship.upper because only one method that begins with a u belongs to
starship.
This even works with variable names. Try typing just the ﬁrst few letters of starship and pressing Tab . If you haven’t deﬁned any other names that share those ﬁrst letters, then IDLE completes the name starship for you.


### Interact with User Input

In this section, you’ll learn how to get some input from a user with input(). You’ll write a program that asks a user to input some text and then displays that text back to them in uppercase.
Enter the following into IDLE’s interactive window:

```python
>>> input()
```
When you press Enter , it looks like nothing happens. The cursor moves to a new line, but a new `>>>` doesn’t appear. Python is waiting for you to enter something!

```python
>>> input()
Hello there!
'Hello there!'
>>>
```


To make input() a bit more user-friendly, you can give it a prompt to display to the user. The prompt is just a string that you put between the parentheses of input(). It can be anything you want: a word, a
symbol, a phrase—anything that is a valid Python string.

```python
prompt = "Hey, what's up? "
user_input = input(prompt)
print("You said: " + user_input)

```
The single space at the end of the string "Hey, what's up? " makes sure
that when the user starts to type, the text is separated from the prompt
with a space. When the user types a response and presses Enter , their
response is assigned to the user_input variable.


```md

Hey, what's up? The Lord is my rock and my fortress and my deliverer.

You said: The Lord is my rock and my fortress and my deliverer,

```
#### Type Conversions

The `TypeError` in the python highlight a common problem when applying user input to an operation that requires a number and not a string: type mismatches.


```python
num = input("Enter a number to be doubled: ")
doubled_num = num * 2
print(doubled_num)

```
If you entered the number 2 at the prompt, then you would expect the
output to be 4. But in this case, you would get 22. Remember, `input()`
always returns a string, so if you input 2, then num is assigned the string "2", not the integer 2. Therefore, the expression `num * 2` returns the string "2" concatenated with itself, which is "22".


To perform arithmetic on numbers contained in a string, you must
ﬁrst convert them from a string type to a number type. There are two
functions that you can use to do this: `int()` and `float()`.
`int()` stands for integer and converts objects into whole numbers,
whereas `float()` stands for *floating-point number* and converts objects into numbers with decimal points.

```python
>>> int("12")
12

>>> float("12")
12.0

```
Notice how float() adds a decimal point to the number. Floating-point numbers always have at least one decimal place of precision. For
this reason, you can’t change a string that looks like a floating-point
number into an integer because you would lose everything after the
decimal point.

```python
>>> int("12.0")
Traceback (most recent call last):
File "<stdin>", line 1, in <module>
ValueError: invalid literal for int() with base 10: '12.0'
```

### Putting Type Conversions together


```python

num= input("Enter a number to be doubled: ")
doubled_num=num*2
print(doubled_num)
```
The issue is on the line
and 2 is an integer.

You can ﬁx the problem by passing num to either int() or float(). Since
the prompts asks the user to input a number, and not speciﬁcally an integer, let’s convert num to a floating-point number:

```python
num = input("Enter a number to be doubled: ")
doubled_num = float(num) * 2
print(doubled_num)
```

### Converting numbers to strings

```python

>>> num_pancakes = 10
>>> "I am going to eat " + num_pancakes + " pancakes."
Traceback (most recent call last):
File "<stdin>", line 1, in <module>
TypeError: can only concatenate str (not "int") to str

```
Since num_pancakes is a number, Python can’t concatenate it with the
string "I'm going to eat". To build the string, you need to convert
num_pancakes to a string using str():

```python
>>> num_pancakes = 10
>>> "I am going to eat " + str(num_pancakes) + " pancakes."
'I am going to eat 10 pancakes.'
```

str() can even handle arithmetic expressions:

```python
>>> total_pancakes = 10
>>> pancakes_eaten = 5
>>> "Only " + str(total_pancakes - pancakes_eaten) + " pancakes left."
'Only 5 pancakes left.'
```

### Streamline your print statements

Suppose you have a string, name = "Gideon", and two integers, heads = 2
and arms = 3. You want to display them in the string "Gideon has
2 heads and 3 arms". This is called *string interpolation*, which is
just a fancy way of saying that you want to insert some variables into
speciﬁc locations in a string.

```python
>>> name + " has " + str(heads) + " heads and " + str(arms) + " arms"

'Gideon has 2 heads and 3 arms'

```
This code isn’t the prettiest, and keeping track of what goes inside or
outside the quotes can be tough. Fortunately, there’s another way of
interpolating strings: formatted string literals, more commonly
known as f-strings. The easiest way to understand f-strings is to see them in action.

```python
f"{name} has {heads} heads and {arms} arms"

'Gideon has 2 heads and 3 arms'

```

1. The string literal starts with the letter f before the opening quota-
tion mark.

2. Variable names surrounded by curly braces ({}) are replaced by
their corresponding values without using str().

```python
>>> n = 3
>>> m = 4
>>> f"{n} times {m} is {n*m}"
'3 times 4 is 12'
```

### Functions and Loops

Functions are the building blocks of almost every Python program.
They’re where the real action takes place!

You’ve already seen how to use several functions, including `print()`,
`len()`, and `round()`. These are all built-in functions because they
come built into the Python language itself. You can also create user-
defined functions that perform speciﬁc tasks.

### Functions are Values

One of the most important properties of a function in Python is that
functions are values and can be assigned to a variable.

In IDLE’s interactive window, inspect the name len by typing the fol-
lowing in at the prompt:


```python
>>> len
<built in function len>

```
Python tells you that `len` is a built-in function. Just like integer values have a type called `int`, and strings have a type `str`, function values also have a type:

```python
>>> type(len)
<class 'builtin_function_or_method'>

```
The name `len`, though, can be assigned to a diﬀerent value, if you like:

```python
>>> len = "I'm not the len you're looking for."
>>> len
"I'm not the len you're looking for."

```

Now `len` has a string value, and you can verify that the type is str with
`type()`:

```python
>>> type(len)
<class 'str'>
```

Even though you can change the value of the name len, it’s usually a
bad idea to do so. Changing the value of len can make your code con-
fusing because it’s easy to mistake the new len for the built-in function.
The same goes for any built-in function.

### How Python executes Functions

The ﬁrst thing to notice is that you can’t execute a function by just
typing its name. You must `call` the function to tell Python to actually
execute it.
```python
>>> # Typing just the name doesn't execute the function.
>>> # IDLE inspects the variable as usual.
>>> len
<built-in function len>

>>> # Use parentheses to call the function.
>>> len()
Traceback (most recent call last):
File "<pyshell#3>", line 1, in <module>
len()
TypeError: len() takes exactly one argument (0 given)


```

In this example, Python raises a TypeError when `len()` is called because `len()` expects an argument.

An argument is a value that gets passed to the function as input.
Some functions can be called with no arguments, and some can take
as many arguments as you like. len() requires exactly one argument.

When a function is done executing, it returns a value as output. The
return value usually — but not always — depends on the values of any
arguments passed to the function.

1. The function is called, and any arguments are passed to the func-
tion as input.

2. The function executes, and some action is performed with the
arguments.

3. The function returns, and the original function call is replaced
with the return value.


```python
num_letters = len("four")
```

First, `len()` is called with the argument "four". The length of the string is calculated, which is the number 4. Then `len()` returns the
number 4 and replaces the function call with the value.
"four"
You can imagine that, after the function executes, the line of code
looks like this:

```python
>>> num_letters = 4
```

Then Python assigns the value 4 to `num_letters` and continues executing any remaining lines of code in the program.

### Side Effects

You’ve learned how to call a function and that they return a value when
they are done executing. Sometimes, though, functions do more than
just return a value.

When a function changes or aﬀects something external to the func-
tion itself, it is said to have a side e ect. You have already seen one
function with a side eﬀect: `print()`.

When you call `print()` with a string argument, the string is displayed
in the Python shell as text. But print() doesn’t return any text as a
value.

To see what `print()` returns, you can assign the return value of `print()`
to a variable:

```python
>>> return_value = print("What do I return?")
What do I return?
>>> return_value
>>>
```
When you assign `print("What do I return?")` to `return_value`, the string "What do I return?" is displayed. However, when you inspect the value of return_value, nothing is shown.

```python
type(return_value)
<class 'NoneType'>
>>> print(return_value)
None
```

When you call `print()`, the text that gets displayed is not the return
value. It’s a side eﬀect of `print()`.

### Write your own functions

As you write more complex programs, you may ﬁnd that you need to
repeatedly use the same few lines of code. For instance, you might
need to calculate the same formula with diﬀerent values several times
in your code.
You might be tempted to copy and paste similar code to other parts of
your program and modify it as needed, but this is usually a bad idea!
If you ﬁnd a mistake in some code that’s been copied and pasted all
over the place, you’ll have to apply the ﬁx everywhere the code was
copied. That’s a lot of work!

### The Anatomy of a function

1. The `function signature` deﬁnes the name of the function and any inputs it expects.

2. The `function body` contains the code that runs every time the
function is used.


Let’s start by writing a function that takes two numbers as input and
returns their product. Here’s what this function might look like, with
the signature, body, and return statement identiﬁed with comments:

```python
def multiply(x,y): # function signature
    # Function body
    product=x*y
    return product
```

***Important***:

To deﬁne a function in IDLE’s interactive window, you need to
press `Enter` twice after the line containing return in order for
Python to register the function:

```python
>>> def multiply(x, y):
...product = x * y
...return product
... # <--- Hit Enter a second time here
>>>

```

### The Function Signature

The ﬁrst line of code in a function is called the *function signature*.
It always starts with the `def` keyword, which is short for “deﬁne.”

```python
def multiply(x,y):
```
The function signature has four parts:
1. The def keyword
2. The function name, multiply
3. The parameter list, (x,y)
4. A colon (:) at the end of the line

When Python reads a line beginning with the def keyword, it creates
a new function. The function is assigned to a variable with the same
name as the function name.

The *parameter list* is a list of parameter names surrounded by open-
ing and closing parentheses. It deﬁnes the function’s expected inputs.
(x, y) is the parameter list for the multiply function. It creates two
parameters, x and y.