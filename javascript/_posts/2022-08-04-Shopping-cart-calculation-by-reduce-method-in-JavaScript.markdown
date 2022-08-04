---
layout: post
title:  "Shopping cart calculation with reduce method in JavaScript"
date:   2022-08-04 23:10:48 +0900
category: JavaScript
---
![Cart calculation with reduce method](/javascript/assets/images/ShoppingCartwithReduceMethod.png)

Reduce method has a large number of operations in JavaScript. We can do many cool calculations with this reduce() method. Reduce method always returns a single value, array, or object.
We can do any calculation from a large number of arrays, objects, or iterable data.
Reduce() method iterates over the set of data and calculate the value and return it as a single number, array, or object.
If you want to learn more about Reduce method in JS then please read more about it here - [Reduce method in JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)

Today We will use reduce method to calculate a shopping cart to get total numbner of items and total price of the cart.

Let's start

`Calculating a cart with reduce() method`

Let's make an array called cart.

{% highlight javascript %}
  // Cart array
  const cart = [
    {
        title: "iPhone 12 Pro Max",
        price: 599.99,
        amount: 1
    },
    {
        title: "Sumsang Galaxy S9",
        price: 699.99,
        amount: 2
    },
    {
        title: "Xiami Redmi Note 2",
        price: 499.99,
        amount: 3
    },
    {
        title: "RealMe Color Phone",
        price: 399.99,
        amount: 3
    },
    {
        title: "OPPO A20",
        price: 299.99,
        amount: 3
    },
    {
        title: "Google Pixel",
        price: 399.99,
        amount: 1
    }
]

{% endhighlight %}

`Calculate the Cart`

{% highlight javascript %}

let {totalItems, cartTotal} = cart.reduce((total, cartItem)=>{
    const {amount, price} = cartItem;
    // count items
    total.totalItems += amount

    //count sum 
    total.cartTotal += amount * price
    return total
},{
    totalItems: 0, 
    cartTotal: 0
});

cartTotal = parseFloat(cartTotal.toFixed(2))

console.log(totalItems, cartTotal)

{% endhighlight %}

### Output is 
> total items are: 13 and total price is: 5999.87

> 13 5999.87

`Explanation: `

Here we have used let to destructing the total items and **cartTotal** because we have overwritten the **cartTotal** to get the correct number of decimal points.
We have destructing amount and price.
In count, items have been added to the **cartTotal** variable in every iteration. The initial value of **total.cartTotal** is 0.
When we count the sum of the price product we have multiplied the price and amount to get the correct value.
At last we have used **parseFloat()** function and **toFixed()** function to get the correct number of decimal value.

Happy coding :)


