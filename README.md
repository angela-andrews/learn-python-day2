# Day 2 of Learning Python

We've all heard that if you already know a programming language, learning another one will be easier. Well, as a JavaScript developer I must say, learning Python (again!) is going to be easier than learning PHP or JavaScript the first time around. I've tried learning Python years ago when my son became interested in programming and I sure wish I'd kept up with it. Going into day 2 of learning Python, I've be introduced to lists, tuples and ranges.  All examples in  this post are using version 3.7.2.

## Lists
Lists are a built-in python data structure (sequence types). They are very similar to arrays in JavaScript, a list of items, separated by commas and surrounded by brackets.

[Lists](https://docs.python.org/3/library/stdtypes.html#sequence-types-list-tuple-range) are mutable, meaning  they can be changed after it is created. They are an ordered sequence of items. holding a collection of things; strings, numbers, booleans, etc. They are zero indexed based structures. You can access an item by their index number which is their position in the list.

2 images

```
>>> my_list [1, True, 3, 'candy', 3.4, 'Cardi B'] >>> my_list[5] 'Cardi B' >>>
```
An easy way to always access the last item in the list is by using the **len** method. No matter the length of the list, you can have access to the last item.
