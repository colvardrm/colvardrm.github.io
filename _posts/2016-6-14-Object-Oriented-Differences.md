---
layout: post
title: For Those Coming From Object Oriented Programming
---
There are several differences between functional languages and object-oriented languages, as you might imagine. I will focus on Elm, but these apply to several languages.	Firstly, the big difference between functional and object-oriented programming, and really the defining difference, is that **functions are treated as first-class citizens in functional languages**, including Elm. What does this mean? It means you can pass functions around just as you would variables of any type. An example would be beneficial. 


I'll use [the core library's List package](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/List) as an example, specifically, the map function. 

```elm
map : (a->b) -> List a -> List b
```

Looking at the map function, it takes a function that maps from one type to another as one of its parameters, and a list of the type to map to the other. It then applies the specified function to each element in the list, producing a list of the mapped-to type. IF you wanted to, you could think of it as passing a recipe around. In object-oriented languages, you would have a method that makes the recipe with all of the ingredients and gives you the finished product. In functional programming, you could pass the recipe itself to the function with the ingredients, and have it make the recipe for you wherever you want. There are more appropriate analogies as you get deeper in, but this will suffice for now.

	
Another difference lies in Elm's approach to uncertainty. Whereas many object-oriented languages give you certain limited tools to handle errors in the (exceptions for Java and some Javascript), Elm aims to produce code that effectively *cannot* fail, discounting hardware failures. If it crashes, it is because you told it to somewhere in the code, and this is backed up by NoRedInk's claim that their Elm code has not caused a single runtime error in the year they've been using it. I'll discuss this aspect further in the [uncertainty post](http://colvardrm.github.io/Elm-Uncertainty), but for now, back to the differences.




