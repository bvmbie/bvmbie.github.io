---
layout: post
title:      "Working with hashes in Ruby"
date:       2020-01-26 19:23:27 +0000
permalink:  working_with_hashes_in_ruby
---

### What is a hash

Hashes are collections just like arrays. They are useful when the information is catogorical or each value has a name attached to it. 

For example, a shopping list. It has items and each item has a number of how many of them are needed. 

### Creating a hash

A hash can be created by using the implicit form: 

`list = {"apples" => 3, "oranges" => 4}  `

Or by using symbols:

`list = {:apples => 3, :oranges => 4}`

This can be written little bit neater:

`list = {apples: 3, oranges: 4} `

### Retrieving from a hash

If we need a reminder of just how many pears were on the list we can get the value of a key from the hash.

```
list[:pears]  
=> 5
```

### Adding to a hash

If we later decide that we also need to buy pears, we can add to the hash without rewriting the original hash.

```
list[:pears] = 5

puts list  
=> {:apples => 1, :oranges => 2, :pears => 5} 
```

Or we can do the opposite and get the key from the value.

```
list.key(5)  
=> :pears
```

### Removing from a hash

Lets say we have already bought apples. This key and value pair can now be removed from our hash.

```
list.delete(:apples)

puts list
=> {:oranges => 2, :pears => 5} 
```

To completely empty the list we use the `.clear` method

```
list.clear
=> {}
```

To check if our hash is empty use the `.empty?` method

```
list.empty?  
=> true  
```

### Length of a hash

Sometimes it's useful to know the length of the hash without seeing the original hash.

```
list.length  # returns the number of key-value pairs
```

### Itirating over a hash

Lets say we want to return a paragraph of everything we need to buy. This can be done by itirating over each item on the list and interpolating them into a string.

```
list = {apples: 3, oranges: 4, pears: 5}


list.each {|key, value| puts "You need #{value} #{key}"}  

=> You need 3 apples
You need 4 oranges
You need 5 pears
```

### Using a hash as a named parameter

Hashes are also useful when you want to name your parameters. This way you can't accidentally pass arguments in the wrong order. It's especially useful when collaborating with other programmers.

```
def say_hi(name:, greeting:)
  puts "#{greeting} #{name}!"
end

say_hi(name: "Lisa", greeting: "Hello")
=> Hello Lisa!
```


