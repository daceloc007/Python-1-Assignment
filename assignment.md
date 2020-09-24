# Python I - Assignment

The Python I assignment has three components

- Practice code execution
- Practice with data types
- Practice with lists

> Note that this assignment assumes you have a working installation of Python and that you have access to a Terminal.

## Instructions

We'll be working through problems designed to get your hands on everything you learned - strings and lists 
(and their methods), along with iteration using for loops. The goal of is to begin to get comfortable writing very 
basic Python and executing the code in a variety of ways. 

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

$$
\textrm{revenue} = \textrm{sales} * \textrm{average_price}
$$

In your Python script declare the following variables.  Be sure to add comments to your code to keep it as readable as 
possible.

```python
sales = 150
average_price = 2100
cogs_percentage = 0.59
```

Let's assume these numbers represent a full year of sales.  Calculate the following terms: `annual_gross_revenue`,
`monthly_gross_revenue`, and `quarterly_gross_revenue`.  After you have declared these variables use `print` statements to ensure 
that the values are shown in the terminal when you execute the script. If are a more advanced student and you need more 
of a challenge for this exercise that the print statements use the `format` method and that the values are rounded and 
presented with only two significant digits. 

Be sure that you can:

- Execute your script directly from the command line
- Execute your script from IPython or Jupyter using the magic command `run`

### QUESTION 2

Net revenue accounts for the cost of goods sold or COGS.  For our example net revenue can simply be 
 
$$
\textrm{net_revenue} = {gross_revenue-cogs}
$$
 
and then too calculate `cogs` you may make the assumption that it is just a percentage of gross revenue.
 
Net revenue accounts for the amounts associated with discounts, production, shipping, and much more.  Add another 
section to your python script that summarizes the different net revenues. 

### QUESTION 3

Throughout this course we will introduce you to many of the built-in functions that contribute to the Python ecosystem.
One such function [input()](https://docs.python.org/3/library/functions.html#input) allows you to gather input data 
during code execution.  

Replace the hard-coded variable for `sales` in your script with `sales = input("Enter total sales:")` and then execute
the code again.  To ensure you script runs without errors you will also need to cast the value in sales from a string 
into a a float.  Experiment with reasonable and unreasonable inputs to get a sense for what kind of error messages are 
produced.  Use print statements along with the built-in function 
[isinstance()](https://docs.python.org/3/library/functions.html#isinstance) to keep track of what happens with 
different types of inputs (int, float, str, boolean).  

If you are a more advanced student include some input sanitization in your script and provide the user with 
meaningful error messages.

> HINT: use print messages to help debug your code

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


