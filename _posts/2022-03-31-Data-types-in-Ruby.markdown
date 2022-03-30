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

{% endhighlight %}

