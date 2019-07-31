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

```
>>> my_list [1, True, 3, 'candy', 3.4, 'Cardi B'] >>> my_list[len(my_list)-1] 'Cardi B' >>>
```

Since lists are zero indexed, you can always access the first item, no matter the length by the [0] index.

```
>>> my_list[0] 1 >>> my_list [1, True, 3, 'candy', 3.4, 'Cardi B'] >>>
```

Slicing up a list is a great way to access a group of items from the list. Instead of just accessing an item one at a time, the slice object gives you access by where you want to start, where you want to stop and the steps in between.

**[start index:end index: step]**
```
>> my_list [1, 2, 3, 4, 5] >>> my_list[0:2] [1, 2] >>>
```

[0:2] starting at index 0 and up to, but not including index 2.  Also, you don't need the 0, you can leave it off and it's understood as 0.

```
>>> my_list[:7:2] [1, 3, 5, 7] >>>
```

[0:9:2] starting at index 0 and up to, but not including index 9 counting by 2s.

```
>>> my_list = [1,2,3,4,5,6,7,8,9,10] >>> my_list[0:9:2] [1, 3, 5, 7, 9] >>>
```

To return a list that returns every other item (by 2s).

```
>>> my_list[::2] [1, 3, 5, 7, 9] >>>
```
Reverse a list.

```
>> my_list[::-1] [10, 9, 8, 7, 6, 5, 4, 3, 2, 1] >>>
```

Lists are mutable. You can update and change them any way you like. Reference the index and assign a new item.

```
>>>my_list = [1,2,3,4,5,6,7,8,9,10] > my_list[0] = 'a' >>> my_list ['a', 2, 3, 4, 5, 6, 7, 8, 9, 10]
```
## Functions

Loved the familiarity of these good old methods. Python makes these functions available for quick and easy data manipulation. First up:

**.pop()** returns and removes items from any position in the list. Using pop() without any index will remove and return the last item in the list.

```
>>> my_list ['a', 2, 3, 4, 5, 6, 7, 8, 9, 10, 'bug'] >>> my_list.pop() 'bug'
```

Using **.pop()** with an index value, you can target any item you like to be popped off and returned.

```
>>> my_list= [1,2,True,'apricot',5,'Cardi B'] >>> my_list.pop(4) 5 >>> my_list [1, 2, True, 'apricot', 'Cardi B'] >>>
```

**.pop()** can behave like either a queue or a stack. Both are data structures in programming and process data in very different ways. Queue is my favorite, I see FIFO, I think SQS (AWS), first-in first-out (FIFO). Any item added at the end (enqueue) will be the last one to be accessed (dequeue).  You have to do an awful lot of popping to get to the last one if your queue is contains a lot of items. **pop(0)** will make your list behave like a queue **.pop()** will make your list behave like a stack. A stack just what it sounds like, laundry. It is a first-in last-out structure. Any item added at the end of the stack will be the first out off the stack. If your favorite jeans are folded first and are at the bottom of the stack, you may as well grab the ones off the top and work your way down. You don't want to look like you're re-running your jeans, do you?


Learn more about queues and stacks [here](https://www.101computing.net/stacks-and-queues-using-python/).

Next up is **.remove()** which is great when you want to remove an item by it's value. Strange thing is, if that item is a Boolean, it'll remove the item in the 0 index. I didn't know that was a thing until I just tested it.

```
> my_list= [1,2,True,'apricot',5,'Cardi B'] 
>>> my_list.remove(True) 
>>> my_list [2, True, 'apricot', 5, 'Cardi B'] 
>>> my_list.remove(5) 
>>> my_list [2, True, 'apricot', 'Cardi B']
```

**.reverse() **is a handy for when you need to swap the order of the list.

```
>>> my_list ['a', 2, 3, 4, 5, 6, 7, 8, 9, 10] 
>>> my_list.reverse() 
>>> my_list [10, 9, 8, 7, 6, 5, 4, 3, 2, 'a'] 
>>> my_list.reverse() 
>>> my_list ['a', 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

Sometimes you just want to throw an item on the end, **.append()** does the trick. Add the item inside the method and voila!

```
>>> my_list ['a', 2, 3, 4, 5, 6, 7, 8, 9, 10] 
>>> my_list.append('bug') 
>>> my_list ['a', 2, 3, 4, 5, 6, 7, 8, 9, 10, 'bug']
```

Last one is **.insert()**. You can add a new item to any position you want to in your list. Specify the index and the value and insert away. It'll make room and put your item right where you want it.
```
>>> my_list= [1,2,True,'apricot',5,'Cardi B'] 
>>> my_list.insert(2, 43.9) 
>>> my_list [1, 2, 43.9, True, 'apricot', 5, 'Cardi B']
```

## Tuples
Tuples are immutable and fixed-sized, meaning they cannot be changed. They're good for items that don't need to change, like x and y coordinates. You can't assign an item to an index, again immutable. To create a tuple, list items in parentheses, separated by commas. 

_someTuple = (some item, another item, last item,..._)

```
>>> coord = (4.0, 3.2) 
>>> coord[1] 3.2 
>>> coord[1] = 2.9 
Traceback (most recent call last): File "<stdin>", line 1, in <module> TypeError: 'tuple' object does not support item assignment
```

You can create a tuple from a tuple.  This will not change the original tuple, just copy it's values into a new one. Note the comma after the item in parenthesis.

