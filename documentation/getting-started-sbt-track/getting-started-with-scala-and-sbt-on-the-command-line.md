---
title: Getting Started with Scala and sbt on the Command Line
layout: inner-page-no-masthead
disqus: true
redirect_from:
  - documentation/getting-started-sbt-track/getting-started-with-scala-and-sbt-in-the-command-line.html
next-page: testing-scala-with-sbt-on-the-command-line
---

In this tutorial, you'll see how to create a Scala project from
a template. You can use this as a starting point for your own
projects. We'll use [sbt](http://www.scala-sbt.org/0.13/docs/index.html), the de facto build tool for Scala. sbt compiles,
runs, and tests your projects among other related tasks.
We assume you know how to use a terminal.

## Installation

1. Make sure you have the Java 8 JDK (also known as 1.8)
    * Run `javac -version` on the command line and make sure you see
    `javac 1.8.___`
    * If you don't have version 1.8 or higher, [install the JDK](http://www.oracle.com/technetwork/java/javase/downloads/index.html)

2. Install sbt
    * [Mac](http://www.scala-sbt.org/0.13/docs/Installing-sbt-on-Mac.html)
    * [Windows](http://www.scala-sbt.org/0.13/docs/Installing-sbt-on-Windows.html)
    * [Linux](http://www.scala-sbt.org/0.13/docs/Installing-sbt-on-Linux.html)

## Create the project
1. `cd` to an empty folder.
* Run the following command `sbt new scala/hello-world.g8`.
This pulls the 'hello-world' template from GitHub.
It will also create a `target` folder, which you can ignore.
* When prompted, name the application `hello-world`. This will
create a project called "hello-world".
* Let's take a look at what just got generated

```
- hello-world
    - project (sbt uses this to install manage plugins and dependencies)
        - build.properties
    - src
        - main
            - scala (All of your scala code goes here)
                -Main.scala (Entry point of program) <-- this is all we need for now
    build.sbt (sbt's build definition file)

```

After you build your project, sbt will create more `target` directories
for generated files. You can ignore these.

## Running the project
1. `cd` into `hello-world`.
* Run `sbt`. This will open up the sbt console.
* Type `~run`. The `~` is optional and causes sbt to re-run on every file save,

allowing for a fast edit/run/debug cycle. sbt will also generate a `target` directory
which you can ignore.

## Modifying the code
1. Open the file `src/main/scala/Main.scala` in your favorite text editor.

* Change "Hello, World!" to "Hello, New York!"
* If you haven't stopped the sbt command, you should see "Hello, New York!"
printed to the console.
* You can continue to make changes and see the results.


## Adding a dependency
Changing gears a bit, let's look at how to use published libraries to add
extra functionality to our apps.

1. Open up `build.sbt` and add the following line anywhere in the file:

```
libraryDependencies += "org.scala-lang.modules" %% "scala-parser-combinators" % "1.0.5"
```

Here, `libraryDependencies` is a set of dependencies, and by using `+=`,
we're adding the [scala-parser-combinators](https://index.scala-lang.org/scala/scala-parser-combinators) dependency to the set of dependencies that sbt will go
and fetch when it starts up. Now, in any Scala file, you can import classes,
objects, etc, from scala-parser-combinators with a regular import.

Find published libraries at [Scaladex](https://index.scala-lang.org/).

## Next steps
Now that you know how to create a Scala project, you
can continue learning online for free with [Scala Exercises](http://scala-exercises.org) or choose
from our [list of educational resources](http://scala-lang.org/documentation/).

[Up Next: Testing Scala with sbt on the command line]({{ site.baseurl }}/documentation/getting-started-sbt-track/testing-scala-with-sbt-on-the-command-line.html)
