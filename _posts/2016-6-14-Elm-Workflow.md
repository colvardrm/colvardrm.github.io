---
layout: post
title: Workflow in Development
---

One of the problems I've faced recently is in the way to approach the workflow in Elm. I'm used to writing a fair amount of code all at once and testing it, but this is bad practice. More recently, though, I've been transitioning over to many small cycles of development with immediate testing. This is, oddly enough, partly because of Elm's structure and encouraged programming style. It's recommended right in the Elm tutorial to develop in small bits, first establishing a base and then slowly adding on to it. There are some pretty good lessons to be learned from functional programming that can apply to object-oriented programming as well. Things like:

* One function should do one thing. It is strongly discouraged to have functions with side effects in Elm. Each function should do exactly what it says in the name, and nothing else
<li> Because one function should do one thing, make a function for any process more complicated than a few lines at most. This makes the code much more readable. Also, avoid anonymous functions where the purpose isn't immediately obvious. 

```elm
List.map square [1,2,3,4] 
```

is more readable than 

```elm
List.map \n -> n*n [1,2,3,4]
```

and this only becomes more true as the functions get more complicated
</li>
* For functional languages specifically, a helpful tip would be to pretend the function you need in the current function already exists, then write the functions you need to make that true. It's much easier to think of what you need now than what you'll need to do for the entire project to work all at once.
