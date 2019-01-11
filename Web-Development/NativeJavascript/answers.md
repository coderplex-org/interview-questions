# Answers to the frontend questions Native script
1. Write a function which can add all the arguments and return the value ?
 
 Before ES6
 
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

2. Explain the inheritance in javascript?
    
    Prototypes are the mechanism by which javascript gets the inheritance. In other Object Oriented languages, inheritance is implemented by copying the properties of the parent to children but in javascript a link is formed between parent to children with a property called `__proto__` .
    Each object in javascript has a reference to the proto object by which it can access properties and objects from its parent object. So if we change the parent property the from the child we are actually changing parent itself.


3. Explain the closures?
    
    Closure in javascript is the phenomenon in javascript where the javascript engine will bind the variables declared outside the function and used inside the function like below. Here `name` is 
    ```
    function memberAge(name){

        return function(age){
            console.log(name+ " age is "+age);
        }

    }
    var printAge = memberAge("Raj");

    printAge(30); // prints Raj age is 30
    ```
    Variables inside the function have access to the memory of outer declared variables although the outside function or context is no longer running.


4. Difference between `var` ,`let` & `const` ?
    
    `let` and `const` are scoped to a block of code and same is not in the case of `var`.
    ```
    {
        var x=1; // assigend to global scope
        let y=2; // block scoped
        const z=3:
        y="3";
    };

    console.log(x); // prints 1
    console.log(y); // Reference error 
    ```
    `const` is used for binding a varaible name for example x to value and see that no rebinding happens.

    ```
    const x = "6";
    x={y:"1"}; // Type error

    ```
    But we can assign a value to x.y but not the binding of variable x to the object.
    ```
    const x={};
    x.y=7;
    console.log(x.y)

    ```

5. What would be the output of the following code?
    ```
    function a(){
        console.log(b);
    }
    var b=6;
    a();
    ```
    
    b will be `undefined` as only the variables are hoisted but not the assignment.


6. How the javascript engine and Browser handles asynchronous calls?
    
    Javascript Runtime has a message queue, an event loop and a call stack which will help to execute its asynchronous calls. 

    The **call stack** is where the javascript runtime stack up of all its execution context if there are nested calls. 

    ```

    function foo(b) {
    var a = 10;
    return a + b + 11;
    }

    function bar(x) {
    var y = 3;
    return foo(x * y);
    }

    console.log(bar(7)) // returns 42

    ```
    - Here when `bar` is called it will create two frames in the call stack. One for the current execution context and another one for `bar`.
    - `bar`  will call `foo` and pushed one more execution context into the call stack.
    - When `foo` is finished its execution context gets popped out and the `bar` will be returned control. 
    - When `bar` is finished its execution context gets popped out the call stack and the current execution context continues till it finishes

    **Event loop** checks if call stack is empty and if anything appears in message queue . If there is any function appears in message queue and call stack is empty then the event loop pushes the oldest function from message queue to call stack where it gets executed.

    **Message queue** is where once the asynchronus calls are finished their call back functions are pushed to this queue.

    So though at any time only one thing running in javascript but event loop helps it to execute the asynchronous callbacks in message queue from call stack which got loaded into message queue once an asynchronous function is fixed.

    https://www.youtube.com/watch?v=8aGhZQkoFbQ


7.Difference between callbacks and promises?
    
    Callback is the function which gets executed once the asynchronous callback finishes.
    Promise is an object represents the completion and failure of asynchronous operation. 

    When Promises are created it will have two functions as parameters `resolve` and `reject` .`resolve` is the function to be called when the asynchronous function is success and reject when it got failed. 
    A promise can success or fail only once. If promise is chained with callbacks using `then` and `catch` the correct callback is executed is based on the success(`resolve`) or failure (`reject`)  of this promise respectively. 

    Using `then` function we can return Promises and can be chainable. This will help us to create asynchronous functions depend on asynchronous function.

    ```
    var prom=new Promise(function(resolve,reject){

        setTimeout(function(){
            resolve("Hi");
        },1000)
    });
    prom.then(function(response){
    return ( new Promise(function(resolve,reject){
            setTimeout(function(){
            resolve(response+ " John")     
            },1000)
    }))

    }).then(function(response){
        console.log(response) // prints Hi John after 2000 seconds
    })

    ```
    https://developers.google.com/web/fundamentals/primers/promises 
    https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Using_promises#Guarantees



8. What are the differences between React and Angular?
    
    React more developer friendly and Angular build on solid software principles like MVC and dependency injection.

    https://www.telerik.com/docs/default-source/whitepapers/telerik-com/choose-the-right-javascript-framework-for-your-next-web-application_whitepaper.pdf?download=true


9. How do you simulate the low speed networks?
    
    Browsers are providing options to customize network speed so we can test the slow network speeds. We can check in network tab in Chrome Dev tools.


10. Why the `use strict` is used?
    
    `use strict` tells the javascript runtime to execute javascript code in strict mode and throw errors if they are any undeclared variables.

    For example 
    ```
    `use strict'
    x = "12" // throws error

    ```
    ```
    var y = "7";
    delete y // throws error 

    ```

    https://www.w3schools.com/js/js_strict.asp