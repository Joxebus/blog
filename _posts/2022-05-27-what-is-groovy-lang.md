---
title:      "What is Groovy Lang?"
subtitle:   "Groovy is an optional typed language designed to compile to bytecode compatible with the JVM"
date:       2022-05-27 19:50
author:     "Omar Bautista"
header-img: "/blog/assets/img/2022/what_is_groovy.png"
category:   techblog
tags:       [groovy, groovylang, programming, joxebus, jvm, java]
---

## What is Groovy lang?

[![What is groovy lang](/blog/assets/img/2022/what_is_groovy.png "What is Groovy")](/blog/assets/img/2022/what_is_groovy.png)

There is something that is very true, and I am not going to deny it, nothing like first-hand information, 
by this I mean that good documentation or information on programming issues is usually in English, 
this time I will try to do a Spanglish-style tutorial where each one of us can understand what we are 
talking about with the least loss of information and relevant concepts. I will try!

We could say that Groovy…

- is a dynamic  and agile language for the [JVM](http://es.wikipedia.org/wiki/JVM "Java Virtual Machine") (JAVA Virtual Machine)
- it has the capabilities and strengths of Java but with additional and very powerful features inspired by languages such as [Python](http://es.wikipedia.org/wiki/Python "Python"), [Ruby](http://es.wikipedia.org/wiki/Ruby "Ruby"), [Smalltalk](http://es.wikipedia.org/wiki/Smalltalk "Smalltalk")  among others.
- makes new programming features available to JAVA developers in most cases without the need for a learning curve.
- integrates all existing JAVA features, objects and libraries.
- and much much more ([click here](http://groovy-lang.org/documentation.html "Groovy Documentation") to see the complete documentation).

We could say that Groovy is JAVA on steroids. With a few exceptions, JAVA codes are also valid codes 
for Groovy. In fact, when programming in Groovy, we can assume that we can perform certain tasks 
without needing to import classes, just as JAVA imports the java.lang package  Groovy inherits by default this behavior for packages:

```shell
- java.io
- java.math
- java.net
- java.util
- groovy.lang
- groovy.util
```

This means that these packages do not need to be imported to make use of their classes and functions. 
When scripting this is very efficient, since we don't need to worry if we mistakenly forget to import 
one of these commonly used classes.

There are many concepts that we should read thoroughly to fully understand where the idea of 
Groovy comes from, but the truth is that I leave that to you, for now there are some considerations 
that we must take into account to be able to execute Groovy Scripts on our PC.

**Installation**

Considerations to start programming with Groovy:

- Groovy runs on the JVM so I recommend downloading the JDK first from the Oracle page.
- You must download the latest stable version of Groovy, for today this would be 4+ and you can 
download it [here](https://groovy.apache.org/download.html "Download Groovy") .

Once installed, open the console and type the following command:

```shell
> groovy -v

Groovy Version: 3.0.6 JVM: 16.0.2 Vendor: GraalVM Community OS: Mac OS X
```


[![Groovy Version](/blog/assets/img/2022/groovy_version.png "cmd-groovy-version")](/blog/assets/img/2022/groovy_version.png)

Another simple way to install it is by unsing [SDKman](https://sdkman.io/ "Download and install SDKman")

```shell
sdk install groovy
```

or 

```shell
sdk install groovy <specific_version>
```

We restart the console and run the command again `groovy -v` and it should already have been configured for testing.

Doubts, comments or contributions are welcome, in the next post we will see how to make our first `hello world!` and some Groovy basics.