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
    <p>A value from a dictionary: {{ mydict['key'] }}.</p>
    <p>A value from a list: {{ mylist[3] }}.</p>
    <p>A value from a list, with a variable indexy: {{ mylist[myintvar] }}.</p>
    <p>A value from an object's method: {{ mydict.values() }}.</p>
</body>
</html>
```
