
let can be re-assigned.

### Examples of usage:

1. Multiple variables in one line
```js
let user = 'John', age = 25, message = 'Hello';
```

2. Multiline variant (the normal way)
```js
let user = 'John';
let age = 25;
let message = 'Hello';
```

3. Multiple variables in a multiline style (it contains 2 spaces)
```js
let user = 'John',
   age = 25,
   message = 'Hello';
```

4. "comma-first" style
```js
let user = 'John'
  , age = 25
  , message = "Hello";
```

All styles work just fine, but for readability purposes, stick with the second option.


### Real life analogy

variables work as a "box" for data with uniquely-named sticker on it.

message can be the name of the box and it holds the value "Hello" in it:
![[Pasted image 20240731160723.png]]

we can also add any value to the box and we can change it as many times as we want. the latter option is a `let` re-assignment attribute which doesn't occur in the `const` function.

```js
let hello = 'Hello world!';
let message;
// copy 'Hello world' from hello into message
message = hello;
// now two variables hold the same data
alert(hello); // Hello world!
alert(message); // Hello world!
```