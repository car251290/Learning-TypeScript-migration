# Learning-TypeScript-migration
Learning how to migrate 
Types provide a way to describe the shape of an object, providing better documentation, and allowing 
TypeScript to validate that your code is working correctly.

The type system in TypeScript has different levels of strictness when working with a codebase:

A type-system based only on inference with JavaScript code
Incremental typing in JavaScript via JSDoc
Using // @ts-check in a JavaScript file

## TypeScript code
TypeScript with strict enabled
Each step represents a move towards a safer type-system, but not every project needs that level of verification.

## TypeScript with JavaScript
This is when you use an editor which uses TypeScript to provide tooling like auto-complete, jump to symbol and refactoring tools like rename. The homepage has a list of editors which have TypeScript plugins.

## How to switch my code from JS to JTS
If you have a lot of JavaScript files you want to add errors to then you can switch to using a jsconfig.json. You can skip checking some files by adding a // @ts-nocheck comment to files.

TypeScript may offer you errors which you disagree with, in those cases you can ignore errors on specific lines by adding // @ts-ignore or // @ts-expect-error on the preceding line.
## Properties are inferred from assignments in class bodies
ES2015 does not have a means for declaring properties on classes. Properties are dynamically assigned, just like object literals.

In a .js file, the compiler infers properties from property assignments inside the class body. The type of a property is the type given in the constructor, unless it’s not defined there, or the type in the constructor is undefined or null. In that case, the type is the union of the types of all the right-hand values in these assignments. Properties defined in the constructor are always assumed to exist, whereas ones defined just in methods, getters, or setters are considered optional.
## Enum
A helpful addition to the standard set of datatypes from JavaScript is the enum. As in languages like C#, an enum is a way of giving more friendly names to sets of numeric values.

## enum color
enum Color {
  Red,
  Green,
  Blue,
}

let c: Color = Color.Green;
class Type {
  constructor() {
    this.constructorOnly = 0;
    this.constructorUnknown = undefined;
  }
  method() {
    this.constructorOnly = false;
    // the boolean if the false or true
Type 'boolean' is not assignable to type 'number'.
Type 'boolean' is not assignable to type 'number'.
    this.constructorUnknown = "plunkbat"; 
    this.methodOnly = "ok"; 
  }
  method2() {
  //Boleean true
    this.methodOnly = true; 
  }
null, undefined, and empty array initializers are of type any or any[]
Any variable, parameter or property that is initialized with null or undefined will have type any, even if strict null checks is turned on. Any variable, parameter or property that is initialized with [] will have type any[], even if strict null checks is turned on. The only exception is for properties that have multiple initializers as described above.

function Foo(i = null) {
  if (!i) i = 1;
  var j = undefined;
  j = 2;
  this.l = [];
}

var foo = new Foo();
foo.l.push(foo.i);
foo.l.push("end");Try
Function parameters are optional by default
Since there is no way to specify optionality on parameters in pre-ES2015 Javascript, all function parameters in .js file are considered optional. Calls with fewer arguments than the declared number of parameters are allowed.

It is important to note that it is an error to call a function with too many arguments.

For instance:

function bar(a, b) {
  console.log(a + " " + b);
}

bar(1); // OK, second argument considered optional
bar(1, 2);
bar(1, 2, 3); // Error, too many arguments
Expected 0-2 arguments, but got 3.
Expected 0-2 arguments, but got 3.
Try
JSDoc annotated functions are excluded from this rule. Use JSDoc optional parameter syntax ([ ]) to express optionality. e.g.:

/**
 * @param {string} [somebody] - Somebody's name.
 */
function sayHello(somebody) {
  if (!somebody) {
    somebody = "John ";
  }
  console.log("Hello " + somebody);
}

sayHello();

## Index TypeScript

Write a HTML page
Right click on the wwwroot folder (if you don’t see the folder try building the project) and add a New Item named index.html inside. Use the following code for index.html

## You can also import declarations from other files using import types. This syntax is TypeScript-specific and differs from the JSDoc standard:
// @filename: types.d.ts
export type Pet = {
  name: string,
};

// @filename: main.js
/**
 * @param p { import("./types").Pet }
 */
function walk(p) {
  console.log(`Walking ${p.name}...`);
}
## Html

<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <script src="scripts/app.js"></script>
    <title></title>
</head>
<body>
    <div id="message"></div>
    <div>
        Compiler: <input id="compiler" value="TypeScript" onkeyup="document.getElementById('message').innerText = sayHello()" /><br />
        Framework: <input id="framework" value="ASP.NET" onkeyup="document.getElementById('message').innerText = sayHello()" />
    </div>
</body>
</html>

