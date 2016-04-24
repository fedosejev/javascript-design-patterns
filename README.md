# Examples of design patterns in JavaScript

## Creational Design Pattern

### Constructor Pattern

```js
var Tesla = function (model, color) {
  this.model = model;
  this.color = color;
  this.isStarted = false;
  
  this.start = function () {
    this.isStarted = true;
    console.log('Started ' + this.model);
  };
  
  this.stop = function () {
    this.isStarted = false;
    console.log('Stopped ' + this.model);
  };
};

var modelS = new Tesla('Model S', 'white');
var modelX = new Tesla('Model X', 'black');
var model3 = new Tesla('Model 3', 'red');

modelS.start();
modelS.stop();
```

+ [Example](https://repl.it/CJDf)

#### Drawbacks

+ `start` and `stop` is created for each object, i.e. `modelS`, `modelX` and `model3` have their own copies of `start` and `stop` functions.

#### `prototype` version

```js
var Tesla = function (model, color) {
  this.model = model;
  this.color = color;
  this.isStarted = false;
};

Tesla.prototype.start = function () {
  this.isStarted = true;
  console.log('Started ' + this.model);
};

Tesla.prototype.stop = function () {
  this.isStarted = false;
  console.log('Stopped ' + this.model);
};

var modelS = new Tesla('Model S', 'white');
var modelX = new Tesla('Model X', 'black');
var model3 = new Tesla('Model 3', 'red');

modelS.start();
modelS.stop();
```

+ [Example](https://repl.it/CJDm)

#### ECMAScript 2015 version

```js
class Tesla {
  constructor(model, color) {
    this.model = model;
    this.color = color;
    this.isStarted = false;
  }
  
  start() {
    this.isStarted = true;
    console.log('Started ' + this.model);
  }
  
  stop() {
    this.isStarted = false;
    console.log('Stopped ' + this.model);
  }
}

var modelS = new Tesla('Model S', 'white');
var modelX = new Tesla('Model X', 'black');
var model3 = new Tesla('Model 3', 'red');

modelS.start();
modelS.stop();
```

+ [Example](https://repl.it/CJDz)
