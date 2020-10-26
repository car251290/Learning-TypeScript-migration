# Learning-TypeScript-migration
Learning how to migrate 
Types provide a way to describe the shape of an object, providing better documentation, and allowing 
TypeScript to validate that your code is working correctly.

The type system in TypeScript has different levels of strictness when working with a codebase:

A type-system based only on inference with JavaScript code
Incremental typing in JavaScript via JSDoc
Using // @ts-check in a JavaScript file
##TypeScript code
TypeScript with strict enabled
Each step represents a move towards a safer type-system, but not every project needs that level of verification.

## TypeScript with JavaScript
This is when you use an editor which uses TypeScript to provide tooling like auto-complete, jump to symbol and refactoring tools like rename. The homepage has a list of editors which have TypeScript plugins.

## How to switch my code from JS to JTS
If you have a lot of JavaScript files you want to add errors to then you can switch to using a jsconfig.json. You can skip checking some files by adding a // @ts-nocheck comment to files.

TypeScript may offer you errors which you disagree with, in those cases you can ignore errors on specific lines by adding // @ts-ignore or // @ts-expect-error on the preceding line.
