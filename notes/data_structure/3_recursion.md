# Introduction
We're going to take a break from our tour of data structures in order to look at the concept of  _recursion_. Recursion is going to be a useful tool for solving some of the problems we'll be tackling later on, and this is a good place to introduce it and get some practice using it with the data structures we're reviewing.

When you hear the terms  _recursion_  or  _recursive_, this might remind you of the terms  _repetition_  and  _repetitive_—and this is a good connection, because recursion does indeed involve repetition. However, recursion isn't just about repetition.

With recursion, we  _solve a problem by first solving smaller instances of the same problem._  In practice, this often involves calling a function from within itself—in other words, we feed some input into the function, and the function produces some output—which we then feed back into the same function. And we continue to do this until we arrive at the solution.

Recursion is maybe one of the most confusing subjects in computer science. The **idea** here is _to create a function that calls itself._ Here is a really basic example:

```python
def recursvie(input):
    if input < 0:
        return input
    else:
        output = recursive(input - 1)
        return output
```

The above code doesn't do anything interesting, but it shows the main parts of a recursive function. 

1. _**A recursive function needs to call itself at some point**_. 
2. _**A recursive function needs a base case**_. 
3. _**A recursive function needs to do is to alter the input parameter at some point**_.
   
You can think of a recursive function kind of like a _while loop_ in some regards. You keep going through some code again and again until you hit some exit condition. In a recursive function the base case is like the exit function. 

Without a nice base case, you could get stuck in something called **infinite recursion**. That means your code keeps calling itself and executing again and again, but because you never tell it when to stop, it just keeps going infinitely.

If you aren't altering the input parameter or giving yourself some condition for changing every time you iterate, you'll never really know when to stop. And again you'll end up in _infinite recursion_. 

Watch [this video](https://youtu.be/_aI2Jch6Epk) (minute 1:40) to learn more about some of the nuances of recursive functions.

