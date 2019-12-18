# Introduction
Stacks are also list-based data structures, so they have a bit of a different flair than arrays and linked lists. 

The _**main idea**_ is a stack is like a stack of objects in real life. You keep putting on elements on top and you have easy access to remove or look at the top element.

Stacks could be really useful when you only care about the most recent elements or the order in which you see and save elements actually matters. Maybe you have a page like a news feed. You'll need to access the more recent elements more quickly and more frequently, but you may need to show all of the elements when the user scrolls down. 

There is some specific **terminology** associated with stacks. When you add an element to a stack, the operation is called **push** (instead of _insert_). When you take an element off of stack, the operation is called a **pop** (instead of _remove_). Remember, all you need here is to look at the top element of the stack. So the operation should be constant time (`O(1)`

Constant time is possibly a confusing point because a stack is pretty abstract, it could be actually implemented with another data type. What each element looks like and there's connected aren't actually specified, just the methods for adding and removing elements. For example, you could use a linked list to implement a stack. You'd keep track of the front of a single linked list and just keep adding elements on top as you went. 

You might see the notation **LIFO** (Last In, First Out) associated with stacks. The last one you push is always the first one you pop. 

## Implementing a Stack Using a Linked List
See an implementation in [this notebook](linkedlist-implement-stack.ipynb)

## Build a Stack
See [this notebook](python_stack_practice.ipynb) for an example of building a stack in python.

## Balanced Parentheses Excercise
See [this notebook](Balanced-Parentheses-Exercise-Stacks.ipynb) for this practice.

## Reverse Polish Notation
See [this notebook](Reverse-Polish-notation.ipynb).

## Reverse a Stack
See [this notebook](Reverse-a-stack.ipynb).

## Minimum Bracket Reversals
See [this notebook](Minimum-bracket-reversals.ipynb).

# Queues
Imagine a line of people all waiting to get their hands on the best chocolate pancakes in existence. The way this works is person who's been in the line the longest gets her pancakes and gets out first. 

You could perhaps call this a **FIFO** (First In, First Out) structure or a **queue**. 

_A **queue** is kind of the opposite of a stack in this way._ In a stack, the most recently added elements comes out first, but in queue the older element comes out first. _Otherwise, queues are pretty similar to stacks._ The first element (or the oldest element) in a queue is called the **head**. The last element (newest element) in a queue is called the **tail**. When you add an element to the tail, the operation is called **enqueue**. When you remove the head element, the operation is called **dequeue**. There's also an operation called **peek**, where you look at the head element but you don't actually remove it. 

Again, you can implement this data sctructure with a linked list, where you also save references to the head and tail so you can look them both up in constant time. 

There are actually two special types of queues that show up a lot. A **deque**, pronounced like the work "deck", or double-ended queue is a queue that goes both ways. You can _enqueue_ or _dequeue_ from either end. If you think about it, a _deque_ is kind of a generalized version of both stacks and queues, since you can represent either of them with it. You could treat it like a stack and add and remove elements from the same end, or you could treat it like a queue and add elements on one end and remove them from the other.

### Priority Queue
Let's examine a **Priority Queue** now. In a priority queue you assign each element a numerical priority when you insert it into the queue. When you dequeue, you remove the element with the highest priority. This doesn't really follow the rules of a normal queue, where you remove the oldest element first. However, if the elements have the same priority, the oldest element is the one that gets dequeued first.

## Build a Queue Using Array
See [this notebook](Build-a-queue-using-an-array.ipynb).

## Build a Queue Using a Linked List
See [this notebook](Build-a-queue-using-a-linked-list.ipynb).

## Building a Queue Using a Stack
See [this notebook](Build-a-Queue-Using-a-Stack.ipynb).

## Building a Queue Using High-Level Python
See [this notebook](Build-a-Queue-Using-High-Level-Python.ipynb).

## Reverse a Queue
See [this notebook](Reverse-a-queue.ipynb).


