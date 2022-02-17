[![General Assembly Logo](https://camo.githubusercontent.com/1a91b05b8f4d44b5bbfb83abac2b0996d8e26c92/687474703a2f2f692e696d6775722e636f6d2f6b6538555354712e706e67)](https://generalassemb.ly/education/web-development-immersive)

# Python

Hey, Polyglots! Ready for another programming language?

## Prerequisites

- Know and use the basics of JavaScript

## Objectives

By the end of this, students should be able to:

-   Use the Python REPL
-   Compare and contrast basic language features and types from Python with basic language features and types from Javascript.
-   Write and run simple script in Python.

## Python REPL

Typing `python3` onto the command line will bring you into this REPL using Python version > 3.7, similar to calling `node` to run the `node` REPL.

**note:** Macs have Python 2 installed already. Remember to use `python3`! There are several things in this course that will break if you try to run them in Python 2, which is what will run on most of your machines if you simply type `python`

To run Python scripts, simply run
`python3 filename.py` from the command line. If you _do_ want to run Python in version 2.7.0 or the original Python version install on your machine, simply call `python` without the extra 3.

_Hint: to print to the console in Python, we use `print("hello world")`_

## Core Syntax, Variables, and Operators

### Syntax

1. Snake Case: `keep_your_variables_defined_this_way` and `we_are_in_pythons_house_now`.
2. **Parens** `()` in Python are required around parameters at all times
3. Line breaks/ **whitespace** instead of semicolons, and closing curly braces!
4. **colons** `:` directly after the first line of the block statement, immediately followed by a new, indented line. Colons replace `{` in JS.

### Variables

Similar to JS, but different.

```python
>>> x = 2 # assigns x to numerical value 2
>>> x = "Take it easy dude. But take it!" # reassigns x to string value
```

By default, variables are locally scoped. So `name = "GArnet"` in Python is like `let name = "GArnet"` in JS.

For constants, there is no way to make a variable specifically unable to be changed! But it is a widely practiced _convention_ to declare constants in all caps:

NUMBER_OF_DAYS_IN_A_WEEK = 7

### Floats and Integers

Unlike JavaScript, which has a single Number data type, Python has separate data types for integers (whole numbers) and floats (decimals).

### Booleans

In Python, true and false are represented by `True` and `False` (yes, case
matters).

The falsy values of Python are:

`False` `None` `0` `0.0` `''` `[]` `{}`

`None` is equivalent to Javscripts's `null`.

### Operators

|                      |        JavaScript                    |        Python               |
|:---------------------|:------------------------------------:|:---------------------------:|
| logical operators    | `&&`, <code>&#124;&#124;</code>, `!` | `and`, `or`, `not`          |
| relational operators | `==` `===` `!=` `>` `<` `>=` `<=`          | `==` `!=` `>` `<` `>=` `<=` |
| arithmetic operators | `+`, `-`, `*`, `/`, `%`              | `+`, `-`, `*`, `/`, `//`, `%`     |

#### Loose vs. Strict Comparison

The `==` comparison operator in Python is equivalent to the `===` strict comparison operator in JavaScript.
_There is no loose comparison operator in Python_

#### Brief Aside: Double Slash (`//`) Operator

`//` is the floor division operator. It returns the quotient rounded down to the nearest integer:

```python
>>> 14.5 / 3    # => 4.833333
>>> 14.5 // 3   # => 4.0
```

Note that operations on floats will still return floats no matter the operator.

To convert between floats and integers, use:

```python
>>> int(14.5)    # => 14
>>> float(14)    # => 14.0
```

## Strings

In Python, there is no difference between using `" "` or `' '`.
[Escape Characters](http://python-reference.readthedocs.io/en/latest/docs/str/escapes.html)
are evaluated in both.

```python
>>> print("This is a \n new line.")
# => This is a
# => new line.
```

### String Interpolation

There are many options for string interpolation in Python. One option is `.format()`.

`.format()` is appended to a string and takes a parameters the strings to be
concatenated. If the string contains empty `{}`s, the parameters fill the `{}`s
in the order passed in. If they contain a number (beginning with 0), they will
be mapped to the parameter passed to `.format()` at said index.

```python
>>> thing_to_do = "Take it"
>>> way_to_do_it = "easy"
>>> pronoun = "dude"

>>> "{} {} {}. But {}!".format(thing_to_do, way_to_do_it, pronoun, thing_to_do)
# => 'Take it easy dude. But Take it!'

>>> "{0} {1} {2}. But {0}!".format(thing_to_do, way_to_do_it, pronoun)
# => 'Take it easy dude. But Take it!'
```

However, a newer and better option called _f-strings_ was introduced in Python 3.6.

`f` is prepended to a string and variable names in curly braces are interpolated into the string, similar to template literals in JavaScript:
```python
>>> thing_to_do = "Take it"
>>> way_to_do_it = "easy"
>>> prnoun = "dude"

>>> f"{thing_to_do} {way_to_do_it} {pronoun}. But {thing_to_do}!"
# => 'Take it easy dude. But Take it!'
```

## Collections

### Lists

Python lists are comparable to JavaScript arrays. They store comma separated values
of varying data types between square brackets `[]`:

```python
animals = ["lions", "tigers", "bears"]
```

Much like accessing values in a JavaScript array, you can access elements in a list using bracket notation and the element's index (beginning with 0):

```python
animals[0]
# => "lions"
```

Lists in Python also support negative indices, with -1 returning the last item in the list, -2 return the second to last, and so forth:

```python
animals[-1]
# => "bears"
```

`len()` is used to get the length of a list in Python.

```python
len(secret_files) # => 300
```

We can merge lists together using the `+` operator:

```python
secret_files = ["TOP SECRET", "ALSO TOP SECRET", "DON'T EVEN LOOK AT THIS"]
new_secret_files = ["PRETTY DARN SECRET", "WE SEEM NOT TO BE TRUSTED QUITE AS MUCH WITH TOP SECRET", "MAYBE IT'S THAT WE LEAVE SECRETS IN ALL CAPS IN PLAIN TEXT"]

secret_files = secret_files + new_secret_files
```

#### List Methods

- `.append()`  instead of `.push()`

```python
secret_files.append("He's guilty.")
```

`.pop()` removes the last element from a Python list.

We do not have built-in operators for removing or adding to the _beginning_ of a
list!

`.remove(n)` allows us to remove an element at any index. Thus, `list.remove('TOP SECRET)`
would remove the first element from a list.

### Dictionaries

#### Dictionaries - Purpose

- _Dictionaries_ in Python are similar to _objects_ in JavaScript

- In computer science these types are also known as _associative arrays_ or _maps_.

- A **dictionary** provides a container for **`key: value`** pairs. We can refer to `key: value` pairs as **items**.

- _Dictionaries_ have a class (type) of `dict`.

#### Dictionaries - Basic Syntax

- Like _objects_ in JS, a **dictionary** is created with a set of _curly braces_:

```python
student = {
	'name': 'Fred',
	'course': 'WDI',
	'current_week': 4
}
```
- Unlike in JS, _strings_ used as keys must be quoted.

#### Dictionaries - Features

Dictionaries have the following features:

- They are unordered (just like JS objects)

- They are mutable:
 	- The values assigned to a key can be changed
 	- New `key: value` pairs (items) can be added
 	- Existing items can be deleted

- Any immutable type can be used as a key, including _numbers_ and _tuples_ (which we'll cover in a bit).

#### Dictionaries - Getting/Setting Values

- We use _square brackets_ to get and set an item's value:

```python
name = student['name']
print(name)
> Fred
student['name'] = 'Tina'
print(name)
> Tina
```

- Unlike with _objects_ in JS, Python _dictionaries_ **have no dot notation**.

#### Dictionaries — get Method

- Unlike JS which returns `undefined` when accessing a property that does not exist, a _dictionary_ will raise a `KeyError`.

- One option to avoid this error is to use the `get` method:

```python
birthdate = student['birthdate']
> KeyError: 'birthdate'
print( student.get('birthdate', 'unknown') )
> unknown
print( student.get('birthdate') )
> None
```

#### Dictionaries - in Operator

- Another way to avoid the `KeyError` is to use the `in` operator to check if the _dictionary_ includes a key:

```python
import datetime

if 'birthdate' in student:
	today = datetime.datetime.today()
	is_birthday = (student['birthdate'].month == today.month and
		student['birthdate'].day == today.day)
```

#### Dictionaries - Adding Items

- Simply assigning to a _key_ that does not exist will create a new item in the dictionary:

```python
student['age'] = 21
```

#### Dictionaries - Deleting Items

- The `del` operator deletes an item from a _dictionary_:

```python
del student['age']
'age' in student
> False
```

#### Dictionaries - Number of Items

- Use the built-in `len` function to retrieve the number of items in a _dictionary_:

```python
print( student )
> {'name': 'Tina', 'course': 'WDI'}
len(student)
> 2
len({})
> 0
```

## Control Flow

### Conditionals

Again, colons and whitespace are critical to working Python code. Aside from
that and the use of `elif` vs. `else if`, these should feel very similar to Javascript conditional statements.

```python
if x < 0:
  print('Negative')
elif x == 0:
  print('Zero')
else:
  print('Positive')
```

### Loops

Also like Javascript, Python employs `while` and `for` loops.

In Python, `while` loops behave the same way they do in JavaScript:

```python
count = 0
while count < 5:
	print(count)
	count += 1

# 0
# 1
# 2
# 3
# 4
```

Unlike `for` loops in JavaScript, all `for` loops in Python are `for ... in` loops. They always iterate over an iterable datatype. We'll cover the `range()` operator in more depth in the next lesson, but for now, be aware this in Python:

```python
for i in range(5):
    print(i)
```

Is the equivalent of this in JavaScript:

```javascript
for (let i = 0; i++; i < 5) {
	console.log(i);
}
```

#### Iterating over lists 

A very common use case for a `for` loop is to iterate over a list:

```python
animals = ["lions", "tigers", "bears"]
for animal in animals:
	print(animal)
# => "lions"
# => "tigers"
# => "bears"
```

Python also allows for an optional `else` statement with each of these. With
`while` loops, the `else` statement is executed once the `while` condition is
no longer true. With `for` loops, `else` is executed upon the loop's
completion.

```python
count = 0
while count < 5:
   print(count, " is  less than 5")
   count = count + 1
else:
   print(count, " is not less than 5")
```

```python
count = 15
for i in range(1,count):
  print(i)
else:
  print("done")
```

Again, this `else` is optional and different in nature from a conditional else.
It functions more as a completion handler.

#### Iterating over Dictionaries

- `for` loops can be used to iterate over a dictionary's `key: value` pairs. However, the following is considered to be a Python [anti-pattern](https://en.wikipedia.org/wiki/Anti-pattern):

```python
for key in student:
    print( f"{key} = {student[key]}" )
```

- The preferred way is to use the `items()` method to obtain a [dictionary view object](https://docs.python.org/3/library/stdtypes.html#dictionary-view-objects)...

## Dictionary - Practice Exercise (5 minutes) 

- Define a Python _dictionary_ named **`where_are_my_things`** containing a few items; where  the `keys` are things you have, and the `value` is the location you keep those things.

- Write a `for` loop that iterates over the items in the dictionary and prints each one as _My [thing] is kept [location]_.

## Functions

Functions in Python are much like in JavaScript. For example, like in JavaScript, functions need a an **explicit return**.

In Python, you define a function using the _def_ keyword:

```python
def function_example(param_one, param_two):
  """Example function returning string interpolation of parameters."""
  concat = f"What a splendid function! I've got my {param_one} and {param_two}."
  return concat
```

#### Brief Aside: Docstrings

You may have noticed something like

`"""This function..."""`

within each of our example functions. These are called `docstrings` and are
conventionally used in Python to provide documentation throughout a codebase.
Code will run fine without them, but that would stray from Python's conventions
as well as throw you into linter message hell. Try them out!

&#x1F535; **Activity** FizzBuzz!
```
- create a new file "fizzbuzz"
- Add the code to solve FizzBuzz, explained below.
- You may have solved this in JavaScript or on a whiteboard before!
- If you learn something, or something unexpected happens, share in a thread below
- 7 min
```  

_**Fizzbuzz** is a classic, easy whiteboard problem in interviews. Remarkably, many hiring managers report that a majority of their applicants cannot solve it._

_You write a function that will count from 1-99 printing 1 of four things for each number._
_If the number is divisible by 3, print "fizz"._
_If the number is divisible by 5, print "buzz"._
_If the number is divisible by 3 and 5, print "fizzbuzz"._
_And otherwise, just print the number._

_For the first 20 numbers, your console should look like this:_

```py
1
2
fizz
4
buzz
fizz
7
8
fizz
buzz
11
fizz
13
14
fizzbuzz
16
17
fizz
19
buzz
```

## Additional Resources

-   [Python's Documentation](https://docs.python.org/3/)
