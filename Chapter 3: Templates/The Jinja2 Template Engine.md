## Rendering Templates


**Example 3-1. templates/index.html: Jinja2 template **
```html
<h1>Hello World! </h1>
```

**Example 3-2. templates/user.html: Jinja2 template **
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
