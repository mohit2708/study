### Ques. What is angular?
* Angular is a **TypeScript-based open-source** front-end platform that makes it easy to build web/mobile/desktop application development framework created by Google. 
* It is used to build frontend, single-page applications that run on JavaScript.

### Ques. What is the difference between AngularJS and Angular?
|AngularJS|Angular|
|---|---|
|It is based on MVC architecture |This is based on Service/Controller()|
|It uses use JavaScript to build the application | It Uses TypeScript to build the application |
| Based on controllers concept | This is a component based UI approach |
|No support for mobile platforms | Fully supports mobile platforms |
| Difficult to build SEO friendly application | Ease to build SEO friendly applications |


### Ques. What is TypeScript?
* TypeScript is an object-oriented strongly typed language.
* TypeScript is a strongly typed superset of JavaScript created by Microsoft that adds optional types, classes, async/await and many other features, and compiles to plain JavaScript.
* We can install TypeScript globally.
```javascript
npm install -g typescript
```
 ### Ques. What are the key components of Angular?
Angular has the key components below.
1. **Component:** These are the basic building blocks of an Angular application to control HTML views.
2. **Modules:** An Angular module is a set of angular basic building blocks like components, directives, services etc. An application is divided into logical pieces and each piece of code is called as "module" which perform a single task.
3. **Templates:** These represent the views of an Angular application.
Services: Are used to create components which can be shared across the entire application.
4. **Metadata:** This can be used to add more data to an Angular class.

### Ques. What are directives?
* Directives are classes that add additional behavior to elements in your Angular applications.
* Directive are elements which change the appearance or behavior of the DOM elements.
* Directive in angular can be categorized into the following types:
1. **Component Directive:-**
2. **Structural Directive:-** 
* Structural directives are used to change the DOM layout by adding and removing DOM elements. It basically changes the structure of the DOM
Examples of structural directives are **ngIf**, **ngFor**, **ngSwitch**.
* All structural Directives are preceded by Asterix (*)symbol.
  * ***ngIf —** adds or removes element from DOM.
  * ***ngFor —** renders list of elements on every iteration.

3. **Attribute directive:-** 
* Attribute directives are used to change the appearance or behavior of an element.
* Examples of attributes directives are **ngStyle**, **ngClass**, **ngModel**
  * **ngStyle —** used to apply styles that will change the appearance.
  * **ngClass —** used to apply CSS classes to change the appearance.

### Ques. How to create custome directive?
```javascript
ng g directive name_of_the_directive
```

### Ques. What are component?
* Components are the most basic UI building block of an Angular app.
* These components are associated with a template and are a subset of directives. 

### Ques. Download the node?
* Go to the url:- https://nodejs.org/en/
* Check the version of node:- open the cmd and run this commend:- **node -v**
* check the version of npm:- **npm -v**

### Ques. Install the Angular CLI?
```javascript
npm install -g @angular/cli
```
* install the **specific version** of angular-cli.
```javascript
npm install -g @angular/cli@12
```
* Check the version of angular cli
```javascript
ng version
```


### Ques. Create the project?
```javascript
ng new my-first-project
cd my-first-project
ng serve
```

### Folder Structure?
* package.json
* src
    * app
    * assets:- css, js, img
    * favicon.ico
    * index.html
    * main.ts
    * styles.scss
* angular.json:- project ki configration

### Create the component?
```javascript
ng generate component login (OR)
ng g c component_name 
```

### Create model
* model have multipal component.
```javascript
# Create model
ng g m user_auth
```
* create component in model
```javascript
ng g c user_auth/login
```


### Ques. What is data binding? Which type of data binding does Angular deploy?
* Data binding in AngularJS is the synchronization between the model and the view.
* When data in the model changes, the view reflects the change, and when data in the view changes, the model is updated as well.
* We can make connections in **two different ways** one way and two-way binding.

* **One-way data binding** is a one-way interaction between component and its template. If you perform any changes in your component, then it will reflect the HTML elements. It supports the following types −
  * **String interpolation:-** Interpolation is used to display data from component to view (DOM). It is denoted by the expression of {{ }} and also known as **mustache** syntax.
  * **Event binding:-** Events are actions like mouse click, double click, hover or any keyboard and mouse actions. If a user interacts with an application and performs some actions, then event will be raised. It is denoted by either parenthesis () or on-
  * **Property binding:-** Property binding is used to bind the data from property of a component to DOM elements. It is denoted by [].


### Ques. What are Single Page Applications (SPA)?

### Ques. What are decorators in Angular?
* Decorators are a design pattern that is used to separate modification or decoration of a class without modifying the original source code.
* In AngularJS, decorators are functions that allow a service, directive, or filter to be modified before it is used.
* **There are four main types of angular decorators:**
  * **Class decorators**, such as **@Component** and **@NgModule**
  * **Property decorators** for properties inside classes, such as **@Input** and **@Output**
  * **Method decorators** for methods inside classes, such as **@HostListener**
  * **Parameter decorators** for parameters inside class constructors, such as **@Inject**



