# Why data structures?

_Data structures_  are containers that organize and group data together in different ways. When you write code to solve a problem, there will always be data involved—and how you store or structure that data in the computer's memory can have a huge impact on what kinds of things you can do with it and how efficiently you can do those things.

In this section, we'll start out by reviewing some basic data structures that you're probably at least partly familiar with already.

Then, as we go on in the course, we'll consider the pros and cons of using different structures when solving different types of problems.

We'll start with a discussion of a very general structure—a  **collection**.

Collection is just a group of things. Collections don't have a particular order. So, we can't say "give me the third element in the collection", since there's no inherent order. 

Collections also don't need to have the same type of object. 

A collection on its own isn't something you can use in a programming language. However, there are many data structures that are extensions of collections. They just add more rules to the ones that already apply for collections.   

## Properties of collections

As Brynn discussed, collections:

-   Don't have a particular order (so you can't say "give me the 3rd element in this collection")
-   Don't have to have objects of the same type

# Lists
A list has all the properties of a collection. So, it has a group of things but _**the objects have an order**_. The order really doesn't mean much and there's no fixed length. You can add or remove objects from a list. 

What exactly the implementation looks like for adding/removing elements will change based on the language and the type of data structure. 

In this course, we'll learn about different types of list. Different programming languages treat them differently. Sometimes a list is incorporated as a core feature of a programming language, but what that looks like can vary widely. Here, we're focused on the theoretical concepts that could apply to any language. 

## Properties of lists

As Brynn described, lists:

-   Have an  **order**  (so you can say things like "give me the 3rd item in the list")
-   Have  **no fixed length**  (you can add or remove elements)

# Arrays
Arrays are perhaps the most common implementations of lists. In many programming languages, the ability to create an array is built in as a core feature. 

An array is a list with few added rules (so, we already know it has order). In some languages you can only have objects with the same types in the same array, and in some languages your array can contain different types. So, we can't use that as a rule to define arrays. 

It'd also be nice to say that arrays have a set size that you determine right when you create them. Again, this is only true in some programming languages, so we need to avoid adding that to our definition. 

Defining the thing that different languages call arrays is actually pretty hard. 

There's one big feature that differentiates arrays from lists. **Each array has a location called an _index_**. An **index** is just the number associated with that place in the array. 

It'd make sense to number indices from one, but **normally an index starts at zero**. 

Having indices can make using arrays a great or sometimes a terrible choice for the code you're working on. If you need to access a certain location in the middle frequently, using an array can be great choice. You just need to keep track of how long the array is, calculate the middle element, and get the object in that index. 

**Insertion and deletion can be really messy with arrays**. **Inserting in the end is often easy** but it can be hard if the array has a set size and you've already filled it up. 

**Insertion is difficult if you want to put an element in the middle of an array**. If you want to do a normal insert, you'll need to move everything after the inserted element back into different indices. The operation as a whole is pretty inefficient since you need to move every element behind the one you're inserting back in the array. In the worst case, this operation takes linear time or `O(n)`. 

**Deletion causes a same problem**. If you delete an element, you have an empty index. 

Again, all of these can change based on the way a particular language implements an array but it's important to consider we're talking about arrays abstractly. 

## Arrays vs. lists vs. Python lists

The distinction between arrays and lists can be a little confusing, especially because of how Python implements the data structure it calls a "list". Below, we'll go over some key points that should make this clearer.

### Arrays

An array has some things in common with a list. In both cases:

-   There is a collection of items
-   The items have an order to them

But as Brynn discussed in the video, one of the key differences is that  _arrays have indexes, while lists do not_.

To understand this, it helps to know how arrays are stored in memory. When an array is created, it is always given some initial size—that is, the number of elements it should be able to hold (and how large each element is). The computer then finds a block of memory and sets aside the space for the array.

Importantly, the space that gets set aside is one, continuous block. That is, all of the elements of the array are  _contiguous_, meaning that they are all next to one another in memory.

Another key characteristic of an array is that all of the elements are the same size.

When we represent an array visually, we often draw it as a series of boxes that are all of the same size and all right next to one another:

<p align="center">
<img src="img/array1.png" alt="drawing" width="300"/>
</p>

Because all of the elements are 1) next to one another and 2) the same size, this means that if we know the location of the first element, we can calculate the location of any other element.

For example, if the first element in the array is at memory location  `00`  and the elements are 24 bytes, then the next element would be at location 00 + 24 =  `24`. And the one after that would be at 24 + 24 =  `48`, and so on.

Since we can easily calculate the location of any item in the array, we can assign each item an index and use that index to quickly and directly access the item.

<p align="center">
<img src="img/array2.png" alt="drawing" width="300"/>
</p>

### Lists

In contrast, the elements of a list may or may not be next to one another in memory! For example, later in this lesson we'll look at  _linked lists_, where each list item points to the next list item—but where the items themselves may be scattered in different locations of memory. In this case, knowing the location of the first item in the list does not mean you can simply calculate the location of the other items. This means we cannot use indexes to directly access the list items as we would in an array. We'll explore linked lists in more detail shortly.

## Python lists

In Python, we can create a list using square brackets  `[ ]`. For example:

```python
>>> my_list = ['a', 'b', 'c']
>>> my_list
['a', 'b', 'c']
```

And then we can access an item in the list by providing an index for that item:

```python
>>> my_list[0]
'a'
>>> my_list[1]
'b'
>>> my_list[2]
'c'
```

But wait, didn't we just say that lists  _don't_  have indexes!? This seems to directly contradict that distinction.

The reason for this confusion is simply one of terminology. The earlier description we gave of lists is correct  _in general_—that is, usually when you hear someone refer to something as a "list", that is what they mean. However, in Python the term is used differently.

We will not get into all of the details, but the important thing you need to know for this course is the following: If you were to look under the hood, you would find that  **a Python list is essentially implemented like an array**  (specifically, it behaves like a  _dynamic array_, if you're curious). In particular,  **the elements of a Python list are contiguous in memory, and they can be accessed using an index.**

In addition to the underlying array, a Python list also includes some additional behavior. For example, you can use things like  `pop`  and  `append`  methods on a Python list to add or remove items. Using those methods, you can essentially utilize a Python list like a stack (which is another type of data structure we'll discuss shortly).

In general, we will try to avoid using things like  `pop`  and  `append`, because these are high-level language features that may not be available to you in other languages. In most cases, we will ignore the extra functionality that comes with Python lists, and instead use them  **as if they were simple arrays**. This will allow you to see how the underlying data structures work, regardless of the language you are using to implement those structures.

Here's the bottom line:

-   Python lists are essentially arrays, but also include additional high-level functionality
-   During this course, we will generally ignore this high-level functionality and treat Python lists as if they were simple arrays

This approach will allow you to develop a better understanding for the underlying data structures.