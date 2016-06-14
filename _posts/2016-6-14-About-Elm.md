---
layout: post	
title: About Elm
---
Elm is a functional programming language that compiles to Javascript, written by Evan Czaplicki for the purpose of having a functional way to program Web UIs. You can see the tutorial for the Elm architecture at [the elm architecture tutorial page](http://guide.elm-lang.org/), and download the core at [the core's github page](https://github.com/elm-lang/core). Completing the tutorial grants a basic understanding of how Elm programs are constructed, as well as some of the more important features of Elm, like its view of model-view-controller, commands, subscriptions, and some basic UI creation. If you have a good understanding of functional languages, especially Haskell, Elm will be a fairly easy transition. For others, [it will require a bit of a shift](http://colvardrm.github.io/Object-Oriented-Differences).

Elm focuses on ensuring good coding practices by enforcing them through its strong typing system, single assignment, and approach to handling uncertainty. Elm's systems strongly encourage programming in small chunks, and force you to handle errors throughout your application. While this may sound annoying, by forcing you to do it, it can prevent many runtime errors in practice by not allowing the program to compile until all cases are handled. For big applications where errors could be in one of many files made up of thousands of lines of code, this explicit approach can be extremely beneficial.

The syntax of elm is pretty similar to Haskell. Functions are denoted by arrows, like so:

```elm

toString : a -> String

```

toString is a function that takes a generic type **a** and returns a String. Speaking of types, types always begin with capital letters in Elm, and variables begin with lowercase letters. Type annotations, like the one shown above, declare the type of a variable/function (technically the same thing in Elm, separated to make it a bit clearer). Type aliases are quite a bit like constructors for object-oriented languages, but are really more like records. Their syntax is something like:

```elm

type alias Person =
                  { name : String
                  , age : Int
                  }
```

A very important note with these is that a 'constructor' function is automatically generated from this name. So if I wanted to create a Person now, I could just declare it as:

```elm

p = Person "Bob" 23

-- p is now a person.

p.name     --Returns "Bob"
p.age      --Returns 23

```

This follows the standard function syntax, which is the function name followed by each parameter in order separated by spaces.
