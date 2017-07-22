Angular is the next version of AngularJS 1.x, but it is a complete rewrite from its
predecessor.

 It is built on top of the latest web standards
 1. web components,
 2. Observables,
 3. decorators

 the learning curve is minimal, and performance is better.

 new features in Angular:(EAT NONS CNUU)
                       1. ES2015
                       2. Ahead of time compilation
                       3. Typescript
                       4. New language for development
                       5. Observables
                       6. New component router
                       7. Server-side rendering
                       8. Components
                       9. New templating  syntax
                      10. Ultra fast change detection
                      11. Unidirectional data flow
TypeScript is a superset of JavaScript

TypeScript Provides following features to improve developer productivity and build scalabel JavaScript applications
                    1. Static checking
                    2. Symbol-based navigation
                    3. Statement completion
                    4. Code refactoring
data types in TypeScript:
1. String  example:var bookName: string = "Angular";
2. Number  example:var bookVersion: number = 1;
3. Boolean example:var isCompleted: boolean = false;
4. Array   example:var fw: string[] = ['Angular', 'React', 'Ember']; or var fw: Array<string> = ['Angular', 'React', 'Ember'];
5. Enum    example:enum Frameworks { Angular = 5, React, Ember }; var f: Frameworks = Frameworks.Angular;
6. Any     example:var myCollection:any[] = ["value1", 100, 'test', true];
7. Void    example:function simpleMessage(): void { alert("Hey! I return void");}

Functions
Functions are the fundamental building blocks of any JavaScript application
TypeScript
function sum(a: number, b: number): number {
 return a + b;
}
var result = function(a: number, b: number): number {
return a + b;
}

Classes

class Person {
 name: string;
 constructor(name: string) {
 this.name = name;
 }
 sayHello() {
 return 'Hello ' + this.name;
 }
}
var person = new Person('Shravan');
console.log(person.name);
console.log(person.sayHello());


Set up the Angular2 application

hello-world
+- index.html
+- package.json
+- tsconfig.json
+- src
+- app.ts

tsconfig.json
target: Specifies ECMAScript target version: es3 (default), es5, or es2015
module: Specifies module code generation: commonjs, amd, system, umd or
es2015
moduleResolution: Specifies module resolution strategy: node (Node.js) or
classic (TypeScript pre-1.6)
sourceMap: If true, generates corresponding .map file for .js file
emitDecoratorMetadata: If true, enables the output JavaScript to create the
metadata for the decorators
experimentalDecorators: If true, enables experimental support for ES7
decorators
lib: Specifies library files to be included in the compilation
noImplicitAny: If true, raise error if we use any type on expressions and
declarations


imports: We need to specify the other modules on which our module is
dependent. We are going to run our application in a browser, so our
module depends on BrowserModule; we imported it and added it to this
array.
declarations: We need to specify that the components, directives, and pipes belong to
this module.
bootstrap: We need to specify the components that must be bootstrapped when this
module is bootstrapped. The components added here will automatically
be added to the entryComponents property. The components specified
in the entryComponents will be compiled when the module is defined.


SystemJS
It is a universal dynamic module loader. It can load ES2015, AMD, CommonJS modules, and global scripts
in the browser and Node.js.

1. map object tells where to look for JavaScript files,
2. packages object tells how to load when no filename is specified and no file extension is specified.


The Angular CLI is available as a node package. First, we need to download and install it
with the following command:

$ npm install -g @angular/cli

To generate the Angular project using CLI we can use the ng

new project-name command.
$ ng new first-ng-cli-project

To run the
application, we need to navigate to the project folder and run the ng serve command:

$ cd first-ng-cli-project
$ ng serve

The ng serve command compiles and builds the project, and starts the local web server at
http://localhost:4200 URL.

Component:

 ng g component my-new-component

Directive:

 ng g directive my-new-directive
 
Pipe:

 ng g pipe my-new-pipe
 
Service:
 
 ng g service my-new-service
 
Module:
 
 ng g module my-module

Module with routing:

 ng g module my-module --routing

 