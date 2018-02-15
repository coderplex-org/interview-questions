# Answers to the frontend questions Native script
1. 
Without ES6
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
OR
With ES 6 

```
function sum(...args) {
  return args.reduce((a, b) => a + b);
}
```

2. Prototypes are the mechanism by which javascript gets the inheritance. In other Object Oriented languages inheritance is implmented by copying the properties of the parent to children but in javascirpt a link is formed between parent to children with a property called __proto__ .

Each object in javascript has a reference to the proto object by which it can access properties and objects from its parent object. So if we change the parent property the from child we are actually changing parent itself.

3. Closures in javascript is the phenomona in javascript where the javascript engine will bind the  variables declared outside the function and used inside the function like below. Here name is 
```
function memberAge(name){

    return function(age){
        console.log(name+ " age is "+age);
    }

}
var printAge = memberAge("Raj");

printAge(30); // prints Raj age is 30
```
Variables inside the function has access to the memory of outer declared variables though the outside function or context is no longer running.
4. `let` and `const` are scoped to the a block of code and same is not in the case of `var` .
5. b will be `undefined` as only the variables are hoisted but not the assignment.
6. We know javascript is single threaded but the browser is not. The browser will have javascript engine thread and network thread, so when a network request is completed from network thread which is running parallelly to javascript engine thread and the javascript engine will execute the network request callback once it finishes its request.
7. Promises make syntax easier and are the best way to handle asynchronous functions. We can do that with callback but when there is a chain of asynchronous functions it is difficult to handle there.
8. React more developer friendly and Angular build on solid software principles like MVC and dependency injection.
9. Browsers are providing options to throttle networks so we can customize the speed of a network.
10. `use strict` helps the developers to write javascript in a secured way and throw errors if they are any undeclared variables.