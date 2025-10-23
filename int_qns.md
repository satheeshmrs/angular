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


    # 


          
      

     
