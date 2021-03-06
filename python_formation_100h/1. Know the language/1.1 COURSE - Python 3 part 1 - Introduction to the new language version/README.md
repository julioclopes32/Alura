# Python 3 part 1: Introduction to the new language version

We were also able to use Python without installing it on our machine, running it through a web service. There are several websites that offer this service, including [repl.it](https://replit.com/).


## Print()

print can receive:

value is the value we want to print, the ellipses indicate that the function can receive more than one value, just separate them with a comma.
sep is the separator between values, by default the separator is a blank.
end is what will happen at the end of the function, by default there is a newline, a newline (\n).
We can press the Q key to exit the function documentation and CTRL + C or CTRL + D to exit the Python help console. Back in Python's own console, we can test the print function with the values ​​we saw:
```
>>> print("Brazil", "won", 5, "world titles", sep="-")
Brazil-won-5-world titles
```
As we modified the separator, the values ​​are now separated by a hyphen. Let's test the end now, not passing anything to it:
```
>>> print("Brazil", "won", 5, "world titles", end="")
Brazil won 5 world titles>>>
```
A new line is not created, that is, what we put inside the end will be printed at the end of the function.

## type()

The variable's type depends on the value we pass to it. We can "ask" the variable what its type is by passing it to the type function:
```
>>> type(parents)
<class 'str'>
>>> type(amount)
<class 'int'>
```
The value str means that the variable is of type string, as its value is enclosed in double quotes. And int means the variable is of type integer, since we pass an integer value to the variable.

## input()
the input function always returns a text (string). Therefore, it is necessary to convert the returned value to the type of need.

## Variables
Knowing that Python uses dynamic typing, a variable only exists when we assign a value.
There is no static variable declaration in Python, as in languages ​​like C, Java or C#. In these languages, we indicate the type and name of the variables and it already exists.
For example:
```
int age;
```
Note that we only declare the variable's type and name, without having assigned the value.
In Python, the variable only exists when we assign a value, as in the example below:
```
age = 12
```
This makes perfect sense since we don't have an explicit type declaration like in the Java or C# language.

## Variable Patterns (Snake_Case)
Python conventionally uses the Snake_Case pattern for variable names (or identifiers).

An example of variables in Snake_Case are:
```
wife_age = 20
profile_vip = 'Flávio Almeida'
receipts_in_delay = 30
```
In other languages ​​the CamelCase pattern is also used. Same example with CamelCase (which is not the Python default):
```
Wife age = 20
VIPprofile = 'Flávio Almeida'
receiptsOverdue = 30COPY CODE
```
Let's follow the Python pattern in this course, which is Snake_Case!

## Operations
### (Types)
We cannot perform addition, subtraction, etc. math operations involving a string. To solve the problem, we can use the int() function, which converts a string containing a number, into an integer.
ex:
```
print(1+"2")
TypeError: unsupported operand type(s) for +: 'int' and 'str'
```
```
print(1+int("2"))
3
```
### integer division
The // operator is also called integer division and always returns the truncated integer value (no rounding).
```
>>> print(3//2)
1
```

## round()
Round() is a built-in function available with python. It will return you a float number that will be rounded to the decimal places which are given as input.

If the decimal places to be rounded are not specified, it is considered as 0, and it will round to the nearest integer.
```
round(float_num, num_of_decimals)
```
float_num: the float number to be rounded.
num_of_decimals: (optional) The number of decimals to be considered while rounding. It is optional, and if not specified, it defaults to 0, and the rounding is done to the nearest integer.
ex: 
```
>>> round(2.55567,4)
2.5557
```

## String
### String Concatenation
#### simple concatenation
```
rodada = 1
total_de_tentativas = 5
print("Tentativa", rodada, "de", total_de_tentativas)
>>> Tentativa 1 de 5
```
#### .format()
```
rodada = 1
total_de_tentativas = 5
print("Tentativa {} de {}".format(rodada, total_de_tentativas))
>>> Tentativa 1 de 5
```
é importante citar que a função format pode inverter os parâmetros, como um array:
```
rodada = 1
total_de_tentativas = 5
print("Tentativa {1} de {0}".format(rodada, total_de_tentativas))
>>> Tentativa 5 de 1
```
#### f-strings
Starting with Python version 3.6, a new feature has been added to perform string interpolation. This feature is called f-strings or formatted string literals.
This feature works as follows. Let's imagine that we have a variable name:
```
>>> name = 'Matheus'
>>> print(f'My name is {name}')
My name is Matheus
```

## .format()
### decimal numbers
to represent decimal numbers in format, it's best to input ```:f``` to let python know we are inputting a float.
```
>>> print("R$ {:f}".format(1.59))
R$ 1.590000
```
To adjust the decimal number placeholders, we do:
```
>>> print("R$ {:2f}".format(1.59))
R$ 1.59
```
To stablish an certain number size we do:
```
>>> print("R$ {:7.2f}".format(1.5))
R$    1.50
```
in this case, we are going to notice the empty spaces are going to be completed with spaces = ' '.
To complete the empty spaces with 0s, we do:
```
>>> print("R$ {:07.2f}".format(1.5))
R$ 0001.50
```

### Integers
We were able to format whole numbers too, not just floating numbers. For whole numbers, we pass the letter d:
```
>>> print("R$ {:07d}".format(4))
R$ 0000004
```
### Dates
Python has a module called datetime that allows us to, for example, to get the time and date for today.
```
>>> from datetime import datetime
>>> print(datetime.now())
2020-08-08 06:28:42.715243
```
to format the Date, we can use .format():
```
>>> print("Today's date is {:%Y-%m-%d %H:%M}".format(datetime.now()))
Today's date is 2020-08-08 06:29
```

## Iterations
### For
#### For (array)
```
>>> fam = [1.73, 1.68, 1.71, 1.89]
>>> for height in fam :
        print(height)
1.73
1.68
1.71
1.89
```
in this case we are going to iterate throught an array, and we create a variable to iterate, in this case it's ```height```.
#### For (range)
the function range has 3 parameters:
```
range(start, stop, step)
```
- Parameter	Description:
  - start - (Optional). An integer number specifying at which position to start. Default is 0
  - stop - (Required). An integer number specifying at which position to stop (not included).
  - step - (Optional). An integer number specifying the incrementation. Default is 1
```
>>> for x in range(3, 16, 3):
        print(x)
3
6
9
12
15
```
#### For (matrix)
```
>>> import numpy as np
>>> arr = np.array([[1, 2, 3], 
                    [4, 5, 6]])
>>> for x in arr:
        for y in x:
            print(y)
1
2
3
4
5
6
```

## Iteration (Stop) - For and While
### break
The break statement in Python terminates the current loop and resumes execution at the next statement, just like the traditional break found in C. 

The break statement can be used in both while and for loops.
```
>>> for x in range(3, 16, 3):
        print(x)
        break
>>> print("hello")
3
hello
```
### continue
The continue statement in Python returns the control to the beginning of the while loop. The continue statement rejects all the remaining statements in the current iteration of the loop and moves the control back to the top of the loop.

The continue statement can be used in both while and for loops.
```
>>> for x in range(3, 16, 3):
        print(x)
        continue
        print(x+1)
3
6
9
12
15
```
### else
Python supports to have an else statement associated with a loop statements.
- If the else statement is used with a for loop, the else statement is executed when the loop has exhausted iterating the list. generally this happens when you always have to execute something at the end of the loop
- If the else statement is used with a while loop, the else statement is executed when the condition becomes false.
```
>>> for x in range(3, 16, 3):
        print(x)
    else:
        print("finish loop")
3
6
9
12
15
finish loop
```
## Random numbers
To generate a random number between 0 - 1.0:
```
>>> import random
>>> random.random()
0.6022965518496559
```
To generate a random float between a - b:
```
>>> random.uniform(a, b)
3.1800146073117523
```
To generate a random float between a - b:
```
>>> random.randint(0, 100+1)
25
```

## Importing Settings
When we run a file directly in Python, it internally creates a variable and fills it. And through this variable we can make a query, because if it is filled, it means that the file was executed directly, but if the variable is not filled, then it means that the file was only imported.

This variable is ```__name__```, and it is filled with the value ```__main__``` if the file is executed directly. Let's then do if to check if it is filled or not:
```
import random

def jogar():
    # código omitido

if (__name__ == "__main__"):
    jogar()
```
In this case if this file is imported it will execute nothing. But, if it is executed directly it's going to execute the function ```jogar()```