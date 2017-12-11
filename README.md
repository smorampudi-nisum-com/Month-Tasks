# Month-Tasks

Closures:-
A closure is an inner function that has access to the outer (enclosing) function’s variables—scope chain. The closure has three scope chains: it has access to its own scope (variables defined between its curly brackets), it has access to the outer function’s variables, and it has access to the global variables.

The inner function has access not only to the outer function’s variables, but also to the outer function’s parameters. The inner function cannot call the outer function’s arguments object, however, even though it can call the outer function’s parameters directly.

We can  create a closure by adding a function inside another function.


1)Closures have access to the outer function’s variable even after the outer function returns.
    closures are created when you define a function, not when you execute it. Closures also don’t go away after you execute      that function.
   We can access the data in a closure long after a function is defined and after it gets executed as well.
2)Closures store references to the outer function’s variables.
3)Since closures give us references to variables in scopes, the access that they give us means both read and write, not just read.
4)closures give us access to nested scopes at the time we define functions, when we define multiple functions in the same scope, that scope is shared among all created closures, and of course, because of this, the global scope is always shared among all closures.
