---
title:      "Apache Groovy and data types"
subtitle:   "Groovy is an optional typed language and in this post we are going to see some data types that can be used."
date:       2022-06-07 22:09
author:     "Omar Bautista"
header-img: "/blog/assets/img/2022/what_is_groovy.png"
category:   techblog
tags:       [joxebus, programming, java, groovy, desveloper]
---

## Apache Groovy and data types

[![What is groovy lang](/blog/assets/img/2022/what_is_groovy.png "Basic concepts of Groovy Lang")](/blog/assets/img/2022/what_is_groovy.png)

Groovy comes with several improvements over Java, today we are going to understand why everything
is an object to Groovy, first let's talk about some classes that will be automatically
be taken when use a specific value.

The following script will allow us to understand the data types assigned per each declaration.

```groovy
def name = '"Joxebus"'  // This variable is used for String interpolation at GString sample                        

def elements = [
                1,                              // java.lang.Integer
                11111111111,                    // java.lang.Long
                11111111111111111111,           // java.math.BigInteger
                0.1,                            // java.math.BigDecimal
                0..5,                           // groovy.lang.IntRange
                'x'..'p',                       // groovy.lang.ObjectRange
                "Normal String",                // java.lang.String
                'Another normal String',        // java.lang.String
                "GString with value $name",     // groovy.lang.GString
                [],                             // java.util.ArrayList
                [:]                             // java.util.LinkedHashMap

]

elements.each{ println it.getClass().name }
```

#### Output
```shell
java.lang.Integer
java.lang.Long
java.math.BigInteger
java.math.BigDecimal
groovy.lang.IntRange
groovy.lang.ObjectRange
java.lang.String
java.lang.String
org.codehaus.groovy.runtime.GStringImpl
java.util.ArrayList
java.util.LinkedHashMap
```

As you can see in the output, there is no primitives on Groovy, in the case of having an `int` declared
this will be automatically taken as it's wrapper `java.lang.Integer`, the same for other types, such
`long`, `byte`, `char`, `short`, etc.

Additionally, when a number is bigger than a `java.lang.Long` this will be assigned to a `java.math.BigInteger`
a special case here will be the numbers decimals, everytime a number with decimals is declared this will
be automatically assigned to a `java.math.BigDecimal` this is because `double` and `float` sacrifices
precision over speed you can look for `IEEE 754` to know more about this issue and the `Standard for Floating-Point Arithmetic`.

Even when Groovy takes this as `BigDecimal` by default, you can still use `double` or `float`

```groovy
double first = 0.09d
double second = 0.01D
```

```groovy
double first = 0.09f
double second = 0.01F
```

But you must know about what I mention before and **never use them for operations over things like money**
this is the output when you try to sum those numbers.

```groovy
double first = 0.09d
double second = 0.01d
double third = first + second
```
#### Result
```shell
0.09999999999999999
```

### Strings

There are different ways to declare a `String` with Groovy:

- `''`: produces normal String **not a `char` or `Character`**
- `""`: produces normal String but allow String interpolation as in the sample by using the `$` dollar sign
- `''' Something here '''`: multiline String
- `""" Something here """`: multiline String with interpolation allowed

**Note:** All the Strings that uses interpolation are assigned as `groovy.lang.GString`

There are more ways to declare a `String` with Groovy, for a full description you can visit the [official
site.](https://groovy-lang.org/syntax.html#all-strings)

### Ranges

To declare a range is as simple as using the operator `..` you can declare a range
of numbers like this:

```groovy
def numbers = 1..9
def letters = 'a'..'z'
```

#### Result
```shell
[1, 2, 3, 4, 5, 6, 7, 8, 9]
[a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, x, y, z]
```

### Collections

There are 2 collections that are the most used in Groovy, `Lists` and `Maps`, to declare and use this
are very simple:

```groovy
def list = ["This", "is", "a", "list"]
```

In the same way you can iterate in the Java way, or you can use the `.each` closure

#### Java Style
```java
for(String it : list) {
   println it    
}
```

#### Groovy Style
```groovy
list.each { 
    println it
}
```

**Note:** `it` is an object provided to any closure and takes the argument as the value in the current
position on _each_ iteration.

If you need to use for example an `Array` instead of a `List` here are some code snippets:

```
String[] words = ["This", "is", "a", "list"]
int[]  numbers = [1,2,3]
```
In this case when you assign the value, Groovy knows what is the final type that have to be assigned.

The `Maps` are very simple too by using the structure `key:value` let's take a look to a quick sample:

```groovy
def map = [name:"Omar", lastname:"Bautista", age:34]
```

And this is how we iterate over a `Map`

#### Java Style

```java
for (Map.Entry<String,String> entry : map.entrySet()) {
    println("Key ${entry.getKey()} Value = ${entry.getValue()}")
}
```

#### Groovy Style

```groovy
map.each{
    println "Key ${it.key} Value = ${it.value}"
}
```

**or**
```groovy
map.each{ key, value ->
    println "Key ${key} Value = ${value}"
}
```

As you can see working with data types with Groovy is very easy, and now you know a little more about
how this works, you can test any of this samples on my [Online Groovy Console](https://onlinegroovyconsole.herokuapp.com/), 
thanks for reading and see you next time. 
