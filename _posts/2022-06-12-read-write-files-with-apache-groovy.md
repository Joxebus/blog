---
title:      "Read / Write files with Apache Groovy"
subtitle:   "This post talk about how we can easily work with files using Apache Groovy"
date:       2022-06-12 21:23
author:     "Omar Bautista"
header-img: "/blog/assets/img/2022/what_is_groovy.png"
category:   techblog
tags:       [joxebus, programming, java, groovy, desveloper]
---

## Read / Write files with Apache Groovy

[![What is groovy lang](/blog/assets/img/2022/what_is_groovy.png "Basic concepts of Groovy Lang")](/blog/assets/img/2022/what_is_groovy.png)


### Reading files

In the previous post I talked about some substantial differences between Groovy and Java, 
now we are going to talk about how to work with Files in Groovy

First, reading files in Groovy is just as easy or easier than reading files in Java.
Of course not, let's first look at an example of reading files in Java which would look something like this.

#### Since Java 8
```groovy
Path filePath = Path.of("file.txt");
StringBuilder contentBuilder = new StringBuilder();

try (Stream<String> stream = Files.lines(Paths.get(filePath), StandardCharsets.UTF_8)) {
    //Read the content with Stream
    stream.forEach(s -> contentBuilder.append(s).append("\n"));
} catch (IOException e) {
    e.printStackTrace();
}

String fileContent = contentBuilder.toString();
```

Of course there are ways to do it in less code, personally I do prefer Groovy's style

```groovy
String fileContent = new File("file.txt").text
```

or we can read line by line

```groovy
new File("file.txt").eachLine { line -> println line }
```

### Writing into a file
Groovy is very intuitive, there is not much to explain, now, if we want to write into file, 
we just need to create a PrintWriter object for the file and then call the method `print` or `println`
to write on it as in the following sample.

```groovy
File file = new File('output.txt')
out = file.newPrintWriter()
10.times { out.println("line $it") }
out.close() // The file needs to be closed for it to be saved to the file
```

As we saw, reading/writing files in Groovy is quite simple.

Now I will show you some samples that might help you when you work with files on Groovy

#### Collect filenames on a directory

```groovy
List<String> fileNames = new File("<your-directory>")
        .listFiles()        // method from Java 8
        .collect{ it.name } // closure from Groovy
```


#### Filter files on a directory with a REGEX
```groovy
String regex = /.*\.pdf/
List<String> fileNames = []
new File("<your-directory>")
        .eachFileMatch(~regex) { file -> // Closure eachFileMatch
          fileNames << file.name         // The file variable is of type java.io.File
        }
```

#### Iterate over directories

```groovy
import groovy.io.FileType

new File("<your-directory>")
        .eachFile(FileType.DIRECTORIES) { directory -> // Closure eachFile
          fileNames << directory.name                  // The directory variable is of type java.io.File
        }
```

There more cool things that you can easily do with Groovy and Files, iterate over a directory, find
all the files in a subdirectory, find text on a file, etc. 

The last example shows how to collect all occurrences of a specific word, it will print the `file name`, 
the `word` and the `lines` on the file where it was found.

```groovy
File dir = new File('<your-directory>')
String regex = /.*\.txt/
String word = "word"

dir.eachFileMatch(~regex) { file ->
  List lineNumbers = []
  file.readLines()
      .eachWithIndex{ line, index ->
        if(line.contains(word)) {
         lineNumbers << index
        }
      }
  
  if(lineNumbers) {
     println "File: ${file.name} contains [$word] at lines $lineNumbers"
  }
}
```

Thanks for reading I hope this samples can help you to better understand how Groovy works with Files.