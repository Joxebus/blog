---
title:      "Working with Groovy Closures"
subtitle:   "This post is a sample on how to work with Groovy Closures"
date:       2022-06-22 19:40
author:     "Omar Bautista"
header-img: "/blog/assets/img/2022/what_is_groovy.png"
category:   techblog
tags:       [joxebus, programming, java, groovy, desveloper, closure]
---

## Working with Groovy Closures

[![What is groovy lang](/blog/assets/img/2022/what_is_groovy.png "Basic concepts of Groovy Lang")](/blog/assets/img/2022/what_is_groovy.png)

A Groovy closure is a code block or a method pointer, when we use a closure it gives us a default 
variable called "it" and it is the one that receives the data that is sent to it.

#### Closure definition:
```groovy
def clos = { println it }

clos("Hello")
```

#### Output:

```shell
Hello
```


Of course, we can also make our own closures with the parameters that we decide. 
The syntax would be the following:

```groovy
def nameClosure = { parameter1, parameter2 ->
   // Operations to perform with the parameters
}
```


To finish, I will give you a simple exercise:

> Given a written composition, make a Groovy script that does the following:
>
> - Take only the first letter of each word in that wording, and convert it to uppercase.
> - Respect punctuation marks and line breaks.
>
> Sample input text: \
> **Lorem ipsum dolor sit amet, consectetur adipiscing elit. \
> Aliquam vel luctus orci**

#### Groovy Code
```groovy
String text = '''Lorem ipsum dolor sit amet, consectetur adipiscing elit. 
Aliquam vel luctus orci'''

// Definition of the closure
def firstLetterToUpperCase = { it[0].toUpperCase() + it.substring(1) }

String result = text.split(' ').collect(firstLetterToUpperCase).join(' ')

println result
```

#### Output:
```shell
Lorem Ipsum Dolor Sit Amet, Consectetur Adipiscing Elit. 
Aliquam Vel Luctus Orci
```