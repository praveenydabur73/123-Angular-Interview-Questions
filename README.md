# 123-Angular-Interview-Questions
123 Angular Interview Questions
![](coverPage.png)

It's a book about frontend interview question. We hope that it will help all Angular developers to prepare for a technical job interview. 

1. What is Angular 5?
Angular is a framework for building client applications in HTML and either JavaScript or a language like a TypeScript that compiles to JavaScript.It is best suited for Single Page Application(SPA).
2.Why Angular?
User Experience similar to a Desktop Application
Productivity and Tooling
Performance
Community
Full-featured Framework
Validation, Routing, DI…
Platform for Targeting Native Mobile, not just Web Browsers
TypeScript
Angular 2 was written in TypeScript, a superset of JavaScript that implements many new ES2016+ features.
 Modular
Hence angular have clean and clear structure.
Unit Testing
Easy to Unit Test and easy to maintain the code.
3. What’s New in Angular 5?
The Angular 5 Contains bunch of new features, performance improvements and a lot of bug fixes and also some surprises to Angular lovers.

Make AOT the default
Watch mode
Type checking in templates
More flexible metadata
Remove *.ngfactory.ts files
Better error messages
Smooth upgrades
Tree-Shakeable components
Hybrid Upgrade Application
Performance Improvements
4. What’s New in Angular 4?
Angular 4 contains some additional Enhancement and Improvement. Consider the following enhancements.

Smaller & Faster Apps
View Engine Size Reduce
Animation Package
NgIf and ngFor Improvement
Template
NgIf with Else
Use of AS keyword
Pipes
HTTP Request Simplified
Apps Testing Simplified
Introduce Meta Tags
Added some Forms Validators Attributes
Added Compare Select Options
Enhancement in Router
Added Optional Parameter
Improvement Internationalization
5. What Is Angular CLI?
The Angular CLI is a tool to initialize, develop, scaffold and maintain Angular applications.Using CLI , you can create a UNIT and END-TO-END test fo the Angular application.

6. What Is Bootstrapping in Angular?
main.ts is the entry point of your application, compiles the application with just-in-time and bootstrap the application.The Bootstrap is the root AppComponent that Angular creates and inserts into the “index.html” host web page.The bootstrapping process creates the components listed in the bootstrap array and inserts each one into the browser (DOM).

The bootstrapping process sets up the execution environment, digs the root AppComponent out of the module’s bootstrap array, creates an instance of the component and inserts it within the element tag identified by the component ’s.selector

7. What Is Architecture Overview of Angular?
overview

Modules
Angular apps are modular in nature.
The angular application is nothing but collections of individual modules.
Angular has its own modularity system called NgModules.
Every Angular app has at least one NgModule class, the root module, conventionally named.AppModule
An NgModule, whether a root or feature, is a class with a@NgModule decorator.
Components
A component controls a patch of the screen called a view.
You define a component’s application logic—what it does to support the view—inside a class. The class interacts with the view through an API of properties and methods.
Angular creates, updates, and destroys components as the user moves through the application.
At least one component should be there called Root Component(app.component.ts)
Metadata
Components have @component decorator , contains selector , template,templateUrl , style , styleUrls , providers.
selector: CSS selector that tells Angular to create and insert an instance of this component where it finds a <hero-list>tag in parent HTML. For example, if an app’s HTML contains,<hero-list></hero-list> then Angular inserts an instance of the view HeroListComponent between those tags.
templateUrl: module-relative address of this component’s HTML template, shown above.
providers: an array of dependency injection providers for services that the component requires.
Templates
You define a component’s view with its companion template. A template is a form of HTML that tells Angular how to render the component.
A template looks like regular HTML
Data binding
Angular supports data binding, a mechanism for coordinating parts of a template with parts of a component. Add binding markup to the template HTML to tell Angular how to connect both sides.

Directives
Angular templates are dynamic. When Angular renders them, it transforms the DOM according to the instructions given by directives.

A directive is a class with a @Directive decorator.

Services
A class contains the Business Logic.

8. How To Angular 5 generate Component, Directive, Pipe, Service, Class, and Module?
Scaffold	Usage
Component	ng g component my-new-component
Directive	ng g directive my-new-directive
Pipe	ng g pipe my-new-pipe
Service	ng g service my-new-service
Class	ng g class my-new-class
Guard	ng g guard my-new-guard
Interface	ng g interface my-new-interface
Enum	ng g enum my-new-enum
Module	ng g module my-module
 

9. What Is the Angular Compiler? Why we need Compilation in Angular?
The Angular compiler converts our applications code (TypeScript) into JavaScript code + HTML before browser downloads and runs that code.

The Angular offers two ways to compile our application code-

Just-in-Time (JIT) – JIT compiles our app in the browser at runtime (compiles before running).
Ahead-of-Time (AOT) – AOT compiles our app at build-time (compiles while running).
10. What Is the difference between JIT compiler and AOT compiler?
JIT (Just-in-Time) –

JIT compiles our app in the browser at runtime.
Compiles before running
Each file compiled separately
No need to build after changing our app code and it automatically reflects the changes in your browser page
Highly secure
Very suitable for local development
AOT (Ahead-of-Time) –

AOT compiles our app code at build time.
Compiles while running
Compiled by the machine itself, via the command line (Faster)
All code compiled together, inlining HTML/CSS in the scripts
Highly secure
Very suitable for production builds
11.Explain the life cycle hooks of Angular 5 application
Angular 5 component/directive has lifecycle events, managed by @angular/core. It creates the component, renders it, creates and renders its children, processes changes when its data-bound properties change, and then destroys it before removing its template from the DOM. Angular provides a set of lifecycle hooks(special events) which can be tapped into this lifecycle and perform operations when required. The constructor executes prior to all lifecycle events. Each interface has a single hook method prefixed with ng. For example, ngOnint interface has Oninit method that must be implemented in the component.

Some of the events are applicable for both component/directives while few are specific to components.

ngOnChanges: Responds when angular sets its data-bound property which receives the current and previous object values.
ngOnInit: Initializes the component/directive after first ngOnChange triggers. This is most frequently used method to retrieve the data for the template from a back-end service.
ngDoCheck: Detect and act upon changes occurring outside Angular context. It is called when every change detection run.
ngOnDestroy: Cleanup just before Angular destroys the directive/component. Unsubscribe observables and detach event handlers to avoid memory leaks.
Component-specific hooks:

ngAfterContentInit: Component content has been initialized
ngAfterContentChecked: After Angular checks the bindings of the external content that it projected into its view.
ngAfterViewInit: After Angular creates the component’s view.
ngAfterViewChecked: After Angular checks the bindings of the component’s view.
12. What is Lazy Loading and How to enable Lazy Loading?
Most of the enterprise application contains various modules for specific business cases. Bundling whole application code and loading will be huge performance impact at initial call. Lazy lading enables us to load only the module user is interacting and keep the rest to be loaded at runtime on demand.

Lazy loading speeds up the application initial load time by splitting the code into multiple bundles and loading them on demand.

Every Angular application must have one main module say AppModule. The code should be splitted into various child modules (NgModule) based on the application business case.

Plunkr Example:

We don’t require to import or declare lazily loading module in root module.
Add the route to top-level routing (app.routing.ts) and set loadChildren. loadChildren takes an absolute path from root folder followed by #{ModuleName}. RouterModule.forRoot() takes routes array and configures the router.
Import module specific routing in the child module.
In the child module routing, specify a path as empty string ‘ ‘, the empty path. RouterModule.forChild again takes routes array for the child module components to load and configure router for child.
Then, export const routing: ModuleWithProviders = RouterModule.forChild(routes);
13. What are the core differences between Observables and Promises?
A nice answer is taken from stack overflow:

A Promise handles a single event when an async operation completes or fails.

Note: There are Promise libraries out there that support cancellation, but ES6 Promise doesn’t so far.

An Observable is like a Stream (in many languages) and allows to pass zero or more events where the callback is called for each event. Often Observable is preferred over Promise because it provides the features of Promise and more. With Observable, it doesn’t matter if you want to handle 0, 1, or multiple events. You can utilize the same API in each case. Observable also has the advantage over Promise to be cancelable. If the result of an HTTP request to a server or some other expensive async operation isn’t needed anymore, the Subscription of an Observable allows to cancel the subscription, while a Promise will eventually call the success or failed callback even when you don’t need the notification or the result it provides anymore. Observable provides operators like map, forEach, reduce, … similar to an array. There are also powerful operators like retry(), or replay(), … that are often quite handy.

Promises vs Observables

Promises:
returns a single value
not cancellable
Observables:
works with multiple values over time
cancellable
supports map, filter, reduce and similar operators
proposed feature for ES 2016
use Reactive Extensions (RxJS)
an array whose items arrive asynchronously over time
14. What are differences between Constructors and OnInit?
Constructors:-
1.      The constructor is a default method runs when a component is being constructed.
2.      The constructor is a typescript feature and it is used only for a class instantiations.
3.      The constructor called first time before the ngOnInit().
ngOnInit:-
1.      The ngOnInit event is an Angular 5 life-cycle event method that is called after the first ngOnChanges and the ngOnInit method is use to parameters defined with @Input otherwise the constructor is OK.
2.      The ngOnInit is called after the constructor and ngOnInit is called after the first ngOnChanges.
3.      The ngOnChanges is called when an input or output binding value changes.
15. What are Event Emitters and how it works in Angular 5?
Angular 5 doesn’t have bi-directional digest cycle, unlike angular 1. In angular 5, any change occurred in the component always gets propagated from the current component to all its children in the hierarchy. If the change from one component needs to be reflected to any of its parent component in a hierarchy, we can emit the event by using Event Emitter API.

In short, EventEmitter is class defined in @angular/core module which can be used by components and directives to emit custom events.

@output() somethingChanged = new EventEmitter();

We use somethingChanged.emit(value) method to emit the event. This is usually done in setter when the value is being changed in the class.

This event emit can be subscribed by any component of the module by using subscribe method.

myObj.somethingChanged.subscribe(val) => this.myLocalMethod(val));

16. Explain local reference variables, ViewChild, and ContentChild.
Local template variables in angular5 are used to refer HTML elements and use their properties to access siblings or children.

Let’s consider you have an input field named username.

<input type="text" required ... />

This HTMLInputField can be made available to the template using # symbol with a variable name say username.

<input type="text" #username required ... />

Now, this HTMLInputElement can be accessed from anywhere in the current template, for example, checking validation and showing appropriate message based on the validation rule. But, username HTML reference is not accessible in the component/directive.

To access this in the component, angular 5 provides @ViewChild decorator which accepts the local reference variable.

@ViewChild('username') username: HTMLInputElement;

ViewChild an element can be read after the view is initialized (ngAfterViewInit).

ContentChild is used to query the reference of the DOM within ng-content. Content Child are set before the ngAfterContentInit lifecycle hook.

17. Explain tsconfig.json file.
The tsconfig.json file corresponds to the configuration of the TypeScript compiler (tsc).

{ 
   "compilerOptions": { 
      "target": "es5", 
      "module": "commonjs", 
      "moduleResolution": "node", 
      "sourceMap": true, 
      "emitDecoratorMetadata": true, 
      "experimentalDecorators": true, 
      "lib": [ "es2015", "dom" ], 
      "noImplicitAny": true, 
      "suppressImplicitAnyIndexErrors": true 
   } 
}
target: the language used for the compiled output
module: the module manager used in the compiled output. system is for SystemJS, commonjs for CommonJS.
moduleResolution: the strategy used to resolve module declaration files (.d.ts files). With the node approach, they are loaded from the node_modules folder like a module (require('module-name'))
sourceMap: generate or not source map files to debug directly your application TypeScript files in the browser,
emitDecoratorMetadata: emit or not design-type metadata for decorated declarations in a source,
experimentalDecorators: enables or not experimental support for ES7 decorators,
removeComments: remove comments or not
noImplicitAny: allow or not the use of variables/parameters without types (implicit)
18. Explain package.json file.
All npm packages contain a file, usually in the project root, called package.json – this file holds various metadata relevant to the project.

This file is used to give information to npm that allows it to identify the project as well as handle the project’s dependencies.
It can also contain other metadata such as a project description, the version of the project in a particular distribution, license information, even configuration data – all of which can be vital to both npm and to the end users of the package.
The package.json file is normally located at the root directory of a Node.js project.
19. Explain systemjs.config.json file.
system.config.js is the one which allows to load modules(node modules) compiled using the TypeScript compiler.map refers to the name of modules to JS file that contains the JavaScript code.

20. Explain app.module.ts file.
This is root module that tells Angular how to assemble the application. Every Angular app has a root module class.

import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { AppComponent } from './app.component';

@NgModule({
imports: [ BrowserModule ],
declarations: [ AppComponent ],
bootstrap: [ AppComponent ]
})
export class AppModule { }
@NgModule — takes a metadata object that tells Angular how to compile and launch the application.

Imports — the BrowserModule that this and every application needs to run in a browser.

Declarations — the application’s component.

Bootstrap — this is the root component tells which component to run first.

21. What is Dependency Injection?
Dependency injection is the ability to add the functionality of components at runtime. Let’s take a look at an example and the steps used to implement dependency injection.

22. How will you handle errors in Angular 2 applications?
Angular 5 applications have the option of error handling. This is done by including the ReactJS catch library and then using the catch function.

The catch function contains a link to the Error Handler function.
In the error handler function, we send the error to the console. We also throw the error back to the main program so that the execution can continue.
Now, whenever you get an error it will be redirected to the error console of the browser.
23. What is routing?
Routing helps in directing users to different pages based on the option they choose on the main page. Hence, based on the option they choose, the required Angular Component will be rendered to the user.

24. What is @Inputs in Angular5?
@Input decorator binds a property within one component (child component) to receive a value from another component (parent component). This is one-way communication from parent to child. The component property should be annotated with a @Input decorator to act as input property. A component can receive a value from another component using component property binding.It can be annotated at any type of property such as number, string, array or user-defined class. To use an alias for the binding property name we need to assign an alias name as.@Input(alias)

25. What is @Outputs in Angular?
@Output decorator binds a property of a component to send data from one component (child component) to calling component (parent component). This is one-way communication from child to the parent component. @Output binds a property of the type of angular EventEmitter class. This property name becomes custom event name for calling component. @Output the decorator can also alias the property name as @Output(alias) and now this alias name will be used in custom event binding in calling component.

26. What is the difference between Angular  components and directives?
Components and Directives are allowing us to attach behavior to elements in DOM. There are certain differences.

A component is a directive with a view whereas a directive is a decorator with no view.
A component is used to break up the application into smaller components whereas directive is used to design the re-usable components.
A component can use pipes whereas directives can’t.
A component can be present per DOM element whereas directive is used to add behavior to an existing DOM.
27. What is the difference between ActivatedRoute and RouterState in Angular 5?
ActivateRoute and RouterState both refer to Routing in Angular 5.

ActivatedRoute consists of the information about a route associated with the component loaded in outlet whereas RouterState represents the state.
ActivatedRouteSnapshort has old data When Route changes, ActivateRouteSnapshort has data from the previous route whereas the RouteState care about the arrangements and application components.
ActivatedRouteSnapchat to traverse all the activated routes whereas RouterState maintains the states.
28. What are Pipes in Angular 5?
Pipes in Angular 5 are used in templates in order to convert them into a content that is user-friendly and readable one within the interpolation({{}}).

“|” denotes the pipe

29. Why decorators are used in Angular ?
Decorators are used as an identifier of class or type of the objects that are created by the Typescript. Decorators specify the properties of the class.

30. How can you handle errors in Angular  application?
The error in Angular can be handled by

Try – Catch functionality
Observable Errors
Promise Errors
For global error handling we need to implement handle_error()





## Contributing

We always appreciate your feedback on how the book can be improved, and more questions can be added. If you think you have some question then please add that and open a pull request. 


## License

What this means it that the project is free to read and use, but the license does not permit commercial use of the material (i.e you can freely print out the questions for your own use, but you can't sell it). I'm trying to best to publish all of my books in a free + purchased (if you would like to support these projects) form so I would greatly appreciate it if you would respect these terms.

Copyright Praveen Yadav, 2019.
