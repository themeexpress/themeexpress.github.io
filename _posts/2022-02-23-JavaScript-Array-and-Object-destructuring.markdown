---
layout: post
title:  "JavaScript Array and Object destructuring!"
date:   2022-03-22 23:23:48 +0900
categories: JavaScript
---
Today I will discuss about Javascript Array and Object destructuring. destructuring is widely using in ES6, Typescipt and Javascipt libray and framework like React Js. 

`Array destructuring`

{% highlight javascript %}
// Array Destructureing
const fruits = ['Orange','Banana','Lemon','WaterMelon','Apple'];
const friends = ['Sujon','Jakir','Mamun','Rana','Nazrul','Atik',];
const fruit1 = fruits[0];
const fruit2 = fruits[1];
const fruit3 = fruits[2];
console.log(fruit1,fruit2,fruit3);

// Destructuring
const [a,b,c,d] = friends
console.log(a,b,c,d);
const [m,k, ,n,p] = friends
console.log(m,k,n,p);

// Variable replacement
// Conventional way
let first = 'Bob';
let second = 'John';

let temp = second;
second = first;
first = temp;
console.log(first,second);
// Array Distrucruing way
[second, first] = [first,second]
console.log(first,second);
{% endhighlight %}

`Object Destructuring`

{% highlight javascript %}

// Object Destructuring 

const bob = {
  first: 'bob',
  last: 'Sanders',
  city: 'Chigago',
  siblings:{
    sister: 'Jane',
    brother: 'Toni'
  },
};

// Conventinal way

const {first, last, city,siblings:{sister}} = bob
console.log(first, last, city, sister);

// Use it in function

function printPerson(person){
  // console.log(person.first); // output is: bob
  // do it by object distructuring 
  const {first, last, city} = person;
  console.log(first, last, city); //output is: bob Saners
}
printPerson(bob);

{% endhighlight %}
