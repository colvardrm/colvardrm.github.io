---
layout: post	
title: Pattern Matching in Erlang
---
Pattern matching is a simple concept that provides a lot of power to your programs. Erlang and Elm both use it in case...of statements, and it is used to describe how to deal with different inputs to the function. In Erlang, if a case statement doesn't have a catch-all clause, the compiler won't complain. The program will simply crash if it gest an unexpected input, which is actually a good thing in Erlang. In Elm, you must handle all cases for the program to even compile.

```erlang

%% Method showing the case syntax with a catch-all clause
bar(Text) ->
  case Text of
    "Hi" -> something;
    _ -> something_else
  end.


%% Method showing how cases don't need to handle every case
foo(Text) ->
  case Text of
    "Hi" -> something;
    "Hello" -> something_else
  end.


```

As you can see, you specify what you want the input to the statement to look like, then handle the case for it. If you want to have a catch-all clause (which you often don't, as it is good to know when you get unexpected input instead of swallowing the error), you can use the "_" to catch everything.
