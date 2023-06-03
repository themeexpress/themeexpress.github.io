---
layout: post
title:  "Write a method that takes one argument (String), and return an Array of sequence of number need to type the String with cell phone keypad."
date:   2023-06-04 01:23:48 +0900
category: ps_dsa
---

# Problem picture
![Keypad](/ps_dsa/assets/images/keypad.png)

## Sample input output
{% highlight Ruby %}

`a` = `2`
`b` = `22`
`z` = `9999`

# type(‘c’)
output => [222]

type('thanks')
# Output => [8, 44, 2, 66, 55, 7777]

{% endhighlight %}

## Solution

{% highlight Ruby %}

def type(msg)
  data = {
    'a'=>[2],
    'b'=>[22],
    'c'=>[222],
    'd'=>[3],
    'e'=>[33],
    'f'=>[333],
    'g'=>[4],
    'h'=>[44],
    'i'=>[444],
    'j'=>[5], 
    'k'=>[55],
    'l'=>[555],
    'm'=>[6],
    'n'=>[66],
    'o'=>[666],
    'p'=>[7],
    'q'=>[77],
    'r'=>[777],
    's'=>[8],
    't'=>[88],
    'u'=>[888],
    'v'=>[9],
    'w'=>[99],
    'x'=>[999],
    'y'=>[9999],
    'z'=>[99999]
  }
  result = []
  msg.each_char do |char|
    if data.key?(char)
      result += data[char]
    end
  end
  return result
end

print(type('abc'))

{% endhighlight %}


Congratualtions. Problem is solved.

Happy coding :)

