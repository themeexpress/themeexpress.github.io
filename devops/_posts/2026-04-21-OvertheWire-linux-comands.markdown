---
layout: post
title:  "Learning Linux: My Journey Through OverTheWire Bandit (Levels 0-5)"
date:   2026-04-21 22:00:00 +0900
category: Linux
---

# OverTheWire Bandit: Levels 0 to 5
I am currently learning Linux commands by playing the OverTheWire Bandit wargame. It is a fantastic way to get comfortable with the terminal. In this post, I will cover my notes, tips, and the commands I used to solve levels 0 through 5.

---

### Level 0 -> Level 1
**Login:** {% highlight bash %}
ssh bandit0@bandit.labs.overthewire.org -p 2220
{% endhighlight %}
**Password:** `bandit0`

**Puzzle:** The password for the next level is stored in a file called `readme` located in the home directory.

**What I learned:**
1. **`ls`**: Used to list files in the current directory.
2. **`cat readme`**: Used to display the content of the file.

---

### Level 1 -> Level 2
**Login:** {% highlight bash %}
ssh bandit1@bandit.labs.overthewire.org -p 2220
{% endhighlight %}
**Password:** (Use password found in the `readme` file)

**Puzzle:** The password for the next level is stored in a file called `-` located in the home directory.

**What I learned:**
1. **Handling special filenames**: In Linux, `-` is typically treated as an option flag. To cat a file named `-`, you can use standard input redirection:
{% highlight bash %}
cat < -
{% endhighlight %}
*Alternatively, you can use the path `cat ./-` to avoid the ambiguity.*

---

### Level 2 -> Level 3
**Login:** {% highlight bash %}
ssh bandit2@bandit.labs.overthewire.org -p 2220
{% endhighlight %}
**Password:** (Use password found in level 1)

**Puzzle:** The password for the next level is stored in a file called `--spaces in this filename--` located in the home directory.

**What I learned:**
1. **Dealing with spaces**: When filenames contain spaces, you must escape them or use quotes. Using the `--` separator can help distinguish options from filenames.
{% highlight bash %}
cat -- "--spaces in this filename--"
{% endhighlight %}

---

### Level 3 -> Level 4
**Login:** {% highlight bash %}
ssh bandit3@bandit.labs.overthewire.org -p 2220
{% endhighlight %}
**Password:** (Use password found in level 2)

**Puzzle:** The password for the next level is stored in a hidden file in the `inhere` directory.

**What I learned:**
1. **`ls -a`**: The `-a` flag is essential to see hidden files (files starting with a `.`).
2. **`cd inhere`**: Navigation command to change the working directory.
3. **Accessing hidden files with spaces**:
{% highlight bash %}
ls -a
cd inhere
ls -a
cat -- "...Hiding-From-You"
{% endhighlight %}

---

### Level 4 -> Level 5
**Login:** {% highlight bash %}
ssh bandit4@bandit.labs.overthewire.org -p 2220
{% endhighlight %}
**Password:** (Use password found in level 3)

**Puzzle:** The password for the next level is stored in the only human-readable file in the `inhere` directory. (Tip: If your terminal is messed up, try the `reset` command.)

**What I learned:**
1. **Identifying file types**: Instead of checking every file manually with `cat`, I used a simple bash loop to check the file type of each item.
{% highlight bash %}
for i in {0..9}; do file ./-file0$i; done
{% endhighlight %}
This allows you to filter through the data and find the file labeled `ASCII text`. Once identified:
{% highlight bash %}
cat ./-file07
{% endhighlight %}

---

Happy coding! I am looking forward to tackling levels 6–10 next.