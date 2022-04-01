---
layout: post
title:  "Data types in Ruby!"
date:   2022-03-31 0:23:48 +0900
categories: Ruby
---
Ruby is a losing type language means you don't need to mention the data type. It is easy to use and memorize. 
There are 4 basic types in Ruby they are:

 1. Number
 2. Strings
 3. Symbols
 4. Booleans


`1. Number (Integer and Float)`

{% highlight Ruby %}
# Integer
# Addition
1 + 1   #=> 2

# Subtraction
2 - 1   #=> 1

# Multiplication
2 * 2   #=> 4

# Division
10 / 5  #=> 2

# Exponent
2 ** 2  #=> 4
3 ** 4  #=> 81

# Modulus (find the remainder of division)
8 % 2   #=> 0  (8 / 2 = 4; no remainder)
10 % 4  #=> 2  (10 / 4 = 2 with a remainder of 2)
17 / 5  #=> 3, note that it is not 3.4

# Floats
17 / 5.0 #=> 3.4 

# Converting interger to float and float to integer
19.to_f #=> 19.0
19.0.to_i #=> 19

# Some useful number methods
# even and odd
200.even? #=> true
201.even? #=> false

199.odd? #=> true
200.odd? #=> false

{% endhighlight %}

**Some useful number methods**
**even and odd**

{% highlight Ruby %}

200.even? #=> true
201.even? #=> false

199.odd? #=> true
200.odd? #=> false

{% endhighlight %}

`2. Strings`

In Ruby we define string into the single quote or double quote. There are many useful string methods are available in Ruby.

{% highlight Ruby %}
# assign a string
str = "I am string"
str.class #=> String
{% endhighlight %}

**Some useful string methods**
*Concatenation*

{% highlight Ruby %}
str = "frist string"
str2 = "second string"
str.concat(str2) #=> frist stringsecond string
# there are some others way
p str + str2 #=> frist stringsecond string
p str << str2 #=> frist stringsecond string
{% endhighlight %}
*Accessing String as like array elements*

{% highlight Ruby %}

str = "Ruby on Rails"
p str[0] #=> "R"

"Ruby on Rails"[0]      #=> "R"
"Ruby on Rails"[0..1]   #=> "Ru"
"Ruby on Rails"[0, 4]   #=> "Ruby"
"Ruby on Rails"[-1]   #=> "s"

{% endhighlight %}

**capitalize**

{% highlight Ruby %}
"ruby on rails".capitalize #=> "Ruby On Rails"
{% endhighlight %}

**include?**

{% highlight Ruby %}
"ruby on rails".include?("on")  #=> true
"ruby on rails".include?("z")   #=> false
{% endhighlight %}

**upcase**

{% highlight Ruby %}
"ruby".upcase  #=> "RUBY"
{% endhighlight %}

**downcase**

{% highlight Ruby %}
"RUBY".downcase  #=> "ruby"
{% endhighlight %}

**empty?**

{% highlight Ruby %}
"ruby".empty?  #=> false
{% endhighlight %}

**length**

{% highlight Ruby %}
"ruby".length  #=> 4
{% endhighlight %}

**reverse**

{% highlight Ruby %}
"ruby".reverse  #=> "ybur"
{% endhighlight %}

**split**

{% highlight Ruby %}
"Ruby on Rails".split  #=> ["Ruby", "on", "Rails"]
"hello".split("")    #=> ["h", "e", "l", "l", "o"]
{% endhighlight %}

**strip**

{% highlight Ruby %}
" hello, world   ".strip  #=> "hello, world"
{% endhighlight %}

**sub, gsub, insert, delete, prepend**

{% highlight Ruby %}

"he77o".sub("7", "l")           #=> "hel7o"

"he77o".gsub("7", "l")          #=> "hello"

"hello".insert(-1, " dude")     #=> "hello dude"

"hello world".delete("l")       #=> "heo word"

"!".prepend("hello, ", "world") #=> "hello, world!"

{% endhighlight %}


