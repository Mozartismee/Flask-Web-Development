
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
from flask.ext.bootstrap import Bootstrap
# ...
bootstrap = Bootstrap(app)
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
