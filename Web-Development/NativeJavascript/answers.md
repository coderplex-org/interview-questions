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
6. We know javascript is multi threaded . Browser will have javascirpt engine thread and  network thread , so when network request is completed from network thread which is running parallely to javascript engine thread and the javascript engine will execute the network request callback once it finshes its request.
7. 