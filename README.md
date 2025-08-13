# 🧮 Shape Area (Node.js, CommonJS)

A tiny Node.js demo that computes the area of a **circle** and a **square**, emphasizing **CommonJS export/import**:

- `circleArea(radiusLength)` → returns πr²  
- `squareArea(sideLength)` → returns s²  
- Shows how to **export** with `module.exports` and **import** with `require()`.

---

## 🔄 Export & Import Explained (CommonJS)

### What is exported?
In Node’s **CommonJS** system, each file is a module. Whatever you assign to `module.exports` becomes the value other files receive when they call `require()`.

```js
/* shape-area.js */
const PI = Math.PI;

// Define and export circleArea() and squareArea() below

const circleArea = radius=>{
  return PI*radius*radius;
}

const squareArea =radius =>{
  return radius*radius;
}

module.exports.circleArea=circleArea
module.exports.squareArea=squareArea
```
###Importing Module
First, import the shape-area.js module using the require() function (shape-area.js is in the same folder as app.js). Choose one of the two options below for storing the returned module.exports object:

A) Store the entire module.exports object in the variable areaFunctions.
B) Use object destructuring to extract the .circleArea() and .squareArea() methods into their own variables, circleArea and squareArea.
Next, call the circleArea() function with the provided variable radius as an input. Assign the returned value to the variable areaOfCircle.

Then, call the squareArea() function with the provided variable sideLength as an input. Assign the returned value to the variable areaOfSquare.

You may print the values of areaOfCircle and areaOfSquare to the console to see your code work!

```js
/* app.js */ 

const radius = 5;
const sideLength = 10;

// Option 1: import the entire shape-area.js module here.

require('./shape-area.js')

// const areaFunctions = 'replace_me';

const areaFunctions=require('./shape-area.js')
// Option 2: import circleArea and squareArea with object destructuring

const { circleArea, squareArea } = require("./shape-area.js")

// use the imported .circleArea() and .squareArea() methods here

const areaOfCircle = circleArea(radius);

const areaOfSquare = squareArea(sideLength);
/* app.js */ 

const radius = 5;
const sideLength = 10;

// Option 1: import the entire shape-area.js module here.

require('./shape-area.js')

// const areaFunctions = 'replace_me';

const areaFunctions=require('./shape-area.js')
// Option 2: import circleArea and squareArea with object destructuring

const { circleArea, squareArea } = require("./shape-area.js")

// use the imported .circleArea() and .squareArea() methods here

const areaOfCircle = circleArea(radius);

const areaOfSquare = squareArea(sideLength);
```
