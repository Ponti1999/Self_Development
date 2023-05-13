# Kaggle course

<br/>

This is the very base of python learning. <br/>
'*Learn the most important language for Data Science.*' <br/>
Estimate time: 5 hours <br/>
Free course <br/>

[kaggle cours link](https://www.kaggle.com/learn/python) <br/>

<br/>

## Chapters with description and practice:

### [Hello, Python](https://www.kaggle.com/code/colinmorris/hello-python/tutorial)

*This course covers the key Python skills you’ll need so you can start using Python for data science.* <br/>
*We'll start with a brief overview of Python syntax, variable assignment, and arithmetic operators.* <br/>

*Just for fun, try reading over the code below and predicting what it's going to do when run.* <br/>

```Python
spam_amount = 0
print(spam_amount)

# Ordering Spam, egg, Spam, Spam, bacon and Spam (4 more servings of Spam)
spam_amount = spam_amount + 4

if spam_amount > 0:
    print("But I don't want ANY spam!")

viking_song = "Spam " * spam_amount
print(viking_song)
```

- In this code, we create a variable called spam_amount (we also say that spam_amount is *assigned* the value of 0). <br/>

- After we add 4 to spam_amount -> ***spam_amount = spam_amount + 4*** <br/>
  (Other alternative and mostly used way -> ***spam_amount += 4***) <br/>

- We check whether it's greater then 0 using an if statement. <br/>
  (If = check the statement and if it is true then do something.) <br/>

- If spam_amount is indeed greater than 0, we print the message: "But I don't want ANY spam!". <br/>
  (The spam amount is 4 because of the previous line where we added 4 to spam_amount.) <br/>

- Finally, we multiply the string "Spam " by spam_amount to create the final string stored in viking_song. <br/>
  The spam_amount can be 0 too. In this case the viking_song will be nothing. <br/>
  (If we multiply a string with an integer (number) then it will repeat the string as many times as the number is.) <br/>

<br/>

*Python is prized for its readability and the simplicity* <br/>

**Important!!**
- At the end of the ```if``` there is a ```:``` <br/>
  This is a must have. <br/>
  If we don't put it there then we will get an error. <br/>

- After each ```:``` we have to indent the next line. <br/>
  (We can use ```Tab``` or ```Space``` for this.) <br/>
  (The most common is to use 4 spaces.) <br/>
  (If we don't indent the next line then we will get an error.) <br/>

- Each ```:``` indicate a **new code block**. <br/>
  (The code block is a group of code which belongs together.) <br/>
  (The code block is a group of code which is executed together.) <br/>

<br/>

*Strings can be marked either by double or single quotation marks.* <br/>
*A float is a number with a decimal place - very useful for representing things like weights or proportions.* <br/>

*Variable: spam_amount = 0* <br/>
The variable name is spam_amount and we allocate a value to it (0 in this case). <br/>

If we want to get the type of the variable we can use the ```type()``` function. <br/>
It will return the type of the variable e.g int, float, str. <br/>

We can use the ```print()``` function to print out the print contained element. <br/>
e.g. ```print(spam_amount)``` or ```print(type(spam_amount))``` <br/>
<br/>

<img src="img/arithmetic_operators.jpg" style="height: 400 px; width:450 px;"/> <br/>

*The ```//``` operator gives us a result that's rounded down to the next integer.* <br/>

*Order of operations*: <br/>
*The arithmetic we learned in primary school has conventions about the order in which operations are evaluated.* <br/>


*Builtin functions for working with numbers* <br/>
*min and max return the minimum and maximum of their arguments, respectively...*

```Python
print(min(1, 2, 3))
```
Output: 1 <br/>
<br/>

```Python
print(max(1, 2, 3))
```
Output: 3 <br/>
<br/>

*abs returns the absolute value of an argument:*
```Python
print(abs(-32))
```
Output: 32 <br/>
<br/>

```Python
print(float(10))
```
Output: 10.0 <br/>
<br/>

```Python
print(int(3.33))
```
Output: 3 <br/>
<br/>

```Python
print(int('807') + 1)
```
Output: 808 <br/>
<br/>

## [Exercise](https://www.kaggle.com/code/colinmorris/hello-python?scriptVersionId=126670476&cellId=40)

-------------------------

### [Functions and Getting Help](https://www.kaggle.com/code/colinmorris/functions-and-getting-help)

If we forget how a fuction works we can use the ```help()``` function. <br/>
Display the function's arguments and a brief English description of what the function does. <br/>
e.g. ```help(round)``` <br/>

Help on built-in function round in module builtin: <br/>
round(number, ndigits=None)<br/>

    Round a number to a given precision in decimal digits.

    The return value is an integer if ndigits is omitted or None.  Otherwise
    the return value has the same type as the number.  ndigits may be negative.

<br/>

Defining functions <br/>

*Builtin functions are great, but we can only get so far with them before we need to start defining our own functions.* <br/>

*General syntax for a function definition in Python is as follows:*

```Python
def name_of_function(argument1:str, argument2:int, argument3:bool=False, ...):
    # Do stuff here
    return value_to_return
```

If we use the ```help(name_of_function)``` then we will get the following: <br/>

    Help on function least_difference in module __main__:
    name_of_function(argument1, argument2, argument3=False, ...)

<br/>

We need to document our function if we want the informations to display when we call it. <br/>
There are plenty of documentation styles. <br/>
The most common is the following: <br/>
- Doxygen
- Sphinx
- ...

<br/>

```Python
def least_difference(a, b, c):
    """Description of the function.
    What it does and what it returns.

    And an example if it needed.
    """

    # Do stuff here
    return value_to_return
```

<br/>
<br/>

*Functions that don't return*: <br/>

*Python allows us to define such functions. The result of calling them is the special value None. <br/>
(This is similar to the concept of "null" in other languages.)* <br/>

*Function with side effects may do something useful without returning anything* <br/>
