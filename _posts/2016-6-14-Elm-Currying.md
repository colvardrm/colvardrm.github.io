---
layout: post
title: A brief introduction to Currying
---

An important part of elm's logic is that functions don't actually take more than one parameter at a time. Going back to List.map:

```elm
map : (a->b) -> List a -> List b
```

This appears to be a function that takes a function that maps from one object **a** to another **b** and a list of **a** to produce a list of ***b***. This is not strictly true.
