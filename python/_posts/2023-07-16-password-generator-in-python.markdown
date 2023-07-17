---
layout: post
title:  "Strong password generator in Python"
date:   2023-07-16 10:10:48 +0900
category: Python
---
![Keypad](/python/assets/storng-password.png)
Simple example of storing password generator in python. As I said strong password generator it means that there will be a string, numbers, and symbols combination.

{% highlight python %}
  # We have to import the random module to use functions of random like sample()
  class PasswordFunctions:
    def strong_password_generator(self, letters, numbers, symbols):
      small_letters = "abcdefghijklmnopqrstuvwxyz"
      capital_letters = small_letters.upper()
      list_of_letters = list(small_letters + capital_letters)
      list_of_numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
      list_of_symbols = ['<', '>', '?', '{', '}', '@', '*', ')', '(', '&', '$', '#']
      # Get random letters, numbers, and symbols
      amount_of_letter = random.sample(list_of_letters, k=letters)
      amount_of_numbers = random.sample(list_of_numbers, k=numbers)
      amount_of_symbols = random.sample(list_of_symbols, k=symbols)
      temp_password = amount_of_letter + amount_of_numbers + amount_of_symbols
      password = ''.join(str(item) for item in random.sample(temp_password, (letters + numbers + symbols)))
      return password

  password = PasswordFunctions()
  print(password.strong_password_generator(4,5,6))
{% endhighlight %}

### Output:
randomly generated strong password
