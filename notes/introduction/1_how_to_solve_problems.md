# Welcome
At its core, this program is about how to write code to  **solve problems**  and to do so  **efficiently**.

You're probably well aware that computers can be used to solve all sorts of problems—from calculating the fastest route on a map, to sequencing the human genome. But there is almost always more than one way to solve a problem, and some ways can be dramatically more efficient than others. Two approaches may solve the same problem, but one may take milliseconds, while the other takes hours.

How do you look at a problem and identify different ways that you could solve it? And how do you know which approaches are more or less efficient? Will your solution run quickly or slowly? Will it take up a lot of space in the computer's memory, or only a little? Being able to answer these kinds of questions will make you a more effective developer—and also help you perform much better during technical interviews.

The key to mastering these skills is practice. Simply hearing about algorithms and data structures will not make you proficient at analyzing or implementing them in a real-world situation. For that reason, our goal in this program is not only to explain key concepts, but also to give you lots of chances to practice the key skills through hands-on exercises.

# How to solve problems?
Solving problems is one of the most important skills you can learn. Here, we're going to look at how to approach complicated programming problems. We're going to look at a specific problem and talk about how we would go about solving that. Our goal by looking at a particular problem is not just to solve that particular problem but to draw some general lessons about how we can get better as problem solvers.

## Example Problem:
The problem statement is as follows:

"_Given your birthday and the current date, calculate your age in days. Compensate for leap days. Assume that the birthday and current date are correct dates (and no time travel). Simply put, if you were born 1 Jan 2012 and today's date is 2 Jan 2012, you're one day old._"

**So, what's the first thing you should do to solve a problem like this?**

The hardest thing about solving problems is often just figuring out how to get started! There few ways we can get started:

- Start writing code
- Make sure we understand the problem
- Search Google for the answer
- Work out an algorithm that solves

Well! Obviously, the second choice is probably the best choice. It's often tempting to writing code early but again if we haven't understood the problem we'd write the wrong code. So, basically we may end up writing a lot of code that doesn't matter. Searching Google is actually a very good option if this was not a practice problem. 

# Understanding a problem
What does it mean to _understand a problem_? (we're talking about computational problems here). _**What all computational problems have in common is that they have inputs and they have desired outputs**_. So, problem is defined by the set of possible inputs. This is usually an infinite set for most interesting problems and the relationships between those inputs and the desired outputs. That means a solution to a problem is a procedure that can take any input in the input set and produces output, a desired output that satisfies the relationship that we want. 

In the case of our example problem, the relationship that we want is that the output is the number of days between the birthday and the current date. 

# The First Rule
The first rule is to always ask **what are the inputs?**. 

There is one rule before the first rule, the **zeroth rule**. The zeroth rule is **don't panic**.

# What are the inputs?
So, the first question we need to ask for any problem is what are the inputs?

For the problem at hand, they're fairly clearly stated: given _your birthday_ and _current date_, calculate your age in days. So, the inputs are really two dates. 

We also have to be careful that they're all valid. The statement of the question gives a hint that we can assume the dates are correct. Also, the second date needs to be after the first one. So, to be a good _defensive programmer_, we gotta make sure to check if this is true. 

The other assumption that we want is about the range of dates. We're going to require that dates are valid dates in the Gregorian calendar, which started in October 1582. 

# How inputs are represented?
For most real world problems it's up to you to figure out _**how to encode the inputs and this is one of the most important decisions that you can make in solving a problem**_. 

In the case of our problem, let's specify that format of input as six parameters as follows: (year1, month1, day1, year2, month2, day2) and let's call our procedure "daysBetweenDates". 

# What are the outputs?
So, the next thing we need to understand about a problem is what are the outputs? 

The statement of the question gives some idea of what the outputs should be: "calculate your age in days". However, it doesn't specify really explcitly what we want the output to be (print, return, etc.). 

Returning is best. Returning a number is much more useful. 

So, the second rule is: "understanding what the outputs are?"

Make sure before getting to solving the problem, you obey the rules:

- Don't panic!
- What are the inputs?
- What are the outputs?

# Solving the problem
Let's start by working out some examples, just to understand the inputs and outputs are not enough. We need to understand the relationship between the two dates. The examples will also give us some use cases to know that our program is correct. Below are some examples:

```python
daysBetweenDates(2012, 12, 7, 2012, 12, 7)  # 0
daysBetweenDates(2012, 12, 7, 2012, 12, 8)  # 1
daysBetweenDates(2012, 12, 8, 2012, 12, 7)  # 'undefined'
daysBetweenDates(2012, 6, 29, 2013, 6, 29)  # 365
daysBetweenDates(2012, 6, 29, 2013, 6, 31)  # 'undefined', there's no june 31st
```

We need to understand how to solve the problem in a systematic way. So, we need to try to go through a few cases in a very systematic way as a human. 

Let's try this example: `daysBetweenDates(2013, 1, 24, 2013, 6, 29)`. Watch these videos for some ideas: [video1](https://youtu.be/X29RjzKHsWU), [video2](https://youtu.be/-eAKNo9cA6Y).

Basically, the idea is first to find the difference between days. Then, if the years are the same, just add up the number of days in each month between the two dates. If the years are not equal, then add the number of days for each year in between accounting the leap years.

# Algorithm Pseudocode









