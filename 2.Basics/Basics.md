## 2. Python basics
### 2.1 Lines
The statement separator in python is the _semi-colon_(__;__). However, it must be used only when writing more than one statement per line.
<br>The line continuation character is the back-slash (__\__).<br/>
Everything after "#" on a line is treated as comments (is ignored by the interpreter).

Practice:
<br>Enter the following code in a file named _greet.py_.<br/>

```python
# The name variable will contain the string entered.
name = input("Enter the user name: ")
print("Hello " + name) # Display the user name using the print function.
```
Than, execute:

    python greet.py

from a terminal. Notice the displayed message.

### 2.2 Blocks
Python represents block structure using indentation. Other languages uses brackets or _begin/end_ keywords.
<br>This is belived by many to increase the code redability.<br/>
_The indentation level is recommended to be set to 4 spaces and no hard tabs should be used._

### 2.3 Variables and basic built-in types
A variable is a name (a tag) associated (bound) to an _object_. Each object has a type.
<br>Python has many built-in types (all of them are presented in the official documentation: https://docs.python.org/3/library/stdtypes.html)<br/>
Here are some basic built-in types.

#### 2.3.1 Numeric types
Python has integers, floats and complex numbers.
For example:

```python
weight = 80           # An integer.
pi = 3.14             # A float.
c = complex(2.5, 3.5) # A complex number (2.5 + j * 3.5).
```
#### 2.3.2 Booleans
A boolean object can be either _True_ or _False_.

#### 2.3.3 Strings
Strings are used to handle _texts_. Strings are sequences of _Unicode code points_.
<br>Strings are also immutable (unmodifiable). <br/>
There are several ways to specify strings:

```python
s1 = 'Single quoted string'
s2 = "Double quoted string"
s3 = '''Multiline single-quoted string.
This can span on several lines.'''
s4 = """Multiline double-quoted string.
This can span on several lines."""
```
The length of the string can be obtain using the _len_ function:

```python
>>> s = "This is a string"
>>> len(s)
>>> 16
```

Each string can be indexed. The first code point is at index 0.
The last one is at index length of string minus one.
<br>The index can also be a negative integer (unlike in many other languages).
In that case, the index is counted starting from the end of the string (-1 is the last code point in the string) <br/>
Indexing a string will result in a string with length 1.

```python
>>> lang = "Python"
>>> lang[0]
>>> 'P'
>>> lang[len(lang) - 1]
>>> 'n'
>>> lang[-1]
>>> 'n'
```

A string can also be _sliced_.
One method of slicing a string is by specifying the start and end indexes (the end index is non-inclusive).
The start or end index can also be omitted.

```python
>>> lang = "Python"
>>> lang[0:1]
>>> 'P'
>>> lang[0:2]
>>> 'Py'
>>> lang[0:-1]
>>> 'Pytho'
>>> lang[0:0]
>>> ''
>>> lang[0:]
'Python'
>>> lang[1:]
'ython'
>>> lang[:]
'Python'
>>> lang[:-1]
'Pytho'
>>> lang[:-2]
'Pyth'
```

A string can also be sliced by specifying an extra paramter: a _stride_.

```python
>>> lang = "Python"
>>> lang[::1]
'Python'
>>> lang[::2]
'Pto'
>>> lang[::3]
'Ph'
```

As mentioned, strings are _immutable_. Trying to modify a string will raise an exception, which is a mechanism usually used to signal an error
condition.

```python
>>> lang = "Python"
>>> lang[0] = "C"
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object does not support item assignment
>>> lang = "C" + lang[1:]
>>> lang
'Cython'
```

You can test if a string is a substring in another string by using the _in_ keyword.

```python
test = "Py" in "Python" # test will be True
test = "C" in "Python"  # test will be False
```

Strings can be concatenated by using the __+__ operator.

```python
s = "Hello" + " Python" # s will be "Hello Python"
```

There are a lot of operations that can be done of strings via string _methods_.
A few examples:

```python
>>> lang = "python"
>>> lang.index('h')   # First 'h' is at index 3.
3
>>> lang.capitalize() # Make element at index 0 upper-case.
'Python'
>>> lang.upper()      # Make all elements upper-case.
'PYTHON'
>>> lang = "   python  "
>>> lang
'   python  '
>>> lang.strip()      # Remove all spaces at beggining and end.
'python'
```

Consult the official documentation for more string methods.

#### 2.3.4 Bytes

Bytes (byte strings) objects are _immutable_ sequences of single byte values.
The elements can be specified as _ASCII_ characters or as _hexadecimal digits_.
They presents many similarities with strings. Many constructions which applies to strings also applies to byte strings.

```python
>>> s1 = b"Hello" + b" world"
>>> s1
b'Hello world'
>>> s1[0] = 'C'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'bytes' object does not support item assignment
>>> s2 = b"\x48\x65\x6c\x6c\x6f\x20\x77\x6f\x72\x6c\x64"
>>> s2
b'Hello world'
>>> len(s2)
11
>>> s2[0:5]
b'Hello'
>>> s2.upper()
b'HELLO WORLD'
```

Strings can be _encoded_ into byte strings, using some specified _encodings_.
Ones of the most used encodings are _UTF-8_ and _ASCII_.
<br>Similary, byte strings can be _decoded_ into strings.<br/>

```python
>>> "Hello world".encode(encoding='UTF-8')
b'Hello world'
>>> b"Hello world".decode(encoding='UTF-8')
'Hello world'
```

#### 2.3.5 NoneType

_NoneType_ is a type that has only one value, _None_. _None_ is frequently used to indicate _the absence of a value_.
This is conceptually similar to a _null_ reference in _Java_.
