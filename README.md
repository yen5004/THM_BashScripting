# THM_BashScripting
TryHackMe tutorial on Bash scripting

# Bash Scripting

https://tryhackme.com/r/room/bashscripting

# **Bash Scripting**

A Walkthrough room to teach you the basics of bash scripting

LINKS:
https://devhints.io/bash
https://www.codewars.com/

https://www.hackerrank.com/

https://enescayvarli.medium.com/tryhackme-bashscripting-walkthrough-cf8eea1be297

CHAT GPT:
https://devhints.io/bash

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/eb6c5f10-6443-40c9-91ab-8b430b257fed/3f829a72-e6ca-4d52-9e84-d866b337de92/Untitled.png)

# Task 1 Intro

Task 1Introduction

# Welcome to the introductory bash scripting room!

![https://t4.ftcdn.net/jpg/03/28/80/75/240_F_328807501_5WtzgA0Lne9ylGxIFvQWdzHK8sSmtjrp.jpg](https://t4.ftcdn.net/jpg/03/28/80/75/240_F_328807501_5WtzgA0Lne9ylGxIFvQWdzHK8sSmtjrp.jpg)

# What is bash?

Bash is a scripting language that runs within the terminal on most Linux distros, as well as MacOS. Shell scripts are a sequence of bash commands within a file, combined together to achieve more complex tasks than simple one-liner and are especially useful when it comes to automating sysadmin tasks such as backups.

This is a few things among many that you will learn in this room:

- Bash syntax
- Variables
- Using parameters
- Arrays
- conditionals

Throughout this room feel free to work along with me! You can test out the commands shown or integrate them into your own projects, after all you learn by practicing and applying what you have learnt into your own scenarios. Make sure to spawn the tryhackme attackbox or use your own terminal.

I found this website very useful when I was on my journey of learning bash, feel free to use it to help you through this room and for further learning after you finish! [https://devhints.io/bash](https://devhints.io/bash)

Answer the questions below
NAN (No Answer Needed)
Are you ready to go!


# Task 2 1st simple bash script

Task 2 Our first simple bash scripts

Ok now that we have had a brief introduction to what bash is and what it is used for let's jump right into some examples!

First of all let’s lay out our structure.

A bash script always starts with the following line of code at the top of the script.

![https://i.ibb.co/7W5mn0c/carbon-8.png](https://i.ibb.co/7W5mn0c/carbon-8.png)

This is so your shell (whatever type of it) knows that it needs to run your file using bash in the terminal.

Lets get into some basic examples.

![https://i.ibb.co/Hz1VQ1D/carbon-9.png](https://i.ibb.co/Hz1VQ1D/carbon-9.png)

This will return the string “Hello World”. The command “**`echo`**” is used to output text to the screen, the same way as “**`print`**” in python. I suggest you test this out in your terminal to get to grips with bash!

You can also perform normal Linux commands inside your bash script and it will be executed if formatted right. For example we can run the command “**`ls`**” inside our bash script and we will see the output when we run the file. So lets make it do this!

![https://i.ibb.co/HX85VzF/carbon-10.png](https://i.ibb.co/HX85VzF/carbon-10.png)

Now from here on I am going to assume that you have a basic understanding of Linux and its commands, if you don't please go make sure to check out the Linux fundamentals 1 and then come back and try again. [https://tryhackme.com/r/room/linuxfundamentalspart1](https://tryhackme.com/r/room/linuxfundamentalspart1)

I'm also not going to include the **`#!/bin/bash`** at the start of my code snippets otherwise it will take up a lot of room so be aware that you need it always at the start of your files!

Now to run our bash script we must first give it executable permissions

**`Chmod +x yourfile.sh`**

And then we run it using **`./`**

![https://i.ibb.co/ccWWddT/carbon-11.png](https://i.ibb.co/ccWWddT/carbon-11.png)

Please run this for yourself and see what you get.

We can see it has outputted the results of the commands “**`whoami`**” and “**`id`**”.

Answer the questions below

Task 2

Answer the questions below:

1. What piece of code can we insert at the start of a line to comment out our code?

```bash
#
```

1. What will the following script output to the screen, echo “BishBashBosh”

```bash
BishBashBosh
```

********


# Task 3 Variables

Task 3 Variables

Now we are moving onto variables,

in bash these are quite simple and we create them like so:

![https://i.ibb.co/F4c1DFx/carbon-2.png](https://i.ibb.co/F4c1DFx/carbon-2.png)

Where we give the value of **`Jammy`** and assign it to the variable **`name`**.

Please note that for variables to work you cannot leave a space between the variable name, the ”**=**” and the value. They cannot have spaces in.

So how would we now use our variable? Well its also very simple.

We have to add a **`$`** onto front of our variable name in order to use it.

![https://i.ibb.co/CmF2xrZ/carbon-3.png](https://i.ibb.co/CmF2xrZ/carbon-3.png)

If we test this out in our own terminal we get something like this:

```bash
$ name="Jammy"
$ echo $name
Jammy
```

This would output “**Jammy**” to the screen.

Variables make it much easier to store data and rather than typing out the same thing in multiple places we could simply insert our variable with $var and then declare that to a certain value making it easier to fall back on if you do something wrong and need to change it. So how can we debug our code?

Debugging is a very important part of programming so we should get used to problem solving and fixing errors as early as possible. And bash has a few built in features that make our life simple.

When running at the command line you can do:

```bash
**bash -x ./file.sh**
```

You can make a simple bash script(now you know some basic syntax) and make something completely wrong. Then step through your program with debug mode and see what it looks like when it throws errors!

This tells you which lines are working and which lines are not. If you want to debug at a certain point you can insert **`set -x`** into your script and **`set +x`** to end the section like the following:

![https://i.ibb.co/dWYJkjs/carbon-4.png](https://i.ibb.co/dWYJkjs/carbon-4.png)

So lets look at an example. This is our script from earlier being ran with **`bash -x ./example.sh`**

![https://i.ibb.co/288ynDZ/carbon-5.png](https://i.ibb.co/288ynDZ/carbon-5.png)

You can see its outputting a **+** for the command and then the output of what that command executed. If there was an error it would output a **-** on that line this makes it easy to spot where you have gone wrong so you can fix them.

We can also use multiple variables in something like an echo statement. You aren't just limited to using 1!

![https://i.ibb.co/vVp45SD/carbon-6.png](https://i.ibb.co/vVp45SD/carbon-6.png)

Answer the following questions and use this piece of code to guide you.

![https://i.ibb.co/NncnrQ2/carbon-7.png](https://i.ibb.co/NncnrQ2/carbon-7.png)

Task 3

Answer the questions below

What would this code return?

Jammy is 21 years old

How would you print out the city to the screen?

echo $city

How would you print out the country to the screen?

echo $country

**************

# Task 4 Parameters

Task 4 Parameters

We will now look at one of the main features of bash and that's using parameters.

We will firstly  look at parameters specified using the command line when running the file. These come in many forms but often have the "$" prefix because a parameter is still a variable.

Lets start by declaring a parameter that is going to be our first argument when running our bash script.

![https://i.ibb.co/LCnNVNN/carbon-12.png](https://i.ibb.co/LCnNVNN/carbon-12.png)

We now run our script with **`./example.sh Alex`**

And sure enough we get returned with “Alex”

So what if we wanted the 2nd argument? Well the process is very simple and we simply add a **`$2`** instead of **`name=$1`**

Then run with **`./example.sh Alex Tony`**

What do you think it would return?

And it would return "Tony".

What if we didn't want to supply them like this however, and instead it would let us type in our name in a more interactive way, we can do this using **`read`**.

![https://i.ibb.co/tzK62bK/carbon-13.png](https://i.ibb.co/tzK62bK/carbon-13.png)

This code will hang after its ran, this gives you the opportunity to type in your name.

![https://i.ibb.co/BCn4ptM/carbon-14.png](https://i.ibb.co/BCn4ptM/carbon-14.png)

And we can see that it worked!

Maybe try making a little biography maker, where you take the name, age, and job as parameters. Store them inside a variable and then output them to the screen inside a sentence.

However there is so much more that you can do with parameters and I advice you to play around with them, after all practice is what makes you better!

[answer link](Answers%201b24fd413d5749169bae495b1263184d.md)

Answer the questions below

How can we get the number of arguments supplied to a script?

```bash
$#
```

How can we get the filename of our current script(aka our first argument)?

```bash
$0
```

Hint: This is using the $n feature we looked at

How can we get the 4th argument supplied to the script?

```bash
$4
```

If a script asks us for input how can we direct our input into a variable called ‘test’ using “read”

read test

What will the output of “echo $1 $3” if the script was run with “./script.sh hello hola aloha”

hello aloha

************


# Task 5 Arrays

Task 5 Arrays

For this module i suggest you follow along in the attackbox or a standard linux terminal to make it easier to understand.

Arrays are used to store multiple pieces of data in one variable, which can then be extracted by using an index. Most commonly notated as **`var[index_position]`**.

Arrays use indexing meaning that each item in an array stands for a number.

In the array **`['car', 'train', 'bike', 'bus']`** each item has a corresponding index.

All indexes start at position 0

| item | index |
| --- | --- |
| car | 0 |
| train | 1 |
| bike | 2 |
| bus | 3 |

Now we have covered this, let's make an array in bash.

The syntax is as follows.

We have the variable name, in our case ‘transport’

We then wrap each item in brackets leaving a space between each item.

**`transport=('car' 'train' 'bike' 'bus')`**

We can then echo out all the elements in our array like this:

**`echo "${transport[@]}"`**

You can try this in your own terminal and see what it outputs.

Where the "@" means all arguments, and the [] wrapped around it specifies its index.

So what if we wanted to print out the item **`train`**.

We would simply type:

**`echo "${transport[1]}"`**

because the train is at index position 1.

The last thing we will cover is if we want to change an element, or delete it. If we wanted to remove an element we would use the **`unset`** utility.

**`unset transport[1]`**

This now removes the **`train`** item, if we wanted to we could echo it back out and see that it is indeed gone,

Now lets set it to something else. We can do:

**`transport[1]='trainride'`**

If we echo the array then we get:

**`car trainride bike bus`**

So we successfully managed to swap out an element in our array!

As a little side project try building on your previous project of a biography maker, include arrays so that you can store multiple names and multiple facts about the person. Then in the next module we can expand even further.

Given the array please answer the following questions

**`cars=('honda' 'audi' 'bmw' 'tesla')`**

link back

[answer link](Answers%201b24fd413d5749169bae495b1263184d.md) 

Answer the questions below

What would be the command to print audi to the screen using indexing.

echo "${cars[1]}”

Hint: "${variable[index]}”

If we wanted to remove tesla from the array how would we do so?

unset cars[3]

Hint: We can use "unset”

How could we insert a new value called toyota to replace tesla?

cars[3]='toyota’

Hint: use single quotes for the string.

