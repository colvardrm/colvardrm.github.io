---
layout: post
title: A brief introduction to Currying
---

An important part of elm's logic is that functions don't actually take more than one parameter at a time. Going back to List.map:

```elm
map : (a->b) -> List a -> List b
```

This appears to be a function that takes a function that maps from one object **a** to another **b**, and a list of **a** to produce a list of **b**. This is not strictly true. This function actually takes a function that maps from **a** to **b** and produces a function that takes a list of **a**, that then produces a list of **b**. If you were to do something like:

```elm
map : (a->b) -> List a -> List b

-- Two parameters and, as always, one return value. Not good.

toString : a -> String

-- One parameter and one return. Fits what we want.

listToString = List.map toString

-- listToString = <function>: List a -> List String. One parameter and one return value. Good for currying

example = listToString [1, 2, 3, 4]
    
--  example is now a List String
```

This actually doesn't cause an error. It's perfectly fine.

Confused? Welcome to currying.

Currying, in simple terms, is the process of taking a function that takes multiple arguments, and making it only take one. This is one of the things you can do if you have functions as a first class citizen. As you saw in the example, you can make "shortcuts" for functions by going from more generic functions with fewer specified parameters to more specific functions that you pass in as arguments. Currying is pretty important and useful, but that should be a decent enough example for now.
