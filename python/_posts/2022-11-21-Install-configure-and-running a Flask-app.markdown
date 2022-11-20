---
layout: post
title:  "Getting start with Flask"
date:   2022-11-21 01:23:48 +0900
category: Python
---

Flask is a favorite library for web application development in Python. It is simple, light weight and fast growing library and privides extensive area in web application development. If you want to know more about Flask please read the documentation from here [Flask](https://flask.palletsprojects.com/en/2.2.x/)

## Prerequisite 
1. Python installed in your machine
2. PIP installed in your machine

`Note:` I am using MacOS. If you use windows then some command might be change

Lets start..
## Make a new directory
Make a directory to install Flask app

{% highlight python %}
    $ mkdir FlaskApp
    $ cd FlaskApp
{% endhighlight %}

## Create virtual environment for our project
To create virtual environment please execute this command

{% highlight python %}
    $ python -m venv virtual
    # Here virtual is a name. You can named it anything
{% endhighlight %}

## Activate virtual env
{% highlight python %}
    $ source virtual/bin/activate
    # Here virtual is my virtual env name. If your env is another name then used that name
{% endhighlight %}

## Install Flask
{% highlight python %}
    $ pip install flask
{% endhighlight %}

## Create an python file to write our first route for App
{% highlight python %}
    $ touch app.py
{% endhighlight %}

## Initialize the Flask App 
Write folling code in `app.py` file.
{% highlight python %}

    from flask import Flask
    # Create a Flask Instance
    app = Flask(__name__)

    # Create a route decorator
    @app.route('/')
    def index():
        return "<h1>This is Home page</h1>"

{% endhighlight %}

Congratulation!! We have created our first route. Now If we can run our local server then We can see our app.

## Run the Flask App
To run the app we need to export the `app.py`
Please execute following commands serially
{% highlight python %}
    $ export FLASK_APP=app.py   
    $ flask run
{% endhighlight %}

If everything is fine then a local server will start in `http://127.0.0.1:5000` address. If we browse this in our browser then we can see our text "This is Home page"

Congratulation!! You have successfully install and run the Flask App.
`Note:` If you want to deactivate the virtual env then simply type `deactivate`.

Happy Coding :)
