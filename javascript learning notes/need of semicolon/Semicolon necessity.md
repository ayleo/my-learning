

Below there will be a case of JS code which runs into an error if there isn't a semicolon at the end of the `alert` line.
1. 
```javascript
alert("There will be an error")
[1, 2].forEach(alert)
```

& below there will be a case of JS code which works perfectly if the semicolon is set at the end of the line.
2. 
```javascript
alert("All fine now"); 
[1, 2].forEach(alert)
```


## Why is this the matter?


For the first case, JavaScript reads the code like this:

```javascript
alert("There will be an error")[1, 2].forEach(alert)
```

Here's why:

1. JavaScript sees the `alert()` function call.
2. It then encounters the opening square bracket `[` on the next line.
3. Instead of inserting a semicolon after the `alert()` call, it assumes you're trying to use the square bracket notation to access a property of the result of `alert()`.
4. The code is essentially trying to access the property `[1, 2]` of the `undefined` value returned by `alert()`, which leads to an error.


In the second case:

```javascript
alert("All fine now");
[1, 2].forEach(alert)
```

This works correctly because:

1. The semicolon explicitly ends the `alert()` statement.
2. JavaScript recognizes the next line as a new, independent statement.
3. It correctly interprets `[1, 2]` as an array literal, not as a property access attempt.

This behavior stems from JavaScript's grammar rules and ASI. The language tries to be forgiving about semicolon usage, but in some cases (like this one), it can lead to unexpected results.



### To avoid such issues, you can:

- Always use semicolons to explicitly terminate statements.
- If you prefer a semicolon-less style, you can start lines that begin with `[` or `(` with a semicolon:

```javascript
alert("No error this way either")
;[1, 2].forEach(alert)
```

This practice ensures that even without a semicolon after `alert()`, the `[1, 2]` is interpreted as the start of a new statement.