---
title:      "Differences between Groovy and Java"
subtitle:   "This article will give you an overview about the differences between Groovy and Java language."
date:       2022-06-01 12:22
author:     "Omar Bautista"
header-img: "/blog/assets/img/2022/what_is_groovy.png"
category:   techblog
tags:       [joxebus, programming, java, groovy, desveloper]
---

## Differences between Groovy and Java

[![What is groovy lang](/blog/assets/img/2022/what_is_groovy.png "Basic concepts of Groovy Lang")](/blog/assets/img/2022/what_is_groovy.png)

In the [previous post]({{ site.baseurl }}{{ page.previous.url }} "Groovy Basics") we saw some differences 
between Groovy and Java, let's remember that Groovy is based on Java, Python, Smalltalk among others 
as I mentioned in the [post](/blog/techblog/2022/05/27/what-is-groovy-lang.html "What is Groovy?"). 
Well, some of the points that we must touch to remember would be the following.

<table width="100%" align="center"><tbody><tr><td width="25%"><h2>&nbsp;<strong>Case</strong></h2></td> 
<td width="25%"><h2><strong>Groovy</strong></h2></td><td width="25%"><h2>&nbsp;<strong>Java</strong> 
</h2></td><td width="25%"><h2><strong>Difference</strong></h2></td></tr><tr>
<td width="25% ">&nbsp;<strong>Variables</strong></td>
<td width="25%">&nbsp;def variable<div></div>&nbsp;def list = []</td>
<td width=" 25%">&nbsp;String variable;<div></div>&nbsp;ArrayList list = new ArrayList();</td>
<td width="25%">In Java you always have to define a variable type, in Groovy it is not necessary to 
specify what type it is, nor are the ; except&nbsp;when 2 or more variables are declared on one line.</td></tr>
<tr><td width="25%">&nbsp;<strong>Assigning values</strong></td>
<td width="25%">&nbsp; variable = "Hello Goovy World"<div></div>&nbsp;variable = 12</td><td width="25%">&nbsp; variable = "Hello World";
<div></div>&nbsp;variable = 12; // data type error</td><td width="25%">&nbsp;Groovy allows the flexibility 
of changing the data type at runtime, very useful but remember not to abuse, you can lose track of 
what it does your code.</td></tr><tr><td width="25%">&nbsp;<strong>Print to console</strong></td>
<td width="25%">&nbsp; println variable</td><td width="25%">&nbsp;System.out.println(variable);</td>
<td width="25%">&nbsp;Groovy reminds us a bit of the way that&nbsp;we printed&nbsp;our C/C++ codes 
saves us writing unnecessary stuff.</td></tr><tr><td width="25%">&nbsp;<strong>Conditions</strong></td> 
<td width="25%">&nbsp;<a title="Groovy Truth Table" href="/blog/assets/img/2022/groovyconsole-04-groovy-truth1.png" target="_blank">Groovy Truth</a>&nbsp;(Groovy Truth)</td>
<td width="25%">&nbsp;boolean comparison;</td><td width="25 %">&nbsp;In Java conditions only work with 
Boolean types (true/false)</td></tr></tbody></table>

### First steps with Groovy

I hope that this table, although it is not a lot of information, will help you remember what was in 
the previous post, however, it is important that you take into account some points from now on so 
that you begin to adopt a certain style in your programming. In my words I will try to explain to you what it is.

#### Before starting to program (Conventions)

Convention may refer to:

- The uses and customs
- An international treaty
- Code guidelines

Broadly speaking, as listed in the 2 previous points, the conventions are the customs that we have 
when programming (standards) or whatever they like to call it in their way of understanding it, 
they help our code to be more readable to the user. time to program but not only that, given that 
in development matters we will reach a point where I will begin to explain the development of Groovy 
on Grails for web applications, it is essential that you follow these simple instructions that I show you below.

Note: Later we will see in depth the importance of conventions and why
use them, but if I recommend that you start using them from this
Time for them to get used to them.

In Java it is very common to see these conventions, possibly we had not even noticed but let's start 
with the creation of libraries, the same ones that you add to your classes with the word `import`. 
Let's imagine that we are participating in a project where multiple companies of development, 
the conventions for the libraries that we create should bear the name of the page of our company. 
Suppose that the following url _**www.mywebpage.com**_ 
the way we should organize our libraries (package) would be in the following way `com.mywebpage.MyClassName`

The convention is almost self-explanatory, it begins with the url of our company and from there the 
convention for classes and others begins, it would be something like the following.

- `ClassName`: The first letter of each word is capitalized
- `methodName()`: Methods take the first lowercase and each word extra goes first in uppercase
- `variableName`: Same convention as methods

These are some simple but very useful recommendations that I remind you **take into account** I add an example.

```groovy
class MyFirstClass {
    def variable
    def variableLarge
    def largestVariable

    static ExampleMethod(){
        
    }
}
```

#### New operators and new features

Let's remember that Groovy is a functional, dynamic, flexible language, described by some as almost "magical" now I will show you why, this is due to operators like these

##### `?` _(Null-Safe Object Navigation)_

Checks that a reference is not null before calling a method on it. Goodbye NullPointerException

#### Example:
```groovy
if (obj?.value != null) {
    ...
}
```

##### `?:` _(Elvis)_

Is it an `if...then...else` structure that replaces the ternary operator 

```shell
<condition> ? <expression1> : <expression2>
```

#### Example: Java
```groovy
String name = (person.getName() != null) ? person.getName() : "<unknown>"
```

#### Example: Groovy

```groovy
String name = person.getName() ?: "<unknown>" // Groovy truth
```

#### `*.` (The Spread-Dot Operator)

Use:
```shell
<collection>*.<property>
```

Example:
```groovy
List names = people*.getName()

List names = people*.name
```


##### `<=>` _(Spaceship)_

This operator returns a value of (1,0,-1) depending on whether it is greater(<), equal(=) or less(>) and is used to compare two objects with each other, just like the equals() method of the Object class that all objects have but I show them with an example:

##### Java example:

```java
public int compare(int i1, int i2) {
    if (i1 == i2) return 0;
    else if (i1 < i2) return -1;
    else return 1;
}
```


##### Example in Groovy:

```groovy
int compare(int i1, int i2) {
    i1 <=> i2
}
```


There is still more to come, but I think that this post is enough, I recommend you do some tests in 
the GroovyConsole, we will continue next time with the so-called **closures** of Groovy and how they 
are used and make our lives easier in a little way conventional, I leave you a screenshot to make 
the operation of these operators a little clearer.

[![New Operators part 1](/blog/assets/img/2022/groovy-newoperators-1.png "groovy-newOperators-1")](/blog/assets/img/2022/groovy-newoperators-1. png)
