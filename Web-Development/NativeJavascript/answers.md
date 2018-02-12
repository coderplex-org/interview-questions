# Answers for the Front end questions Native script
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
2. Inheritance works differntly in javascript not like in other languages , here we have parent object set in the prototype properties of the object which it refers if it does not find the current object. It will be a chain of references to parent objects in case of multiple inheritance so it is called prototype chain.
3. Closures in javascript is the block of code and the variables used in it are binded to the block though the variables are defined in its parent object.
4. `var` variables are hoisted prior to the variables are executed but `const` and `let` or not. And simple properties defined by `const` cannot be changed.
5. b will be `undefined` as only the variables are hoisted but not the assignment.
6. We know javascript is multi threaded . Browser will have javascirpt engine thread and network thread , so when network request is completed from network thread which is running parallely to javascript engine thread and the javascript engine will execute the network request callback once it finshes its request.
7. Promises make syntax easier and are best way to handle asynchronous functions. We can do that with callback but when there are chain of asynchronous functions it is difficult to handle there.
8. React more developer friendly and Angular build on solid software principles like MVC and dependency Injection .
9. Browser are provding options to throttle networks so we can customize speed of network.
10. `use strict` helps the devlopers to write javascript in a secured way and throw errors if they are any undeclared vairables .