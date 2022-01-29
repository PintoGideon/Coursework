### What is a programming language ?

Programming in lay man terms is a way for us to give instructions to the computer. Computers don't understand human language for that matter. Computer's speak in ones and zeros. But writing ones and zeros would be difficult for us. It's hard for us to communicate like that.

Humans have developed programming languages that are between human language and machine language.


Let's say you want to book a flight through a website. As a user , you want to pull up a list of flights for a particular destination on the screen. The web page is usually coded in Python or Javascript by a developer. We will call it source code. 

How does the source code in a file convert into zeros and one's so that our machines can understand. We need to translate the source code into machine level language and for that we need a translator.

### What is a translator? 

Well, the translator is another program written by a user. It can either be a compiler or an interpreter.
Python usually uses an interpreter. An interpreter goes line by line through your source code and executes it on our machine. Compilers on the other hand take your code all at once and then translates that into machine code. The differences between these two is a bit complicated and can be covered at a later point.

![Compilers](https://user-images.githubusercontent.com/15992276/151667882-3478dca0-3510-4adc-b223-4911936b9efd.png)


In order for us to be able to write Python code, we can't do it anywhere. If you opened up a text file in your computer and started writing python code, you wouldn't be able to make your machine function accordingly. Why? We need to have a translation service.

### Python Interpreter

How do I get the translation service? Well, you download it on your machine.
Download Python on your machine: https://www.python.org/downloads/

When you click on Downloads, and dowload python on your machine, you are actually downloading this.
https://github.com/python/cpython

It's important that you install python correctly. https://techsviewer.com/how-to-install-python-on-mac/

You just download a tranlsation service called as cypthon. Remember, I told you that the translation service (cypthon) is a layer of software that works between your program and your computer hardware to get your code running.. There are other translation services out there written in different langauges that achieve the same result. When you download from Python, you are actually downloading the translation service (The interpreter).

![Python_Interpreter](https://user-images.githubusercontent.com/15992276/151667884-2efa50c7-3ca5-4f0e-940e-01f2916afece.png)

Just to come full circle, You write python code in a file, the interpreter takes it and converts it into byte code that this is close to a machine readable code, it then uses the CPython Virtual Machine which runs the byte code to convert it into zeroes and ones. The CVM is not an isolated component of Python. It’s just part of the Python system you’ve installed on your machine. Technically, the PVM is the last step of what is called the Python interpreter.

The whole process to run Python scripts is known as the Python Execution Mode


### How do we finally run Python code ?

The interpreter is able to run Python code in two different ways:

1. A script or module
2. A piece of code typed in an interactive session.

A widely used way to run python code is through an interactive session. To start a Python interactive session, just open a command-line or terminal and then type in python or python3 depending on your
python installation. On a Mac system, it is very straight-forward. All you need to do is open Launchpad and search for Terminal, and in the terminal, type Python and boom, it will give you an output with the Python version.

![Python_Program](https://user-images.githubusercontent.com/15992276/151667886-eafd6102-92b1-4f87-bc52-6d39353e56a0.png)

The standard prompt for the interactive mode is >>>, so as soon as you see these characters, you’ll know you are in. Now, you can write and run Python code as you wish, with the only drawback being that when you close the session, your code will be gone.

When you work interactively, every expression and statement you type in is evaluated and executed immediately:

![Python_Program](https://user-images.githubusercontent.com/15992276/151667886-eafd6102-92b1-4f87-bc52-6d39353e56a0.png)


An interactive session will allow you to test every piece of code you write, which makes it an awesome development tool and an excellent place to experiment with the language and test Python code on the fly.

To exit interactive mode, you can use one of the following options:

- quit() or exit(), which are built-in functions
- The Ctrl+Z and Enter key combination on Windows, or just Ctrl+D on Unix-like systems



### REPL

In the python world, it's easy to get overwhelmed by the different developer tools out there. We will learn each of them as we go. Right now, I want to take the path of least resistance and get you'll up and running.

![REPL](https://user-images.githubusercontent.com/15992276/151670703-552c1fff-49e2-4998-afa5-db554cd0f034.png)

You should see this dashboard when you sign in.

![Step_1](https://user-images.githubusercontent.com/15992276/151670852-1b978290-a81d-44cf-bf7d-723874e88c96.png)

Click on the + icon and choose python as your official programming language.

![step_2](https://user-images.githubusercontent.com/15992276/151670850-10bca37b-233e-426a-ba9e-fca2b54d2410.png)

Once, you see your python setup, the world is your oyster. If you have reached this step, you are officially ready to code

![step_3](https://user-images.githubusercontent.com/15992276/151670851-e0e6a0ef-574b-419a-866a-8b1dd41abadd.png)


