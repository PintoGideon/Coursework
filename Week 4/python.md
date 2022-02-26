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