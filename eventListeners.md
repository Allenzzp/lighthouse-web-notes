# EventListener

## Removing Listeners

```js
function callback() {
    //do stm
    element.removeEventListener("click", callback);
}
```

## Wrong Callback Context

```js
const user = {
 firstname: 'Wilson',
 greeting: function(){
   alert('My name is ' + this.firstname);
 }
};

// Attach user.greeting as a callback
element.addEventListener('click', user.greeting);

// alert => 'My name is undefined'
```

- greeting method should be called within context of user
- but when passing method into addEventListener method, only passing a reference without the context
- callback is called in context of **element**, not user

### solution I

call user.greeting() inside an anonymous function

```js
element.addEventListener('click', function() {
  user.greeting();
  // alert => 'My name is Wilson'
});
```

### solution II

use .bind()

```js
// Overwrite the original function with
// one bound to the context of 'user'
user.greeting = user.greeting.bind(user);

// Attach the bound user.greeting as a callback
button.addEventListener('click', user.greeting);
```



## Event Obj

- type (string)
- target (node)
- currentTarget (node)
- bubbles (boolean)
- cancelable (boolean) whether default behaviour can be prevent by calling following method
- preventDefault (function) user agent carry out 
- defaultPrevented (boolean)
- isTrusted (boolean) event originates from the device itself
- stopPropagation (function) stop callback fires along event chain besides additional callbacks of the same event name from being fired on current node
- stopImmedaitePropagation (function)
- eventPhase (number)  phase event is currently in
  - none - 0
  - capture - 1
  - target - 2
  - bubbling - 3
- timeStamp (number) 