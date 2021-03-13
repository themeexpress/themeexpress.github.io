---
published: false
---
## Case change with user build function in Ruby

Case change with user build function in Ruby
Ruby already has build in function to change case. There are upcase and downcase function to do it. But what if we want to wirte a custom function to do this. It’s fun right! Lets start to coding.
```
# Case change
def caseChanger(str, option)
  i = 0
  while(i!=str.size)
    letterr = str[i].to_s
    if (option == 1)#to make lower case
      if(letterr >= 'A' and letterr<='Z' )
        str[i] = (letterr.ord+32).chr
      else
        str[i] =letterr
      end
    else #to make upper case
      if(letterr >= 'a' and letterr<='z' )
        str[i] = (letterr.ord-32).chr
      else
        str[i] =letterr
      end
    end
    i += 1
  end
  puts "Here is string:  #{str}"
end
caseChanger('kamrul',0)
```