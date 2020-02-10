# State-of-the-Art ShitMountain Principles

[![State-of-the-art ShitMountain]]

This a list of state-of-the-art shitmountain principles your project should follow to call it as a proper shitmountain.

## The Principles

### 💩 Name variables in as less words as possible

Less keystrokes, more time for you.

_Good 👍🏻_

```javascript
let a = 42;
```

_Bad 👎🏻_

```javascript
let age = 42;
```

### 💩 Mix variable/functions naming style

Celebrate the multi-naming.

_Good 👍🏻_

```javascript
let wWidth = 640;
let w_height = 480;
```

_Bad 👎🏻_

```javascript
let windowWidth = 640;
let windowHeight = 480;
```
### 💩 Mix Chinese Pinyin/English naming style

Who never forget a few words？

_Good 👍🏻_

```javascript
const uint_16 wendouFreeze;
```

_Bad 👎🏻_

```javascript
const uint_16 windowFreeze;
```

### 💩 Never use Camel-Case

Because we do not need camel.

_Good 👍🏻_

```javascript
const displaythenumberifuserpressthatstupidbutton = 700;
```

_Bad 👎🏻_

```javascript
const displayUserNumber = 700;
```

### 💩 Never write comments

No one is going to read your code anyway.

_Good 👍🏻_

```javascript
const cdr = 700;
```

_Bad 👎🏻_

More often comments should contain some 'why' and not some 'what'. If the 'what' is not clear in the code, the code is probably too messy.

```javascript
// Divide rate change by dT to get differential (ie dr/dt).
// dT is fixed and calculated from the target PID loop time
// This is done to avoid DTerm spikes that occur with dynamically
// calculated deltaT whenever another task causes the PID
// loop execution to be delayed.
const float delta = 
- (gyroRateDterm[axis] - previousGyroRateDterm[axis]) * pidFrequency;
```

### 💩 Always write comments in your native language

I'm at the 8-th level of Davelish (Crazy Dave). If your native language is English you may violate this principle.

_Good 👍🏻_

```javascript
// Waibi waibi, waibi bapo.
toggleModal(false);
```

_Bad 👎🏻_

```javascript
// Hide modal window on error.
toggleModal(false);
```

### 💩 Try to mix formatting style as much as possible

Celebrate the multi-formatting.

_Good 👍🏻_

```javascript
let i = ['tomato', 'onion', 'mushrooms'];
let d = [ "ketchup", "mayonnaise" ];
```

_Bad 👎🏻_

```javascript
let ingredients = ['tomato', 'onion', 'mushrooms'];
let dressings = ['ketchup', 'mayonnaise'];
```

### 💩 Put as much code as possible into one line

Just like reading a real book.

_Good 👍🏻_

```javascript
document.location.search.replace(/(^\?)/,'').split('&').reduce(function(o,n){n=n.split('=');o[n[0]]=n[1];return o},{})
```

_Bad 👎🏻_

```javascript
documentlocation.search
  .replace(/(^\?)/, '')
  .split('&')
  .reduce((searchParams, keyValuePair) => {
    keyValuePair = keyValuePair.split('=');
    searchParams[keyValuePair[0]] = keyValuePair[1];
    return searchParams;
  },
  {}
)
```

### 💩 Fail silently

Whenever you catch an error it is not necessary for anyone to know about it. No logs, no error modals, chill.

_Good 👍🏻_

```javascript
try {
  // Something unpredictable.
} catch (error) {
  // tssss... 🤫
}
```

_Bad 👎🏻_

```javascript
try {
  // Something unpredictable.
} catch (error) {
  setErrorMessage(error.message);
  // and/or
  logError(error);
}
```

### 💩 Use global variables extensively

Globalization principle.

_Good 👍🏻_

```javascript
let x = 5;

function square() {
  x = x ** 2;
}

square(); // Now x is 25.
```

_Bad 👎🏻_

```javascript
let x = 5;

function square(num) {
  return num ** 2;
}

x = square(x); // Now x is 25.
```

### 💩 Create variables that you're not going to use.

Just in case.

_Good 👍🏻_

```javascript
function sum(a, b, c) {
  const timeout = 1300;
  const result = a + b;
  return a + b;
}
```

_Bad 👎🏻_

```javascript
function sum(a, b) {
  return a + b;
}
```


### 💩 You need to have an unreachable piece of code

This is your "Plan B".

_Good 👍🏻_

```javascript
function square(num) {
  if (typeof num === 'undefined') {
    return undefined;
  }
  else {
    return num ** 2;
  }
  return null; // This is my "Plan B".
}
```

_Bad 👎🏻_

```javascript
function square(num) {
  if (typeof num === 'undefined') {
    return undefined;
  }
  return num ** 2;
}
```

### 💩 Use as many nested structures as possible

Triangle principle. Be like a bird - nest, nest, nest.

_Good 👍🏻_

```javascript
function someFunction() {
  if (condition1) {
    if (condition2) {
      asyncFunction(params, (result) => {
        if (result) {
          for (;;) {
            if (condition3) {
            }
          }
        }
      })
    }
  }
}
```

_Bad 👎🏻_

```javascript
async function someFunction() {
  if (!condition1 || !condition2) {
    return;
  }
  
  const result = await asyncFunction(params);
  if (!result) {
    return;
  }
  
  for (;;) {
    if (condition3) {
    }
  }
}
```

### 💩 Change indentation for each line

Avoid indentations since they make complex code take up more space in the editor. If you're not filling like avoiding them then just mess with them.

_Good 👍🏻_

```javascript
const fruits = ['apple',
  'orange', 'grape', 'pineapple'];
  const toppings = ['syrup', 'cream', 
                    'jam', 
                    'chocolate'];
const desserts = [];
fruits.forEach(fruit => {
toppings.forEach(topping => {
    desserts.push([
fruit,topping]);
    });})
```

_Bad 👎🏻_

```javascript
const fruits = ['apple', 'orange', 'grape', 'pineapple'];
const toppings = ['syrup', 'cream', 'jam', 'chocolate'];
const desserts = [];

fruits.forEach(fruit => {
  toppings.forEach(topping => {
    desserts.push([fruit, topping]); 
  });
})
```

### 💩 Do not lock your dependencies

Update your dependencies on each new installation in uncontrolled way. Why stick to the past, let's use the cutting edge libraries versions.

_Good 👍🏻_

```
$ ls -la

package.json
```

_Bad 👎🏻_

```
$ ls -la

package.json
package-lock.json
```

### 💩 Long-read functions are better than short ones.

Don't divide a program logic into readable pieces. What if your IDE's search brakes and you will not be able to find the necessary file or function?

- 10000 lines of code in one file is OK.
- 1000 lines of a function body is OK.
- Dealing with many services (3rd party and internal, also, there are some helpers, database hand-written ORM and jQuery slider) in one `service.js`? It's OK.

### 💩 Use a complex cross-platform cross-compilation toolchain.

Don't forget to cross fingers! Both hands.

### 💩 Avoid covering your code with tests

This is a duplicate and unnecessary amount of work.

### 💩 As hard as you can try to avoid version control

Release new versions as you want, especially if there is more than one developer in a team. This is a "freedom" principle.

### 💩 As many as you can try to release all development versions to ordinary people

Especially if there are many users. Mess their data and burn their devices.

### 💩 Start your project without a README file.

And keep it that way for the time being.

### 💩 Never write any doc/wiki.

Obviously docs/wikis are for shitcode-cleaner, don't give them any chance.

### 💩 You need to have unnecessary code

Don't delete the code your app doesn't use. At most, comment it.
