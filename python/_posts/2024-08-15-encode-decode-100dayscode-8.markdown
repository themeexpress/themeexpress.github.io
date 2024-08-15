---
layout: post
title:  "Encryption and decryption in python"
date:   2024-08-15 19:10:48 +0900
category: Python
---
![encryption](/python/assets/images/encryption.png)

## Simple encode and decode system in Python

{% highlight python %}

alphabet = ['a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z']
description = input("Type 'encode' to encrypt, type 'decode' to decrypt:\n")

def encypt(text, shift):
  print(text, shift)
  encrypted_text = ""
  for letter in text:
    if letter in alphabet:
      position = alphabet.index(letter)
      new_position = position + shift
      if new_position > 25:
        new_position = new_position - 26
      new_letter = alphabet[new_position]
      encrypted_text += new_letter
    else:
      encrypted_text += letter
  return encrypted_text

def decrypt(text, shift):
  decrypted_text = ""
  for letter in text:
    if letter in alphabet:
      position = alphabet.index(letter)
      new_position = position - shift
      if new_position < 0:
        new_position = new_position + 26
      new_letter = alphabet[new_position]
      decrypted_text += new_letter
    else:
      decrypted_text += letter
  return decrypted_text
  
if description == "encode":
  text = input("Type your message:\n").lower()
  shift = int(input("Type the shift number:\n"))
  if shift < 26 and text:
    print(encypt(text, shift))
elif description == "decode":
  shift = int(input("Type the shift number:\n"))
  text = input("Type your message:\n").lower()
  print(decrypt(text, shift))

{% endhighlight %}

### Output:
It will show the encrypted and decrypted text