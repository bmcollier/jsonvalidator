Python JSON Checker
===================

*A super-simple library for validating json against a schema.*

Install from pip
----------------

```pip install jsonism```

Why use Jsonism?
----------------
Jsonism is a great alternative to *jsonschema* when you just want to do some simple validation of JSON without your code getting horrendously complicated. 

It's quick to set up a basic schema checker.

Example usage
-------------

### Import the checker

```python
from jsonism.checker import validate
```

### Basic flat objects

```python
schema = {
    "Bob": str,
    "Lucy": int,
    "Bert": bool
}
input = {
    "Bob": "Is Bob",
    "Lucy": 13,
    "Bert": True
}
validate(input, schema)
```

### Lists

```python
input = ["Bob", "Alice", "John"]
schema = [str]
validate(input, schema)
```

### Other stuff
```python
input = {"Usernames": [{"username": "Bob", "age": 23}, {"username": "Bill", "age": 98}]}
schema = {"Usernames": [{"username": str, "age": int}]}
validate(input, schema)
```

But it doesn't have feature *x*!
--------------------------------

Well, I did say it was simple. I plan on allowing optional value validation in a future version. It will always support the very simple initialisation shown above. If you have a burning desire to add a feature, please either post an issue or make a pull request at https://github.com/bmcollier/jsonism.