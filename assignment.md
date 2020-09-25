# Python I - Assignment

The Python I assignment has three components

- Practice code execution
- Practice with data types
- Practice with strings and lists

> Note that this assignment assumes you have a working installation of Python and that you have access to a Terminal.

## Instructions

We'll be working through problems designed to provide both practice and additional context with the things your have 
learned.  The goal of is to begin to get comfortable writing very basic Python and executing the code in a variety of 
ways.  To answer these questions you will have to create Python scripts that you execute.  `print` statements are 
useful for iterating on and debugging code. Although, 
[print formatting](https://docs.python.org/3/tutorial/inputoutput.html) is not addressed directly in the following 
questions you should do your best to ensure print statements produce thoughtful outputs.
 

We will learn later on that all the data types in Python are 
[Python classes](https://docs.python.org/3/tutorial/classes.html) or objects.  Objects can have data attached to them 
and they can have functions or definitions attached to them.  The latter are referred to as methods.  

To *see* the things associated with your object you can use the command `dir`.

```python
x = 3.1416
print(dir(x))
```

In this exercise we practice with basic data types, strings and lists exploring many of the available methods that help 
make these fundamental units of Python so useful in day to day applications.

## Part 1 - Practice with code execution

There's no better way to learn a programming language than to try and solve real problems with it. To that end, this 
assignment will present the different ways that you may construct a workflow to solve small problems.

In subsequent lessons we will show you how to import code into Jupyter (technically an IPython environment) among other 
ways of interacting with your code, but for now we will keep the focus on scripts (code as part of a text file).

> Although Jupyter notebooks are convenient.  They are not an ideal place to store your source code--use files for this.

The convention for programmers is to use a [text editor](https://en.wikipedia.org/wiki/Text_editor) to edit these files.
Jupyter does provide a function to create and edit text files, but other programs like [atom](https://atom.io/) or 
[VS Code](https://code.visualstudio.com/) are better suited for this purpose.

### QUESTION 1

Open a new file in your text editor in preparation to create a simple script.  You should give your script a short name 
that quickly describes what it does.  In this case you could use the name `calculate_revenue.py`.  Python 
scripts are appended by convention with the file extension `.py`.

As a reminder `revenue` is the amount of gross income produced through sales of products or services.  For the purposes 
of this exercise let's use the following formula.

<img src="https://render.githubusercontent.com/render/math?math=\textrm{revenue} = \textrm{sales} \times \textrm{average_price}">
<p></p>

In your Python script declare the following variables.  Be sure to add comments to your code to keep it as readable as 
possible.

```python
sales = 150
average_price = 2100
cogs_percentage = 0.59
```

Let's assume these numbers represent a full year of sales.  Calculate the following terms: `annual_gross_revenue`,
`monthly_gross_revenue`, and `quarterly_gross_revenue`.  This is really just an estimate since you do not have all the 
data---simple division is all you need.  After you have declared these variables use `print` statements 
to ensure that the values are shown in the terminal when you execute the script. You should be using the string 
[format()](https://docs.python.org/3/library/stdtypes.html#str.format) method to ensure decent looking output.  In this 
case that means that the values are [rounded](https://docs.python.org/3/library/functions.html#round) and presented with 
only two significant digits.

Be sure that you can:

- Execute your script directly from the command line
- Execute your script from IPython or Jupyter using the magic command `run`

### QUESTION 2

Net revenue accounts for the cost of goods sold or [COGS](https://en.wikipedia.org/wiki/Cost_of_goods_sold).  For our 
example net revenue can simply be 
 
<img src="https://render.githubusercontent.com/render/math?math=\textrm{net_revenue} = \textrm{gross_revenue-cogs}">
<p></p> 

and when you proceed to calculate `cogs` you may make the assumption that it is just a percentage of gross revenue.
 
Net revenue accounts for the amounts associated with discounts, production, shipping, and much more.  Add another 
section to your python script that summarizes the different net revenues. 

## Part II - practice with data types

### QUESTION 3

Throughout this course we will introduce you to many of the built-in functions that contribute to the Python ecosystem.
One such function [input()](https://docs.python.org/3/library/functions.html#input) allows you to gather input data 
during code execution.  

In your Python script replace the hard-coded variable for `sales` in your script with `sales = input("Enter total sales:")` 
and then execute the code again.  To ensure your script runs without errors you will also need to cast the value in sales 
from a string into a a float.  To check if it is a valid string the built-in string method `isnumeric()` can be used. 

> HINT: use print messages to help debug your code

If you are a more advanced student you should try to include some input validation in your script and provide the user 
with meaningful error messages.  The input coming from the command line in this case will always default to a string, 
but you will one day write functions that take input from other sources and so you will need to get accustomed to 
working with and casting between different data types.  The built-in function 
[isinstance()](https://docs.python.org/3/library/functions.html#isinstance) is particularly useful for input validation.
  
To better equip yourself for handling different situations you should be using Python's interactive environments like 
a sandbox.  If you are unsure how something might behave you should try it. For example, in an interactive Python 
environment try casting a Boolean into a float.

## Part III - More with data types, strings and lists

### QUESTION 4 

Create a new Python script.  We are going to work with `revenue` based on monthly data.  Use the following data
for sales:

```python
jan_sales = [1834., 2563., 3317., 2606., 2375., 1918.,  812., 1680., 2492., 2776., 2390., 2297.]
feb_sales = [2148., 1745., 2190., 1863., 2589., 2345., 2724., 2239., 2785., 1483., 2038., 2021.]
mar_sales = [1968., 1718., 1882., 1634., 2126., 1252., 2538., 2837., 1223., 2034., 1611., 2791.]
apr_sales = [2496., 2733.,  706., 2386., 3382., 1844., 1440., 2594., 1978., 2023., 2559., 1577.]
may_sales = [2832., 1681., 1954., 1685., 1801., 2294., 1732., 1638., 1949., 2676., 2329., 2370.]
jun_sales = [2335., 2538., 2186., 2186., 2622., 2564., 1269., 3124., 1286., 1689., 2627., 1345.]
jul_sales = [2675., 1651., 1957.,  853., 2229., 2990., 3148., 2917.,  952., 1583., 2447., 2491.]
aug_sales = [2520., 2540., 1756., 1562., 3657., 2941.,  972., 2258., 1413., 1779., 2503., 2860.]
sep_sales = [1827., 2003., 1349., 1858., 1370., 1076., 2897., 2238.,   91., 1951., 2509., 2933.]
oct_sales = [2380., 2467., 1273., 3169., 1192., 2219., 2195., 3157., 2912., 2012.,  722.,  922.]
```

Your new script should produce the same print statements you did in the previous script.  The changes will be:

1. Change the `input` to be the cogs_percentage

2. You will need to determine `sales` and `average_price` from the sales data contained in the above lists.

Some of the functions that will help you here are [sum()](https://docs.python.org/3/library/functions.html#sum) and 
[len()](https://docs.python.org/3/library/functions.html#len).

If you are already comfortable with basic Python you could determine `sales` and `average_price` with either NumPy or 
Pandas, which is how you would handle data like these in practice.

### QUESTION 5

We have already been introduced to many of the 
[built-in functions](https://docs.python.org/3/library/functions.html#len) in Python.  In this exercise we will be 
getting some practice with lists and strings.  There are several ways to manipulate these types of iterables.  We are 
going to use the [string module](https://docs.python.org/3/library/string.html) to showcase some of Python's 
additional functionality for working with strings.  We will cover modules in another lesson, but at a high level we 
are exposing access to additional Python tools.  We will also leverage the 
[random module](https://docs.python.org/3/library/random.html) to answer this question.

We are going to build a password generator.  Let's make the assumption that every password you generate needs to 
contain at least one symbol, one uppercase letter and one lowercase letter.

1. Create an new script named `generate_password.py` or something similar.  

```python
import string
import random

source1 = string.ascii_lowercase
source2 = "!#$%&*+_?@^"
```
 
2. Ensure that your script asks for specified length for the password
3. Create a variable `source3` that has all the uppercase letters
4. Transform `source1`, `source2` and `source3` into lists
5. Use [random.shuffle()](https://docs.python.org/3/library/random.html#random.shuffle) with each of these lists to 
randomize the numbers
6. Use the three sources to generate a password of the specified length
7. Use a print statement to indicate whether or not your password has:
 
    - an uppercase letter
    - a lowercase letter
    - a symbol
    - the correct length

There are many ways to accomplish this. It is okay if your solution does not produce a valid password each time it is run, 
but your print statements should indicate why the password is not valid.  The 
[join() method](https://docs.python.org/3/library/stdtypes.html#str.join) can be useful here.

