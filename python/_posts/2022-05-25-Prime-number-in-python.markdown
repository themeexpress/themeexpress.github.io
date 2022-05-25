---
layout: post
title:  "Prime number in Python"
date:   2022-05-25 09:23:48 +0900
category: Python
---

{% highlight python %}

  def prime_number(last_number):
    primes = []
    for i in range(2, last_number + 1):
      for j in range(2, int(i ** 0.5) + 1):
        if i%j == 0:
          break
      else:
        primes.append(i)

    return primes

  print(prime_number(22))

{% endhighlight %}

### Output: [2, 3, 5, 7, 11, 13, 17, 19]

Happy Coding :)
