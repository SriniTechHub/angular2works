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

 `` (backtick) symbols are the new multiline string syntax in ECMAScript
2015.

Interpolation syntax is one-way data binding, and data flows from the data source
(Component class) to view (template).

Property binding

Property binding is another form of data binding syntax in Angular.
<element-name [element-property-name] = "component-property-name">

Property binding syntax:
element-name: This can be any HTML tag, or custom tag
element-property-name: Specifies the property of the corresponding DOM
element for the HTML tag or custom tag property name surrounded by square
brackets
component-property-name: Specifies the property of the component class or
expression

example of property binding in Angular: <img [src]="headerImage" />

 Angular does not bind values to attributes of HTML elements. Instead, it will bind to properties of corresponding DOM
(Document Object Model) elements

Property binding syntax is also one-way data binding, data flows from
data source (Component class) to view (template).

Instead of using square brackets notation for property binding, we can also use its canonical
form property name prefixed with bind-:
<h1 bind-textContent ="message"></h1>

Attribute binding
Angular always uses properties to bind the data. But if there is no corresponding property
for the attribute of an element, Angular will bind data to attributes. Attribute binding
syntax starts with the keyword attr followed by the name of the attribute and then assigns
it to the property of the Component class or an expression:
<td [attr.colspan]="colSpanValue"></td>

Event binding
Using event binding syntax, we can bind built-in HTML element events, such as click,
change, blur, and so on, to Component class methods. We can also bind custom events on
components or directives
<input type="text" [value]="message" (keypress)="showMessage()"/>

Event binding syntax is also one-way data binding, but the data flows
from view (template) to the Component class.

Instead of using () symbols notation for event binding, we can also use its canonical form
event name prefixed with on-:
<input type="text" on-keypress="showMessage($event)"/>

Two-way data binding
We require the data to flow in both directions, from Component to template and viceversa.

[(ngModel)] = "component-property"


Built-in directives
1. Structural directives
		 ngIf, <element *ngIf="condition"> content </element> example:<div *ngIf="isReady"></div>
		 ngFor, example: <li *ngFor="let framework of frameworks"> {{framework}} </li>
		 ngSwitch.
		 example: 
		 <div [ngSwitch]="selectedCar">
			 <template [ngSwitchCase]="'Bugatti'">I am Bugatti</template>
			 <template [ngSwitchCase]="'Mustang'">I am Mustang</template>
			 <template [ngSwitchCase]="'Ferrari'">I am Ferrari</template>
			 <template ngSwitchDefault>I am somebody else</template>
		</div>

2. Attribute directives
		ngStyle
		example:
		<p [ngStyle]="getInlineStyles(framework)">{{framework}}</p>
		getInlineStyles(framework) {
			 let styles = {
			 'color': framework.length > 3 ? 'red' : 'green',
			 'text-decoration': framework.length > 3 ? 'underline' : 'none'
			 };
			 return styles;
		}
		<p [style.color]="framework.length > 3 ? 'red': 'green'" >
		 {{framework}}
		</p>

		ngClass
		The ngClass directive is used when we need to apply multiple classes dynamically.
		<p [ngClass]="geClasses(framework)">{{framework}}</p>
		geClasses(framework) {
			 let classes = {
			 red: framework.length > 3,
			 bolder: framework.length > 4
			 };
			 return classes;
		}
		
Pros and cons of template driven forms
			It is very easy to create large forms in a declarative fashion using template driven forms.
			However, the downside is all the logic, and validation rules are in HTML. It is difficult to
			unit test validation logic. We have to do end to end testing to verify the functionality using
			tools like protractor.
Reactive forms
			Reactive forms (also known as model-driven forms) are the new approach introduced in
			Angular. In contrast to template driven forms in reactive forms, we will write all the form
			logic like creating controls, forms, and defining validation rules inside our component
			classes using the forms API instead of HTML.
			In a reactive forms approach, we will directly use the classes FormControl, FormGroup,
			FormArray, and FormBuilder to create input controls, forms, and apply validation rules
			inside the Component class.
Pros and cons of reactive forms
			As mentioned earlier, the reactive forms approach is new in Angular. It is very easy to
			define complex forms in code instead. As we are writing all the validation logic in the
			components, unit testing our form's logic is quite easy without any dependency on DOM,
			by simply instantiating the classes.
Unit testing
			Unit testing focuses on testing the individual parts of the applications; for example, in the
			Angular application, we unit test functionality inside the components, services, directives,
			and pipes.
End-to-end testing
			End-to-end testing focuses on testing the entire application, and these tests run against the
			application running in a real browser, interacting with it as a user would in the real world.
Tooling
			The following are the tools required for testing:
				Jasmine: Jasmine is a behavior-driven development framework in order to test
				JavaScript code, you can find more information on Jasmine
				at: https://jasmine.github.io
				Karma: Karma is a test runner we use for running our unit test while developing;
				you can find more information on Karma at: http://karma-runner.github.io
				Protractor: Protractor is an end-to-end testing framework for Angular
				applications. You can find more information on Protractor
				at: http://protractortest.org
Configuration files
			The following are the Karma configuration files:
				karma.conf.js: This is the Karma configuration file that specifies which plugins to
				use, which application and test files to load, which browser(s) to use, and how to
				report test results.
				karma-test-shim.js: This is the shim that makes Karma work with the Angular
				test environment and launches Karma itself; it includes some of the SystemJS
				configuration in order to load Angular test utilities.
Jasmine basics
	Before we start writing the unit tests, let's look at some Jasmine functions that we use for
	writing every unit test.
	
			describe(): The describe function is a global Jasmine function. It is used for
			grouping similar kinds of tests/specs together in a suite. The describe functions
			can be nested. The syntax is as follows:
			
			 describe('suite name', () => {
			 //unit tests - it functions...
			 });
			 
			it(): It is a Jasmine function used for writing the actual unit tests. The syntax is
			as follows:
			
			 it('test name', () => {
			 //unit test code
			 });
			 
			Matchers: Matchers are the built-in Jasmine functions used along with the
			expect() function to compare the actual value with the expected value. Here are the matcher functions provided by Jasmine:
										toBe()
										toEqual()
										toMatch()
										toBeDefined()
										toBeUndefined()
										toBeNull()
										toBeNaN()
										toBeTruthy()
										toBeFalsy()
										toHaveBeenCalled()
										toHaveBeenCalledWith()
										toHaveBeenCalledTimes()
										toContain()
										toBeLessThan()
										toBeLessThanOrEqual()
										toBeGreaterThan()
										toBeGreaterThanOrEqual()
										toBeCloseTo()
										toThrow()
										toThrowError()
			expect(): It is an another Jasmine function that takes a value named actual
			value, and it is used along with matcher functions to assert the expected value.
			
			beforeEach(): beforeEach() is a Jasmine built-in function that runs the code
			inside it before every test in the describe() function.
			
			afterEach(): afterEach() is a Jasmine built-in function that runs the code
			inside it after every test in the describe() function.
			
			beforeAll(): beforeAll() is a Jasmine built-in function that runs the code
			inside it only once before all the tests in the describe() function.
			
			afterAll(): afterAll() is a Jasmine built-in function that runs the code inside
			it only once after all tests completes the execution in the describe() function.
Unit testing
			We can write two kinds of unit tests for Angular applications:
									Isolated unit tests
									Integrated unit tests
									
			Isolated unit tests instantiate the class directly inside tests without any dependency on
			Angular. They are used for testing only the component's logic (not the template), and they
			are suitable for testing services, pipes, and directives.
			
			Integrated unit tests are written using Angular test utility classes; they are used for testing
			more complex scenarios dependent on Angular features, such as modules and templates.



