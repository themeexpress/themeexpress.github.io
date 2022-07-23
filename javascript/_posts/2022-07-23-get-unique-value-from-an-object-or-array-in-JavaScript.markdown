---
layout: post
title:  "Get Unique values from an object or array"
date:   2022-03-22 23:23:48 +0900
category: JavaScript
---
Today I will discuss how to get unique value from an object or array in Javascript. This unique value is widely using in many places like menu category, seperate some unique items. 

**First make an array named is menu with two values object(name and category)**

{% highlight javascript %}
// Menu array
// Unique id in array
const menu = [
    {
        name: 'pancakes',
        category: 'breakfast',
    },
    {
        name: 'burger',
        category: 'lunch',
    },
    {
        name: 'steak',
        category: 'dinner',
    },
    {
        name: 'bacon',
        category: 'breakfast',
    },
    {
        name: 'eggs',
        category: 'breakfast',
    },
    {
        name: 'pasta',
        category: 'dinner',
    },
    {
        name: 'pulao',
        category: 'lunch',
    },
    {
        name: 'ruti',
        category: 'breakfast',
    },
];
// workflow 
// map () to get all instances loop over in the menu array
// new Set() to get the unique values of categories
// ['all', ...] use spread operator to turn it back in array

const categories = ['all', ...new Set(menu.map((item) => item.category))]
console.log('menu categories')
console.log(categories);

{% endhighlight %}

`Workflow`
## Get all instances using map() from the menu array
This **map()** function loop over the array and get the all instance

{% highlight javascript %}

const categories = menu.map((item) => item.category)
console.log(categories);

{% endhighlight %}

### Output is
> (8) ['breakfast', 'lunch', 'dinner', 'breakfast', 'breakfast', 'dinner', 'lunch', 'breakfast']

## We will use set object to get the unique value.

Set object lets you get or store the unique values of any types.

[For more about set object please read set in Javasript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set)

{% highlight javascript %}
  const categories = new Set(menu.map((item) => item.category))
  console.log(categories);
{% endhighlight %}

### Output is
> Set(3) {'breakfast', 'lunch', 'dinner'}

Every this good but the problem the set object gives us an object. We need as array. How can I get it?
The easy solution is use spread operator.
The spread operator returns it as array.
[More about spread operator please read] (https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)

{% highlight javascript %}

  const categories = ['all', ...new Set(menu.map((item) => item.category))]
  console.log(categories);

{% endhighlight %}

### Output is
> (4) ['all', 'breakfast', 'lunch', 'dinner']

This is how we can get the unique value from an object or array. This is super useful in real life.

:) Happy coding
