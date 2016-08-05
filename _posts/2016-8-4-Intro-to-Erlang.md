---
layout: post	
title: Intro to Erlang
---
Erlang is a functional programming language developed by Ericsson originally for the purpose of monitoring and controlling telecom switches, which resulted in its core principles of concurrency, distribution, and fault tolerance. In contrast to Elm, Erlang is not a strongly-typed language. In fact, it doesn't have visible types at all, except at the compiler level and as annotations. Its syntax is a bit ugly, but that's not a particularly big deal. You can see some functions below. As it is a functional language, everything is encapsulated in a function of some kind, except for things like record and module declarations. You can see this below.

```erlang
-module(hello_world)         %the module declaration

%% Exported methods can be used outside of the module. 
%% The numbers after the slash represent the "arity", or number of arguments
-export(hello_world/0, foo/1)

%% Record named state with a field for text, annotated as a string with a default value of ""
-record(state, {text = "" :: string()}).

%% Method showing off the record syntax and variables
foo(State=#state{text = TextToPrint}) ->
  TextToPrint = "Hi",       %This will cause an error unless TextToPrint is already "Hi".
  io:format("~p~n", [TextToPrint]).

%% Method hello_world, which simply prints out "Hello World!"
hello_world() ->
  io:format("Hello World!").


```

What this code also shows is a variable declaration. The "foo" method takes a parameter called "State", which we declare to be a record of "state", declared in the line with -record. Variables in Erlang are capitalized and can be declared inside a function body or in a function head, as it is in the "foo" method. Lowercase words are atoms, which only represent what they are called. For example, the atom 'infinity' does not really represent the concept of infinity, but simply 'infinity' - the term itself. There is a defined order so that terms can be compared, like numbers to atoms. The first io:format call takes the specifications of how to print the variables, and the list of variables to print. If you've used C's printf function, it's very similar logically.

Functions in Erlang are declared with the function name, a set of parentheses containing the arguments, and an arrow. Statements are separated by commas, and functions are ended with a full stop. As indicated in the example, variables cannot be reassigned in Erlang, as it is a single-assignment language. This might seem like a pain, but it helps maintain a clean state by ensuring you always know what the value of a given variable is once it has been assigned. What the above code shows is that the equals sign at first acts as an assignment, then as a pattern match. As a result, the program will crash if the value of TextToPrint is not already "Hi". Pattern matching can be very powerful, but I'll talk about it later.
