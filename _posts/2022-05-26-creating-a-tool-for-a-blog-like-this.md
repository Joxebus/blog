## Creating a tool for a blog like this 

![blog-groovy-script](/blog/assets/img/2022/blog_script.png)

Recently I was thinking about creating a blog for my site on [Github](https://joxebus.github.io)
I've already had 2 blogs, one is hosted on Medium and the other on Wordpress, the thing is that
I want to collect everything in a single place, so I find out this site where they explain [how to
create a blog with Jekyll](https://chadbaldwin.net/2021/03/14/how-to-build-a-sql-blog.html) (BTW it is a nice and helpful post)

Anyway, so I read the article and everything was very simple I've already had my profile site with
Github Pages, so I thought it will be nice to have something in another repository and then just add it
to my dot IO profile.

### Laziness

I'm a lazy person, so if have opportunity to create a tool for something to simplify my life, I will do it.

### The programming language

My favorite language since 2010 and till today it's Groovy, so I have created a script that help
me to configure (I know, configuration is a one time thing) and create new blog posts in this repo
in a simple way.

Groovy is a language for the JVM, it compiles to Java bytecode, to me, it's like Java with asteroids
yep I code with Java, so far I like the JVM but not so much the verbosity of Java itself and when I 
knew Groovy it was like having the best of 2 worlds, a Static and Compiled language at the same time.

I had created a series of videos about Groovy on my [YouTube channel](https://www.youtube.com/c/Joxebus) 
everything is on Spanish because I consider that there is not so much info regarding this in that language.

### The tool

To create a script with Groovy is very simple you just need to start a file (in my case is called `blog.groovy`)
with this line at first:

```powershell
#!/usr/bin/env groovy
```

This line tells to your computer that it is a file that runs with Groovy, you need to give
execution privileges and for that you just need to execute the following command:

```powershell
chmod +x blog.groovy
```

Now write your code there, you can either use Groovy or Java that's why I liked so much, anyway
the reason why I wrote that tool is because the file format for the archives with Jekyll is like
`yyyy-MM-dd-title-of-your-post.md` and don't want to write things like that everytime I want to create
a new entry to me is easily to do something like this.

```powershell
blog -n "Creating a tool for a blog like this"
```

That's how I automatically create a new entry with date and the title from anywhere on my terminal,
see, I'm lazy but now when I want to create a new blogpost I will just need to execute that command
and that's it, if you are interested on this tool you can see the source code in this project called
[blog-jekyll-tool](https://github.com/Joxebus/blog-jekyll-tool), I'm open to receive feedback and 
pull requests, thanks for reading me.