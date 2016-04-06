## 5. Nested functions, closures and lambdas
### 5.1 Nested functions and closures
Python supports nested function definitions (meaning functions defined inside other functions).  
Here is an example:  

```python
>>> def make_greeter(name):
...     def greeter():
...         print("Hello {}".format(name))
...     return greeter
... 
>>> greet = make_greeter("Adrian")
>>> greet()
Hello Adrian
```

In section 4.6 we have seen that functions are objects.  
So, if functions are objects, it means that a function can receive as parameter another function or it can return a function.  
Returning to our example, we notice that the *make_greeter()* function returns another function (the _greeter()_ function).  
The _greeter()_ function is a _nested function_, because it is defined inside the *make_greeter()* function.   
The *make_greeter()* function is the _enclosing function_ of the _greeter()_ function.  

Another thing we notice is the fact that the _greeter()_ function accesses the _name_ parameter of its enclosing function.  
Because the _name_ parameter is referenced by the _greeter()_ function, its referred object is kept alive after the *make_greeter()* function has finished.  
This makes the _greeter()_ function not only nested function, but also a _closure_. Closures _captures_ the environment needed by their execution.  
