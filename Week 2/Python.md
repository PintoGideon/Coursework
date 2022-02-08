### Setting up VS Code

Visual Studio Code (or VS Code) is a free and open source graphical code editor. VS Code offers plenty of extensions to customize your experience. We’ll be using the powerful Python extension to edit our code because it’s jam-packed with helpful features.

### Installation

Download Visual Studio Code: https://code.visualstudio.com/download
and the 
Python Extension for Visual Studio Code: https://marketplace.visualstudio.com/items?itemName=ms-python.python

### Advantages

You’ll want to use a code editor for your Python projects as your projects grow in scope. It’ll allow you to easily manage projects with multiple files and modules. The Python extension also offers a built-in REPL, so that we can quickly and easily test out snippets of code and instantly see the results.

Code editors also offer syntax highlighting, syntax checking, auto-completion, and more.

### Creating a Virtual Environment
A Virtual Environment in Python is a self-contained directory that contains a Python installation for a particular version of the language. It’s a very useful way to make sure that we’re using the right Python version when we’re working on a particular project.

Let’s create a project directory and a Python Virtual Environment

Open a terminal window. Type the following.
(Do not type the `$` character, that signifies a prompt.)

```shell
$ cd
$ mkdir pythonworkshop
$ cd pythonworkshop
$ python3.9 -m venv env
$ source env/bin/activate

```
***Note***: `source env/bin/activate` is how you activate your virtual environment on Mac or Linux. You’ll want to do that each time you enter this Python project directory from a new shell.

```shell
(env) $
```


### Checking VS Code

```shell
code --version

1.32.3
a3db5be9b5c6ba46bb7555ec5d60178ecc2eaae4
x64
```

### Opening your First Project

On Mac OS, follow these steps in you terminal application, or follow the steps manually in the program you use to manage files.

```shell
# change to our home directory
$ cd

# enter the directory of the pyworkshop folder from the last step
$ cd pyworkshop

# activate the virtual environment
source env/bin/activate

# make a new empty python file called project.py
(env) $ touch project.py

# Open VS Code using the current directory as a project.

(env) $ code .

```

### Keyboard Shortcuts
To get started with VS Code, you only need to remember two keyboard shortcuts.

1. Show Command Palette
`⌘⇧P (command + shift + P)` on Mac OS.

The command palette lets you search and run any of the commands available within VS Code. If you don’t know how to do something, the command palette will usually point you in the right direction.

The command palette is how you’ll navigate VS Code.

2. Quick Open, Go to File
Open Quick Open with `Ctrl+P` on Windows and Linux, and `⌘P(command + P)` on Mac OS.
Quick open is how you’ll navigate your codebase and files.

***To dismiss either dialog, press the Escape key. Write these two shortcuts down, because we’ll be using them frequently for the rest of the course.***


### Working with Python and VS code

Once we open our first Python file in VS Code, we’ll see some configuration pop-ups. For the time being, *don’t* dismiss them.

### Configuring VS Code for Python

If you haven’t created a `project.py` file in the `pyworkshop` directory, now is the time to do so. You can make a new file (Ctrl+N or ⌘P) and then save it (Ctrl+S or ⌘S).

Now that you’ve learned the necessary keyboard shortcuts, use Quick Open with Ctrl+P or ⌘P to open the project.py file.

***Info:*** If you haven’t installed the Python extension at this point, you’ll get a pop-up recommending you install it for this type of file. Please install it now, and reload VS Code when prompted to load the extension.

### Configuring the Interpreter

Many operating systems include Python, but unfortunately it’s usually a few versions behind.
We never want to use Python2 for new Python projects, and we want to make sure we select the latest version of Python3 that we installed in the pre-requisites.

Luckily, VS Code is smart. If you launch it from a directory with an activated virtual environment, it’ll automatically pick up the correct interpreter. You can always see what your interpreter is set to on the left side of the status bar at the bottom of the window.


![interpreter](https://user-images.githubusercontent.com/15992276/152420582-408b2c2f-e89a-4b4a-a8a8-3ed08f8a2679.png)


Per the VS Code documentation, linting highlights syntactical and stylistic problems in your Python source code. A linter will give you code hints about a variety of different types of problems. For example, when you have subtle errors in your code, like trying to use a variable you haven’t defined yet. A linter will also show you when you’re not following Python style convention called PEP8. PEP8 is a set of defined rules for how Python code should look. We’ll cover it in more depth later, but what you need to know right now is that PEP8 warnings are not syntax errors. If your code doesn’t adhere to the PEP8 standard, it will still run.

By default the linter will run every time you save a file, so it’s good practice to save often with (Ctrl+S or ⌘S).

![linter](https://user-images.githubusercontent.com/15992276/152420581-52794e51-60d8-454e-b3a9-8c6b1e95456e.png)

Let’s go ahead and click install on the Linter popup.

***Note:*** If you accidentally dismissed the popup, open the command palette and search for Python: Select Linter, then select pylint. The popup will now reappear, and you can hit install. Expand this section for more details.

### Open The REPL

To start the REPL in VS code, open the command palette and search for and select “Start REPL”. The advantage to starting the REPL from inside VS Code is that it respects the environment you already set up, that is the version of Python you chose earlier.

![REP:](https://user-images.githubusercontent.com/15992276/152420580-7bc00fea-afa1-410f-bcc8-343cfc61b782.png)


***Note***: If you’d like to start the REPL from the command line outside of the editor, type python in your shell,

Running this command should bring up a new pane at the bottom of your editor that you can type into. A great feature of the REPL is that we can instantly see the result of commands being run.

### More about REPL's.

Let’s get familiar with the REPL.

***comments start with #. They will be ignored.***

`>>>` - this is the prompt. In example code, lines starting with `>>>` means they are input
lines that don’t start with either of these are output that was produced by running input from the prompt
by typing these line of code at the `>>>` prompt, and press enter after each line.

```python
# My REPL. Don't copy the >>> symbols, that means the code was entered
# into the prompt.
#
# If the line does not start with >>>, that means it is output,
# not input
>>> name = "Gideon"
>>> name
'Gideon'
```
In the REPL, we can see the value of any variable just by entering it into the prompt.

You can copy and paste code into the REPL, even multiple lines of code at once. Copy the three lines below and paste them into your REPL. What’s the result?


***Gideon, why have we wasted time setting up so many different environments? Well, a lot of people waste too much time in the setup and setting the right environment. Why not get the boring part out of the way, and just focus on the learning. There are a lot of internet articles out there and I want to funnel all the content to a battle tested environment which is more closed to a real-world scenario"***


### Running Code

 We’ll mostly be working with Python program files in the course with the occasional use of REPL.

### Creating Python Files with the *.py extension
You know a file is a Python program when it ends with a `.py` extension.

To create a new file in VS Code, and `⌘N (command + N)` on Mac OS.

This will open a new file. Next, save the file with a `.py` extension. Create a new simple Python program in a file called `hello.py` in your pyworkshop directory with the following contents:

```python
# In file: hello.py
greetings = ["Hello", "Bonjour", "Hola"]

for greeting in greetings:
    print(f"{greeting}, World!")


```

### Opening The VS Code Terminal Window
Next, you’ll need to open your terminal if you don’t have it open already. The quick keyboard shortcut to do that is Ctrl - `

If you already had your Python REPL open, you’ll need to select a terminal with a shell in it (generally, the one labeled with 1:).

![zsh](https://user-images.githubusercontent.com/15992276/152420578-530674da-e1a4-4156-ba0d-040e3609edaf.png)
![vs_code_python](https://user-images.githubusercontent.com/15992276/152420579-df8fc726-9308-445c-96ea-ebe0a5d0ac31.png)

### Running The File
Once you’ve opened your hello.py file and selected your new terminal window, open the VS Code command palette.

***Note*** Open the command palette with Ctrl+Shift+P on Windows and Linux, and ⌘⇧P (command + shift + P) on Mac OS.
Select Python: Run Python File in Terminal


You should see:
```python
Hello, World!
Bonjour, World!
Hola, World!
```

If you have gotten this far, I am very optimistic for your journey ahead. This is hard stuff.:tada:


### Anatomy of a python program

Please try to type this program out line by line and see if 
you get the results by running the python file. 

![python_program](https://user-images.githubusercontent.com/15992276/152905420-19a5315d-77bd-460c-b38a-6c37385d0c71.png)


Helpful information about the program can be encapsulated in a 
comment. The comment is seperated by triple quotes
"""

The first thing we're doing is importing the popular requests library. 

```python
import requests
```

Next, we define the URL for the GitHub search API, which we found in the documentation for that endpoint in a variable called GITHUB_API_URL. This variable is named in all upper case because it’s a constant. A value that we don’t expect to change over the course of our program.


```python

GITHUB_API_URL = "https://api.github.com/search/repositories"

```

First, the code in the main method will run. This code defines three different languages we’d like to see results for.

```python
languages = ["python", "javascript", "ruby"]
```
Then calls the `repos_with_most_stars` method with that language list, and gets back a list of results


```python
results = repos_with_most_stars(languages)

```
Let’s jump to the `repos_with_most_stars` function. We know it’s a function because of the `def` keyword, followed by a function name, parameters – both required and optional in parenthesis, and finally, a colon :. It accepts a list of languages to sort by, as well as some optional parameters for how we want to sort the list. By default, we sort it by the number of stars the repo has, in descending order.


```python
def repos_with_most_stars(languages, sort="stars", order="desc"):

```
Next, we need to create a query string that this particular API understands. We do that in the `create_query` function. This function takes the languages as a required parameter, and the minimum number of stars we’d like to query for as an optional parameter.

```python
def create_query(languages, min_stars=50000):

```

In this function, we create a query string that looks like this `stars:>50000 language:python language:javascript language:ruby`. These parameters of this query string are defined by the expectations of the API that we’re working with. We return this value.

Since the query is a little confusing, there’s a comment in the code that explains what it does. The comment starts with #.
Back in the `repos_with_most_stars` function, we use our query string as part of the parameters that we’ll be passing in to the API, along with the URL that we’ll be using.

We declare them in a dictionary called params, like this:

```python
# looks like: q=stars:>50000+language:python+language:javascript+language:ruby+&sort=stars&order=desc'
params = {"q": query, "sort": sort, "order": order}

```

These params map to part of a URL that will look like this: `q=stars:>50000+language:python+language:javascript+language:ruby+&sort=stars&order=desc`
Next, we use these parameters as well as the URL defined in `GITHUB_API_URL` to call the API using the requests library.

```python
    response = requests.get("https://api.github.com/search/repositories", params=params)
```
We’re requesting the data at this URL: `https://api.github.com/search/repositories?q=stars:>50000+language:python+language:javascript+language:ruby+&sort=stars&order=desc`

We’re using the requests library because it allows us to quickly and easily work with the data returned from an API.
Next, we quickly check the HTTP status code to make sure that it was 200. If it wasn’t, that means that something went wrong with our request and we’ll want to throw an exception to quit our program.

```python
 if status_code != 200:
        raise RuntimeError(f"An error occurred. HTTP Code: {status_code}.")

```
If everything went OK, we get the JSON from the response as a Python dictionary, using response.json(), next, we return the data in the “items” key back to the main method. In this case, we don’t care about the additional data that the API returned.

```python
response_json = response.json()
  return response_json["items"]

```

Next, back in the main method, we go through each result, and print out a line with the name of the repo, the language, and the amount of stars it has.

```python
 print(f"-> {name} is a {language} repo with {stars} stars.")
```

### Results

![python](https://user-images.githubusercontent.com/15992276/152905566-2dc1b81f-6dbe-4188-b3aa-32129e37b3be.png)


### Continuing our Basics in Strings

You know what a string is and how to describe string literals
in your code. 

1. String Concatenation
You can combine, or concatenate, two strings using the + operator:

```python
>>> string1 = "abra"
>>> string2 = "cadabra"
>>> magic_string = string1 + string2
>>> magic_string
'abracadabra'
```
In this example, the string concatenation occurs on the third line. You concatenate string1 and string2 using +, and then you assign the result to the variable magic_string. Notice that the two strings are joined without any whitespace between them.
You can use string concatenation to join two related strings, such as joining a ﬁrst name and a last name into a full name:

```python
>>> first_name = "Gideon"
>>> last_name = "Pinto"
>>> full_name = first_name + " " + last_name
>>> full_name
'Gideon Pinto'
```

Here, you use string concatenation twice on the same line. First, you concatenate first_name with `" "` to ensure a space appears after the ﬁrst name in the ﬁnal string. This produces the string "Gideon ", which you then concatenate with last_name to produce the full name "Gideon Pinto".

2. String Indexing
Each character in a string has a numbered position called an *index*. You can access the character at the nth position by putting the number n between two square brackets ([]) immediately after the string:

```python
>>> flavor = "fig pie"
>>> flavor[1]
'i'

```

flavor[1] returns the character at position 1 in "fig pie", which is `i`.

Wait. Isn’t `f` the ﬁrst character of "fig pie"?
In Python—and in most other programming languages—counting al-
ways starts at zero. To get the character at the beginning of a string, you need to access the character at position 0:

```python
>>> flavor[0]
'f'
```

The following ﬁgure shows the index for each character of the string
"fig pie":

![off_by_one](https://user-images.githubusercontent.com/15992276/152906901-a3d2fde5-f5fa-4709-ac13-330967c5c2fc.png)

Forgetting that counting starts with zero and trying to access
the ﬁrst character in a string with the index 1 results in an o -
by-one error. Oﬀ-by-one errors are a common source of frustration for beginning and experienced programmers alike!
If you try to access an index beyond the end of a string, then Python raises an ```IndexError:```

```python
>>> flavor[9]
Traceback (most recent call last):
File "<pyshell#4>", line 1, in <module>
flavor[9]
IndexError: string index out of range
```

The largest index in a string is always one less than the string’s length.
Since "fig pie" has a length of seven, the largest index allowed is 6.

Strings also support negative indices:

```python
>>> flavor[-1]
'e'
```

The last character in a string has index -1, which for "fig pie" is the letter e. The second to last character i has index -2, and so on.

Just like with positive indices, Python raises an IndexError if you try to access a negative index less than the index of the ﬁrst character in the string:

![negative](https://user-images.githubusercontent.com/15992276/152918294-29a82d42-f71b-42bd-987d-ff1daa06b1c8.png)

```python
>>> flavor[-10]
Traceback (most recent call last):
File "<pyshell#5>", line 1, in <module>
flavor[-10]
IndexError: string index out of range
```
Negative indices may not seem useful at ﬁrst, but sometimes they’re a better choice than a positive index.

For example, suppose a string input by a user is assigned to the variable user_input. If you need to get the last character of the string, how do you know what index to use?

One way to get the last character of a string is to calculate the ﬁnal index using len():

```python
final_index = len(user_input) - 1
last_character = user_input[final_index]
```

***Python has a built-in len() function that you can use to determine the length of a string***

```python
>>> letters = "abc"
>>> len(letters)
3
```

Getting the ﬁnal character with the index -1 takes less typing and
doesn’t require an intermediate step to calculate the ﬁnal index:

```python
last_character = user_input[-1]
```

### String Slicing

string "fig pie". You could access each character by index and con-catenate them like this:

```python
>>> first_three_letters = flavor[0] + flavor[1] + flavor[2]
>>> first_three_letters
'fig

```

If you need more than just the ﬁrst few letters of a string, then getting each character individually and concatenating them together is clumsy and long-winded. Fortunately, Python provides a way to do this with much less typing.
You can extract a portion of a string, called a substring, by inserting a colon between two index numbers set inside square brackets like
this:

```python
>>> flavor = "fig pie"
>>> flavor[0:3]
'fig'
```

flavor, starting with the character at index 0 and going up to but not including the character at index 3. The [0:3] part of flavor[0:3] is called a *slice*.


String slices can be confusing because the substring returned by
the slice includes the character whose index is the ﬁrst number but doesn’t include the character whose index is the second number.

To remember how slicing works, you can think of a string as a sequence of square slots. The left and right boundaries of each slot are numbered sequentially from zero up to the length of the string, and each slot is ﬁlled with a character in the string.

![slice](https://user-images.githubusercontent.com/15992276/152917390-f98cd468-5346-436f-a7e9-4e571bf37d6f.png)

So, for "fig pie", the slice [0:3] returns the string "fig", and the slice [3:7] returns the string " pie".
If you omit the ﬁrst index in a slice, then Python assumes you want to start at index 0:

```python
>>> flavor[:3]
'fig'
```

The slice [:3] is equivalent to the slice [0:3], so flavor[:3] returns the ﬁrst three characters in the string "fig pie".
Similarly, if you omit the second index in the slice, then Python assumes you want to return the substring that begins with the character whose index is the ﬁrst number in the slice and ends with the last character in the string:

```python
>>> flavor[3:]
' pie'
```
For "fig pie", the slice [3:] is equivalent to the slice [3:7]. Since the character at index 3 is a space, flavor[3:9] returns the substring that starts with the space and ends with the last letter: " pie".

If you omit both the ﬁrst and second numbers in a slice, you get a
string that starts with the character at index 0 and ends with the last character. In other words, omitting both numbers in a slice returns the entire string:

```python
>>> flavor[:]
'fig pie
```

It’s important to note that, unlike with string indexing, Python won’t raise an IndexError when you try to slice between boundaries that fall outside the beginning or ending boundaries of a string:

```python
>>> flavor[:14]
'fig pie'
>>> flavor[13:15]
''
```


In this example, the ﬁrst line gets the slice from the beginning of the string up to but not including the fourteenth character. The string assigned to flavor has a length of nine, so you might expect Python to throw an error. Instead, it ignores any nonexistent indices and returns the entire string "fig pie".

The third line shows what happens when you try to get a slice in which the entire range is out of bounds. flavor[13:15] attempts to get the thirteenth and fourteenth characters, which don’t exist. Instead of raising an error, Python returns the *empty string "".*

***Note***:

The empty string is called empty because it doesn’t contain any
characters. You can create it by writing two quotation marks
with nothing between them:
```python
empty_string = ""

```
A string with anything in it—even a space—is not empty. All of
the following strings are non-empty:

```python
non_empty_string1 = " "
non_empty_string2 = "  "
non_empty_string3 = "      "
```

Even though these strings don’t contain any visible characters,
they are non-empty because they do contain spaces.

You can use negative numbers in slices. The rules for slices with negative numbers are exactly the same as the rules for slices with positive numbers. It helps to visualize the string as slots with the boundaries labeled with negative numbers:

![negative_slice](https://user-images.githubusercontent.com/15992276/152918562-295a507a-1dc8-4c11-b90e-6d6abd1b85f6.png)


Just like before, the slice [x:y] returns the substring starting at index x and going up to but not including y. For instance, the slice [-7:-4] returns the ﬁrst three letters of the string "fig pie":

```python
>>> flavor[-7:-4]
'fig'
```
Notice, however, that the rightmost boundary of the string does not have a negative index. The logical choice for that boundary would seem to be the number 0, but that doesn’t work.

Instead of returning the entire string, [-7:0] returns the empty string:

```python
>>> flavor[-7:0]
''
```

This happens because the second number in a slice must correspond
to a boundary that is to the right of the boundary corresponding to the ﬁrst number, but both -7 and 0 correspond to the leftmost boundary in the ﬁgure.

Slices with negative indices are useful, though, for getting the last few characters in a string. For example, flavor[-3:] is "pie".

### Strings are Immutable

Strings are immutable, which means that you can’t change
them once you’ve created them. For instance, see what happens when
you try to assign a new letter to one particular character of a string:


```python
>>> word = "goal"
>>> word[0] = "f"
Traceback (most recent call last):
File "<pyshell#16>", line 1, in <module>
word[0] = "f"
TypeError: 'str' object does not support item assignment
```

Python throws a TypeError and tells you that str objects don’t support item assignment.
If you want to alter a string, then you must create an entirely new string. To change the string "goal" to the string "foal", you can use a string slice to concatenate the letter "f" with everything but the ﬁrst letter of the word "goal":

```python
>>> word = "goal"
>>> word = "f" + word[1:]
>>> word
'foal'

```
First, you assign the string "goal" to the variable word. Then you concatenate the slice word[1:], which is the string "oal", with the letter "f" to get the string "foal". If you’re getting a diﬀerent result here, then make sure you’re including the colon character (:) as part of the string slice.

