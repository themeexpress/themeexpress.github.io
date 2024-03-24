---
layout: post
title:  "Hangman game in Python"
date:   2024-03-24 10:10:48 +0900
category: Python
---
![Hangman](/python/assets/images/Hangman.png)
![Hangman](https://en.wikipedia.org/wiki/Hangman_(game))
Simple example of storing password generator in python. As I said strong password generator it means that there will be a string, numbers, and symbols combination.

{% highlight python %}
  # We have to import the random module to use functions from random module like sample(),choice() etc
  
  import random

  stages = ['''
      +---+
      |   |
      O   |
    /|\  |
    / \  |
          |
    =========
    ''', '''
      +---+
      |   |
      O   |
    /|\  |
    /    |
          |
    =========
    ''', '''
      +---+
      |   |
      O   |
    /|\  |
          |
          |
    =========
    ''', '''
      +---+
      |   |
      O   |
    /|   |
          |
          |
    =========''', '''
      +---+
      |   |
      O   |
      |   |
          |
          |
    =========
    ''', '''
      +---+
      |   |
      O   |
          |
          |
          |
    =========
    ''', '''
      +---+
      |   |
          |
          |
          |
          |
    =========
  ''']
  words_list = ["hangman", "tuise", "buzz"]
  chosen_word = random.choice(words_list)
  display = []
  word_len = len(chosen_word)
  for _ in range(word_len):
    display += "_"
  lives = word_len
  # set the end_game false
  end_game = False
  while not end_game:
    guess = input("Guess a letter: ").lower()
    for position in range(word_len):
      letter = chosen_word[position]
      if letter == guess:
        display[position] = letter
    if guess not in chosen_word:
      lives -= 1
      if lives == 0:
        end_game = True
        print("You lose")
    if "_" not in display:
      end_game = True
      print("You win")

    # Print the ASCII art from 'stages' that corresponds to the    # current number of 'lives' the user has remaining.
    print(stages[lives])

  
{% endhighlight %}

### Output:
It will show the loss or win if loss then show a hangman ASCII
