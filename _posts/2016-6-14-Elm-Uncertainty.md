---
layout: post
title: Uncertainty in Elm
---

As mentioned before in the [post about differences between functional and object-oriented programming](http://colvardrm.github.io/Object-Oriented-Differences), Elm handles uncertainty in a very different way from object-oriented languages. At its core lies three structures that help you deal with functions outside of Elm in a functional way - Maybe, Result, and the less common Task. These simply represent operations that are inherently uncertain - decoding a Json object, parsing an integer from a string, these sorts of things. In object-oriented languages, it is up to you to handle the potential for these operations failing by throwing and catching exceptions. This leads to situations in large projects where you aren't certain of whether an exception has been handled or not somewhere in the code, possibly in some other file. Elm forces you to handle these cases every time they come up before the program will even compile. Each module must handle its own problems. If your program compiles, it will run without having to worry about exceptions.
