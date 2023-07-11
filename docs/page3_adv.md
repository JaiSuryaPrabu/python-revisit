# Advanced Topics

## Lambda
### History
* Lambda functions came from **lambda calculus**
* It can *abstract* completely
* **Lambda calculus** is **Turing complete**

### Examples
Basic representation of a `function` in python
``` py linenums="1"
def number(x):
    return x
```
`number()` accepts `x` value and returns it.

By using `lambda` we can:
``` py linenums="1"
lambda number x : x
```

Syntax for the lambda function:
`lambda <function_name> <arguments> : <function_code>`