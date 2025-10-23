# What is angular? why it was introduced?
 - Angular is open-source web application framework for building dynamic, single-page applications with highly intuitive UI.
 - It Supports
    - 2-Way binding
     - Component Based Architecture
     - Dependancy Injection.
  
  - Angular was introduced to create SPA, bring structure and consistancy to web applciaions with scalability and maintainability

# What is TypeScript?
 - Typescript is a programming language developed by Microsoft.
 - It's a superset of javascript --> means JS also valid typescript.
 - Adds Optional Static Typing and other powerful features
 - Key features:
   -  Static Typing:
       - you can define types for variable, function params, return values and objects.
        ```javascript
          let name: string = "Satheesh";
          let age: number = 30;
        ```
        - this allows compiler to catch type-related errors before runtime
    
    - Type Inference:
      - Typescript can automatically infer types even if you don't explicitly declare them
        ```javascript
          let message = "Hello"; // inferred as string
        ```
    - Interfaces and Type Aliases:
        - Let you define the custom types and enforce structure on objeccts
          ```javascript
              interface User {
                name: string;
                age: number;
              }

              const user: User = { name: "Alice", age: 25 };
          ```

    - Classes and Object-Oriented Features
        - TypeScript support classes, inheritance, access modifiers (public, private, protected) and more
          ```typescript
              class Person {
                constructor(public name: string) {}
                greet() {
                    console.log(`Hello, ${this.name}`);
                }
              }
          ```

      - Tooling and IDE Support
        -  Because of typing information, editors like VS Code can provide auto-complete, intelligent refactoring and error detection

      - Transpilation
        - Typescript code is compiled (transpiled) into plain javascript using typescript compiler (tsc)
        - This makes it compatible any browser or runtime that support javascript


  # Why USe Typescript
    - Early Error Detection - during compile instead of runtime
    - Improved Code Quality - Types make the code self-documenting and easier to reafctor
    - Scalability - Ideal for large projects and teams code maintailable and harable
    - Better integration - Works seemlessly with React, Node.js, Angular and other JS frameworks

  # What is Data Binding in Angular? Which data binding does angular apply?
   - Data binding refers the process that establish connection between application's data (component class) and the view
   - It allows data synchronization between model and view
   - Four Ways:
      - One-Way Data Binding:
          - one-way data binding means data flows in only one direction- either from component to view or view to the component
          - three forms
              - Interpolation ({{ }}) (Data flows from component → template.)
                - Using to display data in view
                  ```html
                    <p>Hello, {{ userName }}!</p>
                  ```
                  ```javascript
                    export class AppComponent {
                      userName = 'Satheesh';
                    }
                  ```
               - Property Binding ([property]="expression") - Data flows from component → DOM element property.
                  - Used to bind values to HTML element properties or directives.
                     ```html
                       <img [src]="imageUrl" alt="User Photo">
                   ```
                  ```javascript
                    export class AppComponent {
                      imageUrl = 'assets/profile.jpg';
                    }
                  ```

              - Event Binding ((event)="expression")
                - Used to capture user actions (like clicks, keypresses) and send them to the component.

                  ```html
                       <img (click)="onClick()" alt="User Photo">
                   ```
                  ```javascript
                        export class AppComponent {
                           onClick() {
                             alert('Button clicked!');
                            }
                       }
                  ```
                  ✅ Data flows from template → component.

               - Two-way Data Binding ([(ngModel)])
                  - Two-way data binding allows synchronization in both directions
                  - when component changes the view updates
                  - when the user update the input view the component data changes automatically 

                    ```html
                      <input [(ngModel)]="userName" placeholder="Enter your name">
                      <p>Hello, {{ userName }}!</p>
                   ```
                  ```javascript
                        export class AppComponent {
                           userName = '';
                       }
                  ```
                    | **Type**             | **Syntax**                  | **Direction**              | **Example**                         |
                    |----------------------|-----------------------------|-----------------------------|-------------------------------------|
                    | **Interpolation**    | `{{ expression }}`          | Component → Template        | `<p>{{ name }}</p>`                 |
                    | **Property Binding** | `[property]="expression"`   | Component → DOM             | `<img [src]="imageUrl">`            |
                    | **Event Binding**    | `(event)="expression"`      | Template → Component        | `<button (click)="save()">`         |
                    | **Two-Way Binding**  | `[(ngModel)]="property"`    | Component ↔ Template        | `<input [(ngModel)]="name">`        |


    
          
      # What are Single Page Applications (SPAs)?
       - SPA loads a single web page from server and dynamically update it as the user interact with it
       - Unlike traditional websites an SPA only loads main page once after that it updates parts of page without needing to refresh the whole page.
       - SPAs are more faster, responsive and provide seemless experience to the user
    
      # Difference between Angular and Angular JS?
       - **AngularJS** is the **legacy** version — built with JavaScript, follows the **MVC pattern**, and mainly supports desktop applications.  
       - **Angular (2+)** is a **complete rewrite** — built with **TypeScript**, follows a **component-based architecture**, and supports **both web and mobile apps**.
         | **Feature** | **AngularJS (v1.x)** | **Angular (v2+)** |
         |--------------|----------------------|-------------------|
         | **Architecture** | MVC (Model-View-Controller) | Component-based architecture |
         | **Language** | JavaScript | TypeScript (superset of JavaScript) |
         | **Mobile Support** | Not supported | Fully mobile-supported |
         | **Performance** | Slower due to two-way binding with watchers | Faster with improved change detection (using Zone.js) |
         | **Dependency Injection (DI)** | Limited | Improved and more powerful DI |
         | **DOM Manipulation** | Done directly using directives | Uses a virtual DOM-like approach for better performance |
         | **Routing** | Uses `ngRoute` | Uses `@angular/router` with advanced features |
         | **Directives** | Built-in directives like `ng-model`, `ng-repeat` | Uses standard directives and decorators like `*ngIf`, `*ngFor` |
         | **Expression Syntax** | Uses `{{ }}` for binding | Uses `{{ }}` and `[]` / `()` / `[()]` for binding |
         | **Testing** | Supported via Jasmine/Karma | Better testing tools and modular testing support |
         | **Support and Updates** | No longer actively supported | Actively developed and maintained by Google |
         | **Learning Curve** | Easier for beginners | Steeper learning curve due to TypeScript and modular structure |

     # What are Decorators in Angular?
       - Decorators are special functions that attach metadata to classes, methods, properties or parameters
       - Key part of angular works, enabling it to understand manage components
       - Decorators are Typescript features (based on ES7 proposals) used by Angular to annotate and configure classes. They tell Angular how to process a class or a part of it.
       ```javascript
              @Component({
                selector: 'app-hello',
                templateUrl: './hello.component.html'
            })
           export class HelloComponent { }
      ```
       - Here, @Component is a decorator that tells Angular this class is a component, and it also provides configuration metadata.
    
     - Types of Angular Decorators
        - Class Decorators
             - These are applied to classes tell angular what kind of object the class represents
               | **Decorator** | **Purpose** |
               |----------------|-------------|
               | `@Component` | Marks a class as an Angular component. |
               | `@Directive` | Defines a custom directive. |
               | `@Pipe` | Declares a class as a pipe for data transformation. |
               | `@Injectable` | Marks a class as available for dependency injection. |
               | `@NgModule` | Declares an Angular module. |

               ```javascript
                 @Injectable({
                  providedIn: 'root'
                  })
                  export class UserService { }
               ```

          - Property Decorators
             - used to define how class properties interact with  Angular.
               | **Decorator** | **Purpose** |
               |----------------|-------------|
               | `@Input()` | Marks a property as an input that receives data from a parent component. |
               | `@Output()` | Marks a property as an output that emits events to a parent component. |
               | `@HostBinding()` | Binds a property to a host element attribute. |
               | `@HostListener()` | Subscribes to DOM events on the host element. |

                ```javascript
                  @Input() title: string;
                  @Output() clicked = new EventEmitter<string>();

                  @HostListener('click')
                  onClick() {
                    this.clicked.emit(this.title);
                  }
                ```

            - Method Decorators
              - Used for methods, typically to handle host events.
                ```javascript
                    @HostListener('window:resize', ['$event'])
                    onResize(event: Event) {
                      console.log('Window resized:', event);
                    }
                ```

            - Parameter Decorators
              - Used to inject dependencies into constructors.
              ```javascript
                constructor(@Inject(HttpClient) private http: HttpClient) { }
              ```

     # advantages of Angular?
       - **Two-Way Data Binding** – Keeps the model and view automatically synchronized.  
       - **Component-Based Architecture** – Promotes reusability and organized code structure.  
       - **Dependency Injection (DI)** – Simplifies service management and promotes modularity.  
       - **TypeScript Support** – Enables type safety, better tooling, and early error detection.  
       - **Directives** – Extend HTML with custom behaviors and reusable logic.  
       - **Reactive Programming with RxJS** – Handles asynchronous data streams efficiently.  
       - **Powerful CLI (Command Line Interface)** – Simplifies development, testing, and deployment.  
       - **Cross-Platform Development** – Supports building web, mobile, and desktop applications.  
       - **High Performance** – Uses Ahead-of-Time (AOT) compilation and efficient change detection.  
       - **Strong Community Support** – Backed by Google with a large ecosystem and resources.
    
     # Templates in Angular?
       - A **template** in Angular defines the **view (UI)** of a component.
       - It describes **how the component should be rendered in the browser**, combining **HTML** with **Angular directives**, **bindings**, and **expressions** to display dynamic data and handle user interactions.
       - 1. **Inline Template** – Defined directly inside the `@Component` decorator using the `template` property
            ```typescript
             import { Component } from '@angular/core';

             @Component({
               selector: 'app-greeting',
               template: `<h2>Hello, {{ userName }}!</h2>`
             })
             export class GreetingComponent {
               userName = 'Satheesh';
             }
            ```
            
       - 2. **External Template** – Stored in a separate `.html` file and referenced using the `templateUrl` property.
              ```typescript
                           import { Component } from '@angular/core';

                           @Component({
                             selector: 'app-dashboard',
                             templateUrl: './dashboard.component.html'
                           })
                           export class DashboardComponent {
                             title = 'Admin Dashboard';
                           }
            ```
                ```
               ```

  # What are Annotations?
   - **Annotations** in Angular are a form of **metadata** attached to classes using **decorators** (like `@Component`, `@NgModule`, etc.).  
   - They **tell Angular how to process a class** — whether it’s a component, directive, module, or service — and what configuration it needs.
   - This metadata informs Angular about how to treat those classes.
   - In simpler terms:  
           > 🧠 **Annotations describe how a class should behave within the Angular framework.**
    ```typescript
       @Component({
       selector: 'app-header',
       templateUrl: './header.component.html',
       styleUrls: ['./header.component.css']
       })
       export class HeaderComponent {
       // Component logic here
       }
    ```
     Here, @Component is an annotation that marks the HeaderComponent class as an Angular component and provides additional information, such as the template and associated styles.

# What are Directives?
 - **Directives** in Angular are special classes that let you **manipulate the DOM** or **extend the behavior of elements** in your application.
 - HTML that tell Angular how to modify the appearance, behavior, and layout of the page elements. There are 3 major types of Directives:
 - They add extra functionality to existing HTML elements, components, or attributes — helping make your UI more dynamic and interactive.
 - Angular provides **three main types** of directives:
    -  ### 1. **Component Directives**
       - Technically, **every component is a directive** with its own **template**.
       - Used to create reusable UI blocks.
       - Declared with the `@Component()` decorator.
     
   - ### 2. Structural Directives
      - Used to add or remove elements from the DOM dynamically.
      - They change the structure of the view.
      - Identified by a * prefix (e.g., *ngIf, *ngFor, *ngSwitchCase).
      ```html
       <p *ngIf="isLoggedIn">Welcome back!</p>

        <ul>
           <li *ngFor="let item of items">{{ item }}</li>
        </ul>
       ```
  - ### 3. Attribute Directives
    - Used to change the appearance or behavior of an existing element, component, or another directive.
    - They don’t add or remove elements, just modify how they look or act.
    - Built-in: ngClass, ngStyle
     
    # ⚙️ Built-In Angular Directives

| **Type** | **Directive** | **Purpose** |
|-----------|----------------|--------------|
| **Structural** | `*ngIf` | Conditionally includes an element in the DOM. |
| **Structural** | `*ngFor` | Repeats a template for each item in a list. |
| **Structural** | `*ngSwitch` | Displays elements based on a switching condition. |
| **Attribute** | `ngClass` | Adds or removes CSS classes dynamically. |
| **Attribute** | `ngStyle` | Applies dynamic inline styles. |
| **Attribute** | `ngModel` | Enables two-way data binding on form inputs. |

---

# 🧾 Summary

| **Directive Type** | **Example** | **Purpose** |
|--------------------|-------------|--------------|
| **Component** | `@Component({...})` | Defines a reusable UI block with template & logic. |
| **Structural** | `*ngIf`, `*ngFor` | Changes DOM structure by adding/removing elements. |
| **Attribute** | `[ngStyle]`, `[ngClass]`, custom | Modifies existing element’s appearance or behavior. |



# AOT Compiler?
 - Ahead of Time compiler converts the angular HTML and Typescript code into javascript suring build phase
 - instead of combiling code in the browser (JIT) compilation

# What are the Components in Angular?
 - A **Component** in Angular is the **building block** of the application’s UI.
 - It controls a specific **view (HTML template)** and contains both **logic (TypeScript code)** and **data (properties and methods)** that define how that view behaves.
 - ## 🏗️ Structure of a Component - Each Angular component consists of **three main parts**:
   -  1. **Template (HTML)** – Defines the **view** (what the user sees).
   -  2. **Class (TypeScript)** – Contains the **logic and data** of the component.
   -  3. **Metadata (Decorator)** – Provides **configuration** information to Angular using the `@Component()` decorator.


# How angular works?
# ⚙️ How Does an Angular Application Work?

An Angular application works through several stages — from **bootstrapping** to **rendering**, **data binding**, and **DOM updates** — using modules, components, and services.

---

## 🧠 Mermaid Diagram: Angular Application Workflow



<img width="1024" height="1536" alt="image" src="https://github.com/user-attachments/assets/3723e06b-1208-4097-9b21-7c09520ef015" />



  
    
   




      

     
