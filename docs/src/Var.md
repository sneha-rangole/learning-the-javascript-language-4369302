Here are some important notes and definitions related to JavaScript's `var` statement in simple language:

### Important Notes on `var` in JavaScript
1. Scope:
   - `var` is function-scoped or globally scoped.
   - It is not block-scoped, meaning a `var` variable inside an `if`, `for`, or `while` loop can be accessed outside of that block.

2. Hoisting:
   - Variables declared with `var` are hoisted to the top of their scope.
   - Only the declaration is hoisted, not the initialization.
   - Example:
     ```js
     console.log(a); // undefined (not an error)
     var a = 10;
     ```
   - This is treated as:
     ```js
     var a;
     console.log(a); // undefined
     a = 10;
     ```

3. Re-declaration:
   - You can declare the same variable multiple times with `var` without errors.
   - Example:
     ```js
     var x = 5;
     var x = 10; // No error
     console.log(x); // 10
     ```

4. Global Variables:
   - If `var` is used outside a function, it becomes a global variable.
   - Example:
     ```js
     var name = "John"; // Global variable
     function sayHello() {
       console.log("Hello " + name);
     }
     sayHello(); // Hello John
     ```

5. `var` inside a function:
   - When declared inside a function, it is limited to that function.
   - Example:
     ```js
     function example() {
       var a = 10;
       console.log(a); // Works inside the function
     }
     example();
     console.log(a); // Error: a is not defined
     ```

6. Avoid using `var` in modern JavaScript:
   - `let` and `const` are recommended because they have block scope and prevent unintended re-declarations.

---

### Key Definitions
- Variable: A container for storing data.
- Scope: The area where a variable is accessible.
- Hoisting: JavaScript moves declarations to the top of their scope before executing code.
- Global Variable: A variable accessible from anywhere in the code.
- Function Scope: A variable declared inside a function is only available within that function.

Would you like a summary of `let` and `const` as well?