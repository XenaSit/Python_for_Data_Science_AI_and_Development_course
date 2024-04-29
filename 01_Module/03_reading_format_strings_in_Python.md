# Reading: Format Strings in Python

#### Estimates effort: 5 mins

Format strings are a way to inject variables into a string in Python. They are used to format strings and produce more human-readable outputs. There are several ways to format strings in Python:

## > String interpolation (f-strings)

Introduced in Python 3.6, f-strings are a new way to format strings in Python. They are prefixed with 'f' and use curly braces {} to enclose the variables that will be formatted. For example:

    name = "John"
    age = 30
    print(f"My name is {name} and I am {age} years old.")
    Copied!
    This will output:
    My name is John and I am 30 years old.


## > str.format()

This is another way to format strings in Python. It uses curly braces {} as placeholders for variables which are passed as arguments in the format() method. For example:

    name = "John"
    age = 50
    print("My name is {} and I am {} years old.".format(name, age))
    Copied!
    This will output:
    My name is John and I am 50 years old.

## > % Operator

This is one of the oldest ways to format strings in Python. It uses the % operator to replace variables in the string. For example:

    name = "Johnathan"
    age = 30
    print("My name is %s and I am %d years old." % (name, age))
    Copied!
    This will output:
    My name is Johnathan and I am 30 years old.

Each of these methods has its own advantages and use cases. However, f-strings are generally considered the most modern and preferred way to format strings in Python due to their readability and performance.

## > Additional capabilities

F-strings are also able to evaluate expressions inside the curly braces, which can be very handy. For example:

    x = 10
    y = 20
    print(f"The sum of x and y is {x+y}.")
    Copied!
    This will output:
    The sum of x and y is 30.