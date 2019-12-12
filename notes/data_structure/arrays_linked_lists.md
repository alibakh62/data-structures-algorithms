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