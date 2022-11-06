---
layout: post
title:  "Getting start to using git(version control)"
date:   2022-11-06 01:23:48 +0900
category: VersionControl
---

# SSH key generation, git initialization, first commit and push
It is now demanding to use a verstion control for your project. It is very helpful in you future development or team work. 

I am going to discuss the easy way to start with

# Prerequisites 
1. First install git in your PC. I will recommand the git bash(command prompt). It is easy to use and developer friendly.
To install git bash or git please click here [Git or git bash](https://git-scm.com/)
2. Please create an account in github if you don't have yet, it is free. [Github](https://github.com/)

## generate ssh key
Go to your command prompt(terminal for mac or linux and powersell for or git bash for windows) and go to root folder
create a folder name `.ssh`
{% highlight python %}
  $ mkdir .ssh
{% endhighlight %}

->Navigate to .ssh folder 

{% highlight python %}
  $ cd .ssh
{% endhighlight %}

To generate ssh key type this command

{% highlight python %}
  $ ssh-keygen(linux or MacOS)
  $ ssh-keygen.exe(for windows)
{% endhighlight %}


It might be ask your password in mac.
It will create two files in .ssh folder
`1) id_rsa`  `2) id_rsa.pub`
We are interested on `id_rsa.pub`
To see the `id_rsa.pub` type this command in command prompt
{% highlight python %}
  $ cat id_rsa.pub
{% endhighlight %}

It will show the some code. Copy it. We will use it in github ssh key setup.

Login github account and go to `settings->SSH and GPG keys`.
Click `New SSH key` button and it will give you an input box. Paste the id_rsa.pub code (we copied before) and click the `Add SSH key` button.

Now we all set. lets start the initialize the git in our project.

## Initialize the git in our project
Navigate to project. For example our project name is `FlaskApp` in Desktop.
{% highlight python %}
  $ cd FlaskApp
{% endhighlight %}

Now type the commands sequentially

{% highlight python %}
  $ git config --global user.name "Your Name"
  $ git config --global user.email "you@youraddress.com"
  $ git config --global push.default matching
  $ git config --global alias.co checkout
  $ git init
{% endhighlight %}

Create an repository in Git hub account.
We have created the project and initialize so we will start from second part of git suggesions. Type the commands sequentially.

…or push an existing repository from the command line
{% highlight python %}
  git remote add origin https://github.com/themeexpress/Test.git
  git branch -M main
  git add .
  git commit -m "Initial commit"
  git push -u origin main
{% endhighlight %}

It push command shows no errors then you are successfully pushed your first commit.

Congratualtions. You are now able to use version control

Happy coding :)

