---
layout: post
title:  "Emoji conversion in Python"
date:   2022-08-12 09:23:48 +0900
category: Python
---

![Emoji conversion](/python/assets/images/emoji_conversion_in_python.png)

About emoji Unicode please read here [Emoji Unicode](https://unicode.org/emoji/charts/emoji-list.html)

{% highlight python %}

  def emoji_converter(message):
    words = message.split(" ")
    emojis = {
        ":)": "\U0001F600",
        ":(": "\U0001F606",
        ":>": "\U0001F61C",
        ":<": "\U0001F917"
    }
    output = ""
    for word in words:
        output += emojis.get(word, word) + " "
    print(output)

message = input("> ")

emoji_converter(message)

{% endhighlight %}

### Output: 

![Emoji conversion](/python/assets/images/emojiOutput.jpeg)


Happy Coding :)
