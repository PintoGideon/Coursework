### Conditional Logic

Conditional logic is based on performing diﬀerent actions depending on whether or not some expression, called a conditional, is true or
false. This idea is not speciﬁc to computers. Humans use conditional logic all the time to make decisions.

You may ﬁnd it helpful to think of boolean comparators as asking a question about two values. a == b asks whether or not a and b have the same value. Likewise, a != b asks whether or not a and b have diﬀerent values.

Conditional expressions are not limited to comparing numbers. You may also compare values such as strings:

```python
>>> "a" == "a"
True
>>> "a" == "b"
False
>>> "a" < "b"
True
>>> "a" > "b"
False
```

The comparators < and > represent the notions of greater than and less than when used with numbers, but more generally they represent the
notion of order. In this regard, "a" < "b" checks if the string "a" comes before the string "b". But how are string ordered?
In Python, strings are ordered lexicographically, which is a fancy way of saying they are ordered as they would appear in a dictionary. So you can think of "a" < "b" as asking whether or not the letter a comes before the letter b in the dictionary.

Lexicographic ordering extends to strings with two or more characters by looking at each component letter of the string:

```python
>>> "apple" < "astronaut"
True
>>> "beauty" > "truth"
False
```
### The 'and' keyword

Consider the following statements:

1. Yahweh is love.
2. Yahweh is just.

Both of these statements are true. 

When we combine these two statements using and, the resulting sentence “Yahweh is love and Yahweh is just” is also a true statement.
If both statements are negated, the compound statement “Yahweh is not love and Yahweh is not just” is false.

When two statements P and Q are combined with and, the truth value of the compound statement “P and Q” is true if and only if both P and
Q are true.

```python
>>> 1 < 2 and 3 < 4
# Both are True
True
Both statements are True, so the combination is also True.
>>> 2 < 1 and 4 < 3
# Both are False
False
```

Both statements are False, so their combination is also False.

```python
>>> 1 < 2 and 4 < 3
# Second statement is False
False

1 < 2 is True, but 4 < 3 so their combination is False.

>>> 2 < 1 and 3 < 4 # First statement is False

False
```
### The 'or' keyword

When we use the word “or” in everyday conversation, sometimes we mean an exclusive or. That is, only the ﬁrst option or the second
option can be true.

In Python the or keyword is inclusive. That is, if P and Q are two expressions, the statement “P or Q” is true if any of the following are true:
1. P is true
2. Q is true
3. Both P and Q are true


```python
>>> 1 < 2 or 3 < 4 # Both are True
True

>>> 2 < 1 or 4 < 3 # Both are False
False

>>> 1 < 2 or 4 < 3 # Second statement is False
True

>>> 2 < 1 or 3 < 4 # First statement is False
True

```

Note that if any part of a compound statement is `True`, even if the other part is `False`, the result is always true `True`.

### The 'not' Keyword

The not keyword reverses the truth value of a single expression:

```python
>>> not True
False
>>> not False
True
```

### The 'if' statement
An if statement tells Python to only execute a portion of code if a con-
dition is met.


```python
if 2 + 2 == 4:
    print("2 and 2 is 4")

```

You can read as "if 2 + 2 is 4", then print the string '2 and 2 is 4'.

Just like while loops, an if statement has three parts:

1. The if keyword
2. A test condition, followed by a colon
3. An indented block of code that is executed if the test condition is True

```python
grade = 95
if grade >= 70:
print("You passed the class!")
print("Thank you for attending.")
```

### The else keyword

The else keyword is used after an if statement in order to execute some code only if the if statement’s test condition is False.

```python
grade = 40
if grade >= 70:
    print("You passed the class!")
else:
    print("You did not pass the class :(")


print("Thank you for attending.")

```

### The elif keyword

The elif keyword is short for “else if” and can be used to add additional conditions after an if statement.

1. The elif keyword
2. A test condition, followed by a colon
3. An indented code block that is executed if   the test condition evaluates to `True`

```python


grade = 85
# 1
if grade >= 90:
    print("You passed the class with a A.")

elif grade >= 80:
    print("You passed the class with a B.")

elif grade >= 70:
    print("You passed the class with a C.")

else:
    print("You did not pass the class :(")


print("Thanks for attending.")
# 6
```


### Find the Factors of a Number

A factor of a positive integer n is any positive integer less than or equal to n that divides n with no remainder.

3 is a factor of 12 because 12 divided by 3 is 4, with no remainder. However, 5 is not a factor of 12 because 5 goes into 12 twice
with a remainder of 2.
Write a program called factors.py that asks the user to input a posi-
tive integer and then prints out the factors of that number. Here’s a sample run of the program with output:

```python
Enter a positive integer: 12
1 is a factor of 12
2 is a factor of 12
3 is a factor of 12
4 is a factor of 12
6 is a factor of 12
12 is a factor of 12
```

```python
# Display all the factors of a number chosen by the user
num = int(input("Enter a positive integer: "))

for divisor in range(1, num + 1):
    if num % divisor == 0:
        print(f"{divisor} is a factor of {num}")


```
The following example uses a for loop with an if statement to compute and display the sum of all even integers less than 100:

```python
sum_of_evens = 0

for n in range(101):
    if n % 2 == 0:
        sum_of_evens = sum_of_evens + n

print(sum_of_evens)


```

### break and continue


The `break` keyword tells Python to literally break out of a loop. That is, the loop stops completely and any code after the loop is executed.

```python

for n in range(4):
    if n == 2:
        break
    print(n)

print(f"Finished with n={n}")

```
Only the ﬁrst two numbers are printed in the output:

```python
0
1
Finished with n = 2
```

The `continue` keyword is used to skip any remaining code in the loop body and continue on to the next iteration.

For example, the following code loops over the numbers 0 to 3, printing each number as is goes, but skips the number 2:

```python

for i in range(4):
    if i == 2:
        continue
    print(i)

print(f"finished with i = {i}")
```

```python
0
1
3
Finished with i = 3
```

To summarize, the break keyword is used to stop a loop if a certain condition is met, and the continue keyword is used to skip an iteration
of a loop when a certain condition is met.

### The try and execept keywords

A full list of Python’s built-in exceptions can be found in the oﬃcial
docs.

Sometimes you can predict that a certain exception might occur. Instead of letting the program crash, you can catch the error if it occurs and do something else instead.

For example, you might need to ask the user to input an integer. If the user enters a non-integer value, such as the string "a", you need to let them know that they entered an invalid value.

```python
try:
    number = int(input("Enter an integer"))
except ValueError:
    print("That was not an integer")

```

The `try` keyword keyword is used to indicate a try block and is followed by a colon. The code indented after try is executed. In this case, the user is asked to input an integer. Since `input()` returns a string, the user input is converted to an integer with int() and the result is assigned to the variable number.

If the user inputs a non-integer value, the `int()` operation will raise a `ValueError`. If that happens, the code indented below the line except
`ValueError` is executed. So, instead of the program crashing, the string "That was not an integer" is displayed.

If the user does input a valid integer value, then the code in the except `ValueError` block is never executed.

On the other hand, if a diﬀerent kind of exception had occurred, such as a `TypeError`, then the program will crash. The above example only handles one type of exception — a `ValueError`.

You can handle multiple exception types by separating the exception names with commas and putting the list of names in parentheses:

```python
   def divide(num1, num2):
       try:
           print(num1/num2)
       except(TypeError, ZeroDivisionError):
           print("Encountered a problem")
```

The function divide() takes two parameters num1 and num2 and prints the result of dividing num1 by num2.

If `divide()` is called with an argument that is a string, then the division operation will raise a `TypeError`. Additionally, if num2 is 0, then a
`ZeroDivisionError` is raised.

### Simulate Events and Calculate Probabilities

This is a simple simulation known as a *Monte Carlo* experiment. Each experiment consists of a trial, which is just some process that can be repeated, such as flipping a coin. Each trial generates an outcome, such as landing on heads or tails. The trial is repeated over and over again in order to calculate the probability that
some outcome occurs.

In order to do this, we need to add some randomness to our code.

### The `random` module

Python provides several functions for generating random numbers in the random module. A module is a collection of related code. Python’s standard library is an organized collection of modules that you can import into your own code in order to solve various problems.

```python
>>> import random

>>> random.randint(1, 10) # 9

```

The `randint()` function in the random module has two required parameters called a and b and returns a random integer that is greater than
or equal to a and less than or equal to b. Both a and b must be integers.

Since the result is random, your output will probably be diﬀerent than 9. If you type the same code in again, you will likely get a diﬀerent number.
Since `randint()` is located in the random module, you must type random followed by a dot (.) and then the function name in order to use it.

So, for `randint(1, 10)`, each integer between 1 and 10 has a 10% chance of being returned. For `randint(0, 1)`, there is a 50% chance a 0 is returned.

### Flipping Fair Coins

One trial for our experiment will be flipping the coin. The outcome is either a heads or a tails. The question is: in general, over many coin flips, what is the ratio of heads to tails?


Let’s think about how to solve this problem. We’ll need to keep track of how many times we get a heads or tails, so we need a heads tally
and a tails tally. Each trial has two steps:

1. Flip the coin.
2. If the coin lands on heads, update the heads tally. Otherwise, the coin lands on tails so update the tails tally.

We need to repeat the trial many times, say 10,000. A for loop over range(10_000) is a good choice for doing something like that.


```python

import random

def coin_flip():
    """Randomly return 'heads' or 'tails'"""
    if random.randint(0,1)==0:
        return 'heads"
    else: 
        return "tails"

heads_tally=0
tails_tally=0

for trial in range(10_000):
    if coin_flip() == "heads":
        heads_tally = heads_tally + 1
    else:
        tails_tally = tails_tally + 1

ratio = heads_tally / tails_tally
print(f"The ratio of heads to tails is {ratio}")
```

If you save the above code to a ﬁle and run it a few times, you will see that the result is usually between .98 and 1.02. If you increase the
range(10_000) in the for loop to, say, range(50_000), the results should get closer to 1.0.
This behavior makes sense. Since the coin is fair, we should expect that after many flips, the number of heads is roughly equal to the num-
ber of tails.


In life, things aren’t always fair. A coin may have a slight tendency to land on heads instead of tails, or vice versa. So, how do you simulate
something like an unfair coin?

### Tossing Unfair Coins

randint() returns a 0 or 1 with equal probability. If 0 represents tails and 1 represents heads, then to simulate an unfair coint we need a way to return one of 0 or 1 with a higher probability.


The `random()` function can be called without any arguments and returns a floating-point number greater than or equal to 0.0 but less than 1.0. Each possible return value is equally likely. In probability theory, this is known as a *uniform probability distribution.*

One consequence of this is that, given a number n between 0 and 1, the probability that random() returns a number less than n is just n itself.
For example, the probability that random() is less than .8 is .8 and the probability that random() is less than .25 is .25.

```python
import random

import random
def unfair_coin_flip(probability_of_tails):
    if random.random() < probability_of_tails:
        return "tails"
    else:
        return "heads"

```

Running this simulation a few times shows that the ratio of heads tails has gone down from 1 in the experiment with a fair coin to about .43.

### Extra

Suppose two candidates, Candidate A and Candidate B, are running for mayor in a city with three voting regions. The most recent polls
show that Candidate A has the following chances for winning in each
region:
• Region 1: 87% chance of winning
• Region 2: 65% chance of winning
• Region 3: 17% chance of winning
Write a program that simulates the election 10,000 times and prints
the percentage of where Candidate A wins.


```python
from random import random

num_times_A_wins = 0
num_times_B_wins = 0

num_trials = 10_000

for trial in range(0, num_trials):
     votes_for_A = 0
     votes_for_B = 0

     # Determine who wins the 1st region
     
     if random() < 0.87:
         votes_for_A = votes_for_A + 1
     else:
         votes_for_B - votes_for_B + 1
        
      # Determine who wins the 2nd region
     if random() < 0.65:
         votes_for_A = votes_for_A + 1
     else:
         votes_for_B = votes_for_B + 1

     # Determine who wins the erd region
    if random() < 0.17:
        votes_for_A = votes_for_A + 1
    else:
        votes_for_B = votes_for_B + 1
    
     # Determine overall election outcome
    if votes_for_A > votes_for_B:
        num_times_A_wins = num_times_A_wins + 1
    else:
        num_times_B_wins = num_times_B_wins + 1


print(f"Probability A wins: {num_times_A_wins / num_trials}")
print(f"Probability B wins: {num_times_B_wins / num_trials}")



```


### Tuples , Lists and Dictionaries

So far, you have been working with fundamental data types like str, int, and float. Many real-world problems are easier to solve when
simple data types are combined into more complex data structures.

A data structure models a collection of data, such as a list of numbers, a row in a spreadsheet, or a record in a database. Modeling the data that your program interacts with using the right data structure is often the key to writing simple and eﬀective code.

### Tuples

Perhaps the simplest compound data structure is a sequence of items.

A *sequence* is an ordered list of values. Each element in a sequence is assigned an integer, called an index, that determines the order in
which the values appear. Just like strings, the index of the ﬁrst value in a sequence is 0.

Some real-world examples of sequences include the values emitted by a sensor every second, the sequence of a student’s test scores, or the
sequence of daily stock values for some company over a period of time.

A *tuple* comes from mathematics, where it is used to describe a ﬁnite ordered sequence of values.

Usually, mathematicians write tuples by listing each element, separated by a comma, inside a pair of parentheses. (1, 2, 3) is a tuple
containing three integers.

Tuples are ordered because their elements appear in an ordered fashion. The ﬁrst element of (1, 2, 3) is 1, the second element is 2, and the third is 3

### How to create a tuple

1. Tuple literals
2. The `tuple()` built in

Just like a string literal is a string that is explicitly created by surrounding some text with quotes, a tuple literal is a tuple that is written out explicitly as a comma-separated list of values surrounded by parentheses.

```python
my_first_tuple=(1,2,3)

type(my_first_tuple)
<class 'tuple'>

```
Unlike strings, which are sequences of characters, tuples may contain any type of value, including values of diﬀerent types. The tuple (1, 2.0, "three") is perfectly valid.


```python
empty_tuple=()

```

At ﬁrst glance, the empty tuple may seem like a strange and useless concept, but it is actually quite practical.

For example, suppose you are asked to provide a tuple containing all the integers that are both even and odd. No such integer exists, but
the empty tuple allows you to provide the requested tuple.

```python
>>> x = (1)
>>> type(x)
<class 'int'>

```
When you surround a value with parentheses, but don’t include any commas, Python interprets the value not as a tuple but as the type of value inside the parentheses. So, in this case, (1) is a just a weird way of writing the integer 1.
To create the tuple containing the single value 1, you need to include a comma after the 1:

```python
>>> x = (1,)
>>> type(x)
<class 'tuple'>
```


You can also use the `tuple()` built-in to create a tuple from another sequence type, such as a string:

```python
>>> tuple("Python")
('P', 'y', 't', 'h', 'o', 'n')
```
`tuple()` only accepts a single parameter, so you can’t just list the values you want in the tuple as individual arguments. If you do, Python raises a TypeError:

```python
>>> tuple(1, 2, 3)
Traceback (most recent call last):
File "<pyshell#0>", line 1, in <module>
tuple(1, 2, 3)
TypeError: tuple expected at most 1 arguments, got 3

```
You will also get a TypeError if the argument passed to tuple() can’t be interpreted as a list of values:

```python
>>> tuple(1)
Traceback (most recent call last):
File "<pyshell#1>", line 1, in <module>
tuple(1)
TypeError: 'int' object is not iterable
```
The word iterable in the error message indicates that a single integer can’t be iterated, which is to say that the integer data type doesn’t
contain multiple values that can be accessed one-by-one.

Tuples and strings have a lot in common. Both are sequence types with a ﬁnite length, support indexing and slicing, are immutable, and
can be iterated over in a loop.
The main diﬀerence between strings and tuples is that the elements of tuples can be any kind of value you like, whereas strings can only
contain characters.

### Tuples have a length

Both strings and tuples have a length. The length of a string is the number of characters in it. The length of a tuple is the number of
elements it contains.

Just like strings, the length of a tuple:
len() function can be used to determine the
length of a tuple:

```python
>>> numbers = (1,2,3)
>>> len(numbers)
3

```
### Tuples support Indexing and Slicing


```python
name = 'Harin'
name[1]
'a'
```

Like strings, tuples are immutable. This means you can’t change the value of an element of a tuple once it has been created.
If you do try to change the value at some index of a tuple, Python will
raise a TypeError:

```python
>>> values[0] = 2
Traceback (most recent call last):
File "<pyshell#1>", line 1, in <module>
values[0] = 2
TypeError: 'tuple' object does not support item assignment
```

### Tuples are Iterable
Just like strings, tuples are iterable, so you can loop over them:

```python
>>> vowels = ("a", "e", "i", "o", "u")
>>> for vowel in vowels:
...
print(vowel.upper())
...
A
E
I
O
U
```
### Checking existence of values with `in`

```python
>>> vowels = ("a", "e", "i", "o", "u")
>>> "o" in vowels
True
>>> "x" in vowels
False
```

If the value to the left of in is contained in the tuple to the right of the result is True. Otherwise, the result is False.


### Returning Multiple Values from a Function

```python
def adder_subtractor(num1, num2):
    return (num1 + num2, num1 - num2)
adder_subtractor(3, 2)
(5, 1)
```

The function `adder_subtractor()` has two parameters, num1 and num2, and returns a tuple whose ﬁrst element is the sum of the two numbers, and whose second element is the diﬀerence.

Strings and tuples are just two of Python’s built-in sequence types.

Both are immutable and iterable and can be used with index and slicing notation.

### Lists are mutable sequences


The `list` data structure is another sequence type in Python. Just like strings and tuples, lists contain items that are indexed by integers,
starting with 0.

Unlike tuples, lists are mutable.

### Creating Lists

A list literal looks almost exactly like a tuple literal, except that it is surrounded with square brackets ([ and ]) instead of parentheses:

```python
>>> colors = ["red", "yellow", "green", "blue"]
>>> type(colors)
<class 'list'>

```

When you inspect a list, Python displays it as a list literal:

```python
>>> colors
['red', 'yellow', 'green', 'blue']
```
Like tuples, lists values are not required to be of the same type. The list literal ["one", 2, 3.0] is perfectly valid.

You can even create a list from a string:

```python
>>> list("Python")
['P', 'y', 't', 'h', 'o', 'n']
```
Each letter in the string becomes an element of the list. There is more useful way to create a list from a string. You can create a list from a string of a comma-separated list of items using the string object’s `.split()` method:

```python
>>> groceries = "eggs, milk, cheese"
>>> grocery_list = groceries.split(", ")
>>> grocery_list
['eggs', 'milk', 'cheese']


```

The string argument passed to `.split()` is called the separator. By changing the separator you can split strings into lists in numerous
ways:
 
```python
>>> "a;b;c".split(";")
['a', 'b', 'c']

>>> # Split string on spaces
>>> "The quick brown fox".split(" ")
['The', 'quick', 'brown', 'fox']

>>> # Split string on multiple characters
>>> "abbaabba".split("ba")
['ab', 'ab', '']
```

`.split()` always returns a string whose length is one more than the  number of separators contained in the string. The string "abbaabba" contains two instances of the separator "ba" so the list returned by `split()` has three elements. Since the third separator isn’t followed by any other characters, the third element of the list is set to the empty string.


```python
"abbaabba".split("c")
['abbaabba']
```

### Basic List Operations for Algorithms

```python
>>> numbers = [1, 2, 3, 4]
>>> numbers[1]
2
```

You can create a new list from an existing once using slice notation:

```python
>>> numbers[1:3]
[2, 3]
```
You can check for the existence of list elements using the in operator:

```python
>>> # Check existence of an element
>>> "Bob" in numbers
False
```
Because lists are iterable, you can iterate over them with a for loop.

```python
>>> # Print only the even numbers in the list
>>> for number in numbers:
...
if number % 2 == 0:
2409.2. Lists Are Mutable Sequences
...
print(number)
...
2
4
```
### Changing Elements in a List

The ability to swap values in a list for other values is called mutability. Lists are **mutable*. The elements of tuples may not be swapped for new values, so tuples are said to be immutable.

```python
colors = ["red", "yellow", "green", "blue"]
colors[0]="burgundy"
>>> colors
['burgundy', 'yellow', 'green', 'blue']

```

You can change several values in a list at once with a slice assignment:

```python
>>> colors[1:3] = ["orange", "magenta"]
>>> colors
['burgundy', 'orange', 'magenta', 'blue']
```

colors[1:3] selects the slots with indices 1 and 2. The values in these slots are assigned to "orange" and "magenta", respectively.

The list assigned to a slice does not need to have the same length as the slice. For instance, you can assign a list of three elements to a slice with two elements:

```python
>>> colors = ["red", "yellow", "green", "blue"]
>>> colors[1:3] = ["orange", "magenta", "aqua"]
>>> colors
['red', 'orange', 'magenta', 'aqua', 'blue']
```

The values "orange" and "magenta" replace the original values "yellow"cand "green" in colors at the indices 1 and 2. Then a new slot is created atcindex 4 and "blue" is assigned to this index. Finally, "aqua" is assignedcto index 3.

When the length of the list being assigned to the slice is less than the length of the slice, the overall length of the original list is reduced:

```python
>>> colors
['red', 'orange', 'magenta', 'aqua', 'blue']
>>> colors[1:4] = ["yellow", "green"]
>>> colors
['red', 'yellow', 'green', 'blue']
```

The values "yellow" and "green" replace the values "orange" and "magenta" in colors at the indices 1 and 2. Then the value at index 3 is
replaced with the value "blue". Finally, the slot at index 4 is removed from colors entirely.

