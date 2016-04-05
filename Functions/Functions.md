## 4. Functions  
### 4.1 Introduction
Non-trivial programs can use functions for reasons such as modularity, code reuse and maintainability.  
These desiderates are extremely important in software development.  
In python, functions are defined using the _def_ keyword.  
Functions have a _name_ and a _body_. They can have _parameters_ and can _return_ values.    
As a first example, this is a simple function which adds two numbers and return their sum.  
```python
>>> def add(a, b):
...     return a + b
... 
>>> add(3, 4)
7
```
Let us identify each component:
- the _name_ of the function is _add_
- the function have two _parameters_, named _a_ and _b_
- the _body_ of the function contains the _statements_ which gets executed when the function is _called_.  
  In our case, the _body_ of the function is: _return a + b_
- the function _returns_ the sum of _a_ and _b_ using the _return_ statement.  

Next, we _call_ our function by passing the numbers _3_ and _4_ as _arguments_.  
Inside the function, _a_ will be a _variable_ which refers the integer value  _3_.  
Similary, _b_ will be a _variable_ referring the integer value _4_.  
After calling the function, the integer value _7_ is returned, as expected.  
This can be visualized as follows:  
![function call](img/add_function_call.png)
