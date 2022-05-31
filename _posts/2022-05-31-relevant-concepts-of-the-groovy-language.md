---
title:      "Relevant concepts of the Groovy language"
subtitle:   "Something that describes your post"
date:       2022-05-31 13:04
author:     "Omar Bautista"
header-img: "/blog/assets/img/2022/what_is_groovy.png"
category:   techblog
tags:       [joxebus, programming, java, groovy, desveloper]
---

## Relevant concepts of the Groovy language

[![What is groovy lang](/blog/assets/img/2022/what_is_groovy.png "Basic concepts of Groovy Lang")](/blog/assets/img/2022/what_is_groovy.png)

When I said that I was going to explain to you my way of understanding things, I was very serious,
the truth is that it is not very easy for me to make great descriptions and that is why I will try
to put as many images as possible to exemplify everything that I want to make you understand.

### A bit of Syntax

There are some considerations that we must take into account, as you may have noticed in the previous
example, the use of `( )` for a method and and the `;` to end a line they are not necessary,
we have not created any class to execute these instructions and where is the `main`?,
the main is not necessary in a Groovy application of course, to make our code more readable we can
use them as follows .

[![hello-world-groovy](/blog/assets/img/2022/groovyconsole-02-hello-world.png "groovyconsole-02-hello-world")](/blog/assets/img/2022/groovyconsole-02-hello-world.png)

Hey! Wait... is that Java code? Let's remember that Groovy is a programming language based on Java,
so let's remember that with some exceptions, Java codes are also valid to be executed in Groovy,
of course the idea is to use the characteristics of Groovy to make life easier, but if it exists
something we don't know how to do in groovy, we can always insert Java code anywhere in the script
where we need it.

Before continuing, let's pay attention to the aforementioned codes, note that a string can be defined
by single quotes or quotes without any type of error, everything has a reason, but we will see that later.

### Groovy's Truth

When we make an application in Java, to evaluate a condition we require that it return a value `true`
or `false` (there is no other) Groovy goes further by extending the possibilities according to the
following table and to the next example.

**_Groovy Truth Table_**

[![Groovy Truth Table](/blog/assets/img/2022/groovyconsole-04-groovy-truth1.png "groovyconsole-04-groovy-truth")](/blog/assets/img/2022/groovyconsole-04-groovy-truth1.png)

_**Example in the Groovy Console**_

[![Groovy Truth Example](/blog/assets/img/2022/groovyconsole-04-groovy-truth-1.png "groovyconsole-04-groovy-truth-1")](/blog/assets/img/2022/groovyconsole-04-groovy-truth-1.png)

Wait a minute again... where did the data types go? As you can see, defining a data type is a thing
of the past, although as I mentioned before, they may or may not be defined, depending on the
programming style used, the type of script that is being carried out; there will be times when
defining a data type will be necessary, but we will see that in our next post.

Doubts, comments or contributions are welcome, have a great weekend and see you next time.