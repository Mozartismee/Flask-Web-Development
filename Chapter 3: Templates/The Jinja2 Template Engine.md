## Rendering Templates


**Example 3-1. templates/index.html: Jinja2 template**
```html
<h1>Hello World! </h1>
```

**Example 3-2. templates/user.html: Jinja2 template**
```html
<h1>Hello, {{name}}! </h1>
```


**Example 3-3 hello.py Rendering a template**
```py
from flask import Flask, render_template

#...

@app.route('/index')
def index():
  return render_template('index.html')
  

@app.route('/user/<name>')
def user(name):
  return render_template('user.html', name=name)
```

## Variables

```html
<p>A value from a dictionary: {{ mydict['key'] }}.</p>
<p>A value from a list: {{ mylist[3] }}.</p>
<p>A value from a list, with a variable indexy: {{ mydict[myintvar] }}.</p>
<p>A value from an object's method: {{ mydict.somemethod() }}.</p>

```

**Render the templates**
```python
@app.route('/example')
def example():
    mydict = {'key': 'dictionary_value', 'foo': 'bar', 'spam': 'eggs'}
    mylist = ['a', 'b', 'c', 'd', 'e']
    myintvar = 2
    return render_template('example.html', mydict=mydict, mylist=mylist, myintvar=myintvar)

```



**Results**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Example</title>
</head>
<body>
    <p>A value from a dictionary: dictionary_value.</p>
    <p>A value from a list: d.</p>
    <p>A value from a list, with a variable indexy: c.</p>
    <p>A value from an object's method: result_of_somemethod.</p>
</body>
</html>
```

#### filters

```shell
Hello, {{ name | capitalize }}
```
Table 3-1 : Jinja2 variable filters
|Filter name|Description|
|-----------|-----------|
|safe       |renders the value without applying escaping|
|capitalize |Converts the first character of the value to uppercase and the rest to lowercase|
|lower      |Converts the value to lowercase characters|
|upper      |Converts the value to uppercase characters|
|title      |Capitalizes each word in the value|
|trim       |Removes leading and trailing whitespace from the value|
|striptags  |Removes any HTML tags from the value before rendering|
