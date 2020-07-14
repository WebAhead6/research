# Async JavaScript


1. What do we mean by "asynchronous code"? What is "blocking code"? // mervat
2. What are the event loop and the call stack? // tarek
3. How do callbacks and promises help us? // khaled

### Asynchronous Code

- asynchronous code means we are running multiple tasks at the same time. JS is called a single-thread language since the codes is dealing with only one task at a time. In order to make an asynchronous code in JS we can use features like Promise, SetTimeOut.

### Blocking

 - happens when synchronous code is stuck. 
  The code runs in the order it appears in the source, and the later    operation doesn't run till the earlier operation has finished running.


![](https://i.imgur.com/5aznKP4.gif)


### Call Stack

- This is where all your javascript code gets pushed and executed one by one as the interpreter reads your program, and gets popped out once the execution is done. If your statement is asynchronous: setTimeout, ajax(), promise, or click event, then that code gets forwarded to Event table, this table is responsible for moving your asynchronous code to callback/event queue after specified time.

### Event Loop
Event loop handles implementation by checking the call stack and executing the stack frames in LIFO order until the call stack is empty. There’s also the Web API pushing things to the task queue. These functions are deferred to the queue until the stack is clear and then actions in the queue are pushed to the stack and executed.
The call stack is given priority and each frame in the stack is processed to completion before content from the queue is added to the stack. We do not have to wait for the tasks from the queue to run when pushed to the stack though. These types of events are handled by the browser and is added to the queue after completion.
Event loop’s task is to maintain the stack and handle the execution of code. The event loop checks the call stack and if the call stack is empty, it then looks to the queue. If there is anything in the queue, the event loop takes the first task and pushes it to the stack to run.

### Async callbacks

- Async callbacks are functions that are specified as arguments when calling a function which will start executing code in the background. When the background code finishes running, it calls the callback function to let you know the work is done, or to let you know that something of interest has happened. Using callbacks is slightly old-fashioned now, but you'll still see them in use in a number of older-but-still-commonly-used APIs.


- Callbacks are versatile — not only do they allow you to control the order in which functions are run and what data is passed between them, they also allow you to pass data to different functions depending on circumstance. So you could have different actions to run on the response downloaded, such as processJSON(), displayText(), etc.


# Promises

- Promises are the new style of async code that you'll see used in modern Web APIs. A good example is the fetch() API, which is basically like a modern, more efficient version of XMLHttpRequest. 

- Async operations like promises are put into an event queue, which runs after the main thread has finished processing so that they do not block subsequent JavaScript code from running. The queued operations will complete as soon as possible then return their results to the JavaScript environment.

- Promises have some similarities to old-style callbacks. They are essentially a returned object to which you attach callback functions, rather than having to pass callbacks into a function.
