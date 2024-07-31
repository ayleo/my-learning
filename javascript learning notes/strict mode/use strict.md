
Strict mode makes it possible to avoid silent bugs and makes errors visible.
Without use strict, issues or bugs that may occur while not using this mode, will not be visible in the dev console, therefore it is recommended to use it.

### Side notes

> The `"use strict";` directive switches the engine to the “modern” mode, changing the behavior of some built-in features.

> Strict mode is enabled by placing `"use strict"` at the top of a script or function. Several language features, like "classes" and "modules", enable strict mode automatically.


### Examples

In this case, we're introducing an intentional bug. We're omitting the letter `s` from the variable `hasDriversLicense` and calling it using the `if` conditional.

```javascript
'use strict';

let hasDriversLicense = false;
const passTest = true;

if (passTest) hasDriverLicense = true;
if (hasDriversLicense) console.log('I can drive :D')
```

The code above will produce the following error:
```js
script.js:53 Uncaught ReferenceError: hasDriverLicense is not defined
    at script.js:53:32
```
