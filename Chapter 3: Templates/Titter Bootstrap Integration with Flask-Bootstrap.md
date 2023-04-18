
[Bootstrap](http://getbootstrap.com) is an open source framework from Twitter that provide user 
interface components to create clean and attractive web pages that compatible with all modern 
web browsers.

- Responsive design: Bootstrap's fluid grid system and responsive CSS classes allow developers to easily create web pages that look great on any device or screen size.
- UI components: Bootstrap provides a wide range of pre-built UI components, including buttons, forms, navigation menus, modals, and alerts, that can be easily customized and extended to fit your project's needs.
- Customizable styles: Bootstrap includes a variety of built-in styles and themes that can be easily customized using CSS and Sass variables, making it simple to create a unique look and feel for your web pages.
- Cross-browser compatibility: Bootstrap is designed to work seamlessly across all modern web browsers, ensuring that your pages look and function correctly for all users.

### Install
```shell
pip install flask-bootstrap
```
**Example 3-4 shows the initialization of Flask-Bootstrap**
```py
from flask import Flask, render_template
from flask_bootstrap import Bootstrap

app = Flask(__name__)
bootstrap = Bootstrap(app)

@app.route('/')
def index():
    return 'Hello, World!'

@app.route('/user/<name>')
def user(name):
    return render_template('user.html', name=name)

if __name__ == '__main__':
    app.run(debug=True)

```

**Example 3-5. templates/user.html: Template that uses Flask-Bootstrap**
```html
{% exxtends "bootstrap/base.html" %}

{% block title%}Flasky{% endblock %}

{% block navbar %}
<div class="navbar navbar-inverse" role="navigation">
   <div class="container">
      <div class="navbar-header">
        <button type="button" class="navbar-toggle">
          data-toggle="collapse" data-target=".navbar-collapse">
            <span class="sr-only">Toggle navigation</span>
            <span class="icon-bar"></span>
            <span class="icon-bar"> </span>
            <span class="icon-bar"></span>
        </button>
        <a class="navbar-brand" href="/">Flasky</a>
     </div>
     <div class="navbar-collapse collapse">
       <ul class="nav navbar-nav">
         <li><a href="/">Home</a></li>
       </ul>
     </div>
  </div>
</div>

{% endblock %}

{% block content%}
<div class="container">
  <div class="page-header">
    <h1>Hello, {{ name }}!</h1>
  </div>
</div>
{% endblock%}
```

Before running your hello.py, don't forget to configure your [base.html](https://github.com/Mozartismee/Flask-Web-Development/blob/main/Chapter%203:%20Templates/The%20Jinja2%20Template%20Engine.md#inhereitance-basehtml) as we have done on previous section.

**Result**
You could write your name at the end of localhost:5000/user/...., and the web will print out your name.
<img width="1351" alt="截圖 2023-04-18 下午2 45 00" src="https://user-images.githubusercontent.com/108670929/232693860-73313f23-8b2e-48c6-9bdd-6104487d4754.png">


