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



Call/Apply:-


The Apply and Call methods are two of the most often used Function methods in JavaScript, 
and for good reason: they allow us to borrow functions and set the this value in function invocation.
 In addition, the apply function in particular allows us to execute a function with an array of parameters, 
 such that each parameter is passed to the function individually when the function executes—great 
 for variadic functions;
a variadic function takes varying number of arguments, not a set number of arguments as most functions do.


.call():-

syntax:function.call(thisArg, arg1, arg2, ...);
    thisArg:
         Optional. The value of this provided for the call to a function. Note that this may not be the actual 
         value seen by the method: if the method is a function in non-strict mode , null and undefined will be 
         replaced with the global object and primitive values will be converted to objects.
    arg1, arg2, ...:
          Optional. Arguments for the function.

   Return value:

       The result of calling the function with the specified this value and arguments. 
       A different this object can be assigned when calling an existing function. this refers to the current
        object, the calling object. With call, you can write a method once and then inherit it in another object, 
        without having to rewrite the method for the new object.

      

.call()  method allows the calling of a function in a way that 'this' can be specified, 
while also passing in required arguments, if any, to the function.

 i.e. having a function fx:
 var fx = function (arg1,arg2) {
          console.log(this,arg1,arg2);
}

and calling it:

fx.call(null, "first params", "second params"); 
//logs: null, “first params”, “second params”

//and...

fx.call({id : 1, name : "akpos"}, "first params", "second params"); 
//logs {id : 1, name : "akpos"}, "first params", "second params"


.apply() :-
syntax();
                func.apply(thisArg, [argsArray])


            thisArg:
                  Optional. The value of this provided for the call to func.
                  Note that this may not be the actual value seen by the method: if the method is a function
                   in non-strict mode code,null and undefined will be replaced with the global object, 
                   and primitive values will be boxed.
            argsArray:
               Optional. An array-like object, specifying the arguments with which func should be called, 
               or null or undefined if no arguments should be provided to the function. 

.apply() method  is very similar to .call(), just that it requires you to specify the passed arguments to the function as arrays.
  we are using above fx function 

  var fx = function (arg1,arg2) {
          console.log(this,arg1,arg2);
}

fx.apply(null, ["first params", "second params"]); 
//logs null, "first params", "second params"

//and... 

fx.apply({id : 1, name : "akpos"},[ "first params", "second params"]);
//logs {id : 1, name : "akpos"}, "first params", "second params"

as you can see, .call() and .apply() only differ in how they handle function arguments.
