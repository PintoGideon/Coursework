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

*Info:* If you haven’t installed the Python extension at this point, you’ll get a pop-up recommending you install it for this type of file. Please install it now, and reload VS Code when prompted to load the extension.

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

# - comments start with #. They will be ignored.
>>> - this is the prompt. In example code, lines starting with >>> means they are input
lines that don’t start with either of these are output that was produced by running input from the prompt
by typing these line of code at the >>> prompt, and press enter after each line.

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


*** Gideon, why have we wasted time setting up so many different environments? Well, a lot of people waste
too much time in the setup and setting the right environment. Why not get the boring part out
of the way, and just focus on the learning. There are a lot of internet articles out there and I want
to funnel all the content to a battle test environment which is more closed to a real-world scenario"***


### Running Code

 We’ll mostly be working with Python program files in the course with the occasional use of REPL.

### Creating Python Files with the *.py extension
You know a file is a Python program when it ends with a .py extension.

To create a new file in VS Code, and ⌘N (command + N) on Mac OS.

This will open a new file. Next, save the file with a .py extension. Create a new simple Python program in a file called hello.py in your pyworkshop directory with the following contents:

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

Running The File
Once you’ve opened your hello.py file and selected your new terminal window, open the VS Code command palette.

***Note** Open the command palette with Ctrl+Shift+P on Windows and Linux, and ⌘⇧P (command + shift + P) on Mac OS.
Select Python: Run Python File in Terminal


You should see:
```python
Hello, World!
Bonjour, World!
Hola, World!
```

If you have gotten this far, I am very optimistic for your journey ahead. This is hard stuff.:tada:
