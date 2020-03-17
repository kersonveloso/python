# Python

## Basic Data Types

### Primitives

1. Strings `str`
2. Numerical types:
    * Integers `int`
    * Float `float`
<!--You can find out the type of a variable by using the type() method.-->

## Variables

Python variables are dynamically typed.

```python
    x = 1         # integer
    y = 1.0       # float
    z = "string"  # string
```

## Operators

Python permits all basic operator types

```python
    print(10 + 10)   # addition
    print(100 - 10)  # subtraction
    print(10 * 10)   # multiplication
    print(77 / 10)   # division
    print(77 // 10)  # integer division
    print(7 % 2)     # modulo
    print(10 ** 2)   # exponentiation
```
<!--Division by zero is not permited in Python-->

## Type casting

Python is dynamically typed with strong typing meaning that varaibles do not have a type and can be changed to differnt types at runtime. But at the same time it also uses strong typing which means that **type coersion** can't be done, this  `"125" + 10` for exemple leads to a `TypeError`.

The below are permitted though:

```python
    print(125 + 125)                 # "250"
    print("125" + "125")             # "125125"
    print(125 * 4)                   # "500"
    print("125" * 4)                 # "125125125125"
    print("This is a number:", 125)  # "This is a number: 125"
```

### Explicit type casting

The process of converting a value to another type is also called type casting. Though implicit type casting isn't allowed in Python you will often find yourself in need to define an explicit type conversion within your code.

```python
    f = 3.14        # the type is float
    print(type(f))  # <class 'float'>
    s = str(f)      # converting float to string
    print(type(s))  # <class 'str'>
    i = int(f)      # while converting a float value    to   an integer its fractional part is discarded
    print(i)        # 3
    print(type(i))  # <class 'int'>
    f = float(i)    # converting integer to float
    print(f)        # 3.0
    print(type(f))  # <class 'float'>
```

## Function

### Built-in functions

```python
    # finding the length of an object
    print(len(number))  # 3

    # converting types
    integer = int(number)
    float_number = float(number)
    print(str(float_number))  # "111.0"

    # adding and rounding numbers
    my_sum = sum((integer, float_number))
    print(my_sum)  # 222.0
    print(round(my_sum))  # 222

    # finding the minimum and the maximum
    print(min(integer, float_number))  # 111
    print(type(max(integer, float_number, my_sum)))  # <class   'float'>

    print(input())  # permits the user to input data
```

## Numbers

### Reading numbers from user input

 `input()` returns a string, to use a number it has to be converted:

 ```python
    a_int = int(input())
    a_float = float(input())
```

## Strings

### String methods

#### 1. "Changing" a string

The first group of string methods consists of the ones that "change" the string in a specific way, that is they return the copy with some changes made.

Here’s a list of common string methods of that kind:

* `str.replace(old, new[, count])` replaces all occurrences of old with the new. The count argument is optional, and if it is specified, only the first count occurrences are replaced.

* `str.upper()` converts all characters of the string to the upper case.

* `str.lower()` converts all characters of the string to the lower case.

* `str.title()` converts the first character of each word to upper case.

* `str.swapcase()` converts upper case to lower case and vice versa.

* `str.capitalize()` changes the first character of the string to the upper case and the rest to the lower case.

#### 2. "Editing" a string

Often, when you read a string from somewhere (a file or the input) you need to edit it so that it contains only the information you need. For instance, the input string can have a lot of unnecessary whitespaces or some trailing combinations of characters. The "editing" methods that can help with that are `strip()`, `rstrip()` and `lstrip()`.

* `str.lstrip([chars])` removes the leading characters (i.e. characters from the left side). If the argument `chars` isn’t specified, leading whitespaces are removed.

* `str.rstrip([chars])` removes the trailing characters (i.e. characters from the right side). The default for the argument `chars` is also whitespace.

* `str.strip([chars])` removes both the leading and the trailing characters. The default is whitespace.

```python
    whitespace_string = "     hey      "
    normal_string = "incomprehensibilities"

    # delete spaces from the left side
    whitespace_string.lstrip()  # "hey      "

    # delete "i" or "s" or "is" from the left side
    normal_string.lstrip("is")  #   "ncomprehensibilities"

    # delete spaces from the right side
    whitespace_string.rstrip()  # "     hey"

    # delete "i" or "s" or "is" from the right side
    normal_string.rstrip("is")  #   "incomprehensibilitie"

    # no spaces from both sides
    whitespace_string.strip()  # "hey"

    # delete trailing "i" or "s" or "is" from both  sides
    normal_string.strip("is")  # "ncomprehensibilitie"
```

Keep in mind that the methods `strip()`, `lstrip()` and `rstrip()` get rid of all possible combinations of specified characters:

```python
    word = "Mississippi"
    print(word.lstrip("ips"))  # "Mississippi"
    print(word.rstrip("ips"))  # "M"
    print(word.strip("Mips"))  # ""
```

#### 3. Boolean search in a string

Other two useful methods are `startswith()` and `endswith()` that search for the particular pattern in the immediate beginning or end of a string and return True if the pattern is found. Here's the basic syntax of those methods with some simple examples:

```python
    email = "email_address@something.com"
    email.startswith("www.")  # False
    email.endswith("@something.com")  # True
```

Optional arguments `start` and `end` can be added, and in this case, the area of search is delimited by `start` and `end` parameters.

```python
    # syntax: str.startswith(pattern, start, end)

    email = "My email address is 'my_email@something.   com'"
    email.startswith("email", 20)  # False
    email.endswith("@", 20, 30)  # True
```

## Membership testing

Most programs in Python use **containers**, these are data types that allow you to work with any number of objects. You can think of them as real containers filled with numerous things. The way objects are arranged in a container depends on the container type. Examples of built-in Python containers include lists, tuples, sets, dictionaries, strings, and bytes. You will meet these containers later!

When working with containers, you often have to check if a value is present in your container. In Python, operators `in` and `not in` are used for this purpose. The syntax is the same for all containers: `value in container` returns `True` if value exists in container and `False` otherwise. The `not in` operator does the opposite thing, it returns `True` if value does not exist in container.
