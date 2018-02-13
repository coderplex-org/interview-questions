# Answers to the frontend questions Native script
1. 
```
function sum(){
    let 
        sumOfArgs=0,
        i=0;
        for(;i<arguments.length;i++){
            sumOfArgs+=arguments[i];
        }
    return sumOfArgs
}
```
2. Inheritance works differently in javascript not like in other languages, here we have parent object set in the prototype properties of the object which it refers if it does not find the current object. It will be a chain of references to parent objects in case of multiple inheritances so it is called prototype chain.
3. Closures in javascript are the block of code and the variables used in it are bound to the block through the variables are defined in its parent object.
4. `var` variables are hoisted prior to the variables are executed but `const` and `let` or not. And simple properties defined by `const` cannot be changed.
5. b will be `undefined` as only the variables are hoisted but not the assignment.
6. We know javascript is single threaded but the browser is not. The browser will have javascript engine thread and network thread, so when a network request is completed from network thread which is running parallelly to javascript engine thread and the javascript engine will execute the network request callback once it finishes its request.
7. Promises make syntax easier and are the best way to handle asynchronous functions. We can do that with callback but when there is a chain of asynchronous functions it is difficult to handle there.
8. React more developer friendly and Angular build on solid software principles like MVC and dependency injection.
9. Browsers are providing options to throttle networks so we can customize the speed of a network.
10. `use strict` helps the developers to write javascript in a secured way and throw errors if they are any undeclared variables.