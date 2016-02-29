## 4. Lists, tuples, sets and dictionaries
### 4.1 Lists
#### 4.1.1 Lists basics
_Lists_ are mutable sequences of objects having arbitrary types.  
You can create a list by enclosing values in square brackets. For example:  
```python
>>> countries = ["France", "Great Britain", "Germany", "United States"]
>>> countries
['France', 'Great Britain', 'Germany', 'United States']
```
Lists can be _indexed_ by integers, starting from _zero_.  
To find out the length o a list, use the built-in _len_ function.  
```python
>>> countries[0]
'France'
>>> len(countries)
4
>>> countries[0] = "Japan"
>>> countries
['Japan', 'Great Britain', 'Germany', 'United States']
>>> type(countries)
list
```
Lists can also be _sliced_. By slicing a list we obtain another list.  

```python
>>> european_countries = countries[1:3]
>>> european_countries
['Great Britain', 'Germany']
```

An element can be appended to a list by using the _append()_ method.

```python
>>> countries.append("Argentina")
>>> countries
['Japan', 'Great Britain', 'Germany', 'United States', 'Argentina']
>>> len(countries)
5
```

We can also insert elements in a list by using the _insert()_ method.  

```python
>>> countries.insert(3, "Italy")
>>> countries
['Japan', 'Great Britain', 'Germany', 'Italy', 'United States', 'Argentina']
```

We can delete an element in the list using the _del_ statement.  

```python
>>> del countries[4]
>>> countries
['Japan', 'Great Britain', 'Germany', 'Italy', 'Argentina']
```

You can also delete an element by value, using the _remove()_ method.  
For example, to remove the first element equal to 'Great Britain':    

```python
>>> countries.remove('Great Britain')
>>> countries
['Japan', 'Germany', 'Italy', 'Argentina']
```

We can test if an element belongs to a list using the _in_ operator.  

```python
>>> "Germany" in countries
True
>>> "China" in countries
False
```

Lists can be concatenated using the _+_ operator:  

```python
>>> countries += ["Ireland", "Norway"]
['Japan', 'Germany', 'Italy', 'Argentina', 'Ireland', 'Norway']
```

#### 4.1.2 Iterating over lists
Lists can be iterated using the _for_ statement.  
The iteration is done in the order in which the elements were added to the list.

```python
>>> for country in countries:
>>>     print(country, end='')
Japan Germany Italy Argentina
```

#### 4.1.3 Lists comprehensions
Let's say we want to construct a list with all the even numbers from 1 to 99.  
Of course, we can build it like this:  

```python
>>> numbers = []
>>> for i in range(1, 100):
>>>     if i % 2 == 0:
>>>         numbers.append(i)
```

There is more succint way to accomplish this by using a _list comprehension_:    

```python
>>> numbers = [i for i in range(1, 100) if i % 2 == 0]
```

#### 4.1.4 Copying lists
Let's say we want to create a copy of a list. We might try to proceed like this:  

```python
>>> l1 = [1, 2, 3]
>>> l2 = l1
```

But let's see what happend when we modify l1:  

```python
>>> l1[0] = 4
>>> l1
[4, 2, 3]
>>> l2
[4, 2, 3]
```

We can see that l1 was modified as expected. But we can also see that l2 was also modified.  
This is because _both l1 and l2 refers to the same object_ and that object was modified.

We can create a copy of l1 as follows:  

```python
>>> l1 = [1, 2, 3]
>>> l2 = l1[:]     # Or l2 = list(l1), or l2 = l1.copy()
>>> l1[0] = 4
>>> l1
[4, 2, 3]
>>> l2
[1, 2, 3]
```

So, we can see that, in this case, l2 was not modified when l1 changed.  
We have created a _shallow copy_ of l1. We did not create a _deep copy_.  
To see the difference between a shallow and a deep copy, let's consider another example.

```python
>>> person1 = ["John", 25, ["C", "Java"]]
>>> person2 = person1[:]
>>> person1[1] = 30
>>> person1
['John', 30, ['C', 'Java']]
>>> person2
['John', 25, ['C', 'Java']]
>>> person1[2].append("Python")
>>> person1
['John', 25, ['C', 'Java', 'Python']]
>>> person2
['John', 25, ['C', 'Java', 'Python']]
```

The explanation, in this case, is that both person1[2] and person2[2] reference the same object.  
If we really want to create a deep copy, we can use the _deepcopy()_ function from the standard library _copy_ module.  

```python
>>> from copy import deepcopy
>>> person1 = ["John", 25, ["C", "Java"]]
>>> person2 = deepcopy(person1)
>>> person1
['John', 25, ['C', 'Java']]
>>> person2
['John', 25, ['C', 'Java']]
>>> person1[2].append("Python")
>>> person1
['John', 25, ['C', 'Java', 'Python']]
>>> person2
['John', 25, ['C', 'Java']]
```

We can see that this time, the copy remained unchanged after the original has changed.

### 4.2 Tuples
_Tuples_ are _immutable_ sequences of objects having arbitrary types.  
They share a lot of similarities with lists, but, unlike lists, are immutable.  
Because tuples are immutable they use a more compact representation and allocates less memory than lists. 
Tuples can be created by enclosing a group of values in paranthesis.  

```python
>>> person1 = ("John", 30, 726998343)
>>> person1
('John', 30, 726998343)
>>> len(person1)
3
>>> person1_name = ("John",)           # One element tuple.
>>> person1_name
('John',)
>>> name = ("John")                    # A string, not a tuple.
>>> name
'John'
>>> "John" in person1
True
>>> "Alex" in person1
False
```

Like lists, tuples can be indexed by integers, sliced and concatenated.
Unlike lists, they do not support comprehensions (there is no tuple comprehension)

```python
>>> person1[0]
'John'
>>> person1[1]
30
>>> person1[2]
726998343
>>> person1[1:]
(30, 726998343)
>>> person2 = ("Mike", 25, 726339362)
>>> person2
('Mike', 25, 726339362)
>>> persons = person1 + person2
>>> persons
('John', 30, 726998343, 'Mike', 25, 726339362)
>>> len(persons)
6
```

Tuples can be iterated using the _for_ statement.  

```python
>>> all_persons = (person1, person2)
>>> all_persons
(('John', 30, 726998343), ('Mike', 25, 726339362))
>>> len(all_persons)
2
>>> for name, age, telephone in all_persons:
>>>     print("name:", name)
>>>     print("age:", age)
>>>     print("tel:", telephone)
name: John
age: 30
tel: 726998343
name: Mike
age: 25
tel: 726339362
>>> ('Mike', 25, 726339362) in all_persons
True
>>> ('Jack', 25, 726339362) in all_persons
False
```

Tuples are immutable. Trying to modify a tuple will raise a _TypeError_ exception.

```python
>>> person1[0] = "Michael"
TypeError                                 Traceback (most recent call last)
<ipython-input-21-6b8f99475328> in <module>()
----> 1 person1[0] = "Michael"

TypeError: 'tuple' object does not support item assignment
```

### 4.3 Sets
_Sets_ are _unordered_ collection of objects.  