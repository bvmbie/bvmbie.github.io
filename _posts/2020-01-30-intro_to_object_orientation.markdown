---
layout: post
title:      "Intro to Object Orientation"
date:       2020-01-30 12:08:59 +0000
permalink:  intro_to_object_orientation
---


This blog post will explain some key concepts in Object Oriented Ruby.

### Instance methods and class methods

An **instance method** inside of a class such as:

```
class Person

  def speak
    puts "words"
  end

end
```

is called on the instance of the class, and is dependant on creating an instance. 

```
person1 = Person.new
person1.speak # => "words"
```

**Class methods** are called on the class. They can be defined using the ` self.` keyword. 


```
class Person

  def self.speak
    puts "words"
  end

end


Person.speak # => "words"
```

Class methods can only be called on the class and instance methods can only be called on the instance which is an object created out of the class. Class methods can be called without creating an instance. 

### Instance variables and class variables

Similarly object oriented Ruby has instance variables as well as class variables.

**Instance variables** can be defined by creating a writer method (that defines the variable) and reader method.

```
def name=(name)
    @name = name
 end
 
 def name
    @name
 end
```

Ruby also has a short cut for this

`attr_accessor :name`

Creates a writer and reader method for the variable `@name`

`attr_reader :name` creates only a reader method for the varible name. The variable still needs to be defined.

Instance variables can be defined in a initialize method.

```
def initialize(name)
  @name
end
```

This way variables can be assigned on initialization of the new instance.

```
person1 = Person.new("Laura")
person1.name # => "Laura"
```

**Class varibles** are available to the whole class.

They can be defined with the `@@` notation.

```
class Person 
  @@age = 7
	
	def self.age # reader method
	  @@age
  end

end

Person.age # => 7
```
