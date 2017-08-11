---
title: San Diego .NET Users Talk / Brian Noyes Typescript
layout: post
date: 2017-08-01 04:32:31 +0700
author: glenndayton
description: Brian Noyes talk on Typescript
---

        noyes.me/sd-net-ts

### Typescript overview
- Any typescript file can have standard javascript code.

ECMAScript 5 (ES5) is the Javascript version
ECMAScript 2015 (ES6) released in 2015 (big game changer for javascript language features)
ECMAScript 2016/2017 (Nothing new really)

- Typescript gets converted to ES5 code
- Polyfills are used for features that are not yet supported by all browsers

- Can Not Use tells you what javascript versions and things cant be used on some browsers

        Compilers go from High Level to Machine
        Transpilers go from Typescript to ES2015 ( Syntactical and structural )

- Polyfills are used for Promises if browser doesn't support it.

### Build Options

- Visual Studio (migrating away)
  - compileOnSave
  - JavaScript Services

- Visual Studio Code - build task (lightweight)

- I need to make a build task (gulp) build/bundle tasks
- Webpack - build/bundle tasks
  - Development time infastructure for build tasks
  - Compile the .ts into .js
  - Compile sass/less files into .css
  - Minify files
  - Setup local server to view changes on save

Angular CLI is using Webpack!

tslint helps you write clean code

Lot of similarities of C# and Typescript

``` typescript
class SomeClass extends MyBase{
    private _somevar: string = "Yeah";

    public message: string;

    constructor(){
        super();
    }
    get someProp() : string{
        return this._somevar;
    }
    set someProp(value: string) : string{
        this._somevar = value;
    }
    someMethod(): number{
        return 42;
    }
}
```
Visibility modifiers and types are present on Typescript not, ES2015

### Modules

``` javascript
(function(){
    var item = "A";
})();
```

`item` is local to the function, removes the issue of global namespacing problems

tslint.json is a configurable file that modifies tslint

codelyzer brings in angular specific syntax analyzing

Visiblity modifier = Public/private is typescript

### String Templates / Literals

Backticks are used as quotes now.

```typescript
const result = `Hello ${this.name}, are you ${5 + threshold} years old?`;
```

let and const are block scoped.

### Arrow Functions

- Like Lambda exxpressions

```typescript
someMethod(){
    this.startEngine().then((result) => { ... },
                            (error) => { ... });
}
```

#### Working with Visual Studio, use Web Essentials!

Arrow functions means, this means this.

#### With gulp, just type gulp and it'll do everything.

### Promises

```typescript
const promise = new Promise<string>((resolve, reject) => {
   doSomething(){
        resolve("Cool stuff");
   }
   return promise;
});
```

To consume the promise:
sc.startEngine2().then(
    result => console.log(result),
    error => console.error(error)
);

Better method, cleaner:
try{
    const asyncResult = await sc.startEngine();
} catch (error){
    console.error(error);
}

.then, .catch, .finally can be used.

### Typescript types

    public name: string = 'Barney';
    private f: number = 42;

    getUntypedObject() : any {
        return { answer:42, fav: "coolio" };
    }

### tsconfig.json

    noImplicitAny = true, true doesn't allow any to be used

### Interfaces

export interface blah{ }

### Decorators

    @Component({
       ....
    })
    export class CustomerListComponent{}

    Allows you to specify metadata

### Async/Await
Put await in front of call to something that returns a promise
Put async in front of function, method, or property declaration

