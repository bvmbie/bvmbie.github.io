---
layout: post
title:      "Cheatsheet for Looping"
date:       2020-01-17 09:17:14 +0000
permalink:  cheatsheet_for_looping
---


Looping is an essential concept in Ruby. It allows us to repeat a block of code multiple times without having to write it out multiple times. In this blog we are going to look at four ways to make a loop: `loop`, `while`, and `for`.

`loop do`

A simple way of creating a loop is using the `loop` method. It takes in a block of code in between `do` and `end` words, and keeps running this until you exit the loop with `break` keyword. It's very important to remember to break the loop! Otherwise you have created an infinite loop which will likely cause a crash.

Examples:

```
loop do
  puts "This will keep repeating"
  break
end
```

But if the whole idea of a loop is to repeat something this is not very useful. Lets create a more useful code that prints out all even numbers from 0 to 10. We will use a condition with `if` keyword. Only once the condition is true, we will break out of the loop.

```
i = 0
loop do
  i += 2
	puts i
	if i == 10
	  break
  break
 end
end
```

`while` loops

While loop keeps looping a code while the condition its given is true, when the condition becomes false, it exits out of the loop. No `break` keyword is needed.

Example:

```
i = 0

while i < 10
  puts "Hello World"
	i += 1
end
```

This will run as long as i is less than 10. It's important to keep incrementing i on each loop - otherwise we are stuck in an infinite loop.

For loops

The for loop is different from the previous examples because it is used to loop over a collection of elements such as an array or a range. It doesn't have the chance of turning into an infinite loop because it will only run through the collection one time.

Example with an array:

```
x = [1, 2, 3]

for i in x do
  puts i
end
```

This will output all the elements in the x array one time.

Example with a range:

```
for i in 1..3 do
  puts i
end
```

This will output numbers from 1 to 3 one time.



