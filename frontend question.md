# Comprehensive Frontend Interview Questions (JavaScript & React)
ALL notes and interview questions here - https://github.com/priya42bagde
This document compiles a wide range of frontend interview questions covering JavaScript, React, Redux, system design, performance, HTML/CSS, coding problems, and behavioral topics. The questions are sourced from the provided notes and the GitHub repository [priya42bagde](https://github.com/priya42bagde). They are categorized for easy navigation and study.

---

## 📚 Table of Contents
- [JavaScript Core Concepts](#javascript-core-concepts)
- [JavaScript Advanced & Internals](#javascript-advanced--internals)
- [Asynchronous JavaScript](#asynchronous-javascript)
- [JavaScript Coding & Polyfills](#javascript-coding--polyfills)
- [React Core](#react-core)
- [React Hooks & Performance](#react-hooks--performance)
- [React Advanced & Internals](#react-advanced--internals)
- [Redux & State Management](#redux--state-management)
- [Frontend System Design](#frontend-system-design)
- [Performance Optimization](#performance-optimization)
- [HTML & CSS](#html--css)
- [Browser & DOM APIs](#browser--dom-apis)
- [Coding Problems (DSA & Algorithms)](#coding-problems-dsa--algorithms)
- [Low-Level Design (LLD) / Component Design](#low-level-design-lld--component-design)
- [Real-World Scenarios & Problem Solving](#real-world-scenarios--problem-solving)
- [Behavioral & Hiring Manager Questions](#behavioral--hiring-manager-questions)
- [Frontend Architecture & Team Leadership](#frontend-architecture--team-leadership)
- [Testing, CI/CD & Developer Experience](#testing-cicd--developer-experience)
- [Miscellaneous / General](#miscellaneous--general)

---

## JavaScript Core Concepts

### Variables & Scope
1. Difference between `var`, `let`, and `const`.
2. What is scope? Explain global, function, and block scope.
3. What is hoisting?
4. Why do we get `ReferenceError: Cannot access 'x' before initialization`?
5. What is the Temporal Dead Zone (TDZ)?
6. Difference between `undefined` and `not defined`.
7. Truthy and falsy values in JavaScript.

### Functions & Execution
8. Function declaration vs function expression.
9. Arrow functions vs regular functions – differences in `this` and syntax.
10. What is the call stack?
11. What is an execution context?
12. Explain closures with a real-world example.
13. How does the `this` keyword behave in arrow functions, class methods, and event handlers?
14. Explain `call`, `apply`, and `bind` with use cases. Implement polyfills.

### Data Types & Coercion
15. Primitive vs reference types.
16. Type coercion and equality: `==` vs `===`.
17. Difference between `null` and `undefined`.
18. How to check if a variable is an array?

### Objects & Prototypes
19. How does prototypal inheritance work?
20. Prototype chain vs class inheritance.
21. `Object.create()` and ES6 classes.
22. Shallow copy vs deep copy – how to achieve each? Modern solution: `structuredClone()`.

### Arrays & Iteration
23. Difference between `map`, `filter`, and `forEach`.
24. `map` vs `forEach` – when to use which?
25. `slice` vs `splice`.
26. `find`, `some`, `every` – use cases.
27. Sorting arrays with custom comparators.

### ES6+ Features
28. Destructuring (objects and arrays).
29. Spread and rest operators.
30. Template literals.
31. Modules (`import`/`export`).
32. Optional chaining (`?.`) and nullish coalescing (`??`).
33. WeakMap vs Map – real use cases.
34. Symbols and iterators.

---

## JavaScript Advanced & Internals

1. Explain the JavaScript event loop in detail. Microtasks vs macrotasks.
2. How do JavaScript engines optimize code? (JIT, hidden classes, inline caching)
3. How does garbage collection work in V8?
4. What is the difference between `setTimeout` and `setInterval`?
5. Implement a custom Promise (conceptually).
6. How does the browser rendering pipeline work? (HTML → CSS → Layout → Paint → Composite)
7. What causes memory leaks in frontend applications? How to prevent them?
8. Explain `AbortController` and request cancellation.
9. Cross-tab communication methods: `BroadcastChannel`, `storage` events, `postMessage`.
10. Event delegation at scale – benefits and pitfalls.
11. Why does JavaScript have closures? (data privacy, hooks, callbacks, memoization)
12. `var`, `let`, `const` – interviewers want hoisting + TDZ explanation.

---

## Asynchronous JavaScript

1. Synchronous vs asynchronous programming.
2. Callback functions – what are they? Callback hell.
3. Promises – states (pending, fulfilled, rejected) and how they work.
4. `async` / `await` – how they simplify promises.
5. Event loop: Why does a Promise run before `setTimeout`? (Microtasks vs macrotasks)
6. Implement `Promise.all`, `Promise.race`, `Promise.allSettled` from scratch.
7. Difference between microtask queue and callback (macrotask) queue.
8. How to handle multiple independent API calls efficiently? (`Promise.all`, `allSettled`)
9. What are the advantages of `Promise.allSettled` over `Promise.all`?

---

## JavaScript Coding & Polyfills

1. Implement `Promise.all` from scratch.
2. Implement debounce and throttle functions.
3. Implement a deep clone function (deep copy).
4. Write a polyfill for `call`, `apply`, and `bind`.
5. Implement `map`, `reduce`, `filter` from scratch.
6. Flatten a nested array without using `Array.flat()`.
   - Input: `[1,2,3,[4,5,6,[7,8,[10,11]]],9]`
   - Output: `[1,2,3,4,5,6,7,8,10,11,9]`
7. Find the first repeating character in a string (e.g., `"success"` → `"c"`).
8. Find the first non-repeating character in a string.
9. Currying for infinite sum: `sum(10)(20)(30)() → 60`, `sum(10)(20)(30)(40)(50)(60)() → 210`.
10. Find sum of numbers without using a for loop (using `reduce` or recursion).
11. Given an array of users, find all active user ids:
    - `users = [{ id: 1, active: true }, { id: 2, active: false }]`
    - `users = [{ id: 1, active: true }, null, {}, { id: 2, active: false }]`
12. Solve a problem using only `map()` and `filter()` (no loops). Explain edge cases.
13. Implement a custom hook like `useDebounce` or `useFetch` (React).

---

## React Core

1. What is React JS?
2. Why React.js? What problems does it solve?
3. What is JSX and how is it rendered in the browser?
4. What are components? Functional vs class components.
5. What are state and props? Difference between them.
6. What is a hook? Why were hooks introduced?
7. If we have `var`, `let`, `const`, why do we need state variables?
8. What is re-rendering, and why does it happen?
9. What is reconciliation in React? How does the diffing algorithm work?
10. Why are keys important in lists? What happens if keys are unstable?
11. What is the difference between `Router` and `Link` in React Router?
12. What is routing in React? How does it work?
13. Controlled vs uncontrolled components – explain with examples.
14. What is prop drilling? Problems and solutions.
15. How do you pass parent data to a deeply nested child (e.g., 5th child)?
16. Difference between `useMemo` and `React.memo`.
17. Difference between `useMemo` and `useCallback`.
18. What happens if a component wrapped in `memo()` has its own state changes?
19. What happens if a child uses `memo()` and parent props don't change?
20. What is state batching? What changed in React 18 regarding batching?
21. Explain `useEffect` deeply: cleanup function, dependency array pitfalls.
22. Difference between `useEffect`, `useLayoutEffect`, and `useInsertionEffect`.
23. What problems does `useMemo` actually solve? When should you NOT use it?
24. When would you use `React.memo`?
25. Build a custom hook like `useDebounce` or `useFetch`.

---

## React Advanced & Internals

1. How does React Fiber architecture change rendering?
2. What is concurrent rendering? When does it help vs hurt?
3. Explain React Server Components vs Client Components.
4. What is hydration? How do hydration mismatches occur?
5. How does React Context work? When can it hurt performance?
6. Scenario: Context API causes frequent re-renders – why and how to fix?
7. What is code splitting? How does `React.lazy` work internally?
8. How does tree shaking work in modern bundlers?
9. What is the purpose of `Suspense` beyond lazy loading?
10. Explain the concept of "controlled re-render boundaries".
11. How would you build a custom hook library?
12. What are the hidden reasons a component re-renders even when props don't change? (parent re-render, inline functions/objects, context changes)
13. How does React 18's automatic batching work?
14. How do you handle real-time updates efficiently in React?

---

## Redux & State Management

1. What is Redux and why is it used?
2. What problems does Redux solve in large React applications?
3. Explain the Redux data flow (action → reducer → store → view).
4. What is Redux Toolkit and why is it recommended over plain Redux?
5. Explain the flow of Redux Toolkit.
6. How does Redux Toolkit work internally?
7. What is `createSlice()` and what does it contain? (name, initialState, reducers)
8. Explain reducers and `extraReducers` – when to use each?
9. What is `createAsyncThunk()` and why is it used?
10. How does async flow work in Redux Toolkit?
11. Where and why have you used Redux Toolkit in your projects?
12. Redux vs Context API vs Zustand – how do you decide in a large-scale application?
13. Compare Redux, MobX, and Recoil for enterprise-scale state management (pros and cons).
14. How would you design a state management solution for a complex analytics/dashboard app?

---

## Frontend System Design

### Design Problems
1. Design an autocomplete search with debouncing, caching, and race condition handling.
2. Design an infinite scrolling feed (virtualization, pagination, loading states).
3. Design a real-time dashboard with multiple data sources.
4. Design an e-commerce frontend with filters (price, category, rating) and scalable state updates.
5. Design a notification/toast system with queueing, auto-dismiss, and priority handling.
6. Design a search with typeahead/autocomplete.
7. Design a config-driven form renderer using a JSON schema.
8. Design a file upload component with progress tracking and chunked uploads.
9. Design a data table with sorting, filtering, pagination, and performance trade-offs.
10. Design an image gallery with lazy loading and skeleton placeholders.
11. Design a carousel that can handle 1000+ images efficiently.
12. Design a drag-and-drop interface (e.g., kanban board).
13. Design a multi-step form with validation.
14. Design a theme-able, extensible component library.
15. Design a state management solution for a complex app.
16. How would you implement Server-Side Rendering (SSR) for a React application? When to use SSR, SSG, ISR?

### Architecture & Strategy
17. How would you structure a micro-frontend architecture enabling team autonomy and independent releases?
18. How do you manage shared libraries and dependencies in a large monorepo?
19. How would you design SSR/SSG/hydration strategy for a React app?
20. How do you handle breaking API changes safely on the frontend?
21. What is your approach to multi-tenant frontend applications?
22. How do you implement dark mode across an app?
23. How do you ensure accessibility beyond ARIA labels?

---

## Performance Optimization

1. How would you optimize a React application rendering 100k+ items in a list? (virtualization, windowing, pagination)
2. What strategies would you use to improve page load time for a global audience? (CDN, lazy loading, code splitting, image optimization)
3. How do you debug a performance bottleneck in a React app using DevTools? (Profiler, Performance tab)
4. How would you improve Web Vitals (LCP, CLS, INP)?
5. What causes unnecessary re-renders in React? How to avoid them? (memoization, stable props, colocated state)
6. Explain techniques for dynamic code splitting and lazy loading in multi-route SPAs.
7. How do you optimize images and fonts?
8. What are preload, prefetch, and priority hints?
9. How do you analyze bundle size and fix tree shaking failures?
10. What is the difference between virtualization and windowing? Trade-offs.
11. How do you avoid layout thrashing?
12. CPU vs memory bottlenecks – how to identify and fix?
13. Edge caching vs CDN caching strategies.
14. How would you handle a large dataset without blocking the main thread? (Web Workers, virtualization)
15. How do you detect and prevent memory leaks in long-running SPAs?

---

## HTML & CSS

### HTML
1. What are semantic tags in HTML? Give examples.
2. What is the difference between `div` and `span`?
3. How do you create a form with validation?
4. What is the purpose of the `meta` tags?
5. Explain the difference between `localStorage`, `sessionStorage`, and cookies.

### CSS
6. What is a pseudo-class? Give examples (`:hover`, `:nth-child`, etc.).
7. How to center an element horizontally? Vertically? Both?
8. Difference between `relative` and `absolute` positioning.
9. What is Flexbox? Explain main concepts.
10. How would you create a responsive layout with CSS Grid?
11. What are container queries?
12. How do you implement a CSS animation? How to debug janky animations on mobile?
13. Explain the concept of specificity in CSS.
14. What are CSS custom properties (variables)?
15. How do you handle dark mode theming?

### Inline Layout
16. How to place 5 `div`s in a row without using flex, margin, or padding? (Hint: `display: inline-block`)

---

## Browser & DOM APIs

1. How do you select and manipulate DOM elements?
2. Explain event bubbling and capturing.
3. What is event delegation? When would you use it?
4. How does `addEventListener` work? How to remove listeners?
5. What are the different ways to handle forms in JavaScript?
6. Difference between `LocalStorage` and `SessionStorage`.
7. How do you work with cookies in JavaScript?
8. Explain the `IntersectionObserver` API and its use cases (lazy loading, infinite scroll).
9. What is the `ResizeObserver`?
10. How do you implement drag and drop using native APIs?
11. How does the `history` API work for routing?
12. What is the `AbortController` used for?

---

## Coding Problems (DSA & Algorithms)

1. Maximum sum subarray (Kadane's algorithm).
2. Sliding window maximum.
3. Merge k sorted linked lists.
4. Detect a cycle in a linked list.
5. Longest palindromic substring.
6. Design and implement an LRU Cache.
7. Flatten a nested array (recursive/iterative).
8. Find first repeating character in a string.
9. Find first non-repeating character.
10. Implement debounce and throttle.
11. Implement deep clone.
12. Implement `Promise.all`.
13. Currying for infinite sum.
14. Given an array of users with nested null/objects, filter active user ids.

---

## Low-Level Design (LLD) / Component Design

### Component Design Fundamentals
1. Design a Todo List application with add, edit, delete, and mark-as-complete.
2. Design a Tabs component that supports dynamic content loading and async data.
3. Design an Accordion component – should it allow single or multiple panels open? Why?
4. Design a Star Rating component – how would you support half or partial ratings?
5. Design a Progress Bar / Stepper with configurable steps and validation logic.
6. Design a Modal/Dialog component – focus trapping, accessibility, backdrop behavior.
7. Design a Toggle / Switch component – controlled vs uncontrolled patterns.
8. Design a Dropdown / Select component with keyboard navigation and accessibility.

### State, Data & UI Systems
9. Design a Posts with Comments system – how do you manage deeply nested data?
10. Design an E-commerce Filter system (price, category, rating) with scalable state updates.
11. Design a Config-Driven Form Renderer using a JSON schema.
12. Design a Notification / Toast system with queueing, auto-dismiss, and priority.
13. Design a Search with Autocomplete / Typeahead – debouncing, caching, race conditions.

### Performance & Optimization
14. Design a Carousel that can handle 1000+ images efficiently.
15. Implement Virtual Scrolling for very large lists.
16. Design an Image Gallery with lazy loading and skeleton placeholders.
17. Design a Data Table with sorting, filtering, pagination, and performance trade-offs.
18. Implement Debouncing and Throttling in a search or scroll-heavy component.
19. Design a File Upload component with progress tracking and chunked uploads.
20. How do you detect and prevent memory leaks in long-running SPAs?

### Architecture & Scalability
21. How would you design a theme-able, extensible component library?
22. How do you structure a large-scale React application across multiple teams?
23. Design a state management solution for a complex analytics/dashboard app.
24. How would you implement SSR for a React application?

---

## Real-World Scenarios & Problem Solving

1. **Memory Leak**: You notice a memory leak in a production SPA – how do you identify and fix it?
2. **Library Upgrade**: A component breaks when upgrading a library version – how do you manage dependencies?
3. **UI Glitches**: Users report intermittent UI glitches in different browsers – how do you troubleshoot?
4. **Peak Traffic Failure**: A critical UI feature fails during peak traffic – how do you mitigate?
5. **Debugging Production**: How would you debug production issues methodically? (reproduce, logs, profiling, rollback)
6. **When NOT to use JavaScript**: CPU-heavy tasks, long-running blocking logic – use backend or workers.
7. **Authentication Token Expiry**: How do you handle token expiry mid-session? (interceptors, refresh token, queue requests)
8. **Multiple API Calls**: How to load a dashboard with independent APIs efficiently? (`Promise.all`, `allSettled`)
9. **Large List Rendering**: 10k+ items cause UI lag – optimization strategies.
10. **Context Re-renders**: Context API causes frequent re-renders – why and how to fix?
11. **Component Re-renders Unexpectedly**: Component re-renders even when props don't change – hidden reasons.
12. **Poor SEO & Slow TTI**: React app has poor SEO and slow TTI – frontend-level solutions.
13. **Real-time Updates**: How to handle real-time updates efficiently in React?
14. **A/B Testing**: How to implement A/B testing without affecting current users?
15. **CSS Animation Jank**: A CSS animation is janky on mobile – how to identify and fix?

---

## Behavioral & Hiring Manager Questions

1. Explain a frontend project you built end-to-end.
2. Describe the hardest production bug you fixed.
3. How do you balance performance vs feature delivery?
4. How do you handle disagreements in technical decisions?
5. When did you get stuck while using React, and how did you fix it?
6. Have you led a team? What is your current role?
7. Have you handled task distribution and requirement breakdown?
8. Have you been involved in architectural or technical decision-making?
9. How do you mentor juniors through code walkthroughs, tech spikes, and 1:1s?
10. Do you have any questions for me?

---

## Frontend Architecture & Team Leadership

1. How would you structure a micro-frontend architecture for team autonomy?
2. Describe your process for creating and enforcing a scalable design system across distributed teams.
3. How do you manage shared libraries and dependencies in a monorepo?
4. What is your framework for identifying, prioritizing, and reducing technical debt?
5. How do you implement scalable code review workflows (linters, pre-commit hooks, pair programming)?
6. How do you handle versioning of UI contracts?
7. What tools and practices do you use for frontend observability, error tracking, and performance monitoring?
8. How do you ensure secure handling of sensitive user data on the client side? (XSS, CSP, CSRF, token leakage)
9. How would you design a migration strategy from a legacy jQuery app to modern React/Next.js?
10. How do you integrate feature flags (LaunchDarkly, etc.) in React ecosystems?
11. How do you coordinate deployments with DevOps teams? Handling multiple pods with different versions.

---

## Testing, CI/CD & Developer Experience

1. How would you implement a robust frontend monitoring and logging system?
2. What are flaky test detection strategies?
3. Explain contract testing between frontend and backend.
4. What is visual regression testing? How would you implement it?
5. How would you design a CI/CD pipeline for frontend apps with staging, canary, and blue-green deployments?
6. What is chaos engineering for frontend?
7. How do you ensure code quality with testing? (unit, integration, e2e)
8. Have you worked with Storybook? How do you use it?

---

## Miscellaneous / General

1. What is the difference between CSR, SSR, SSG, and ISR?
2. What are Web Vitals and why do they matter?
3. How do you build PWAs with service workers, manifest files, and offline-first experiences?
4. Compare WebSockets, SSE, and WebRTC for real-time features.
5. How do you handle offline-first apps with IndexedDB, background sync, and conflict resolution?
6. What is your strategy for fluid responsive design using CSS Grid, Flexbox, and container queries?
7. How do you extract spacing, font sizes, and colors from Figma designs?
8. How do you approach developing a reusable component from a design?
9. What is atomic design methodology?
10. How do you check page load behavior using browser developer tools? What metrics do you look at?
11. How would you check cumulative layout shifts (CLS) on a page?
12. What tools do you use for frontend performance analysis? (Lighthouse, WebPageTest, Chrome DevTools)

---

*This document is a living compilation. Use it to prepare for frontend interviews at all levels – from junior to senior/staff.*


## 1. Variables & Scope

### Difference between `var`, `let`, and `const`

| Feature | `var` | `let` | `const` |
|---------|------|------|--------|
| **Scope** | Function-scoped | Block-scoped `{ }` | Block-scoped `{ }` |
| **Hoisting** | Hoisted and initialized with `undefined` | Hoisted but not initialized (TDZ) | Hoisted but not initialized (TDZ) |
| **Re-declaration** | Allowed in same scope | Not allowed | Not allowed |
| **Re-assignment** | Allowed | Allowed | Not allowed (for primitives; for objects, properties can be modified) |
| **Global property** | Becomes property of `window` (in browsers) | Does not create property on `window` | Does not create property on `window` |

```javascript
// var example
console.log(x); // undefined (hoisted)
var x = 5;
var x = 10; // allowed

// let example
// console.log(y); // ReferenceError: Cannot access 'y' before initialization
let y = 20;
// let y = 30; // SyntaxError: Identifier 'y' has already been declared

// const example
const z = 40;
// z = 50; // TypeError: Assignment to constant variable
const obj = { a: 1 };
obj.a = 2; // allowed – object is not frozen
```

### What is scope? Explain global, function, and block scope.

**Scope** defines where variables and functions are accessible during runtime.

- **Global scope**: Variables declared outside any function or block are globally accessible. In browsers, global variables become properties of `window`.
- **Function scope**: Variables declared with `var`, `let`, or `const` inside a function are accessible only within that function.
- **Block scope**: Introduced with ES6; `let` and `const` are block-scoped, meaning they are confined to the nearest `{ }` (e.g., `if`, `for`, `while`). `var` ignores block scope.

```javascript
if (true) {
  var a = 1;   // function-scoped (or global)
  let b = 2;   // block-scoped
  const c = 3; // block-scoped
}
console.log(a); // 1
// console.log(b); // ReferenceError: b is not defined
// console.log(c); // ReferenceError: c is not defined
```

### What is hoisting?

Hoisting is JavaScript's behavior where variable and function declarations are moved to the top of their containing scope during compilation.

- `var` declarations are hoisted and initialized with `undefined`.
- `let` and `const` are hoisted but remain uninitialized (in the Temporal Dead Zone).
- Function declarations are hoisted entirely (both name and body), so they can be called before they appear in code.

```javascript
console.log(foo); // undefined (var)
var foo = 'bar';

sayHello(); // "Hello!" – function declaration hoisted
function sayHello() { console.log("Hello!"); }

// Arrow function (assigned to var) – only variable is hoisted, not the assignment
// sayHi(); // TypeError: sayHi is not a function
var sayHi = () => console.log("Hi");
```

### Why do we get `ReferenceError: Cannot access 'x' before initialization`?

This error occurs when trying to access a `let` or `const` variable before its declaration line is executed, because they are hoisted but not initialized. The time between entering the scope and the actual declaration is the **Temporal Dead Zone (TDZ)**.

### What is the Temporal Dead Zone (TDZ)?

The TDZ is the period from entering a block scope until the variable is declared with `let` or `const`. During this time, accessing the variable results in a `ReferenceError`. It prevents accidental use of variables before they are ready.

```javascript
{
  // TDZ for a starts here
  // console.log(a); // ReferenceError
  let a = 10; // TDZ ends here
}
```

### Difference between `undefined` and `not defined`

- **`undefined`** is a primitive value automatically assigned to variables that have been declared but not yet assigned a value. It is a valid value.
- **`not defined`** is a reference error thrown when trying to access a variable that was never declared in the current scope.

```javascript
let a;
console.log(a); // undefined
console.log(b); // ReferenceError: b is not defined
```

### Truthy and falsy values in JavaScript

In JavaScript, every value is either **truthy** or **falsy** when evaluated in a boolean context (e.g., `if` condition).

**Falsy values** (only 8):
- `false`
- `0`, `-0`, `0n` (BigInt zero)
- `""`, `''`, ` `` ` (empty string)
- `null`
- `undefined`
- `NaN`

Everything else is **truthy**, including:
- `"0"`, `"false"`, `" "` (non-empty strings)
- `[]` (empty array)
- `{}` (empty object)
- `function() {}`
- `Infinity`, `-Infinity`

### Additional Questions for Variables & Scope

**Q: What is the difference between `let` and `const` in terms of object mutation?**  
A: `const` prevents reassignment of the variable, but if the variable holds an object, the object's properties can still be mutated. To freeze an object, use `Object.freeze()`.

**Q: Can you declare a `let` variable in a `switch` block without curly braces?**  
A: Yes, but each `case` shares the same block scope. Using `let` in multiple cases without a block will cause a redeclaration error. It's safer to wrap cases in `{}`.

**Q: What is the difference between implicit and explicit global variables?**  
A: Explicit globals are declared with `var` in global scope. Implicit globals occur when assigning to an undeclared variable (without `var`, `let`, `const`) – this creates a property on the global object (but is not hoisted). In strict mode, this throws an error.

**Q: How does strict mode affect scoping and variable declaration?**  
A: Strict mode (`"use strict"`) prevents accidental globals, disallows duplicate parameter names, and changes the behavior of `this` in functions (defaults to `undefined` instead of `window`).

---

## 2. Functions & Execution

### Function declaration vs function expression

| | Function Declaration | Function Expression |
|---|----------------------|----------------------|
| **Syntax** | `function name() {}` | `const name = function() {};` or arrow function |
| **Hoisting** | Entire declaration hoisted (can call before definition) | Only variable declaration hoisted (not assignment) |
| **Name** | Has a named identifier | Can be anonymous or named |
| **Usage** | Can be used anywhere in its scope | Must be defined before invocation |

```javascript
// Function declaration – hoisted
foo(); // "foo"
function foo() { console.log("foo"); }

// Function expression – not hoisted
// bar(); // TypeError: bar is not a function
const bar = function() { console.log("bar"); };
```

### Arrow functions vs regular functions – differences in `this` and syntax

**Syntax differences:**
- Arrow functions omit the `function` keyword; can have implicit return if single expression.
- If only one parameter, parentheses can be omitted.

**`this` binding:**
- **Regular functions**: `this` is determined by how the function is called (dynamic binding). In global context, `this` refers to the global object (or `undefined` in strict mode). As a method, `this` refers to the object. As a constructor, `this` refers to the new instance.
- **Arrow functions**: Do not have their own `this`; they capture `this` from the surrounding lexical scope at the time they are defined (lexical binding). They are not suitable for methods that need their own `this` (e.g., event handlers, object methods that need the object), but they are great for callbacks that need to preserve the outer `this`.

```javascript
const obj = {
  name: "Alice",
  regular: function() { console.log(this.name); },
  arrow: () => console.log(this.name) // `this` is global (or undefined in strict mode)
};
obj.regular(); // "Alice"
obj.arrow();   // undefined (or error in strict mode)

// Arrow functions cannot be used as constructors (no `prototype` property)
// new (() => {}); // TypeError
```

### What is the call stack?

The **call stack** is a data structure that records function calls. When a function is invoked, a frame is pushed onto the stack. When it returns, it's popped. It helps track the execution order and current point of execution. Stack overflow occurs when too many frames are pushed (e.g., infinite recursion).

### What is an execution context?

An **execution context** is an abstract environment where JavaScript code is evaluated and executed. There are three types:
- **Global execution context**: Default context, creates global object and `this`.
- **Function execution context**: Created when a function is called; includes local variables, arguments, and `this`.
- **Eval execution context** (rare).

Each execution context has two phases:
1. **Creation phase**: Hoisting occurs, scope chain is built, `this` is determined.
2. **Execution phase**: Code is executed line by line.

The call stack holds a stack of execution contexts.

### Explain closures with a real-world example

A **closure** is the combination of a function and the lexical environment within which that function was declared. The inner function retains access to variables from its outer scope even after the outer function has returned.

**Real-world example: Counter factory**

```javascript
function createCounter() {
  let count = 0;
  return function() {
    count++;
    return count;
  };
}

const counter = createCounter();
console.log(counter()); // 1
console.log(counter()); // 2
// `count` is private and persists because the inner function closes over it.
```

**Use cases:** Data privacy, function factories, partial application, maintaining state in callbacks.

### How does the `this` keyword behave in arrow functions, class methods, and event handlers?

- **Arrow functions**: Lexical `this` (inherits from enclosing context). In an event listener, if you use an arrow function, `this` will refer to the enclosing context (e.g., the component, not the DOM element). In a class method, if defined as an arrow property, `this` is bound to the instance.
- **Class methods**: Regular class methods have `this` bound to the instance when called as `obj.method()`. But if passed as a callback, `this` can be lost; solutions: bind, arrow method, or using `.bind` in constructor.
- **Event handlers (DOM)**: In regular function event handlers, `this` refers to the element that received the event. In arrow functions, `this` is lexical (often the window or surrounding context). Use regular function if you need the element.

### Explain `call`, `apply`, and `bind` with use cases. Implement polyfills.

All three are used to control the `this` value in functions.

- **`call(thisArg, arg1, arg2, ...)`**: Invokes the function immediately with a given `this` and arguments passed individually.
- **`apply(thisArg, [argsArray])`**: Same as `call`, but arguments are passed as an array.
- **`bind(thisArg, ...args)`**: Returns a new function with the `this` bound permanently; can be called later.

**Use cases:**
- Borrowing methods: e.g., `Array.prototype.slice.call(arguments)`
- Function currying: `const multiply = (a,b) => a*b; const double = multiply.bind(null, 2);`
- Event handlers: ensure `this` refers to the class instance.

**Polyfills:**

```javascript
// call polyfill
Function.prototype.myCall = function(context, ...args) {
  context = context || globalThis;
  const uniqueId = Symbol(); // avoid property collision
  context[uniqueId] = this;
  const result = context[uniqueId](...args);
  delete context[uniqueId];
  return result;
};

// apply polyfill
Function.prototype.myApply = function(context, argsArray) {
  context = context || globalThis;
  const uniqueId = Symbol();
  context[uniqueId] = this;
  const result = context[uniqueId](...argsArray);
  delete context[uniqueId];
  return result;
};

// bind polyfill (simplified)
Function.prototype.myBind = function(context, ...boundArgs) {
  const fn = this;
  return function(...args) {
    return fn.apply(context, boundArgs.concat(args));
  };
};
```

### Additional Questions for Functions & Execution

**Q: What is the difference between `function` and `=>` in terms of `arguments` object?**  
A: Regular functions have an `arguments` array-like object containing passed arguments. Arrow functions do not have their own `arguments`; they inherit from the parent scope.

**Q: What is a higher-order function?**  
A: A function that takes another function as an argument or returns a function (e.g., `map`, `filter`, `reduce`).

**Q: What is memoization?**  
A: An optimization technique that caches the results of expensive function calls. Implemented using closures to store a cache object.

**Q: What is the event loop? How does it work with the call stack and task queue?**  
A: The event loop continuously checks if the call stack is empty; if so, it takes tasks from the task queue (or microtask queue) and pushes them onto the stack. Asynchronous operations (setTimeout, promises) are handled via the event loop.

---

## 3. Data Types & Coercion

### Primitive vs reference types

- **Primitive types**: `string`, `number`, `bigint`, `boolean`, `undefined`, `symbol`, `null`. Stored directly in the variable (value). Immutable. Copied by value.
- **Reference types**: `object`, `array`, `function`, `date`, etc. Stored as reference (memory address). Mutable. Copied by reference.

```javascript
let a = 10;
let b = a; // copy value
b = 20;
console.log(a); // 10

let obj1 = { x: 1 };
let obj2 = obj1; // copy reference
obj2.x = 2;
console.log(obj1.x); // 2
```

### Type coercion and equality: `==` vs `===`

- **`==` (abstract equality)**: Performs type coercion if the operands are of different types. Tries to convert them to a common type before comparison.
- **`===` (strict equality)**: Compares both value and type; no coercion.

**Coercion rules (for `==`):**
- If one operand is number and other is string, convert string to number.
- If one is boolean, convert boolean to number (true→1, false→0).
- If one is object and other is primitive, call `ToPrimitive` on object.
- `null == undefined` is `true`; `null === undefined` is `false`.
- `NaN` is not equal to anything (including `NaN`). Use `isNaN()` or `Number.isNaN()`.

**Best practice:** Always use `===` except when intentionally checking for `null` or `undefined` with `==`.

### Difference between `null` and `undefined`

- **`undefined`**: A variable that has been declared but not assigned a value; also the default return of functions without `return`. Type `undefined`.
- **`null`**: An assignment value representing "no value" or "empty". Type `object` (historical bug) but it's a primitive.

```javascript
let a; // undefined
let b = null; // null
typeof null; // "object"
typeof undefined; // "undefined"
```

### How to check if a variable is an array?

- `Array.isArray(arr)` – preferred, works across realms.
- `arr instanceof Array` – may fail if array comes from another iframe.
- `Object.prototype.toString.call(arr) === '[object Array]'` – reliable fallback.

### Additional Questions for Data Types & Coercion

**Q: What is `NaN` and how to check for it?**  
A: `NaN` (Not-a-Number) is a numeric value that represents an unrepresentable number. `typeof NaN === 'number'`. Use `isNaN(value)` (coerces) or `Number.isNaN(value)` (strict, recommended) to check.

**Q: What is the difference between `Object.is()` and `===`?**  
A: `Object.is()` is similar to `===` but handles two special cases: `Object.is(NaN, NaN)` is `true` and `Object.is(-0, +0)` is `false`. `===` does the opposite.

**Q: How does JavaScript handle implicit coercion in arithmetic?**  
A: The `+` operator prefers string concatenation if either operand is a string; other arithmetic operators (`-`, `*`, `/`) coerce to numbers. Example: `'5' + 3` → `'53'`, `'5' - 3` → `2`.

**Q: What are symbols used for?**  
A: Symbols are unique and immutable primitives used as object property keys to avoid name collisions. They are not enumerable in `for...in` loops, but can be accessed via `Object.getOwnPropertySymbols()`.

---

## 4. Objects & Prototypes

### How does prototypal inheritance work?

Every JavaScript object has an internal `[[Prototype]]` (accessible via `__proto__` or `Object.getPrototypeOf()`). When accessing a property, JavaScript first looks on the object itself; if not found, it follows the prototype chain until it reaches `null`. This is the basis of inheritance.

```javascript
const parent = { a: 1 };
const child = Object.create(parent);
child.b = 2;
console.log(child.a); // 1 (from parent)
console.log(child.b); // 2
console.log(child.toString); // from Object.prototype
```

### Prototype chain vs class inheritance

- **Prototype chain**: JavaScript's native inheritance mechanism based on linking objects. You can create objects that inherit from other objects directly (using `Object.create`).
- **Class inheritance** (ES6): Syntactic sugar over prototypal inheritance. It provides a familiar class syntax (`class`, `extends`, `super`) but still uses prototypes under the hood.

```javascript
// Prototype chain
function Animal(name) { this.name = name; }
Animal.prototype.speak = function() { console.log(`${this.name} makes noise.`); };

function Dog(name) { Animal.call(this, name); }
Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;
Dog.prototype.speak = function() { console.log(`${this.name} barks.`); };

// ES6 Classes
class Animal {
  constructor(name) { this.name = name; }
  speak() { console.log(`${this.name} makes noise.`); }
}
class Dog extends Animal {
  speak() { console.log(`${this.name} barks.`); }
}
```

### `Object.create()` and ES6 classes

- **`Object.create(proto, propertiesObject)`**: Creates a new object with the specified prototype object. Useful for simple inheritance without constructors.
- **ES6 classes**: Provide a more declarative way to define constructors and methods. They also support static methods, private fields (with `#`), and mixins.

### Shallow copy vs deep copy – how to achieve each? Modern solution: `structuredClone()`

- **Shallow copy**: Copies only the top-level properties. Nested objects are still referenced.
  - Methods: spread operator `{...obj}`, `Object.assign({}, obj)`, `Array.slice()`, `[...arr]`.
- **Deep copy**: Recursively copies all nested structures, resulting in a fully independent copy.
  - Traditional: `JSON.parse(JSON.stringify(obj))` – limited (fails with functions, undefined, symbols, circular references).
  - Modern: `structuredClone(obj)` – built-in (available in browsers and Node 17+), handles most types (including Dates, Maps, Sets, arrays, objects, but not functions, DOM elements, etc.).
  - Libraries: Lodash `_.cloneDeep()`.

```javascript
const original = { a: 1, b: { c: 2 } };
const shallow = { ...original };
shallow.b.c = 3;
console.log(original.b.c); // 3 (changed)

const deep = structuredClone(original);
deep.b.c = 4;
console.log(original.b.c); // 3 (unchanged)
```

### Additional Questions for Objects & Prototypes

**Q: How do you check if a property exists in an object?**  
A: 
- `'prop' in obj` – checks own and inherited properties.
- `obj.hasOwnProperty('prop')` – checks own properties only.
- `Object.hasOwn(obj, 'prop')` – modern alternative.

**Q: What is the difference between `Object.keys()`, `Object.values()`, `Object.entries()`?**  
A: They return arrays of own enumerable property keys, values, and key-value pairs, respectively.

**Q: What is property descriptor?**  
A: An object that describes attributes of a property: `value`, `writable`, `enumerable`, `configurable`. Can be retrieved with `Object.getOwnPropertyDescriptor(obj, prop)`.

**Q: How to create a truly immutable object?**  
A: 
- `Object.freeze(obj)` – prevents adding/removing properties and makes all existing properties non-writable (shallow).
- For deep freeze, recursively freeze.
- Using `const` only prevents reassignment, not mutation.

---

## 5. Arrays & Iteration

### Difference between `map`, `filter`, and `forEach`

| Method | Return | Purpose |
|--------|--------|---------|
| `map` | New array of same length | Transform each element |
| `filter` | New array of filtered elements | Select elements based on condition |
| `forEach` | `undefined` | Execute side effects (e.g., logging, updating external variables) |

```javascript
const arr = [1, 2, 3];
const doubled = arr.map(x => x * 2); // [2,4,6]
const evens = arr.filter(x => x % 2 === 0); // [2]
arr.forEach(x => console.log(x)); // logs 1,2,3
```

### `map` vs `forEach` – when to use which?

- Use `map` when you need to transform an array into another array of the same length.
- Use `forEach` when you just need to iterate and perform side effects (like updating UI, printing, or accumulating with external variable). `forEach` does not return a value.

### `slice` vs `splice`

| Method | Returns | Mutates original? | Purpose |
|--------|---------|------------------|---------|
| `slice(start, end)` | New array (shallow copy) | No | Extract a portion without modifying |
| `splice(start, deleteCount, ...items)` | Array of removed elements | Yes | Remove/replace/add elements at any position |

```javascript
const arr = [1, 2, 3, 4];
const sliceRes = arr.slice(1, 3); // [2,3]
console.log(arr); // [1,2,3,4]

const spliceRes = arr.splice(1, 2, 'a', 'b'); // [2,3] removed
console.log(arr); // [1,'a','b',4]
```

### `find`, `some`, `every` – use cases

- **`find(callback)`**: Returns the first element that satisfies the condition; else `undefined`. Use when you need the element itself.
- **`some(callback)`**: Returns `true` if at least one element satisfies the condition; else `false`. Use to check existence.
- **`every(callback)`**: Returns `true` if all elements satisfy the condition; else `false`. Use to validate all.

```javascript
const users = [{ id: 1, active: true }, { id: 2, active: false }];
const user = users.find(u => u.id === 2); // { id:2, active:false }
const hasActive = users.some(u => u.active); // true
const allActive = users.every(u => u.active); // false
```

### Sorting arrays with custom comparators

`sort()` without a comparator converts elements to strings and sorts lexicographically. Provide a comparator function that returns negative, zero, or positive.

```javascript
const numbers = [3, 1, 10, 2];
numbers.sort((a, b) => a - b); // ascending [1,2,3,10]
numbers.sort((a, b) => b - a); // descending

const objects = [{ name: 'John', age: 30 }, { name: 'Jane', age: 25 }];
objects.sort((a, b) => a.age - b.age); // sort by age
```

### Additional Questions for Arrays & Iteration

**Q: How do you flatten an array?**  
A: `flat()` (ES2019): `[1,[2,3]].flat()` → `[1,2,3]`. For deeper, pass depth or `Infinity`. Polyfill via `reduce` and recursion.

**Q: What is the difference between `reduce` and `reduceRight`?**  
A: Both accumulate values; `reduce` goes left-to-right, `reduceRight` goes right-to-left.

**Q: How to remove duplicates from an array?**  
A: Using `Set`: `[...new Set(array)]`. For objects, use `Map` with a unique key.

**Q: How to convert an array-like object to an array?**  
A: `Array.from(arrayLike)`, `[...arrayLike]`, or `Array.prototype.slice.call(arrayLike)`.

**Q: What are the performance implications of `map`, `filter`, `reduce` chains?**  
A: Each method creates a new array and loops through the entire array. For large arrays, consider using a single `reduce` to avoid multiple passes.

---

## 6. ES6+ Features

### Destructuring (objects and arrays)

Allows extracting values from arrays or properties from objects into distinct variables.

```javascript
// Array destructuring
const [first, second] = [1, 2];
const [a, , c] = [1, 2, 3]; // a=1, c=3
const [x, ...rest] = [1, 2, 3]; // x=1, rest=[2,3]

// Object destructuring
const { name, age } = { name: 'John', age: 30 };
const { name: personName, city = 'Unknown' } = obj; // alias and default
const { ...other } = obj; // rest properties
```

### Spread and rest operators

- **Spread (`...`)**: Expands elements (array, object) into individual items.
- **Rest (`...`)**: Collects remaining elements into an array or object.

```javascript
// Spread
const arr = [1, 2];
const newArr = [...arr, 3]; // [1,2,3]
const obj = { a: 1, b: 2 };
const newObj = { ...obj, c: 3 }; // { a:1, b:2, c:3 }

// Rest
function sum(...numbers) { return numbers.reduce((acc, n) => acc + n, 0); }
const [head, ...tail] = [1, 2, 3]; // head=1, tail=[2,3]
```

### Template literals

Strings using backticks `` ` `` that support:
- Multi-line strings
- Interpolation `${expression}`

```javascript
const name = 'Alice';
const greeting = `Hello, ${name}!
Welcome to JavaScript.`;
```

### Modules (`import`/`export`)

ES6 modules allow splitting code into separate files. Use `export` to expose functions/variables, and `import` to consume them.

```javascript
// math.js
export const add = (a, b) => a + b;
export default function multiply(a, b) { return a * b; }

// app.js
import multiply, { add } from './math.js';
```

### Optional chaining (`?.`) and nullish coalescing (`??`)

- **Optional chaining**: Safely access nested properties without worrying about `null` or `undefined`. Short-circuits to `undefined` if any part is nullish.
- **Nullish coalescing**: Returns the right-hand side only when the left is `null` or `undefined` (not for falsy values like `0` or `''`).

```javascript
const user = { profile: { name: 'John' } };
console.log(user.profile?.age); // undefined (no error)
console.log(user.address?.city); // undefined

const value = 0;
const result = value ?? 'default'; // 0 (since 0 is not null/undefined)
const result2 = value || 'default'; // 'default' (since 0 is falsy)
```

### `WeakMap` vs `Map` – real use cases

- **`Map`**: Keys can be any type; holds strong references to keys. Keys are iterable and the map can be cleared. Use for general key-value storage.
- **`WeakMap`**: Keys must be objects; holds weak references to keys, so if there's no other reference, the key can be garbage collected. Not iterable, no `size` property. Use cases:
  - Storing private data for objects without memory leaks.
  - Caching where you don't want to prevent garbage collection.
  - Storing metadata for DOM elements.

```javascript
// WeakMap example: private data
const privateData = new WeakMap();
class Person {
  constructor(name) {
    privateData.set(this, { name });
  }
  getName() {
    return privateData.get(this).name;
  }
}
```

### Symbols and iterators

- **Symbols**: Unique identifiers. Often used to define well-known symbols like `Symbol.iterator` to make objects iterable.
- **Iterators**: Objects with a `next()` method returning `{ value, done }`. Iterable objects have a `[Symbol.iterator]` method.

```javascript
// Making an object iterable
const range = {
  start: 1,
  end: 5,
  [Symbol.iterator]() {
    let current = this.start;
    const end = this.end;
    return {
      next() {
        if (current <= end) return { value: current++, done: false };
        else return { done: true };
      }
    };
  }
};
for (let num of range) console.log(num); // 1 2 3 4 5
```

### Additional Questions for ES6+ Features

**Q: What is the difference between `for...in` and `for...of`?**  
A: `for...in` iterates over enumerable property keys (including prototype chain). `for...of` iterates over iterable values (arrays, strings, maps, sets) – it's the recommended way for arrays.

**Q: What are generators?**  
A: Functions that can be paused and resumed, defined with `function*`. They return an iterator that yields values via `yield`. Useful for lazy evaluation, infinite sequences, and async flows.

**Q: What is the difference between `Promise` and `async/await`?**  
A: Promises are objects representing eventual completion; `async/await` is syntactic sugar over promises, making asynchronous code look synchronous. `await` can only be used inside `async` functions.

**Q: What are private fields in classes?**  
A: Using `#` prefix (e.g., `#privateField`). They are truly private, cannot be accessed outside the class, and are not enumerable.

**Q: What is the `Array.prototype.at()` method?**  
A: `at(index)` allows negative indexing to access elements from the end: `arr.at(-1)` returns last element, equivalent to `arr[arr.length-1]`.

---

## JavaScript Advanced & Internals

### Explain the JavaScript event loop in detail. Microtasks vs macrotasks.

The **event loop** is the mechanism that enables JavaScript’s non‑blocking, asynchronous behavior despite being single‑threaded. It continuously checks the **call stack** and **task queues**, moving tasks to the stack when it’s empty.

There are two main queues:
- **Macrotask (Callback) queue**: Contains tasks like `setTimeout`, `setInterval`, `setImmediate`, I/O events, and UI rendering.
- **Microtask queue**: Contains tasks like `Promise` callbacks (`.then`, `.catch`, `.finally`), `queueMicrotask`, and `MutationObserver`. Microtasks have higher priority.

**Process:**
1. Execute all synchronous code (call stack frames).
2. When the stack is empty, the event loop first processes **all** microtasks in the microtask queue (in FIFO order). If new microtasks are added during this phase, they are also processed before moving to macrotasks.
3. After microtasks are exhausted, one macrotask is taken from the macrotask queue and executed.
4. The browser may perform rendering (if needed) between macrotask cycles.
5. Repeat.

```javascript
console.log('1');
setTimeout(() => console.log('2'), 0);
Promise.resolve().then(() => console.log('3'));
console.log('4');
// Output: 1,4,3,2
// Explanation: synchronous 1,4; microtask (promise) 3; macrotask 2.
```

### How do JavaScript engines optimize code? (JIT, hidden classes, inline caching)

Modern engines (V8, SpiderMonkey) use **Just‑In‑Time (JIT)** compilation, combining interpretation and compilation.

- **Interpretation**: Code starts as bytecode, executed by an interpreter (Ignition in V8). This allows fast startup.
- **JIT compilation**: Hot functions (executed many times) are compiled to machine code by optimizing compilers (TurboFan in V8) for faster execution.
- **Hidden classes**: Instead of dynamic dictionary lookups, objects with the same shape (property names and order) share a hidden class, enabling fast property access via fixed offsets.
- **Inline caching**: When a property is accessed repeatedly, the engine caches the property location based on the hidden class, avoiding repeated lookup overhead.

### How does garbage collection work in V8?

V8 uses a **generational, mark‑and‑sweep** garbage collector.

- **Heap**: Divided into **young generation** (newly allocated objects) and **old generation** (objects that survive multiple collections).
- **Minor GC (Scavenger)**: Runs frequently on the young generation, copying surviving objects to a survivor space. Very fast.
- **Major GC (Mark‑Sweep / Mark‑Compact)**: Runs less often on the old generation. It marks reachable objects, sweeps unreachable ones, and compacts to reduce fragmentation.
- **Incremental marking**: Long pauses are avoided by interleaving marking with JavaScript execution.

### What is the difference between `setTimeout` and `setInterval`?

| | `setTimeout` | `setInterval` |
|---|--------------|---------------|
| **Execution** | Runs once after a delay | Runs repeatedly at a fixed interval |
| **Drift** | No cumulative delay | Can drift if execution time exceeds interval |
| **Cancellation** | `clearTimeout(id)` | `clearInterval(id)` |

**Important**: Both schedule macrotasks. If the callback takes longer than the interval, `setInterval` may queue multiple calls back‑to‑back, causing congestion. A common pattern to avoid this is recursive `setTimeout`:

```javascript
function repeat() {
  // do work
  setTimeout(repeat, delay);
}
```

### Implement a custom Promise (conceptually).

A custom Promise implementation involves managing states (`pending`, `fulfilled`, `rejected`), handling `.then` callbacks (both onFulfilled and onRejected), and supporting chaining and async resolution.

```javascript
class MyPromise {
  constructor(executor) {
    this.state = 'pending';
    this.value = undefined;
    this.handlers = []; // stores { onFulfilled, onRejected }

    const resolve = (value) => {
      if (this.state !== 'pending') return;
      this.state = 'fulfilled';
      this.value = value;
      this.handlers.forEach(h => this._runHandler(h));
    };

    const reject = (reason) => {
      if (this.state !== 'pending') return;
      this.state = 'rejected';
      this.value = reason;
      this.handlers.forEach(h => this._runHandler(h));
    };

    try {
      executor(resolve, reject);
    } catch (err) {
      reject(err);
    }
  }

  _runHandler(handler) {
    if (this.state === 'pending') {
      this.handlers.push(handler);
      return;
    }
    const cb = this.state === 'fulfilled' ? handler.onFulfilled : handler.onRejected;
    if (!cb) {
      // propagate
      const next = this.state === 'fulfilled' ? handler.resolve : handler.reject;
      next(this.value);
      return;
    }
    try {
      const result = cb(this.value);
      handler.resolve(result);
    } catch (err) {
      handler.reject(err);
    }
  }

  then(onFulfilled, onRejected) {
    return new MyPromise((resolve, reject) => {
      this._runHandler({ onFulfilled, onRejected, resolve, reject });
    });
  }

  catch(onRejected) {
    return this.then(null, onRejected);
  }

  // static methods (all, race) would be added similarly
}
```

### How does the browser rendering pipeline work? (HTML → CSS → Layout → Paint → Composite)

The browser rendering pipeline typically involves these steps (per frame):

1. **Parsing HTML** → DOM tree, CSS → CSSOM tree.
2. **Style**: Combine DOM and CSSOM into a render tree (visible nodes with computed styles).
3. **Layout (Reflow)**: Calculate geometry (position, size) for each node in the render tree.
4. **Paint**: Fill in pixels – draw text, colors, images, borders, shadows (creates layers).
5. **Composite**: Combine layers (GPU) and draw to screen.

**Optimizations**:
- Changing properties that affect layout (width, height, position) trigger **layout + paint + composite**.
- Changing paint‑only properties (color, background) trigger **paint + composite**.
- Changing transform/opacity (on a separate layer) triggers **composite only** (the fastest).

### What causes memory leaks in frontend applications? How to prevent them?

Common memory leaks:
- **Global variables**: Accidentally creating globals (`function foo() { x = 10; }`) – use `'use strict'`.
- **Forgotten timers**: `setInterval` / `setTimeout` not cleared.
- **Event listeners** not removed when elements are removed.
- **Closures** holding references to large objects.
- **Detached DOM elements**: Removing elements but still referencing them in JavaScript.
- **Out of scope references**: Variables captured in closures but no longer needed.

**Prevention**:
- Use `let`/`const` and strict mode.
- Clean up timers and listeners in lifecycle hooks (e.g., `componentWillUnmount`, `useEffect` cleanup).
- Avoid storing large data in global scope.
- Use weak references (`WeakMap`, `WeakSet`) for caching or metadata.
- Profile with Chrome DevTools (Memory tab) to identify leaks.

### Explain AbortController and request cancellation.

`AbortController` provides a standard way to cancel asynchronous operations (e.g., fetch, timers). It works via an `AbortSignal` attached to the operation.

```javascript
const controller = new AbortController();
const signal = controller.signal;

fetch('/api', { signal })
  .then(response => response.json())
  .catch(err => {
    if (err.name === 'AbortError') console.log('Fetch aborted');
  });

// Cancel after 1 second
setTimeout(() => controller.abort(), 1000);
```

**Use cases**: Cancelling fetch requests when a component unmounts, implementing debounced search, aborting expensive computations.

### Cross‑tab communication methods: BroadcastChannel, storage events, postMessage.

- **BroadcastChannel**: Simple, same‑origin communication. Create a channel and post messages; all tabs listening receive them.
  ```javascript
  const bc = new BroadcastChannel('my_channel');
  bc.postMessage('Hello');
  bc.onmessage = (e) => console.log(e.data);
  ```
- **localStorage / sessionStorage events**: When storage changes in one tab, a `storage` event fires in other tabs (except the one that made the change). Useful for cross‑tab sync.
- **postMessage** (with `window.opener` or `window.parent`): For communication between a parent window and an iframe, or between windows opened via `window.open()`.
- **SharedWorker**: A background script that can communicate with multiple tabs.

### Event delegation at scale – benefits and pitfalls.

**Event delegation** attaches a single event listener to a parent element instead of many children. The event bubbles up, and the target can be checked.

**Benefits**:
- Reduces memory usage (fewer listeners).
- Works for dynamically added elements.
- Simplifies code.

**Pitfalls**:
- Performance if the parent has many descendants; event target checks become O(n) if not optimized.
- May catch events you don’t want if not filtered properly.
- Not all events bubble (e.g., `focus`, `blur`, `load` can bubble with `useCapture`).
- Need to be careful with `stopPropagation()` – it can break delegation.

**Scalable approach**: Use a library or implement a throttled event handler; filter targets with `closest()` for specific selectors.

### Why does JavaScript have closures? (data privacy, hooks, callbacks, memoization)

Closures are a fundamental feature that allows functions to “remember” their lexical scope even when executed outside that scope.

**Use cases**:
- **Data privacy**: Encapsulate variables not exposed globally (e.g., module pattern, factory functions).
- **React Hooks**: `useState` and `useEffect` rely on closures to maintain state across renders.
- **Callbacks**: Preserve context in asynchronous operations.
- **Memoization**: Cache results of expensive functions (e.g., `useMemo`, `_.memoize`).
- **Function factories**: Create functions with pre‑configured arguments.

### `var`, `let`, `const` – interviewers want hoisting + TDZ explanation.

**Hoisting**: JavaScript moves declarations to the top of their scope during compilation.
- `var` → declaration hoisted, initialized with `undefined`.
- `let` / `const` → declaration hoisted, but not initialized. Access before initialization results in `ReferenceError` due to the **Temporal Dead Zone (TDZ)**.

**TDZ**: The period from entering a block scope until the declaration is executed. Within TDZ, the variable exists but cannot be accessed.

**Example**:
```javascript
console.log(a); // undefined (var)
var a = 1;

console.log(b); // ReferenceError (TDZ)
let b = 2;
```

---

## Asynchronous JavaScript

### Synchronous vs asynchronous programming.

- **Synchronous**: Code executes sequentially; each line waits for the previous to finish. Long operations block the thread.
- **Asynchronous**: Operations (I/O, timers) are delegated, and the program continues without waiting. When the operation completes, a callback or promise is executed via the event loop.

### Callback functions – what are they? Callback hell.

A **callback** is a function passed as an argument to another function, to be executed later. Callback hell refers to deeply nested callbacks that become hard to read and maintain:

```javascript
getUser((user) => {
  getOrders(user.id, (orders) => {
    getOrderDetails(orders[0].id, (details) => {
      // ...
    });
  });
});
```

Solutions: Promises, `async/await`.

### Promises – states (pending, fulfilled, rejected) and how they work.

A Promise represents the eventual completion (or failure) of an asynchronous operation.

- **pending**: Initial state, neither fulfilled nor rejected.
- **fulfilled**: Operation completed successfully, value available via `.then`.
- **rejected**: Operation failed, reason available via `.catch`.

Promises are **immutable** once settled. They support chaining: `.then` returns a new promise, enabling sequential composition.

### `async / await` – how they simplify promises.

`async` functions always return a promise. `await` pauses the function execution until the promise settles, then resumes with the resolved value (or throws if rejected). It allows writing asynchronous code that looks synchronous.

```javascript
async function fetchData() {
  try {
    const response = await fetch('/api');
    const data = await response.json();
    console.log(data);
  } catch (err) {
    console.error(err);
  }
}
```

### Event loop: Why does a Promise run before setTimeout? (Microtasks vs macrotasks)

Promises’ callbacks (`.then`, `.catch`) are **microtasks**, while `setTimeout` callbacks are **macrotasks**. After each macrotask (including the initial script execution), the event loop drains the entire microtask queue before taking the next macrotask. Therefore, a settled promise’s callback always runs before any scheduled `setTimeout`.

### Implement `Promise.all`, `Promise.race`, `Promise.allSettled` from scratch.

**Promise.all**:
```javascript
Promise.myAll = function(promises) {
  return new Promise((resolve, reject) => {
    if (!Array.isArray(promises)) reject(new TypeError('Not an array'));
    const results = new Array(promises.length);
    let completed = 0;
    if (promises.length === 0) resolve(results);
    promises.forEach((p, i) => {
      Promise.resolve(p).then(
        val => {
          results[i] = val;
          completed++;
          if (completed === promises.length) resolve(results);
        },
        err => reject(err)
      );
    });
  });
};
```

**Promise.race**:
```javascript
Promise.myRace = function(promises) {
  return new Promise((resolve, reject) => {
    promises.forEach(p => {
      Promise.resolve(p).then(resolve, reject);
    });
  });
};
```

**Promise.allSettled**:
```javascript
Promise.myAllSettled = function(promises) {
  return new Promise(resolve => {
    const results = [];
    let remaining = promises.length;
    if (remaining === 0) resolve(results);
    promises.forEach((p, i) => {
      Promise.resolve(p).then(
        value => results[i] = { status: 'fulfilled', value },
        reason => results[i] = { status: 'rejected', reason }
      ).finally(() => {
        remaining--;
        if (remaining === 0) resolve(results);
      });
    });
  });
};
```

### Difference between microtask queue and callback (macrotask) queue.

- **Microtask queue**: High priority; processed after each macrotask until empty. Used for promise callbacks, `queueMicrotask`, `MutationObserver`.
- **Macrotask queue**: Lower priority; one task processed per event loop iteration after microtasks are done. Used for `setTimeout`, `setInterval`, I/O, UI rendering.

### How to handle multiple independent API calls efficiently? (`Promise.all`, `allSettled`)

- Use `Promise.all` when you need all to succeed or fail fast (reject on first error).
- Use `Promise.allSettled` when you want to know the outcome of each independent call, regardless of failures (e.g., analytics, fallback data).

### What are the advantages of `Promise.allSettled` over `Promise.all`?

`Promise.allSettled` never rejects; it always resolves with an array of objects describing each promise’s outcome. This is useful when you need to wait for multiple operations and handle errors individually, without failing the whole batch.

---

## JavaScript Coding & Polyfills

### Implement `Promise.all` from scratch (already covered above).

### Implement debounce and throttle functions.

**Debounce**: Delays function execution until after a period of inactivity. Useful for search inputs, window resize.
```javascript
function debounce(fn, delay) {
  let timer;
  return function(...args) {
    clearTimeout(timer);
    timer = setTimeout(() => fn.apply(this, args), delay);
  };
}
```

**Throttle**: Ensures a function is called at most once per interval. Useful for scroll events, button clicks.
```javascript
function throttle(fn, limit) {
  let inThrottle;
  return function(...args) {
    if (!inThrottle) {
      fn.apply(this, args);
      inThrottle = true;
      setTimeout(() => (inThrottle = false), limit);
    }
  };
}
```

### Implement a deep clone function (deep copy).

**Using `structuredClone` (modern)**:
```javascript
const clone = structuredClone(original);
```

**Manual implementation** (handles objects, arrays, dates, maps, sets, and cyclic references):
```javascript
function deepClone(obj, map = new WeakMap()) {
  if (obj === null || typeof obj !== 'object') return obj;
  if (map.has(obj)) return map.get(obj);
  let clone;
  if (obj instanceof Date) clone = new Date(obj);
  else if (obj instanceof Map) {
    clone = new Map();
    map.set(obj, clone);
    obj.forEach((val, key) => clone.set(deepClone(key, map), deepClone(val, map)));
    return clone;
  } else if (obj instanceof Set) {
    clone = new Set();
    map.set(obj, clone);
    obj.forEach(val => clone.add(deepClone(val, map)));
    return clone;
  } else if (obj instanceof Array) {
    clone = [];
    map.set(obj, clone);
    obj.forEach((item, i) => clone[i] = deepClone(item, map));
  } else {
    clone = {};
    map.set(obj, clone);
    for (let key in obj) {
      if (obj.hasOwnProperty(key)) clone[key] = deepClone(obj[key], map);
    }
  }
  return clone;
}
```

### Write a polyfill for `call`, `apply`, and `bind`.

**`call` polyfill** (already provided earlier, but here is a clean version):
```javascript
Function.prototype.myCall = function(context, ...args) {
  context = context ?? globalThis;
  const fnSymbol = Symbol();
  context[fnSymbol] = this;
  const result = context[fnSymbol](...args);
  delete context[fnSymbol];
  return result;
};
```

**`apply` polyfill**:
```javascript
Function.prototype.myApply = function(context, argsArray) {
  context = context ?? globalThis;
  const fnSymbol = Symbol();
  context[fnSymbol] = this;
  const result = context[fnSymbol](...argsArray);
  delete context[fnSymbol];
  return result;
};
```

**`bind` polyfill**:
```javascript
Function.prototype.myBind = function(context, ...boundArgs) {
  const fn = this;
  return function(...args) {
    return fn.apply(context, boundArgs.concat(args));
  };
};
```

### Implement `map`, `reduce`, `filter` from scratch.

**`map`**:
```javascript
Array.prototype.myMap = function(callback, thisArg) {
  const result = [];
  for (let i = 0; i < this.length; i++) {
    if (i in this) { // skip empty slots (sparse arrays)
      result.push(callback.call(thisArg, this[i], i, this));
    }
  }
  return result;
};
```

**`filter`**:
```javascript
Array.prototype.myFilter = function(callback, thisArg) {
  const result = [];
  for (let i = 0; i < this.length; i++) {
    if (i in this && callback.call(thisArg, this[i], i, this)) {
      result.push(this[i]);
    }
  }
  return result;
};
```

**`reduce`**:
```javascript
Array.prototype.myReduce = function(callback, initialValue) {
  let accumulator = initialValue;
  let startIndex = 0;
  if (arguments.length < 2) {
    if (this.length === 0) throw new TypeError('Reduce of empty array with no initial value');
    accumulator = this[0];
    startIndex = 1;
  }
  for (let i = startIndex; i < this.length; i++) {
    if (i in this) {
      accumulator = callback(accumulator, this[i], i, this);
    }
  }
  return accumulator;
};
```

### Flatten a nested array without using `Array.flat()`.

**Input**: `[1,2,3,[4,5,6,[7,8,[10,11]]],9]`  
**Output**: `[1,2,3,4,5,6,7,8,10,11,9]`

**Solution** (recursive):
```javascript
function flattenArray(arr) {
  let result = [];
  for (let item of arr) {
    if (Array.isArray(item)) {
      result.push(...flattenArray(item));
    } else {
      result.push(item);
    }
  }
  return result;
}
```

**Iterative with stack**:
```javascript
function flattenArrayIterative(arr) {
  const stack = [...arr];
  const result = [];
  while (stack.length) {
    const next = stack.pop();
    if (Array.isArray(next)) {
      stack.push(...next);
    } else {
      result.push(next);
    }
  }
  return result.reverse(); // because we popped from end
}
```

### Find the first repeating character in a string (e.g., "success" → "c").

```javascript
function firstRepeating(str) {
  const seen = new Set();
  for (let char of str) {
    if (seen.has(char)) return char;
    seen.add(char);
  }
  return null;
}
```

### Find the first non-repeating character in a string.

```javascript
function firstNonRepeating(str) {
  const count = new Map();
  for (let char of str) {
    count.set(char, (count.get(char) || 0) + 1);
  }
  for (let char of str) {
    if (count.get(char) === 1) return char;
  }
  return null;
}
```

### Currying for infinite sum: `sum(10)(20)(30)() → 60`, `sum(10)(20)(30)(40)(50)(60)() → 210`.

```javascript
function sum(x) {
  let total = x;
  function inner(y) {
    if (y === undefined) return total;
    total += y;
    return inner;
  }
  return inner;
}
// Usage: sum(10)(20)(30)() → 60
```

### Find sum of numbers without using a for loop (using reduce or recursion).

**Using reduce**:
```javascript
const arr = [1,2,3,4];
const sum = arr.reduce((acc, val) => acc + val, 0);
```

**Using recursion**:
```javascript
function sumRecursive(arr, index = 0) {
  if (index === arr.length) return 0;
  return arr[index] + sumRecursive(arr, index + 1);
}
```

### Given an array of users, find all active user ids.

**Array**: `users = [{ id: 1, active: true }, { id: 2, active: false }]`  
Also with `null`, `{}`, etc.

```javascript
function getActiveIds(users) {
  return users
    .filter(user => user && typeof user === 'object' && user.active === true)
    .map(user => user.id);
}
```

### Solve a problem using only `map()` and `filter()` (no loops). Explain edge cases.

**Example**: Given an array of numbers, get the squares of even numbers.  
```javascript
const numbers = [1,2,3,4,5];
const result = numbers
  .filter(n => n % 2 === 0)
  .map(n => n * n);
// result: [4,16]
```
**Edge cases**: Empty array → returns empty array. Sparse arrays: `filter` and `map` skip empty slots. Non‑numeric values should be handled by the predicate (e.g., `typeof n === 'number'`). Ensure `map` is called after `filter` to avoid unnecessary processing.

### Implement a custom hook like `useDebounce` or `useFetch` (React).

**`useDebounce`**:
```javascript
import { useState, useEffect } from 'react';

function useDebounce(value, delay) {
  const [debouncedValue, setDebouncedValue] = useState(value);
  useEffect(() => {
    const handler = setTimeout(() => setDebouncedValue(value), delay);
    return () => clearTimeout(handler);
  }, [value, delay]);
  return debouncedValue;
}
```

**`useFetch`**:
```javascript
function useFetch(url, options = {}) {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    const abortController = new AbortController();
    const signal = abortController.signal;

    fetch(url, { ...options, signal })
      .then(res => {
        if (!res.ok) throw new Error('Network response was not ok');
        return res.json();
      })
      .then(data => {
        setData(data);
        setLoading(false);
      })
      .catch(err => {
        if (err.name !== 'AbortError') {
          setError(err);
          setLoading(false);
        }
      });

    return () => abortController.abort();
  }, [url]);

  return { data, loading, error };
}
```

---

## React Core

### What is React JS?

React is a JavaScript library for building user interfaces, developed by Facebook. It allows developers to create reusable UI components and manage the view layer of applications using a declarative paradigm. React uses a virtual DOM to optimize rendering and improve performance.

### Why React.js? What problems does it solve?

React solves several frontend challenges:
- **Declarative UI**: Instead of imperatively manipulating the DOM, you describe what the UI should look like for a given state. React handles updates efficiently.
- **Component‑based architecture**: Encourages reusability, maintainability, and separation of concerns.
- **Efficient updates**: Virtual DOM diffing minimizes costly DOM manipulations.
- **Unidirectional data flow**: Makes data flow predictable and easier to debug.
- **Ecosystem and community**: Rich tooling, libraries (React Router, Redux), and strong community support.

### What is JSX and how is it rendered in the browser?

JSX is a syntax extension for JavaScript that looks like HTML but gets transformed into regular JavaScript function calls (`React.createElement`). The browser cannot interpret JSX directly; it is transpiled by tools like Babel into `React.createElement` calls, which produce plain JavaScript objects representing the virtual DOM. These objects are then rendered to the actual DOM by React.

Example:
```jsx
const element = <h1>Hello, world!</h1>;
// Transpiles to:
const element = React.createElement('h1', null, 'Hello, world!');
```

### What are components? Functional vs class components.

Components are the building blocks of a React application. They accept inputs (props) and return React elements describing what should appear on screen.

- **Functional components**: Plain JavaScript functions that accept props and return JSX. They are simpler, support hooks, and are the preferred way to write components today.
- **Class components**: ES6 classes that extend `React.Component` and must implement a `render` method. They have lifecycle methods (`componentDidMount`, etc.) and state management via `this.state` and `this.setState`.

### What are state and props? Difference between them.

- **Props** (short for properties): Read‑only data passed from parent to child. They are immutable within the child component.
- **State**: Mutable data managed within a component. When state changes, the component re‑renders.

| | Props | State |
|---|-------|-------|
| Mutability | Immutable (cannot be changed by child) | Mutable (changed via `setState` or hook setters) |
| Ownership | Owned by parent, used by child | Owned by the component itself |
| Purpose | Configure component, pass data down | Handle dynamic data that changes over time |

### What is a hook? Why were hooks introduced?

Hooks are functions that let you “hook into” React state and lifecycle features from functional components. They were introduced in React 16.8 to allow using state, side effects, and other React features without writing classes.

Reasons for hooks:
- Reuse stateful logic across components without complex patterns like HOCs or render props.
- Simplify component logic by grouping related code (e.g., `useEffect` for side effects).
- Avoid the complexity of `this` binding and class lifecycle methods.
- Improve tree‑shaking and reduce bundle size.

### If we have `var`, `let`, `const`, why do we need state variables?

Regular JavaScript variables do not trigger re‑renders when they change. State variables (`useState`) are designed to:
- Preserve values across renders.
- Trigger a re‑render when updated (via the setter function).
- Work within React’s reconciliation cycle. Without them, changes to variables would not be reflected in the UI.

### What is re‑rendering, and why does it happen?

Re‑rendering is the process where React updates the UI to reflect the current state and props. It happens when:
- A component’s state changes.
- Its props change.
- Its parent re‑renders (by default).
- A context value it uses changes.
- A custom hook triggers an update.

React batches updates for performance; re‑rendering does not necessarily mean the DOM is updated – React computes the difference (reconciliation) and only updates the DOM where needed.

### What is reconciliation in React? How does the diffing algorithm work?

Reconciliation is React’s algorithm for determining which parts of the DOM need to be updated when state or props change. It uses a **virtual DOM** (a lightweight representation) and compares it with the previous version.

**Diffing algorithm (simplified)**:
- **Elements of different types**: The whole subtree is torn down and rebuilt.
- **Elements of the same type**: React keeps the same DOM node and only updates changed attributes (e.g., `className`). Then it recursively diffs children.
- **List children with keys**: Keys help identify which items have changed, been added, or removed. Without stable keys, the algorithm may re‑render more than necessary.

### Why are keys important in lists? What happens if keys are unstable?

Keys give each element a stable identity, allowing React to match items between re‑renders. Without keys, React might reuse DOM nodes incorrectly, leading to performance issues or broken UI (e.g., lost focus, incorrect state). If keys are unstable (e.g., using index when the list can reorder), React may re‑create elements unnecessarily or mix up internal state.

### What is the difference between `Router` and `Link` in React Router?

- **`Router`** (e.g., `BrowserRouter`): Provides the routing context and handles history management. It is the parent component that enables navigation and URL sync.
- **`Link`**: A component that renders an anchor (`<a>`) with the `to` prop. It allows navigation without a full page reload, using client‑side routing.

### What is routing in React? How does it work?

Routing in React is the process of mapping URL paths to different components, enabling a single‑page application (SPA) to simulate multiple pages. React Router (or other libraries) listens to URL changes, matches the path against defined routes, and renders the corresponding component without a full browser refresh. It leverages the browser’s History API (`pushState`, `replaceState`) to manage navigation and updates the UI accordingly.

### Controlled vs uncontrolled components – explain with examples.

- **Controlled component**: Form input whose value is controlled by React state. The input’s value is set via `value` prop and updates via `onChange`. React is the single source of truth.
  ```jsx
  const [value, setValue] = useState('');
  <input value={value} onChange={e => setValue(e.target.value)} />
  ```
- **Uncontrolled component**: The DOM itself manages the input state. You access the current value via a ref (`useRef`).
  ```jsx
  const inputRef = useRef();
  <input ref={inputRef} />
  // later: inputRef.current.value
  ```

### What is prop drilling? Problems and solutions.

Prop drilling is passing data through multiple layers of components via props, even when intermediate components don’t need that data. This makes code harder to maintain and refactor.

**Solutions**:
- **Context API**: Create a context and provide values at a higher level, then consume them deep down.
- **State management libraries**: Redux, Zustand, etc.
- **Component composition**: Instead of passing props, pass components as children or use render props to flatten the hierarchy.

### How do you pass parent data to a deeply nested child (e.g., 5th child)?

Using **Context** is the most common approach. Create a context, wrap the parent tree with a `Provider`, and consume the context in the deeply nested child via `useContext` or `Context.Consumer`. Alternatively, use a state management library like Redux that provides global state.

### Difference between `useMemo` and `React.memo`.

- **`useMemo`**: A hook that memoizes the result of a computation. It recalculates only when its dependencies change. Used to optimize expensive calculations inside a component.
- **`React.memo`**: A higher‑order component that memoizes a component. It prevents re‑rendering if the props have not changed (shallow comparison). It wraps the whole component, not a value.

### Difference between `useMemo` and `useCallback`.

- **`useMemo`**: Returns a memoized **value**. It caches the result of a function call.
- **`useCallback`**: Returns a memoized **function** (the function reference is stable). It is essentially `useMemo(() => fn, deps)`.

Use `useCallback` when passing callbacks to child components that rely on reference equality to avoid unnecessary re‑renders.

### What happens if a component wrapped in `memo()` has its own state changes?

The component will still re‑render when its internal state changes, regardless of `memo`. `React.memo` only controls re‑renders triggered by parent prop changes. State updates always cause a re‑render of the component (unless you use other optimizations like `useState` with a functional update that doesn’t change the value).

### What happens if a child uses `memo()` and parent props don't change?

If the child is wrapped with `React.memo` and its props (by shallow comparison) have not changed, the child will **not** re‑render even if the parent re‑renders. This can prevent unnecessary renders.

### What is state batching? What changed in React 18 regarding batching?

State batching is the process of grouping multiple state updates into a single re‑render to improve performance. In React 17 and earlier, batching only happened inside React event handlers (e.g., `onClick`). Updates inside promises, `setTimeout`, or native events were not batched.

**React 18** introduced **automatic batching** for all updates, regardless of where they originate (promises, timeouts, etc.), using `createRoot`. This reduces unnecessary re‑renders.

### Explain `useEffect` deeply: cleanup function, dependency array pitfalls.

`useEffect` lets you perform side effects (data fetching, subscriptions, DOM manipulations) in functional components. It runs after the browser paints.

- **Dependency array**: If omitted, effect runs after every render. If empty (`[]`), runs only once (mount). If values are provided, effect runs when any of those values change.
- **Cleanup function**: Return a function from `useEffect` – it runs before the component unmounts and before the next effect execution (to clean up previous subscriptions). Useful for canceling requests, clearing timers, removing event listeners.

**Pitfalls**:
- Missing dependencies can lead to stale data or infinite loops.
- Including unnecessary dependencies may cause excessive re‑runs.
- Using objects or arrays as dependencies without memoization can cause unwanted re‑runs because reference changes every render.

### Difference between `useEffect`, `useLayoutEffect`, and `useInsertionEffect`.

- **`useEffect`**: Runs asynchronously after the browser paints. Suitable for most side effects.
- **`useLayoutEffect`**: Runs synchronously after all DOM mutations but before the browser paints. Useful for measuring layout or making visual updates that should appear before paint (e.g., scrolling to an element). Use sparingly as it blocks painting.
- **`useInsertionEffect`**: A newer hook (React 18) intended for CSS‑in‑JS libraries to inject styles before layout effects fire. Not meant for general use.

### What problems does `useMemo` actually solve? When should you NOT use it?

`useMemo` solves unnecessary recomputation of expensive calculations on every render. It also helps maintain referential equality for objects/arrays that are dependencies of other hooks (like `useEffect`).

**When NOT to use it**:
- For trivial calculations (e.g., `a + b`); the overhead of memoization may exceed the cost.
- Over‑using `useMemo` can make code less readable and lead to bugs if dependencies are mishandled.
- It does not guarantee that the value won’t be recomputed if React decides to re‑mount the component (e.g., during memory pressure).

### When would you use `React.memo`?

Use `React.memo` for:
- Components that receive the same props often but re‑render due to parent re‑renders.
- Large components that are expensive to re‑render.
- Pure functional components that depend on props only.

Avoid over‑using `memo` because the shallow prop comparison itself costs time. Use it where profiling shows a benefit.

### Build a custom hook like `useDebounce` or `useFetch`.

**`useDebounce`** (example):
```javascript
import { useState, useEffect } from 'react';

function useDebounce(value, delay) {
  const [debouncedValue, setDebouncedValue] = useState(value);
  useEffect(() => {
    const handler = setTimeout(() => setDebouncedValue(value), delay);
    return () => clearTimeout(handler);
  }, [value, delay]);
  return debouncedValue;
}
```

**`useFetch`** (example):
```javascript
function useFetch(url, options = {}) {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    const abortController = new AbortController();
    const fetchData = async () => {
      try {
        const res = await fetch(url, { ...options, signal: abortController.signal });
        if (!res.ok) throw new Error('Network error');
        const json = await res.json();
        setData(json);
        setLoading(false);
      } catch (err) {
        if (err.name !== 'AbortError') {
          setError(err);
          setLoading(false);
        }
      }
    };
    fetchData();
    return () => abortController.abort();
  }, [url, ...Object.values(options)]); // caution: options can cause infinite loops
  return { data, loading, error };
}
```

---

## React Advanced & Internals

### How does React Fiber architecture change rendering?

React Fiber (introduced in React 16) is a complete rewrite of the reconciliation engine. It enables **incremental rendering**, splitting work into chunks and prioritizing updates (e.g., user input over data fetching). Fiber makes React capable of:
- Pausing, aborting, or reusing work.
- Assigning priorities to different types of updates.
- Supporting concurrent rendering and Suspense.

### What is concurrent rendering? When does it help vs hurt?

Concurrent rendering allows React to work on multiple tasks simultaneously, interrupting low‑priority work to handle high‑priority updates (like typing). It helps keep the UI responsive.

**When it helps**: During heavy computations, data fetching, or large list updates – the app stays interactive.
**When it may hurt**: Not all apps need it; it adds complexity and can cause subtle bugs if components assume synchronous rendering.

### Explain React Server Components vs Client Components.

- **Server Components**: Run on the server and send a special JSON-like format to the client. They never re‑render on the client and can access server resources (databases, file system) directly. They reduce bundle size and improve performance.
- **Client Components**: Run in the browser and can have interactivity, state, and effects. They are the traditional React components.

In the new React architecture, components are “use client” or “use server” directives. Server Components can import Client Components, but not vice versa.

### What is hydration? How do hydration mismatches occur?

Hydration is the process where React attaches event listeners and reconciles the server‑rendered HTML with the client‑side virtual DOM. It allows interactive components to “take over” the static markup.

**Hydration mismatches** occur when the HTML generated on the server differs from the initial render on the client (e.g., due to different data, random values, or browser‑only APIs). React will then attempt to patch the mismatch, which can cause performance issues and break user experience.

### How does React Context work? When can it hurt performance?

Context provides a way to pass data through the component tree without prop drilling. It works by creating a `Provider` component that holds a value. Any component that consumes the context via `useContext` will re‑render when the context value changes.

**Performance pitfalls**:
- If the context value changes frequently, many consumers may re‑render.
- When a component consumes context, it cannot be memoized based on props alone; it will re‑render whenever the context value changes, even if the component’s own props didn’t change.
- Using context for global state that changes often (e.g., animations) can cause excessive re‑renders.

### Scenario: Context API causes frequent re‑renders – why and how to fix?

**Why**: The context value is an object that gets re‑created on every render of the provider, causing all consumers to re‑render. Even if the actual data hasn’t changed, the reference changed.

**Fixes**:
- Memoize the context value with `useMemo` to keep the same object unless dependencies change.
- Split contexts into smaller, focused contexts so consumers only subscribe to what they need.
- Use state management libraries (like Redux) that allow selective subscriptions.
- Use `useContextSelector` or similar pattern if available.

### What is code splitting? How does `React.lazy` work internally?

Code splitting is the practice of breaking the bundle into smaller chunks that are loaded on demand, improving initial load time. `React.lazy` allows you to dynamically import a component as a separate chunk.

Internally, `React.lazy` takes a function that calls `import()` and returns a Promise. React suspends rendering until the promise resolves, showing a fallback (via `<Suspense>`). The lazy‑loaded component is then rendered.

### How does tree shaking work in modern bundlers?

Tree shaking is a dead‑code elimination technique that removes unused exports from the final bundle. Bundlers like Webpack and Rollup analyze the import/export graph and only include code that is actually used. This relies on ES modules being statically analyzable.

### What is the purpose of Suspense beyond lazy loading?

Suspense is a generic mechanism for orchestrating asynchronous dependencies in React. Besides lazy loading components, it can be used for data fetching (with libraries like Relay, Next.js) or any asynchronous operation that integrates with Suspense. It lets components “wait” for something before rendering, with a fallback UI.

### Explain the concept of "controlled re‑render boundaries".

A controlled re‑render boundary is a technique to isolate parts of the UI that re‑render frequently from those that don’t. This can be achieved by:
- Using `React.memo` on child components.
- Moving state down to the components that need it.
- Lifting state up only as necessary.
- Using `useMemo` and `useCallback` to stabilize props.
- Structuring context to avoid unnecessary consumers.

### How would you build a custom hook library?

A custom hook library is a collection of reusable hooks. Steps:
1. Design hooks with clear APIs, handling edge cases.
2. Write them as pure functions that follow the Rules of Hooks.
3. Document with examples and TypeScript types.
4. Publish to npm or a private registry.
5. Include tests (React Testing Library) and ensure they work across versions.

### What are the hidden reasons a component re‑renders even when props don't change?

- **Parent re‑render**: By default, when a parent re‑renders, all its children re‑render, regardless of prop changes. (Fixed with `React.memo`)
- **Inline functions/objects**: If you pass an inline function or object as prop, the child sees a new reference on every render, causing a re‑render (unless the child is memoized and uses deep comparison or the prop is memoized).
- **Context changes**: If the component consumes a context that changes, it re‑renders.
- **Hooks with changing dependencies**: `useEffect`, `useMemo`, `useCallback` dependencies may cause re‑execution of hooks, but not necessarily the whole component re‑render.
- **State updates that set the same value**: In React 18, if you set state to the same value (using `setState(prev => prev)`), it may still cause a re‑render in some cases (but not in strict mode?).

### How does React 18's automatic batching work?

Automatic batching in React 18 groups multiple state updates from any source (not just event handlers) into a single re‑render. This is enabled by default when using `createRoot`. It reduces unnecessary renders and improves performance. You can opt out using `flushSync`.

### How do you handle real-time updates efficiently in React?

- Use WebSockets or Server‑Sent Events (SSE) for pushing updates.
- Manage connections with custom hooks that handle lifecycle (connect on mount, disconnect on unmount).
- Use `useRef` to store the connection object.
- Throttle or debounce UI updates if they are frequent.
- Use `useReducer` or state management to batch updates.
- Leverage `React.memo` and careful component structure to avoid re‑rendering large parts of the UI.
- Use virtualization for large lists.

---

## Redux & State Management

### What is Redux and why is it used?

Redux is a predictable state container for JavaScript applications. It centralizes application state in a single store, enforces immutability, and provides a unidirectional data flow (action → reducer → new state). It’s used to manage complex state that is shared across many components, especially in large applications.

### What problems does Redux solve in large React applications?

- **State sharing**: Avoids prop drilling for deeply nested components.
- **Predictability**: State changes happen via pure reducers, making it easier to debug with time‑travel.
- **Separation of concerns**: UI logic is decoupled from state management.
- **Middleware**: Enables handling side effects (async actions, logging) in a structured way.
- **DevTools**: Excellent debugging capabilities.

### Explain the Redux data flow (action → reducer → store → view).

1. **Action**: A plain object with a `type` field describing what happened (e.g., `{ type: 'INCREMENT' }`). Dispatched from the UI.
2. **Reducer**: A pure function that takes the current state and an action, and returns a new state (immutable update). Reducers combine to form the root reducer.
3. **Store**: Holds the state tree. Provides `dispatch`, `getState`, and `subscribe`.
4. **View**: React components subscribe to the store and re‑render when the state changes.

### What is Redux Toolkit and why is it recommended over plain Redux?

Redux Toolkit (RTK) is the official, opinionated toolset for Redux. It simplifies common patterns, reduces boilerplate, and includes best practices out of the box:

- **`configureStore`**: Sets up the store with good defaults (middleware, devtools).
- **`createSlice`**: Automatically generates action creators and reducers.
- **`createAsyncThunk`**: Handles asynchronous actions with loading states.
- **Immer integration**: Allows writing mutable‑looking code in reducers (actual immutability is handled).
- **Redux DevTools** automatically enabled.

### Explain the flow of Redux Toolkit.

1. **Define slices** using `createSlice`. Each slice contains `name`, `initialState`, and `reducers` (functions that handle actions). Reducers can be simple or use `prepare` callbacks.
2. **Combine slices** (if needed) and configure the store with `configureStore`.
3. **Dispatch actions** using the generated action creators (e.g., `increment()`).
4. **Use hooks** (`useSelector`, `useDispatch`) in React components to read state and dispatch actions.
5. **Async logic**: Use `createAsyncThunk` to define thunks that handle async requests and dispatch pending/fulfilled/rejected actions.

### How does Redux Toolkit work internally?

- `createSlice` uses `createReducer` and `createAction` under the hood to generate reducers and action creators. It leverages Immer to allow immutable updates with mutable syntax.
- `configureStore` calls Redux’s `createStore`, applies default middleware (including `redux-thunk`), and enables the Redux DevTools Extension.
- `createAsyncThunk` returns a thunk that dispatches the lifecycle actions automatically and allows handling of the async operation.

### What is `createSlice()` and what does it contain? (name, initialState, reducers)

`createSlice` accepts an object with:
- `name`: A string used as prefix for action types.
- `initialState`: The initial state value.
- `reducers`: An object mapping action names to reducer functions (or `prepare` callbacks). Each reducer function receives `state` and `action` and can mutate the state (thanks to Immer).
- `extraReducers` (optional): Allows responding to actions not defined in the slice (e.g., from `createAsyncThunk`).

It returns an object with `actions` (action creators) and `reducer` (slice reducer).

### Explain reducers and extraReducers – when to use each?

- **`reducers`**: Used for actions that are directly handled by this slice. RTK automatically generates action creators with the same names. Good for synchronous, slice‑specific updates.
- **`extraReducers`**: Used to respond to actions defined elsewhere (e.g., thunks, actions from other slices). It’s often used with `builder` callback to handle `pending`, `fulfilled`, `rejected` of async thunks. It allows a slice to react to actions that are not its own.

### What is `createAsyncThunk()` and why is it used?

`createAsyncThunk` is a function that creates a thunk action that handles asynchronous requests. It takes an action type prefix and a payload creator (async function). It automatically dispatches `pending`, `fulfilled`, and `rejected` actions based on the promise. This reduces boilerplate for loading states and error handling.

### How does async flow work in Redux Toolkit?

1. Define a thunk using `createAsyncThunk`.
2. Inside the payload creator, perform async work (e.g., fetch).
3. Dispatch the thunk from a component.
4. The thunk dispatches the `pending` action immediately.
5. When the async work completes, it dispatches `fulfilled` with the result, or `rejected` with an error.
6. In slices, use `extraReducers` to listen to these actions and update state (e.g., set loading false, store data).

### Where and why have you used Redux Toolkit in your projects?

Common scenarios:
- **Large‑scale apps with complex shared state**: Shopping carts, user authentication, multi‑step forms.
- **Real‑time dashboards**: To manage data from WebSockets across many components.
- **Apps with complex async flows**: To maintain loading/error states in a consistent manner.
- **When multiple features need access to the same data**: E.g., user profile, preferences, notifications.

### Redux vs Context API vs Zustand – how do you decide in a large-scale application?

| | Redux | Context API | Zustand |
|---|-------|-------------|---------|
| **Use case** | Large apps, complex state, frequent updates | Simple state, medium nesting, low update frequency | Small‑medium apps, simple API, minimal boilerplate |
| **Performance** | Optimized with selectors, middleware | Can cause re‑renders; requires careful splitting | Very performant, minimal re‑renders |
| **Boilerplate** | Higher (but RTK reduces it) | Low | Very low |
| **Tooling** | Excellent (DevTools) | Basic | Good |
| **Learning curve** | Steeper | Easy | Easy |

**Decision**: For large‑scale apps with many features, complex async logic, and need for time‑travel debugging, Redux (with RTK) is a solid choice. If you need a lighter alternative with good performance and less boilerplate, Zustand is popular. Context is best for static or low‑frequency updates (e.g., theme, localization) and not recommended for high‑frequency state.

### Compare Redux, MobX, and Recoil for enterprise-scale state management (pros and cons).

| | Redux | MobX | Recoil |
|---|-------|------|--------|
| **Paradigm** | Functional, immutable | Observable, mutable | Atomic, graph‑based |
| **Boilerplate** | High (reducers, actions) | Low (decorators, observables) | Moderate (atoms, selectors) |
| **Learning curve** | Steep | Moderate | Moderate |
| **Performance** | Good with selectors | Excellent (fine‑grained) | Good with derived state |
| **Tooling** | Excellent DevTools | Good | Good (early) |
| **Scalability** | Proven in huge apps | Good, but mutable may cause unpredictability | Newer, but promising |

- **Redux** is battle‑tested, great for large teams due to strict patterns, but requires discipline.
- **MobX** allows more flexibility and less code, but mutable updates can be error‑prone in large teams.
- **Recoil** offers a more React‑centric approach with derived state and concurrent rendering support, but is newer.

### How would you design a state management solution for a complex analytics/dashboard app?

For a dashboard app with:
- Real‑time data (WebSockets)
- Multiple widgets that can be individually refreshed
- Filters that affect many widgets
- Large datasets (need virtualization)

Approach:
1. Use Redux Toolkit for global state (filters, user settings, notifications).
2. Use `createEntityAdapter` for normalized data (e.g., metrics, widgets).
3. Use `createAsyncThunk` for API calls with cancellation support (AbortController).
4. For real‑time updates, use a custom middleware to listen to WebSocket messages and dispatch actions.
5. Use `useSelector` with memoized selectors (Reselect) to avoid re‑renders.
6. For widget‑specific state (e.g., expanded/collapsed), keep it locally in the widget component to avoid global re‑renders.
7. Leverage React.memo for widget components that receive stable props.
8. Use Suspense and lazy loading for heavy dashboard sections.

This combines the predictability of Redux with localized state for performance.


## Design Problems

### Design an autocomplete search with debouncing, caching, and race condition handling.

**Requirements**:
- As user types, fetch suggestions from an API.
- Debounce input to avoid excessive requests.
- Cache results to avoid repeated network calls.
- Handle race conditions: ensure that responses arrive in the correct order.

**Design**:
- **Debouncing**: Use a `setTimeout` that delays the API call until after a pause (e.g., 300ms). Clear previous timer on new input.
- **Caching**: Use a `Map` with the search query as key and the fetched results as value. Check cache before making a request.
- **Race condition handling**: Store the latest request’s identifier (e.g., timestamp or request ID). When a response arrives, compare its ID with the stored latest; if it doesn’t match, ignore it.
- **Implementation**: Use `useState` for input value, `useRef` for cache, debounce timer, and current request ID. Consider using `AbortController` to cancel previous in‑flight requests.

### Design an infinite scrolling feed (virtualization, pagination, loading states).

**Requirements**:
- Load more items as user scrolls near the bottom.
- Use pagination (cursor or offset).
- Virtualization to render only visible items.
- Manage loading and error states.

**Design**:
- **Pagination**: Use offset‑based (page, limit) or cursor‑based (next token). Store a list of items.
- **Scroll detection**: Attach scroll listener to the container; check if scroll position is near bottom (e.g., `scrollHeight - scrollTop <= clientHeight + threshold`). Use throttling for performance.
- **Loading state**: Show a loading spinner when fetching. Prevent duplicate requests.
- **Virtualization**: Use a library like `react-window` or `react-virtualized` to render only the items in viewport. This is crucial for large lists to maintain performance.
- **Error handling**: Display error message and optionally retry button.
- **Edge cases**: When no more items, hide loading indicator; handle empty state.

### Design a real-time dashboard with multiple data sources.

**Requirements**:
- Display widgets with live updates from WebSocket, SSE, or polling.
- Handle multiple data sources simultaneously.
- Ensure performance and scalability.

**Design**:
- **Data fetching strategy**: Use WebSockets for low‑latency updates; for less critical data, use Server‑Sent Events or long polling.
- **State management**: Centralize dashboard state (e.g., Redux) with slices for each widget. Use `createAsyncThunk` for initial data load and WebSocket middleware to dispatch updates.
- **Subscription management**: Use a custom hook that subscribes to the data source on component mount and cleans up on unmount. For multiple sources, use a central manager or a pub/sub pattern.
- **Caching & reconciliation**: Cache incoming data to avoid flickering; merge updates with existing state.
- **Performance**: Use memoized selectors, `React.memo` for widgets, and virtualize if needed. Throttle high‑frequency updates.
- **Error resilience**: Reconnection logic with exponential backoff; display error states per widget.

### Design an e-commerce frontend with filters (price, category, rating) and scalable state updates.

**Requirements**:
- Multiple filter facets that update the product list.
- Efficient state updates without causing excessive re‑renders.
- Pagination or infinite scroll.

**Design**:
- **State**: Use a global store (Redux or Zustand) for filters and product list. Filters: price range, category (multi‑select), rating, etc.
- **Filter logic**: Combine filters into a query object; on filter change, update the query and fetch new products. Debounce price slider input.
- **Caching**: Cache product pages based on filter query to avoid redundant requests.
- **UI performance**: Use `React.memo` for product cards; use `useSelector` with memoized selectors (Reselect) to derive filtered products only when relevant filters change.
- **Pagination**: Implement either offset‑based pagination or cursor‑based; load more on scroll or via “Load More” button.
- **URL synchronization**: Keep filters in URL query parameters for shareability and persistence on refresh.

### Design a notification/toast system with queueing, auto-dismiss, and priority handling.

**Requirements**:
- Display toast notifications with auto‑dismiss.
- Queue multiple notifications if many appear at once.
- Support priorities (e.g., error stays longer or requires manual close).
- Configurable position, animations.

**Design**:
- **Global store**: Maintain an array of notifications, each with id, message, type, priority, autoDismissTimeout, etc.
- **Queue management**: When a new notification is added, if the limit is reached (e.g., max 3 visible), add to a queue. When a notification is removed, show the next from queue.
- **Auto‑dismiss**: Use `setTimeout` per notification; clear timeout on manual close or when notification is removed.
- **Priority handling**: Sort or prioritize showing high‑priority notifications (e.g., errors) over lower ones; maybe replace a low‑priority notification if a high‑priority arrives.
- **UI**: Use a portal to render toasts in a fixed container. Animate in/out.
- **API**: Provide `notify.success()`, `notify.error()` etc., with options.

### Design a search with typeahead/autocomplete.

(Similar to autocomplete design above, but can add highlighting, keyboard navigation.)

**Design**:
- **Input**: Controlled component.
- **Debouncing**: 300ms delay.
- **Source**: Fetch suggestions from API; may also include recent searches.
- **Caching**: In‑memory cache with TTL.
- **Race condition**: Use AbortController or request ID.
- **Accessibility**: ARIA roles (`combobox`, `listbox`, `option`); keyboard navigation (arrow keys, Enter, Esc).
- **Highlighting**: Highlight matching substring in results.
- **Fallback**: Show “no results” when empty.

### Design a config-driven form renderer using a JSON schema.

**Requirements**:
- Render forms based on a JSON schema defining fields, validations, layouts.
- Support dynamic field visibility, dependencies.

**Design**:
- **Schema**: Define fields: type (text, number, select, date), label, placeholder, validations (required, pattern, min/max), conditional display (showIf based on other field values).
- **Parser**: Recursively render components based on field type using a registry (e.g., `FieldComponent` map).
- **State**: Use `react-hook-form` or similar to manage form state, validation, and error messages.
- **Dynamic visibility**: Use `useWatch` to watch other fields and conditionally render.
- **Layout**: Support groups, sections, columns via schema properties.
- **Validation**: Integrate with Zod or Yup schemas derived from the JSON.
- **Extensibility**: Allow custom component registration for custom field types.

### Design a file upload component with progress tracking and chunked uploads.

**Requirements**:
- Upload large files in chunks.
- Show progress per chunk and overall.
- Support pause/resume, retry, and cancellation.

**Design**:
- **Chunking**: Split file into chunks of size (e.g., 1MB). Maintain a chunk queue.
- **Upload logic**: Use `fetch` with `PUT` or `POST` and `Range` headers, or a custom API endpoint that accepts chunks. For each chunk, send a request with chunk index and total chunks.
- **Progress**: Track per‑chunk status (pending, uploading, completed). Calculate overall progress (uploaded bytes / total bytes). Use `XMLHttpRequest` or `fetch` with `upload.onprogress`.
- **Resume**: Store upload state (uploaded chunks) in `localStorage` or IndexedDB; resume by sending only missing chunks.
- **Error handling**: Retry failed chunks with exponential backoff.
- **Abort**: Use `AbortController` to cancel ongoing requests.
- **UI**: Display progress bar, list of files, cancel/pause buttons.

### Design a data table with sorting, filtering, pagination, and performance trade-offs.

**Requirements**:
- Display large datasets with client‑side or server‑side operations.
- Sorting by columns, filtering by text or dropdown, pagination.

**Design**:
- **Data fetching**: Decide between client‑side (all data loaded) or server‑side (pagination and filtering done on server). For large datasets, server‑side is preferred.
- **State**: Store current page, page size, sort column and direction, filter values. Use URL query parameters for shareability.
- **Rendering**: Use virtualization (e.g., `react‑virtual`) if many rows are shown. Use `React.memo` for rows.
- **Sorting**: On column header click, toggle sort direction; re‑fetch data (server‑side) or sort client‑side.
- **Filtering**: Input fields for each column; debounce before sending request.
- **Pagination**: Show page numbers or “Load more”. Use offset/limit.
- **Performance trade‑offs**: Server‑side reduces client memory but increases network requests. Client‑side is faster for filtering/sorting but only suitable for moderate data size. Use virtualization for client‑side tables with many rows.

### Design an image gallery with lazy loading and skeleton placeholders.

**Requirements**:
- Load images as user scrolls.
- Show placeholder skeletons until images load.
- Support responsive layouts (grid, masonry).

**Design**:
- **Lazy loading**: Use `IntersectionObserver` to detect when an image enters the viewport. Set the `src` attribute only when visible. Fallback for older browsers using `loading="lazy"` attribute.
- **Skeletons**: Render a placeholder component with the same dimensions (e.g., a gray box with pulse animation) while `img` is loading. On load, replace with image.
- **Responsive**: Use CSS Grid with `minmax` for responsive columns. For masonry, use a library or CSS columns.
- **Performance**: Use thumbnails; serve responsive images with `srcset` and `sizes`.
- **Error handling**: Show broken image icon on load error.

### Design a carousel that can handle 1000+ images efficiently.

**Requirements**:
- Display one image at a time (or a few) with navigation.
- Smooth transitions.
- Efficient memory usage with 1000+ images.

**Design**:
- **Virtualization**: Only render images that are currently visible plus a buffer (e.g., previous/next slide). Use `IntersectionObserver` to load images on demand.
- **Lazy loading**: Load image `src` only when the slide is about to become visible.
- **State**: Track current index; use `transform: translateX` with CSS transitions for sliding.
- **Performance**: Preload next image(s) for smoother navigation. Avoid rendering all images at once; reuse DOM elements (e.g., only 3–5 slides in the DOM at any time).
- **Memory**: Unload images that are far away by removing their `src` and freeing memory. However, modern browsers handle this; but for extreme cases, you can manage manually.
- **Accessibility**: Keyboard navigation, ARIA roles (`listbox`, `option`), focus management.

### Design a drag-and-drop interface (e.g., kanban board).

**Requirements**:
- Reorder items within a column.
- Move items between columns.
- Touch and mouse support.

**Design**:
- **HTML5 Drag-and-Drop** is limited; use libraries like `react‑dnd`, `dnd‑kit`, or `@dnd‑kit/sortable` for better control.
- **State**: Store columns and cards in a normalized structure. On drag end, update order/column mapping.
- **Accessibility**: Ensure keyboard accessibility (e.g., using arrow keys to move focus, Enter to pick up, arrow to move, Enter to drop).
- **Performance**: Use memoization for column and card components; avoid re‑renders during drag.
- **Visual feedback**: Show placeholder, highlight drop zones.

### Design a multi-step form with validation.

**Requirements**:
- Several steps (e.g., personal info, address, confirmation).
- Client‑side validation per step.
- Keep data across steps; allow go back and edit.
- Submit at the end.

**Design**:
- **State**: Use `useReducer` or context to store form data across steps. Each step's data can be local state but synced to global context.
- **Navigation**: Maintain current step index; on “Next”, validate current step; if valid, proceed.
- **Validation**: Use schema validation (e.g., Zod) per step. Show inline errors.
- **Persistence**: Optionally store draft in `localStorage` to recover on refresh.
- **Submission**: On final step, collect all data and send to API.
- **UI**: Show progress indicator; allow step clicks to navigate.

### Design a theme-able, extensible component library.

**Requirements**:
- Support light/dark themes, custom brand colors.
- Allow consumers to override styles.
- Be extensible with new components.

**Design**:
- **Styling approach**: Use CSS‑in‑JS (emotion, styled‑components) with theming via `ThemeProvider` or use CSS variables for dynamic theming.
- **Base styles**: Provide a set of design tokens (colors, spacing, typography) as CSS custom properties.
- **Theme object**: Define theme object with `colors`, `spacing`, etc. Use React Context to pass theme.
- **Component API**: Use polymorphic `as` prop to allow rendering as different elements. Provide variant props (`variant="primary"`).
- **Extensibility**: Allow consumers to pass custom class names and `style` props. Use composition over inheritance.
- **Documentation**: Provide Storybook for interactive documentation.
- **Tree shaking**: Use barrel exports but ensure proper configuration for bundlers to only include used components.

### Design a state management solution for a complex app.

**Requirements**:
- Handle asynchronous data, caching, optimistic updates.
- Manage shared state across many features.
- Ensure performance.

**Design**:
- **Global state**: Use Redux Toolkit with slices per feature. Use `createEntityAdapter` for normalized data.
- **Async logic**: `createAsyncThunk` for API calls; handle loading/error states.
- **Caching**: Implement a cache layer with expiration; use selectors to retrieve cached data.
- **Optimistic updates**: Update the store optimistically on user actions; if the request fails, rollback using the previous state snapshot.
- **Derived state**: Use `createSelector` (Reselect) for memoized derived data.
- **Cross‑slice communication**: Use `extraReducers` to listen to actions from other slices.
- **Performance**: Use selectors that compute only when needed. Use `React.memo` and `useCallback` to avoid re‑renders.

### How would you implement Server-Side Rendering (SSR) for a React application? When to use SSR, SSG, ISR?

**SSR (Server‑Side Rendering)**:
- Render React components to HTML on the server for each request.
- Improves initial page load and SEO.
- Can be implemented with frameworks like Next.js (using `getServerSideProps`).

**When to use**:
- Content changes frequently (e.g., social media feed, e‑commerce product page with dynamic data).
- SEO is critical and content is user‑specific.

**SSG (Static Site Generation)**:
- Build‑time generation of HTML files.
- Fastest performance, ideal for content that rarely changes (e.g., blog, documentation).

**ISR (Incremental Static Regeneration)**:
- Combines SSG and SSR: static pages can be updated after deployment without a full rebuild.
- Good for sites with large number of pages that need occasional updates (e.g., e‑commerce product pages).

---

## Architecture & Strategy

### How would you structure a micro‑frontend architecture enabling team autonomy and independent releases?

**Micro‑frontends** split the frontend into independently deployable modules, each owned by a team.

**Approaches**:
- **Build‑time integration**: Each micro‑frontend is a separate npm package, composed at build time (e.g., Webpack Module Federation). Teams release independently.
- **Runtime integration**: Use iframes, Web Components, or a container app that loads micro‑frontends at runtime via JavaScript.

**Structure**:
- **Container app**: Provides shell (layout, authentication, routing). Uses Module Federation to load remote modules.
- **Independent teams**: Own their codebase, build pipeline, and deployment. They expose entry points (e.g., a React component) via federation.
- **Shared libraries**: Manage via monorepo (e.g., Nx, Turborepo) with shared UI components, utilities, and types. Use semantic versioning and careful upgrades.
- **Routing**: Typically, the container handles top‑level routing; micro‑apps handle their own sub‑routing.
- **Communication**: Use custom events or a shared state library (e.g., Redux with a central store) but avoid tight coupling. Prefer event‑based communication.
- **Testing**: Each team tests its own app; integration tests ensure contracts.

### How do you manage shared libraries and dependencies in a large monorepo?

**Monorepo tools**: Nx, Turborepo, Lerna, pnpm workspaces.

**Best practices**:
- **Package structure**: Place shared libraries in `packages/` or `libs/`. Each library has its own `package.json` and version.
- **Versioning**: Use independent versioning (each library has its own version) or fixed versioning (all libraries share a version). Independent allows faster updates.
- **Dependency management**: Use `pnpm` or `yarn` workspaces to hoist common dependencies. Ensure peer dependencies are correctly declared.
- **Build caching**: Use Nx or Turborepo to cache build outputs and only rebuild affected packages.
- **Code sharing**: Use TypeScript project references for faster builds.
- **CI/CD**: Configure pipelines to build and test only affected packages using tools like Nx affected.

### How would you design SSR/SSG/hydration strategy for a React app?

**Strategy** depends on content type and performance needs.

- **SSR for dynamic content** (e.g., user dashboard): Use Next.js `getServerSideProps` or a custom Node server with `renderToString`. Ensure hydration matches server HTML.
- **SSG for marketing pages**: Use `getStaticProps` with `revalidate` for ISR.
- **Hybrid**: Use Next.js App Router with `use client` and server components to mix server‑side and client‑side.
- **Hydration**: Ensure that server and client render produce identical HTML. Avoid using browser‑only APIs during server render. Use `useEffect` for client‑only code.
- **Performance**: Stream SSR (React 18 `renderToPipeableStream`) to send HTML progressively.

### How do you handle breaking API changes safely on the frontend?

**Strategies**:
- **Versioned API**: Include API version in URL (e.g., `/v1/users`). Deprecate old versions gradually.
- **Adapters**: Write adapters that transform new API responses to the old shape, so frontend can upgrade later.
- **Feature flags**: Roll out new API calls behind a flag; enable gradually.
- **Backward compatibility**: Backend can support both old and new response shapes for a period.
- **Contract testing**: Use tools like Pact to verify consumer‑provider compatibility.

### What is your approach to multi‑tenant frontend applications?

**Multi‑tenancy**: Single codebase serving multiple tenants (organizations) with custom branding, configuration, and sometimes data isolation.

**Approach**:
- **Theming**: Use CSS variables or dynamic theme loading based on tenant identifier.
- **Configuration**: Fetch tenant config at runtime (e.g., `/api/tenant/config`) and store in context. Adjust UI elements (logos, feature flags).
- **Routing**: Use subdomains (tenant.myapp.com) or paths (`/tenant/:id`) to determine tenant.
- **Data isolation**: Ensure all API requests include tenant ID (e.g., in headers). Use authentication that scopes data.
- **Build**: Single build serving all tenants. Avoid per‑tenant builds for scalability.

### How do you implement dark mode across an app?

**Implementation**:
- **CSS custom properties**: Define colors as variables (`--bg`, `--text`). Switch theme by changing a class on the root element (e.g., `.dark`).
- **Theme provider**: Use React context to store theme preference (`light`, `dark`, `system`). Apply the class accordingly.
- **Persistence**: Save preference in `localStorage`.
- **System preference**: Use `prefers-color-scheme` media query to set default.
- **Transition**: Add smooth transitions for color changes.

### How do you ensure accessibility beyond ARIA labels?

**Accessibility** goes beyond ARIA:
- **Semantic HTML**: Use correct elements (`<button>`, `<nav>`, `<header>`, etc.) rather than divs with roles.
- **Keyboard navigation**: Ensure all interactive elements are reachable with Tab, have visible focus indicators, and support Enter/Space for activation.
- **Screen reader announcements**: Use `aria-live` regions for dynamic updates. Provide alt text for images.
- **Color contrast**: Follow WCAG 2.1 AA standards for text and interactive elements.
- **Touch targets**: Ensure interactive elements are large enough (min 44×44px).
- **Testing**: Use automated tools (axe, Lighthouse) and manual testing with screen readers (NVDA, VoiceOver).
- **Focus management**: Manage focus after navigation or modal open/close.
- **Skip links**: Provide skip‑to‑content links for keyboard users.




## Performance Optimization

### How would you optimize a React application rendering 100k+ items in a list? (virtualization, windowing, pagination)

Rendering 100,000+ DOM nodes at once will severely degrade performance. The key is to render only what’s visible.

**Virtualization / Windowing**  
- Use libraries like `react-window` or `react-virtualized`. They render only the items that fit in the viewport plus a small buffer.
- Example with `react-window`:
  ```jsx
  import { FixedSizeList as List } from 'react-window';
  const Row = ({ index, style }) => <div style={style}>Item {index}</div>;
  <List height={600} itemCount={100000} itemSize={35} width={300}>
    {Row}
  </List>
  ```
- This dramatically reduces DOM nodes and memory usage.

**Pagination**  
- If virtualization is not sufficient or if data comes from an API, implement pagination (offset-based or cursor) to load data in chunks.
- Combine pagination with virtualization for very large datasets where loading all data upfront is impractical.

**Optimizations within each row**  
- Use `React.memo` on row components to avoid re‑rendering when props (e.g., item data) haven’t changed.
- Avoid inline functions/objects in row props.

**Measuring and adjusting**  
- Use the React DevTools Profiler to ensure only visible rows re‑render on scroll.

---

### What strategies would you use to improve page load time for a global audience? (CDN, lazy loading, code splitting, image optimization)

**CDN (Content Delivery Network)**  
- Serve static assets (JS, CSS, images) from a CDN to reduce latency for users worldwide. Use a global CDN like Cloudflare, Fastly, or AWS CloudFront.

**Code Splitting**  
- Split code by routes using `React.lazy` and `Suspense`. This loads only the JavaScript needed for the current page.
- Use dynamic imports for heavy components that are not needed immediately.

**Lazy Loading**  
- Images: use `loading="lazy"` attribute on `<img>`.
- Off‑screen components: load them only when they become visible (using Intersection Observer).

**Image Optimization**  
- Serve responsive images with `srcset` and `sizes`.
- Use modern formats (WebP, AVIF) and fallbacks.
- Compress images; use CDN image optimization services (e.g., Imgix, Cloudinary).

**Font Optimization**  
- Use `font-display: swap` to avoid invisible text during loading.
- Preload critical fonts with `<link rel="preload">`.
- Subset fonts to reduce size.

**Resource Hints**  
- Use `preconnect` for origins you’ll connect to (e.g., API, CDN).
- Use `dns-prefetch` for third‑party domains.

**Minification & Compression**  
- Ensure your bundler (Webpack, Vite) minifies code and uses Brotli or Gzip compression.

**HTTP/2 or HTTP/3**  
- Enable HTTP/2 for multiplexing; consider HTTP/3 for better performance.

**Service Worker**  
- Cache static assets for repeat visits.

---

### How do you debug a performance bottleneck in a React app using DevTools? (Profiler, Performance tab)

**React DevTools Profiler**  
- Record a profile while interacting with the app.
- The “Flamegraph” view shows which components rendered and why.
- Look for components that re‑render frequently or take a long time.
- Use the “Why did this render?” option (with a custom hook or the `why‑did‑you‑render` library) to identify prop changes.

**Browser Performance Tab (Chrome DevTools)**  
- Record a performance trace during the problematic interaction.
- Look for long tasks (yellow/red bars) and inspect the call stack.
- Identify whether the bottleneck is JavaScript (React render) or layout/paint (CSS).
- Use “Timings” to see where time is spent: script, render, paint.

**Lighthouse / Web Vitals**  
- Run Lighthouse to get a high‑level score and suggestions.
- Use the “Performance” panel to measure Core Web Vitals (LCP, CLS, INP).

**Memory Tab**  
- If performance degrades over time, take heap snapshots to find memory leaks.

---

### How would you improve Web Vitals (LCP, CLS, INP)?

**Largest Contentful Paint (LCP)** – Largest element painted (usually hero image or text block)  
- Optimize server response time (TTFB) with CDN and caching.
- Prioritize loading of LCP element: use `<link rel="preload">` for LCP images.
- Avoid lazy‑loading the LCP image.
- Minimize render‑blocking resources (CSS/JS) – defer non‑critical scripts.
- Use server‑side rendering or static generation for fast initial paint.

**Cumulative Layout Shift (CLS)** – Unexpected layout shifts  
- Always set explicit `width` and `height` on images, videos, and iframes.
- Reserve space for dynamic content (e.g., using `aspect-ratio` or placeholder skeletons).
- Insert new content (like ads) in a reserved space.
- Avoid injecting UI elements above existing content.

**Interaction to Next Paint (INP)** – Responsiveness to user input  
- Break up long tasks (use `setTimeout` or `scheduler.yield` in React 18+).
- Use `useTransition` for non‑urgent state updates to keep UI responsive.
- Optimize event handlers: avoid heavy work; offload to Web Workers if possible.
- Reduce JavaScript execution time overall (code splitting, tree shaking).

---

### What causes unnecessary re-renders in React? How to avoid them? (memoization, stable props, colocated state)

**Common causes**:
- Parent re‑renders – by default, children re‑render even if props haven’t changed.
- Inline functions/objects passed as props – new references on every render.
- Context changes – any consumer re‑renders when context value changes.
- State updates that don’t change the value but still trigger re‑render (if using setState with new object reference).

**How to avoid**:
- **`React.memo`** – wrap functional components to prevent re‑renders when props (shallow‑compared) don’t change.
- **`useMemo`** – memoize expensive computations or object/array values.
- **`useCallback`** – memoize functions to avoid new references.
- **Colocate state** – move state down to the component that needs it, rather than lifting it unnecessarily high.
- **Splitting context** – break large contexts into smaller ones so consumers only subscribe to what they use.
- **`useReducer` instead of multiple `useState`** – can help group related state updates and reduce re‑renders if implemented with care.

---

### Explain techniques for dynamic code splitting and lazy loading in multi-route SPAs.

**Route‑based code splitting** – using `React.lazy` with `Suspense`:

```jsx
const Home = React.lazy(() => import('./routes/Home'));
const About = React.lazy(() => import('./routes/About'));

function App() {
  return (
    <Suspense fallback={<Loading />}>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
      </Routes>
    </Suspense>
  );
}
```

**Component‑level lazy loading** – for heavy components like modals, charts, or editors:

```jsx
const HeavyChart = React.lazy(() => import('./HeavyChart'));
// then use it with Suspense
```

**Pre‑loading** – start loading a chunk before navigation using `webpackPrefetch`:

```jsx
import(/* webpackPrefetch: true */ './HeavyComponent');
```

**Pre‑fetching on hover** – trigger dynamic import when user hovers over a link.

**Bundler configuration** – ensure chunks are named and optimized (e.g., Webpack’s `splitChunks`).

---

### How do you optimize images and fonts?

**Images**:
- Use `<img loading="lazy">` for off‑screen images.
- Serve WebP/AVIF with `<picture>` fallbacks.
- Set explicit `width` and `height` to avoid CLS.
- Use `srcset` and `sizes` for responsive images.
- Consider using a CDN that optimizes on‑the‑fly.

**Fonts**:
- Use `font-display: swap` in `@font-face`.
- Preload critical fonts: `<link rel="preload" as="font" href="/font.woff2" crossorigin>`
- Subset fonts to only needed characters.
- Use system fonts as fallback to avoid FOUT.

---

### What are preload, prefetch, and priority hints?

- **`<link rel="preload">`** – tells the browser to download a resource as soon as possible, for resources needed **now** (e.g., LCP image, critical font). It does not execute the resource.
- **`<link rel="prefetch">`** – downloads a resource for a future navigation (e.g., next page). Low priority; may be cached.
- **`<link rel="preconnect">`** – opens a connection to an origin (DNS, TCP, TLS) to reduce latency for future requests.
- **`<link rel="dns-prefetch">`** – resolves DNS only.
- **`fetchpriority` attribute** (experimental) – hints the browser about priority: `high` / `low` / `auto`. Can be used on images, iframes, etc.

---

### How do you analyze bundle size and fix tree shaking failures?

**Analysis**:
- Use `webpack-bundle-analyzer`, `rollup-plugin-visualizer`, or Next.js’ built‑in bundle analysis.
- Check for large libraries, duplicated modules, or unexpected code.

**Fixing tree shaking**:
- Ensure your code uses ES modules (`import`/`export`). CommonJS (`require`) often prevents tree shaking.
- Avoid side‑effects in modules; set `sideEffects: false` in `package.json` if safe.
- Use named imports instead of default imports for libraries that support it (e.g., `import { throttle } from 'lodash-es'`).
- Configure bundler to treat modules with side‑effects properly.
- Remove unused exports (dead code) by ensuring bundler’s mode is `production`.

---

### What is the difference between virtualization and windowing? Trade-offs.

**Virtualization** is the broad concept of rendering only the visible portion of a list, reusing DOM nodes. **Windowing** is a specific implementation (e.g., `react-window`) that renders a “window” of items.

**Trade-offs**:
- **Pros**: Significantly reduces DOM nodes, memory, and render time. Enables infinite lists.
- **Cons**: Adds complexity; layout calculations can be tricky for variable heights. Accessibility can suffer if not implemented carefully (screen readers may not see all items). Scrolling might feel different.

---

### How do you avoid layout thrashing?

**Layout thrashing** occurs when you repeatedly read layout properties (e.g., `offsetHeight`) and then write styles in a loop, forcing the browser to recalculate layout multiple times.

**Avoidance**:
- Batch reads before writes. For example, read all necessary dimensions first, then apply style changes.
- Use `requestAnimationFrame` to schedule changes.
- Prefer CSS transforms (`translate`, `scale`) for animations instead of properties that trigger layout (`top`, `left`, `width`).
- Use `will-change` for elements that will be animated.
- Use `ResizeObserver` instead of listening to `resize` with synchronous layout reads.

---

### CPU vs memory bottlenecks – how to identify and fix?

**CPU bottlenecks** – JavaScript execution causing long tasks, jank, high CPU usage.
- **Identify**: Chrome DevTools Performance tab; look for long “Script” tasks.
- **Fix**: Code splitting, Web Workers for heavy computations, throttle/debounce event handlers, use `useTransition` to prioritize UI updates, avoid expensive renders.

**Memory bottlenecks** – Leaks causing growing memory consumption, eventual slowdown or crash.
- **Identify**: Memory tab, take heap snapshots; compare after user actions to see retained objects.
- **Fix**: Clean up event listeners, intervals, WebSocket connections; avoid retaining large data in closures; use weak references (`WeakMap`, `WeakSet`) for caching; unmount components properly; use `useEffect` cleanup.

---

### Edge caching vs CDN caching strategies.

- **Edge caching** (also often provided by CDNs) caches static assets at edge locations (points of presence) close to users. Typically for static files (JS, CSS, images). You can configure cache headers (`Cache-Control`) and invalidation strategies.
- **CDN caching** can also cache dynamic responses (HTML) using strategies like “stale‑while‑revalidate” to serve stale content while refreshing in the background. Useful for SSR pages.
- **Strategies**:
  - Use `Cache-Control: public, max-age=31536000, immutable` for versioned assets.
  - For HTML, use `s-maxage` and `stale-while-revalidate` for CDNs.
  - Use surrogate keys to purge specific resources.

---

### How would you handle a large dataset without blocking the main thread? (Web Workers, virtualization)

**Web Workers** – offload data processing, sorting, filtering, or any CPU‑intensive task to a background thread.
- The worker processes the dataset and returns a result (e.g., filtered list) to the main thread.
- The main thread remains responsive for UI updates.

**Virtualization** – as described, reduces the number of DOM nodes, so the main thread has less work to do.

**Chunking / Time‑slicing** – break up heavy work into smaller chunks using `setTimeout` or `scheduler.postTask` to allow the browser to handle user interactions in between.

**Streaming / Pagination** – load data incrementally rather than all at once.

**WebAssembly** – if dataset processing is extremely heavy, consider using Wasm for performance (though overkill for most cases).

---

### How do you detect and prevent memory leaks in long-running SPAs?

**Detection**:
- Use Chrome DevTools Memory tab: take heap snapshots before and after a series of user actions that should free memory.
- Look for retained objects that are no longer needed (e.g., detached DOM elements, large arrays).
- Use `performance.memory` (Chrome) to monitor memory usage over time.
- Use the “Performance monitor” to watch JS heap size.

**Prevention**:
- Always clean up `setInterval`/`setTimeout` in `useEffect` cleanup.
- Remove event listeners in cleanup.
- Cancel subscriptions (WebSocket, fetch with AbortController) on unmount.
- Avoid storing large data in global variables or closures that persist.
- Use `useRef` for values that shouldn’t cause re‑renders but be cautious about holding references.
- For caches, use `WeakMap`/`WeakSet` to allow garbage collection when keys are no longer referenced.
- Profile your app after implementing cleanup to ensure no accumulation.


## HTML & CSS

### HTML

#### What are semantic tags in HTML? Give examples.

Semantic tags clearly describe their meaning to both the browser and the developer. They improve accessibility, SEO, and code maintainability.

**Examples**:
- `<header>` – introductory content or navigation links.
- `<nav>` – navigation links.
- `<main>` – the dominant content of the `<body>`.
- `<article>` – self‑contained composition (blog post, news story).
- `<section>` – thematic grouping of content.
- `<aside>` – tangentially related content (sidebar).
- `<footer>` – footer for a section or page.
- `<figure>` and `<figcaption>` – illustrations with captions.
- `<mark>` – highlighted text.
- `<time>` – machine‑readable date/time.

#### What is the difference between `div` and `span`?

- **`<div>`** – block‑level element. Starts on a new line and takes full width available. Used for grouping larger content blocks.
- **`<span>`** – inline element. Does not break lines and only takes as much width as its content. Used for styling or grouping inline text.

#### How do you create a form with validation?

Use `<form>` with input fields and submit button. Validation can be:

- **HTML5 built‑in**: `required`, `pattern`, `type="email"`, `min`, `max`, etc. Browser provides basic validation and error messages.
- **JavaScript validation**: Listen to `submit` event, prevent default, and check values manually. Show custom error messages.

Example:
```html
<form id="myForm">
  <input type="text" id="name" required pattern="[A-Za-z]{3,}">
  <input type="email" id="email" required>
  <button type="submit">Submit</button>
</form>
<script>
  document.getElementById('myForm').addEventListener('submit', (e) => {
    if (!document.getElementById('name').checkValidity()) {
      e.preventDefault();
      alert('Name must be at least 3 letters');
    }
  });
</script>
```

#### What is the purpose of the meta tags?

`<meta>` tags provide metadata about the HTML document. Common uses:

- Character set: `<meta charset="UTF-8">`
- Viewport for responsive design: `<meta name="viewport" content="width=device-width, initial-scale=1">`
- Description for SEO: `<meta name="description" content="...">`
- Author: `<meta name="author" content="...">`
- Refresh/redirect: `<meta http-equiv="refresh" content="5;url=https://...">`

#### Explain the difference between localStorage, sessionStorage, and cookies.

| Feature | localStorage | sessionStorage | cookies |
|---------|--------------|----------------|--------|
| **Capacity** | ~5‑10 MB | ~5‑10 MB | ~4 KB |
| **Lifetime** | Persistent until manually cleared | Tab/window lifetime; cleared on close | Can be set with expiration; can be session‑only |
| **Scope** | Same origin | Same origin, per tab | Same origin; path can be scoped |
| **Sent to server** | No | No | Yes (with every HTTP request) |
| **API** | Simple (`setItem`, `getItem`) | Simple | More complex (document.cookie) |
| **Use case** | Client‑side data, offline storage | Temporary session data | Authentication, tracking, server‑side needs |

---

### CSS

#### What is a pseudo-class? Give examples (:hover, :nth-child, etc.).

A pseudo‑class defines a special state of an element. It is denoted by a single colon `:`.

Examples:
- `:hover` – when the user hovers over an element.
- `:focus` – when an element has focus (e.g., input).
- `:nth-child(an+b)` – selects elements based on their position in a parent.
- `:first-child`, `:last-child`.
- `:not(selector)` – excludes elements.
- `:is()` – matches any of the selectors.
- `:checked` – for radio/checkbox input.

#### How to center an element horizontally? Vertically? Both?

**Horizontally**:
- Inline/inline‑block: `text-align: center` on parent.
- Block with fixed width: `margin: 0 auto`.
- Flexbox: `display: flex; justify-content: center` on parent.
- Grid: `display: grid; place-items: center` (centers both axes).

**Vertically**:
- Flexbox: `display: flex; align-items: center` on parent.
- Grid: `display: grid; align-items: center` (or `place-items: center` for both).
- Absolute positioning with transform:
  ```css
  position: relative; /* on parent */
  .child {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
  }
  ```
- For single line of text: `line-height` equal to container height.

**Both axes**:
- Flexbox: `display: flex; justify-content: center; align-items: center`.
- Grid: `display: grid; place-items: center`.
- Absolute + transform:
  ```css
  .parent { position: relative; }
  .child {
    position: absolute;
    top: 50%; left: 50%;
    transform: translate(-50%, -50%);
  }
  ```

#### Difference between relative and absolute positioning.

- **`position: relative`** – Positions the element relative to its normal position. Offsets (`top`, `left`, etc.) move it from its original spot, but it still occupies its original space in the document flow.
- **`position: absolute`** – Removes the element from the document flow. It is positioned relative to its nearest positioned ancestor (non‑`static`). If none, it uses the initial containing block (usually the viewport). It does not affect the layout of other elements.

#### What is Flexbox? Explain main concepts.

Flexbox is a one‑dimensional layout model that arranges items in rows or columns with powerful alignment and distribution capabilities.

**Main concepts**:
- **Container** with `display: flex`.
- **Main axis** – defined by `flex-direction` (row or column).
- **Cross axis** – perpendicular to the main axis.
- **Properties on container**:
  - `flex-direction`: row | row-reverse | column | column-reverse.
  - `justify-content`: alignment along main axis (flex-start, center, space-between, etc.).
  - `align-items`: alignment along cross axis (stretch, center, baseline, etc.).
  - `flex-wrap`: wrap items to multiple lines.
  - `gap`: space between items.
- **Properties on items**:
  - `flex-grow`: how much an item can grow.
  - `flex-shrink`: how much it can shrink.
  - `flex-basis`: initial size.
  - `align-self`: override container’s `align-items`.

#### How would you create a responsive layout with CSS Grid?

CSS Grid is a two‑dimensional system. For responsiveness:
- Use `grid-template-columns` with `repeat(auto-fit, minmax(min, max))`.
- Example: `grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));` – creates as many columns as possible, each at least 250px wide, growing equally.
- Combine with media queries to adjust grid structure at different breakpoints.
- Use `fr` units for flexible sizing.

#### What are container queries?

Container queries allow styling of an element based on the size of its **parent container**, not the viewport. They enable true component‑level responsiveness.

Syntax:
```css
.component {
  container-type: inline-size;
}
@container (min-width: 400px) {
  .component .child {
    display: flex;
  }
}
```
This makes components reusable in different contexts.

#### How do you implement a CSS animation? How to debug janky animations on mobile?

**Implementing animation**:
- Define keyframes with `@keyframes`.
- Apply with `animation` property: `animation: name duration timing-function delay iteration-count direction fill-mode;`

**Debugging janky animations**:
- Use Chrome DevTools Performance tab to record and identify long tasks and layout/paint events.
- Check that you are animating only **compositor‑only** properties: `transform` and `opacity`. Avoid animating `width`, `height`, `top`, `left`, etc., which trigger layout.
- Enable the “Paint flashing” option in DevTools to see repaints.
- Use `will-change` sparingly for elements you will animate (e.g., `will-change: transform`).
- On mobile, reduce animation complexity; test with throttled CPU.

#### Explain the concept of specificity in CSS.

Specificity determines which CSS rule is applied when multiple rules target the same element. It is calculated as a 4‑part score: inline styles, IDs, classes/pseudo‑classes, elements/pseudo‑elements.

- Inline styles: 1,0,0,0
- ID: 0,1,0,0
- Class, attribute, pseudo‑class: 0,0,1,0
- Element, pseudo‑element: 0,0,0,1

Higher score wins. If equal, later rule wins (order matters). `!important` overrides all but should be used sparingly.

#### What are CSS custom properties (variables)?

CSS custom properties (aka CSS variables) allow you to store values for reuse. They are defined with `--` prefix and accessed with `var()`.

Example:
```css
:root {
  --primary-color: #3498db;
}
.button {
  background-color: var(--primary-color);
}
```
They are dynamic and can be updated via JavaScript or media queries, making them powerful for theming.

#### How do you handle dark mode theming?

**Approaches**:
- **CSS custom properties**: Define light and dark color schemes in separate classes or via `prefers-color-scheme`.
  ```css
  :root {
    --bg: white;
    --text: black;
  }
  @media (prefers-color-scheme: dark) {
    :root {
      --bg: black;
      --text: white;
    }
  }
  .dark {
    --bg: black;
    --text: white;
  }
  ```
- **User toggle**: Add a class (e.g., `.dark`) to a parent element and define overrides.
- Use JavaScript to read user preference and apply the appropriate class.

---

### Inline Layout

#### How to place 5 divs in a row without using flex, margin, or padding? (Hint: display: inline-block)

Using `display: inline-block`:

```html
<style>
  .box {
    display: inline-block;
    width: 100px;
    height: 100px;
    background: red;
  }
</style>
<div class="box"></div>
<div class="box"></div>
<div class="box"></div>
<div class="box"></div>
<div class="box"></div>
```
Note: Inline‑block elements respect whitespace between them in HTML, which creates a small gap. To remove gap, set parent `font-size: 0` and reset font‑size on children.

---

## Browser & DOM APIs

#### How do you select and manipulate DOM elements?

**Selecting**:
- `document.getElementById(id)` – single element.
- `document.querySelector(selector)` – first match.
- `document.querySelectorAll(selector)` – NodeList.
- `document.getElementsByClassName(class)` – HTMLCollection.
- `document.getElementsByTagName(tag)`.

**Manipulating**:
- Change content: `element.textContent`, `element.innerHTML`.
- Attributes: `element.setAttribute(name, value)`, `element.getAttribute(name)`.
- Classes: `classList.add()`, `remove()`, `toggle()`, `contains()`.
- Styles: `element.style.property = value` (inline).
- Create elements: `document.createElement(tag)`, append with `appendChild` or `append`.

#### Explain event bubbling and capturing.

Events propagate in three phases: **capturing** (from window down to target), **target**, and **bubbling** (from target back up). By default, event listeners are registered for the bubbling phase. To listen in capturing phase, set `useCapture: true` in `addEventListener`.

- **Bubbling** – the event triggers on the target element and then on each ancestor.
- **Capturing** – the event triggers on ancestors first, then the target.

#### What is event delegation? When would you use it?

Event delegation is a technique where a single event listener is attached to a parent element to handle events on its children, leveraging event bubbling. This reduces memory usage and works for dynamically added elements.

**Use cases**:
- Handling clicks on many similar items (e.g., list items, buttons).
- When elements are added/removed dynamically (e.g., chat messages, todo items).

Example:
```javascript
document.querySelector('#list').addEventListener('click', (e) => {
  if (e.target.matches('li')) {
    console.log('Item clicked:', e.target.textContent);
  }
});
```

#### How does `addEventListener` work? How to remove listeners?

`addEventListener(event, callback, options)` attaches an event handler. It does not overwrite existing handlers (unlike `onclick` property). You can pass `{ once: true }` for one‑time execution.

To remove, use `removeEventListener` with the same function reference. That’s why anonymous functions cannot be removed unless stored in a variable.

#### What are the different ways to handle forms in JavaScript?

- **Traditional submit**: Listen to `submit` event on form, call `preventDefault`, collect values via `FormData` or accessing inputs by id.
- **FormData API**: `new FormData(formElement)` to get key‑value pairs.
- **Controlled components** (in React): state holds values.
- **Uncontrolled**: Access values via refs when needed.

#### Difference between LocalStorage and SessionStorage.

(See earlier table – localStorage persists, sessionStorage per tab.)

#### How do you work with cookies in JavaScript?

- **Read**: `document.cookie` returns a string of all cookies; parse manually.
- **Write**: `document.cookie = "name=value; expires=...; path=...; secure"`.
- **Delete**: Set expiry date in past.
- Libraries like `js-cookie` simplify.

#### Explain the IntersectionObserver API and its use cases (lazy loading, infinite scroll).

`IntersectionObserver` watches elements and triggers a callback when they enter/exit the viewport (or a specified root element). It is asynchronous and efficient, avoiding scroll listeners.

**Use cases**:
- Lazy loading images: observe images, set `src` when visible.
- Infinite scroll: load more content when a sentinel element appears.
- Analytics: track when an element is viewed.
- Animation: trigger entrance animations.

#### What is the ResizeObserver?

`ResizeObserver` reports changes to the dimensions of an element. It is useful for responsive components that need to react to size changes (e.g., charts, adaptive layouts). Unlike `window.resize` events, it targets specific elements and works cross‑browser.

#### How do you implement drag and drop using native APIs?

Native HTML5 drag‑and‑drop uses `dragstart`, `dragend`, `dragover`, `drop` events. You need to set `draggable="true"` on draggable elements, and call `preventDefault` on `dragover` to enable drop.

Example:
```html
<div draggable="true" ondragstart="dragStart(event)">Drag me</div>
<div ondrop="drop(event)" ondragover="allowDrop(event)">Drop here</div>
<script>
  function dragStart(e) { e.dataTransfer.setData('text/plain', e.target.id); }
  function allowDrop(e) { e.preventDefault(); }
  function drop(e) {
    e.preventDefault();
    const data = e.dataTransfer.getData('text/plain');
    const dragged = document.getElementById(data);
    e.target.appendChild(dragged);
  }
</script>
```
For more complex drag‑and‑drop, consider libraries like `react-dnd` or `dnd-kit`.

#### How does the history API work for routing?

The History API (`window.history`) allows manipulation of the browser session history without reloading the page. Key methods:

- `history.pushState(state, title, url)` – adds a new entry.
- `history.replaceState(state, title, url)` – replaces current entry.
- `popstate` event – fires when the user navigates with back/forward.

Modern SPAs use this to implement client‑side routing: listening to `popstate`, updating the view, and using `pushState` for navigation.

#### What is the AbortController used for?

`AbortController` allows cancelling asynchronous operations like fetch requests, timers, or any operation that accepts an `AbortSignal`. It provides a way to clean up pending requests on component unmount or user action.

Example:
```javascript
const controller = new AbortController();
fetch(url, { signal: controller.signal })
  .then(res => res.json())
  .catch(err => {
    if (err.name === 'AbortError') console.log('Fetch aborted');
  });
// later
controller.abort();
```
It can also be used with `addEventListener` to remove listeners via `signal`.


## Low-Level Design (LLD) / Component Design

### Component Design Fundamentals

#### Design a Todo List application with add, edit, delete, and mark‑as‑complete.

**Requirements**: Manage a list of todos; each todo has an id, text, and completed flag. Support adding, editing, deleting, and toggling completion.

**Design considerations**:
- **State**: Use `useState` (or `useReducer` for complex updates) to store todos array.
- **Edit mode**: Track which todo is being edited (or use a separate edit field).
- **Accessibility**: Keyboard navigation, focus management.
- **Persistence**: Optionally store in `localStorage`.
- **Performance**: Use `useCallback` for handlers, `React.memo` for each todo item to avoid unnecessary re‑renders.

**Implementation skeleton**:
```jsx
const TodoApp = () => {
  const [todos, setTodos] = useState([]);
  const [newTodo, setNewTodo] = useState('');
  const [editId, setEditId] = useState(null);
  const [editText, setEditText] = useState('');

  const addTodo = () => { /* add new todo */ };
  const toggleTodo = (id) => { /* toggle completed */ };
  const deleteTodo = (id) => { /* delete todo */ };
  const startEdit = (todo) => { /* set editId, editText */ };
  const saveEdit = () => { /* update todo text */ };

  return ( /* JSX with input, list of TodoItem components */ );
};
```

#### Design a Tabs component that supports dynamic content loading and async data.

**Requirements**: Tabs should be able to load content dynamically (e.g., each tab’s content may be fetched from an API when selected). Support async loading states.

**Design**:
- **Props**: `tabs` array (each with label, content load function or component).
- **State**: `activeTab` index, `loading` per tab, `content` cache per tab.
- **Behavior**: When a tab becomes active, if its content hasn’t been loaded, trigger async load and show loading spinner.
- **Accessibility**: Use ARIA roles (`tablist`, `tab`, `tabpanel`). Handle keyboard navigation (arrow keys).
- **Performance**: Cache loaded content to avoid re‑fetching.

**Implementation**:
```jsx
const Tabs = ({ tabs }) => {
  const [active, setActive] = useState(0);
  const [contentCache, setContentCache] = useState({});
  const [loading, setLoading] = useState(false);

  useEffect(() => {
    if (!contentCache[active] && tabs[active].load) {
      setLoading(true);
      tabs[active].load().then(data => {
        setContentCache(prev => ({ ...prev, [active]: data }));
        setLoading(false);
      });
    }
  }, [active, contentCache, tabs]);

  const activeContent = contentCache[active] ?? (tabs[active].content || <div>No content</div>);
  return ( /* JSX with tab buttons and panel */ );
};
```

#### Design an Accordion component – should it allow single or multiple panels open? Why?

**Requirements**: Accordion collapses/expands sections. Decide on behavior (single open at a time vs. multiple open).

**Design**:
- **Props**: `allowMultiple` boolean, `children` (array of panel items), optionally `defaultOpen` indices.
- **State**: Store `openIndices` (array if multiple, single index if single).
- **Why choose single vs multiple?**
  - **Single** (default) is simpler and keeps UI tidy; useful for limited vertical space or step‑by‑step flows.
  - **Multiple** gives user flexibility; good for settings panels where users may want to see several sections at once.

**Implementation**:
```jsx
const Accordion = ({ allowMultiple = false, children }) => {
  const [open, setOpen] = useState([]); // array of indices

  const toggle = (index) => {
    if (allowMultiple) {
      setOpen(prev => prev.includes(index) ? prev.filter(i => i !== index) : [...prev, index]);
    } else {
      setOpen(prev => prev[0] === index ? [] : [index]);
    }
  };
  return ( /* render children with open state */ );
};
```

#### Design a Star Rating component – how would you support half or partial ratings?

**Requirements**: Display a star rating (1‑5). Support whole, half, or custom fractional values.

**Design**:
- **Props**: `value` (number), `onChange` (for interactive), `precision` (0.5 or 0.1), `size`, `readOnly`.
- **Implementation**: Render 5 stars, each star can be partially filled using a technique like:
  - Two overlapping elements (a full star and a half star) with clip‑path or width percentage.
  - SVG with gradient or mask.
- **Interaction**: On click, determine mouse position within the star to compute fractional value.
- **Accessibility**: Use `role="slider"` with `aria-valuenow`, keyboard support (arrow keys).

**Example approach**:
```jsx
const Star = ({ filled, fraction, onClick }) => {
  // fraction: 0 (empty), 0.5 (half), 1 (full)
  // Use background image or SVG with linear gradient
};
```

#### Design a Progress Bar / Stepper with configurable steps and validation logic.

**Requirements**: Show a multi‑step process (e.g., form steps). Each step can have validation before proceeding. Visual indication of completed/active/pending steps.

**Design**:
- **Props**: `steps` array (each with label, component), `validateStep` function per step, `onComplete`.
- **State**: `currentStep`, `stepData` (collected data).
- **Behavior**: When user clicks “Next”, run validation; if passes, move to next step. When “Previous”, go back. On last step, call `onComplete`.
- **Styling**: Use CSS classes for step indicators (completed, active, pending). Use `flex` or `grid`.

**Implementation**:
```jsx
const Stepper = ({ steps, onComplete }) => {
  const [current, setCurrent] = useState(0);
  const [data, setData] = useState({});
  const handleNext = async () => {
    const isValid = await steps[current].validate?.(data);
    if (isValid !== false) {
      if (current === steps.length - 1) onComplete(data);
      else setCurrent(prev => prev + 1);
    }
  };
  // render step content and navigation
};
```

#### Design a Modal/Dialog component – focus trapping, accessibility, backdrop behavior.

**Requirements**: Modal that traps focus, is keyboard accessible (ESC to close), has backdrop, and is accessible.

**Design**:
- **Props**: `isOpen`, `onClose`, `title`, `children`, `closeOnBackdropClick`, `closeOnEsc`.
- **Focus trapping**: Use `useEffect` to move focus to the first focusable element inside modal on open, and restore focus to the trigger on close. Use a ref to track focusable elements.
- **Accessibility**: Set `role="dialog"`, `aria-modal="true"`, `aria-labelledby` referencing title. Ensure backdrop is inert to screen readers.
- **Backdrop**: Render a semi‑transparent overlay; on click, call `onClose` if `closeOnBackdropClick`.
- **Portal**: Render modal at the end of the `body` using `ReactDOM.createPortal` to avoid stacking issues.

**Implementation**:
```jsx
const Modal = ({ isOpen, onClose, children }) => {
  useEffect(() => {
    const handleEsc = (e) => { if (e.key === 'Escape') onClose(); };
    if (isOpen) {
      document.addEventListener('keydown', handleEsc);
      // trap focus logic
    }
    return () => document.removeEventListener('keydown', handleEsc);
  }, [isOpen, onClose]);

  if (!isOpen) return null;
  return ReactDOM.createPortal(/* modal JSX */, document.body);
};
```

#### Design a Toggle / Switch component – controlled vs uncontrolled patterns.

**Requirements**: A switch that can be controlled (value passed from parent) or uncontrolled (internal state). Support `onChange` callback.

**Design**:
- **Uncontrolled**: Internal `useState`, initial value from `defaultChecked`.
- **Controlled**: Parent manages value via `checked` prop; component becomes read‑only to parent updates.
- **Both patterns**: Check if `checked` prop is defined; if yes, use controlled; otherwise use internal state.
- **Accessibility**: `role="switch"`, `aria-checked`, keyboard support (Space/Enter).
- **Styling**: Use CSS pseudo‑elements for slider effect.

```jsx
const Toggle = ({ checked: controlledChecked, defaultChecked = false, onChange }) => {
  const [internalChecked, setInternalChecked] = useState(defaultChecked);
  const isControlled = controlledChecked !== undefined;
  const current = isControlled ? controlledChecked : internalChecked;

  const handleToggle = () => {
    const newValue = !current;
    if (!isControlled) setInternalChecked(newValue);
    onChange?.(newValue);
  };
  return <button role="switch" aria-checked={current} onClick={handleToggle} />;
};
```

#### Design a Dropdown / Select component with keyboard navigation and accessibility.

**Requirements**: Custom dropdown that supports selection, keyboard navigation (arrow keys, Enter, Esc), and ARIA attributes.

**Design**:
- **Structure**: Button (trigger) + popup list. Use `role="combobox"`, `aria-expanded`, `aria-haspopup="listbox"`.
- **Keyboard**:
  - Arrow down/up: move focus through options, update `aria-activedescendant`.
  - Enter/Space: select focused option.
  - Esc: close without selection.
- **Focus management**: Keep focus on the trigger; manage active descendant.
- **Virtualization** if many options.
- **Outside click**: Use `useRef` and event listener to close when clicking outside.
- **Portal** for popup to avoid overflow clipping.

**Implementation**:
```jsx
const Dropdown = ({ options, value, onChange }) => {
  const [isOpen, setIsOpen] = useState(false);
  const [highlightedIndex, setHighlightedIndex] = useState(-1);
  // handle keyboard events
  // render button and list with aria attributes
};
```

---

### State, Data & UI Systems

#### Design a Posts with Comments system – how do you manage deeply nested data?

**Requirements**: Display posts, each with comments, comments may have nested replies.

**Design**:
- **Data structure**: Use normalized state (e.g., entities for posts, users, comments). Store comments as map with parent references. Build tree on demand.
- **State management**: Redux Toolkit with `createEntityAdapter` for normalized data. Or use React Query for server state and local state for UI.
- **Rendering**: Recursive component for comment tree. Use memoization to avoid re‑renders on deep trees.
- **Optimistic updates**: When adding comment, update local state immediately, then sync with server.
- **Performance**: Use virtual scrolling for long comment threads.

#### Design an E-commerce Filter system (price, category, rating) with scalable state updates.

**Requirements**: Multiple filter facets that update product list. Efficient updates and URL sync.

**Design**:
- **State**: Store filter values in a global store (Redux/Zustand) or React context. Use `useReducer` for complex filter logic.
- **Debouncing**: For price slider, debounce updates to avoid excessive API calls.
- **URL sync**: Use `useEffect` to sync filters to URL query params; on page load, parse query to set initial filters.
- **Performance**: Use memoized selectors (Reselect) to compute filtered products; cache API results per filter combination.
- **Scalability**: For large product sets, move filtering to backend; send filter parameters to API.

#### Design a Config-Driven Form Renderer using a JSON schema.

**Requirements**: Render forms from a JSON definition, with validation, conditional fields, and custom components.

**Design**:
- **Schema structure**: `{ fields: [{ name, type, label, validation, conditions, options }] }`.
- **Renderer**: Iterate over fields; map `type` to a React component (text input, select, date picker). Use a component registry.
- **Validation**: Integrate with Zod or Yup; generate validation schema dynamically.
- **Conditional fields**: Use `useWatch` (React Hook Form) to listen to values and filter fields based on conditions.
- **State management**: Use `react-hook-form` for form state and validation.
- **Extensibility**: Allow consumers to pass custom field components.

#### Design a Notification / Toast system with queueing, auto-dismiss, and priority.

**Requirements**: Manage multiple toasts; auto‑dismiss after timeout; queue when limit reached; support priorities (error stays longer, etc.)

**Design**:
- **Store**: Use a state array of notifications, each with id, message, type, priority, timeout.
- **Queue**: When adding, if current visible count >= max, push to queue. On dismiss, show next from queue.
- **Auto‑dismiss**: `setTimeout` per notification; clear on manual close. Higher priority = longer duration.
- **Positioning**: Use portal to render fixed container.
- **API**: `toast.success()`, `toast.error()`, etc., returning dismiss function.

```jsx
const ToastContainer = () => {
  const [notifications, setNotifications] = useState([]);
  const addToast = (toast) => { /* manage queue */ };
  const removeToast = (id) => { /* remove from array and trigger next */ };
  // render list of Toasts
};
```

#### Design a Search with Autocomplete / Typeahead – debouncing, caching, race conditions.

**Requirements**: Input with suggestions, async fetching, prevent out‑of‑order responses.

**Design**:
- **Debouncing**: 300ms delay; cancel previous timer.
- **Caching**: Map (key = query) to suggestions; check cache before fetch.
- **Race condition**: Use request ID or `AbortController`. Each new request aborts previous.
- **Accessibility**: ARIA combobox, listbox, option. Keyboard navigation.
- **Highlighting**: Use `dangerouslySetInnerHTML` or regex replace to highlight matched text.

---

### Performance & Optimization

#### Design a Carousel that can handle 1000+ images efficiently.

**Requirements**: Smooth sliding, load images on demand, avoid memory bloat.

**Design**:
- **Virtualization**: Only render current, previous, next slide (buffer). Use `transform: translateX` for sliding.
- **Lazy loading**: Use `IntersectionObserver` or `loading="lazy"` on images. Preload next image.
- **DOM nodes**: Maintain only a few slide elements; reuse them as index changes.
- **Memory**: Unload images that are far away by removing `src` and letting GC collect.
- **Accessibility**: Keyboard arrows, ARIA roles.

#### Implement Virtual Scrolling for very large lists.

**Requirements**: Efficiently render 100k+ items by only rendering visible portion.

**Design**:
- **Library**: `react-window` or `react-virtualized`.
- **Manual implementation**:
  - Compute total height = itemHeight * itemCount.
  - Track scrollTop; calculate start index = floor(scrollTop / itemHeight), end index = start + visibleCount + buffer.
  - Render only those items, absolutely positioned or using `transform: translateY`.
  - Use `useRef` to listen to scroll events and throttle.

**Edge cases**: Variable heights require measuring each item; libraries handle that.

#### Design an Image Gallery with lazy loading and skeleton placeholders.

**Requirements**: Grid of images, load as user scrolls, show skeleton while loading.

**Design**:
- **Lazy loading**: Use `IntersectionObserver` to set `src` when image enters viewport. Fallback `loading="lazy"` for simpler.
- **Skeletons**: Show a placeholder div with the same dimensions (aspect ratio) and a pulse animation.
- **Responsive**: Use CSS Grid or flex with `object-fit: cover`.
- **Error handling**: On error, show broken image icon.
- **Performance**: Use `srcset` for responsive images, WebP format.

#### Design a Data Table with sorting, filtering, pagination, and performance trade-offs.

**Requirements**: Table with large datasets, support sorting on columns, filtering, pagination.

**Design**:
- **Data fetching**: Choose client‑side (if dataset manageable) or server‑side (if huge). Server‑side reduces memory but increases network calls.
- **State**: Store current page, page size, sort column/direction, filters.
- **Rendering**: Virtualize rows if many visible at once. Use `React.memo` for rows.
- **Sorting**: On column click, update state; if server‑side, fetch new data; if client‑side, sort array (memoize).
- **Filtering**: Text inputs with debounce; if client‑side, filter array.
- **Trade‑offs**: Client‑side allows instant filtering/sorting but limits data size. Server‑side more scalable but adds latency.

#### Implement Debouncing and Throttling in a search or scroll-heavy component.

**Debouncing** (search input):
```jsx
const debouncedSearch = useCallback(
  debounce((query) => { /* fetch */ }, 300),
  []
);
const handleChange = (e) => debouncedSearch(e.target.value);
```

**Throttling** (scroll event):
```jsx
const throttledScroll = useCallback(
  throttle(() => { /* handle scroll */ }, 200),
  []
);
useEffect(() => {
  window.addEventListener('scroll', throttledScroll);
  return () => window.removeEventListener('scroll', throttledScroll);
}, []);
```

#### Design a File Upload component with progress tracking and chunked uploads.

**Requirements**: Upload large files in chunks, show progress, pause/resume, retry.

**Design**:
- **Chunking**: Split file into chunks (e.g., 1MB). Maintain array of chunks and uploaded flags.
- **Upload loop**: Send chunks sequentially; track progress (uploaded bytes / total bytes). Use `fetch` with `AbortController` for cancel.
- **Resume**: Store chunk state in `localStorage`/IndexedDB; on resume, start from first missing chunk.
- **Retry**: On chunk failure, retry with exponential backoff.
- **Progress**: Use `setState` to update progress bar.
- **UI**: Display file name, overall progress, cancel/pause buttons.

#### How do you detect and prevent memory leaks in long-running SPAs?

**Detection**:
- Chrome DevTools Memory tab: Take heap snapshots before and after actions; look for retained objects.
- Use `performance.memory` (Chrome) to monitor heap size over time.
- Check for detached DOM elements (elements removed from DOM but still referenced in JS).

**Prevention**:
- Cleanup `setInterval`/`setTimeout` in `useEffect` cleanup.
- Remove event listeners in cleanup.
- Cancel fetch requests with `AbortController` on unmount.
- Use `WeakMap`/`WeakSet` for caches.
- Avoid storing large objects in closures that outlive their purpose.
- Profile with React DevTools to see if components are being unmounted properly.

---

### Architecture & Scalability

#### How would you design a theme-able, extensible component library?

**Design**:
- **Styling**: Use CSS custom properties (variables) for theming. Provide default theme values.
- **Theme provider**: Use React Context to pass a theme object (colors, spacing, typography) to all components.
- **Component API**: Support `className` and `style` props for overrides. Use `polymorphic` components (`as` prop).
- **Extensibility**: Expose base components that can be composed. Allow consumers to pass custom render props.
- **Documentation**: Storybook with interactive examples and theme switching.
- **Tree shaking**: Use ES modules and named exports; configure bundler to eliminate unused components.

#### How do you structure a large-scale React application across multiple teams?

**Structure**:
- **Monorepo** (e.g., Nx, Turborepo) with packages for shared UI, utils, hooks.
- **Feature‑based folder structure** (e.g., `features/auth`, `features/dashboard`). Each feature contains its own components, logic, tests.
- **Shared libraries**: UI components, API clients, types, constants.
- **Routing**: Central routing with lazy loading of features.
- **State management**: Use a global store (Redux) for shared state; feature‑local state where possible.
- **Team autonomy**: Teams own their features; they can release independently with Module Federation or versioned packages.
- **Code review and standards**: ESLint, Prettier, TypeScript strict.

#### Design a state management solution for a complex analytics/dashboard app.

**Requirements**: Real‑time data, multiple widgets, filters that affect many components.

**Design**:
- **Store**: Redux Toolkit with slices for:
  - Filters (global time range, date picker)
  - Widget data (each widget’s data, loading, error)
  - User preferences
- **Normalization**: Use `createEntityAdapter` for time‑series data.
- **Async**: `createAsyncThunk` for API calls; caching with `selectors` that return memoized data.
- **WebSocket integration**: Middleware that dispatches actions on incoming messages.
- **Performance**: Use `useSelector` with shallow equality or memoized selectors. Use `React.memo` for widgets.
- **Derived data**: Use Reselect to compute aggregated metrics only when raw data changes.

#### How would you implement SSR for a React application?

**Approaches**:
- **Frameworks**: Next.js (recommended), Remix, or custom Node server with React’s `renderToString`/`renderToPipeableStream`.
- **Data fetching**: Fetch data on the server (e.g., `getServerSideProps` in Next.js) and pass it as props to the component.
- **Hydration**: Server‑rendered HTML is sent to client; React attaches event listeners and reconciles.
- **Performance**: Use streaming SSR (`renderToPipeableStream`) for faster TTFB.
- **Caching**: Use CDN caching with `stale-while-revalidate` for pages.
- **Challenges**: Ensure server and client environment compatibility (avoid `window` usage in server). Use `useEffect` for client‑only code.

---

This comprehensive guide covers the most common component design questions with practical considerations and implementation insights. Each design can be expanded with full code examples, but the key is to understand the trade‑offs, accessibility, performance, and scalability aspects.

## Real-World Scenarios & Problem Solving

### Memory Leak: You notice a memory leak in a production SPA – how do you identify and fix it?

**Identify**:
- Use Chrome DevTools **Memory** tab: take heap snapshots before and after the suspected user actions (e.g., opening/closing a modal, navigating between pages). Compare snapshots to see which objects are retained.
- Look for **detached DOM nodes** – elements removed from the DOM but still referenced in JavaScript (e.g., event listeners not cleaned, closures holding references).
- Monitor `performance.memory` in real time to see JS heap growth.
- Use the **Performance** tab with “Memory” checkbox to correlate memory usage with actions.

**Common causes**:
- Event listeners not removed on component unmount.
- `setInterval` / `setTimeout` not cleared.
- WebSocket connections not closed.
- Large data structures kept in global state or closures.
- Forgotten subscriptions (e.g., to observables).

**Fix**:
- Add cleanup functions in `useEffect` (return function).
- Use `AbortController` for fetch requests.
- Use `WeakMap` / `WeakSet` for caches.
- Ensure global event listeners are removed.
- Use React DevTools profiler to detect unmounted components that are still referenced.
- Consider using a tool like `why-did-you-render` to spot accidental retention.

---

### Library Upgrade: A component breaks when upgrading a library version – how do you manage dependencies?

**Approach**:
1. **Read release notes** and changelogs carefully for breaking changes.
2. **Test in isolation** – create a branch, upgrade the library, run tests, and manually test affected components.
3. **Use dependency management tools** – `npm outdated` to see which libraries can be upgraded. `npm audit` for security.
4. **Pin exact versions** in `package.json` for critical libraries to avoid unexpected upgrades.
5. **Use version ranges** for non‑critical ones, but lock with `package-lock.json` or `yarn.lock`.
6. **Implement abstraction** – wrap external libraries in your own adapter components to isolate changes.
7. **Stagger upgrades** – upgrade one library at a time to isolate issues.
8. **Rollback** – if a critical break occurs, revert the version and investigate later.

**For major upgrades** (e.g., React 16 → 17 → 18):
- Use codemods (like `react-codemod`) to automate migration.
- Run in development mode to catch deprecation warnings.
- Test across all browsers and devices.

---

### UI Glitches: Users report intermittent UI glitches in different browsers – how do you troubleshoot?

**Process**:
1. **Reproduce** the issue consistently if possible. Use browser dev tools to emulate different devices and network conditions.
2. **Check browser console** for JavaScript errors or warnings that correlate with the glitch.
3. **Use remote debugging** – tools like BrowserStack, Sauce Labs, or real devices to test across environments.
4. **Look at rendering issues**:
   - Use the **Rendering** tab in DevTools (paint flashing, layout shifts).
   - Check for **CSS compatibility** (vendor prefixes, unsupported properties).
   - Verify that animations use `transform` and `opacity` to avoid repaints.
5. **Inspect event handlers** – might be conflicting or firing multiple times.
6. **Check for race conditions** in asynchronous code – ensure that UI updates are idempotent and handle out‑of‑order responses.
7. **Collect logs** – implement telemetry to capture console logs, network errors, and user actions.
8. **Consider browser extensions** that might interfere; test in incognito mode.

---

### Peak Traffic Failure: A critical UI feature fails during peak traffic – how do you mitigate?

**Immediate actions**:
- **Rollback** the recent deployment if it correlates with the failure.
- **Scale up** server resources (if backend) or enable more CDN edge nodes.
- **Feature flag** – disable the failing feature remotely to restore core functionality.
- **Switch to a fallback UI** – show a degraded experience (e.g., static placeholder) until the issue is resolved.

**Long‑term**:
- **Load testing** – simulate high traffic before release (tools: k6, Artillery).
- **Implement caching** at multiple layers (CDN, browser, server).
- **Use circuit breakers** for external API calls to prevent cascading failures.
- **Ensure the frontend can degrade gracefully** – e.g., show skeleton loaders, retry mechanisms.
- **Monitor** key metrics (error rates, latency) and set up alerts.

---

### Debugging Production: How would you debug production issues methodically? (reproduce, logs, profiling, rollback)

**Systematic approach**:
1. **Gather information** – user reports, timestamps, affected browsers, reproduction steps.
2. **Check monitoring tools** (Sentry, Datadog, New Relic) for errors, stack traces, and performance metrics.
3. **Reproduce locally** – use the exact version (with source maps) to mimic the environment.
4. **Enable verbose logging** (if safe) to capture state at the moment of failure.
5. **Use remote debugging** – tools like Chrome DevTools on Android devices, or Safari Web Inspector for iOS.
6. **Profile performance** – use the **Performance** tab in Chrome DevTools to capture a trace from a real user (if possible via remote tools).
7. **Rollback** to a known‑good version if the issue is urgent and a fix isn’t immediate.
8. **Post‑mortem** – analyze root cause, write tests to prevent regression.

---

### When NOT to use JavaScript: CPU-heavy tasks, long-running blocking logic – use backend or workers.

**Scenarios**:
- **Large data processing** (sorting, filtering, complex calculations) – offload to Web Workers or the backend.
- **Image/video processing** – use backend services or Canvas + WebGL with off‑thread rendering.
- **Intensive animations** – use CSS animations/transitions instead of JS, or requestAnimationFrame with careful batching.
- **Real‑time ML inference** – consider WebAssembly or backend.

**Why**:
- JavaScript runs on the main thread; blocking it leads to jank, unresponsiveness.
- Web Workers run in a separate thread, allowing parallel execution without blocking UI.
- Backend offloading is ideal for heavy or security‑sensitive tasks.

---

### Authentication Token Expiry: How do you handle token expiry mid-session? (interceptors, refresh token, queue requests)

**Strategy**:
- Use **axios interceptors** or custom fetch wrapper to catch 401 responses.
- On 401, attempt to **refresh the token** using a refresh token (stored securely, e.g., httpOnly cookie).
- **Queue pending requests** while refreshing to avoid multiple refresh calls.
- After successful refresh, retry the queued requests with the new token.
- If refresh fails, redirect to login page.
- Use **short‑lived access tokens** and refresh them before expiry (e.g., using a timer).

**Implementation**:
```javascript
let isRefreshing = false;
let refreshSubscribers = [];

const onRefreshed = (token) => {
  refreshSubscribers.forEach(cb => cb(token));
  refreshSubscribers = [];
};

const refreshToken = async () => {
  if (!isRefreshing) {
    isRefreshing = true;
    try {
      const newToken = await getNewToken();
      setToken(newToken);
      onRefreshed(newToken);
    } catch (err) {
      redirectToLogin();
    } finally {
      isRefreshing = false;
    }
  }
  return new Promise(resolve => {
    refreshSubscribers.push(resolve);
  });
};
```

---

### Multiple API Calls: How to load a dashboard with independent APIs efficiently? (Promise.all, allSettled)

**Options**:
- **`Promise.all`** – if all calls must succeed for the dashboard to render. Fails fast if any fails.
- **`Promise.allSettled`** – if you want to load independent widgets, each can show its own error state. Waits for all calls to complete (or fail) before rendering.
- **`Promise.race`** – rarely used; for timeouts.

**Implementation**:
```javascript
useEffect(() => {
  const fetchData = async () => {
    setLoading(true);
    const results = await Promise.allSettled([
      fetch('/api/users'),
      fetch('/api/stats'),
      fetch('/api/notifications')
    ]);
    // process each result: if fulfilled, set data; if rejected, set error
    setLoading(false);
  };
  fetchData();
}, []);
```

**Performance**:
- Consider **parallel requests** with `Promise.all` for speed.
- Use **React Query** or **SWR** for automatic caching and retries.

---

### Large List Rendering: 10k+ items cause UI lag – optimization strategies.

**Strategies**:
- **Virtualization** – render only visible items (react-window, react-virtualized). This reduces DOM nodes dramatically.
- **Windowing** – same concept, often used interchangeably.
- **Pagination** – load data in pages; combine with virtualization if needed.
- **Infinite scroll** – load more as user scrolls.
- **Memoization** – wrap each row with `React.memo` to avoid re‑renders.
- **Debounce scroll events** if using custom virtualization.

**Example**:
```jsx
import { FixedSizeList as List } from 'react-window';
const Row = ({ index, style }) => <div style={style}>Item {index}</div>;
<List height={600} itemCount={10000} itemSize={35} width={300}>
  {Row}
</List>
```

---

### Context Re-renders: Context API causes frequent re-renders – why and how to fix?

**Why**:
- When the context value changes, **all consumers** re‑render, regardless of which part of the value they use.
- If the context value is an object that is re‑created on each render (e.g., `<Provider value={{ user, setUser }}>`), every consumer re‑renders.

**Fixes**:
- **Memoize the context value** with `useMemo`.
- **Split contexts** into smaller pieces (e.g., `UserContext`, `ThemeContext`) so consumers only subscribe to what changes.
- Use **`useContextSelector`** (if using a library like `use-context-selector`) to subscribe only to specific parts.
- Move state down to the components that actually need it (colocate state).

**Example**:
```jsx
const value = useMemo(() => ({ user, setUser }), [user]);
<Provider value={value}>{children}</Provider>
```

---

### Component Re-renders Unexpectedly: Component re-renders even when props don't change – hidden reasons.

**Common hidden reasons**:
- **Parent re‑renders** – by default, a component re‑renders when its parent re‑renders, even if props are identical. Fix: use `React.memo`.
- **Inline functions/objects** passed as props create new references each render. Fix: use `useCallback` and `useMemo`.
- **Context changes** – if the component consumes any context, a context update triggers re‑render.
- **State updates that set the same value** – React 18 may still re‑render even if value hasn’t changed (though it usually doesn’t for primitive values).
- **Key changes** – if a component’s key changes, React treats it as a new component and unmounts/mounts.

**Debug**:
- Use `why-did-you-render` library to log prop changes.
- Use React DevTools Profiler to see why a component rendered (highlight updates).

---

### Poor SEO & Slow TTI: React app has poor SEO and slow TTI – frontend-level solutions.

**SEO issues**:
- **Server‑Side Rendering (SSR)** or **Static Site Generation (SSG)** with frameworks like Next.js.
- Ensure meta tags (title, description, Open Graph) are rendered on the server.
- Use semantic HTML.

**Slow TTI (Time to Interactive)**:
- **Code splitting** – lazy load non‑critical components and routes.
- **Bundle optimization** – tree shaking, minification, remove unused dependencies.
- **Reduce JavaScript** – audit bundle size, use lightweight alternatives.
- **Prioritize critical CSS** – inline above‑the‑fold styles, defer non‑critical CSS.
- **Use `preconnect` and `preload`** for important resources.
- **Optimize images** – use modern formats, responsive sizes.
- **Lazy load off‑screen images**.
- **Service Worker** for caching assets.

---

### Real-time Updates: How to handle real-time updates efficiently in React?

**Approaches**:
- **WebSockets** (or Socket.io) for low‑latency bidirectional communication.
- **Server‑Sent Events (SSE)** for server‑to‑client streaming.
- **Polling** as fallback (with exponential backoff).

**Efficiency**:
- **Throttle UI updates** – use `requestAnimationFrame` or `useDeferredValue` (React 18) to avoid blocking the main thread.
- **Batch updates** – group multiple incoming messages into a single state update.
- **Use `useReducer`** with a reducer that merges data intelligently.
- **Memoize components** to avoid re‑rendering everything on every update.
- **Virtualization** for real‑time lists (e.g., live feeds).

**Example WebSocket hook**:
```javascript
const useWebSocket = (url) => {
  const [data, setData] = useState(null);
  useEffect(() => {
    const ws = new WebSocket(url);
    ws.onmessage = (event) => {
      setData(JSON.parse(event.data));
    };
    return () => ws.close();
  }, [url]);
  return data;
};
```

---

### A/B Testing: How to implement A/B testing without affecting current users?

**Implementation**:
- Use a feature flag service (e.g., LaunchDarkly, Optimizely) that can assign users to variants.
- **Variant assignment** – deterministic based on user ID or cookie, so users see consistent experience.
- **Initialization** – fetch assignment early (e.g., on app boot) and store in context.
- **Render conditionally** based on variant.
- **Avoid layout shift** – ensure that variant components have the same dimensions as the control.
- **Analytics** – track which variant users saw to measure impact.

**For performance**:
- Use asynchronous loading of the testing SDK.
- Consider server‑side assignment if using SSR.

---

### CSS Animation Jank: A CSS animation is janky on mobile – how to identify and fix?

**Identify**:
- Use Chrome DevTools **Performance** tab, record while animation runs.
- Look for long **Layout** or **Paint** events. If they appear during animation, the property being animated is causing layout recalculations.
- Enable **Paint flashing** and **Layout Shift Regions** to visualize repaints.

**Common causes**:
- Animating properties that trigger layout (e.g., `width`, `height`, `top`, `left`).
- Heavy JavaScript executing on the main thread during animation.
- Missing `will-change` hint for animated elements.
- Compositing issues (e.g., elements not on their own layer).

**Fixes**:
- Animate only **`transform`** and **`opacity`** – these are handled by the compositor thread.
- Use `will-change: transform` for elements you intend to animate, but sparingly to avoid memory overhead.
- Move heavy JavaScript out of animation frames (use `requestAnimationFrame` with throttling).
- Ensure animated elements are in a separate compositing layer (by using `transform: translateZ(0)` or `will-change`).
- Test on real mobile devices with throttled CPU.

---

This guide provides a practical, actionable approach to common real‑world frontend challenges. Each scenario emphasizes systematic diagnosis and proven mitigation techniques.

## Behavioral & Hiring Manager Questions

Behavioral questions are designed to understand your past experiences, decision‑making, communication, and leadership skills. Use the **STAR method** (Situation, Task, Action, Result) to structure your answers. Below are guidelines and example responses for each question.

---

### Explain a frontend project you built end‑to‑end.

**Approach**: Choose a project that showcases your full‑stack thinking, technical depth, and ownership. Describe the problem, your role, the technologies used, and the impact.

**Example**:
> “I led the development of a real‑time dashboard for monitoring customer support metrics. The problem was that the existing dashboard had 10‑second delays and could not handle concurrent users during peak hours.
>
> **My role**: I was the sole frontend developer, collaborating with two backend engineers and a product manager.
>
> **Tech stack**: React with Redux Toolkit for state, WebSockets for real‑time data, and Chart.js for visualizations. I implemented virtual scrolling for the activity log (10k+ rows) and used Web Workers to offload data aggregation.
>
> **Challenges**: We had to handle high‑frequency updates (100 events per second). I batched WebSocket messages and used `useDeferredValue` to avoid jank.
>
> **Result**: The dashboard loaded in under 2 seconds, rendered smoothly on low‑end devices, and reduced average issue resolution time by 30% because support agents could see live data.”

---

### Describe the hardest production bug you fixed.

**Approach**: Focus on a bug that was elusive, required deep investigation, and had significant impact. Explain your diagnostic process and the fix.

**Example**:
> “We had a memory leak in a single‑page application that caused the browser to crash after about an hour of usage. It was hard to reproduce because it only happened when users navigated through many screens.
>
> **Process**:
> 1. I used Chrome DevTools Memory tab to take heap snapshots before and after navigation. I noticed detached DOM nodes accumulating.
> 2. I traced them to a custom modal component that added a global scroll‑block event listener but never removed it on unmount. The listener kept a reference to the modal’s DOM element.
> 3. I also discovered a `setInterval` in a chart component that wasn’t cleared, holding onto large data arrays.
>
> **Fix**: I added cleanup functions in `useEffect` for both issues. I also introduced a custom ESLint rule to enforce cleanup for all timers and event listeners.
>
> **Result**: The memory leak was eliminated, and the app remained stable for days. The incident taught us to enforce cleanup patterns and use heap snapshots in our testing.”

---

### How do you balance performance vs feature delivery?

**Approach**: Show that you prioritize based on impact, data, and business goals. You don’t over‑optimize prematurely but make performance a non‑negotiable for critical user flows.

**Example**:
> “I treat performance as a feature, not an afterthought. I balance by:
> - **Setting performance budgets** early (e.g., bundle size, Time to Interactive). If a new feature threatens to exceed the budget, we discuss trade‑offs.
> - **Using data** – I check Lighthouse scores and Core Web Vitals. If a feature is critical for conversion (e.g., checkout), I allocate extra time for optimization.
> - **Deferring non‑critical optimizations** – for internal tools, we may accept slightly slower load times if it accelerates delivery, but we always track regressions.
> - **Iterative improvement** – we release a feature, monitor real‑user metrics, and then optimize if needed. This prevents over‑engineering while maintaining a fast baseline.”

---

### How do you handle disagreements in technical decisions?

**Approach**: Emphasize collaboration, data‑driven reasoning, and maintaining positive relationships. Show that you can advocate for your view while being open to alternatives.

**Example**:
> “I believe healthy disagreements lead to better solutions. I handle them by:
> - **Understanding the other person’s perspective** – I ask questions to uncover their concerns and constraints.
> - **Gathering evidence** – I prototype both approaches, run benchmarks, or present data (e.g., bundle size, render performance) to support my case.
> - **Focusing on the problem, not the person** – I frame the discussion around technical trade‑offs, not ego.
> - **Escalating when necessary** – if we cannot agree, I propose a quick spike or bring in a third team member. Ultimately, I respect the decision of the team lead or architect.
>
> For example, we debated whether to use Redux or Context for a new feature. I preferred Redux for predictability and DevTools, while another developer wanted Context to reduce boilerplate. I built a small prototype showing that Context caused unnecessary re‑renders because the state changed frequently. After seeing the data, we agreed on Redux Toolkit, which satisfied both concerns.”

---

### When did you get stuck while using React, and how did you fix it?

**Approach**: Describe a technical problem that had you stuck for a while, how you debugged it, and what you learned.

**Example**:
> “I was building a drag‑and‑drop kanban board with React. The issue was that after dropping a card, the state updated correctly, but the card would visually jump back to its original position for a split second before snapping to the new column.
>
> **What I tried**: I checked the reducer, verified that the state was immutable, and used `React.memo` on the card components. Nothing worked.
>
> **How I fixed it**: I realized that the drag library I was using (`react-dnd`) was updating the DOM imperatively during the drag. After the drop, React would reconcile its virtual DOM and reset the card’s inline styles. I solved it by resetting the drag preview style in a `useLayoutEffect` after the state update, ensuring that React’s reconciliation happened after the drop animation.
>
> **Lesson**: I learned that mixing imperative DOM manipulation (like drag libraries) with React’s declarative model requires careful timing. I also became more proficient in `useLayoutEffect` and the React lifecycle.”

---

### Have you led a team? What is your current role?

**Approach**: Be honest about your level of leadership. If you haven’t formally led, talk about technical leadership, mentoring, or owning significant features.

**Example** (senior individual contributor):
> “In my current role as Senior Frontend Engineer, I don’t have direct reports, but I lead the frontend guild of 6 engineers. I drive architectural decisions, set coding standards, and conduct code reviews. I also mentor two junior developers through weekly 1:1s and pair programming. I’ve been responsible for breaking down epics into tasks and leading the implementation of our design system.”

**Example** (team lead):
> “I’ve been a Frontend Tech Lead for the past two years, leading a team of 4 frontend engineers. I handle sprint planning, technical design reviews, and cross‑team coordination. I’m also responsible for hiring, performance reviews, and fostering a culture of continuous improvement.”

---

### Have you handled task distribution and requirement breakdown?

**Approach**: Show your ability to translate high‑level requirements into actionable tasks, estimate effort, and distribute work based on team skills.

**Example**:
> “Yes, regularly. When we receive a feature request, I first clarify requirements with the product manager and designer. Then I break it down into smaller tasks (e.g., API integration, UI components, state management, tests, accessibility). I estimate each task using t‑shirt sizing or story points.
>
> During sprint planning, I facilitate the team to pick tasks based on capacity and skill set. I ensure that dependencies are identified and that parallel work is possible. I also track progress in Jira and adjust assignments if someone is blocked.
>
> For example, when we built a new checkout flow, I decomposed it into 12 tasks, assigned two engineers to work on different parts (one on the payment form, one on the order summary), and handled the API integration myself because I had prior experience with the payment gateway.”

---

### Have you been involved in architectural or technical decision-making?

**Approach**: Highlight specific decisions you influenced, the trade‑offs considered, and the outcome.

**Example**:
> “Yes, I’ve been part of several architectural decisions:
> - **State management**: When we started a new product, I proposed using Redux Toolkit over plain Redux because it reduced boilerplate and aligned with our team’s familiarity. I led a proof of concept and convinced the team.
> - **Monorepo adoption**: I championed moving our five separate frontend projects into a single Nx monorepo. I demonstrated how it would improve code sharing, simplify dependency management, and speed up CI with affected builds. After a trial, we adopted it and saw a 30% reduction in build times.
> - **Design system**: I helped architect our component library with CSS modules and theming support, making it reusable across multiple teams.”

---

### How do you mentor juniors through code walkthroughs, tech spikes, and 1:1s?

**Approach**: Describe specific mentoring practices that help juniors grow.

**Example**:
> “I believe in building confidence and ownership. For **code walkthroughs**, I ask juniors to explain their solution first, then I ask open‑ended questions like ‘What edge cases did you consider?’ or ‘How could we make this more testable?’ rather than simply pointing out issues. I also do live pair programming on complex tasks.
>
> **Tech spikes**: I assign small spikes (e.g., ‘evaluate React Query for data fetching’) with a clear goal and timebox. After the spike, we do a knowledge‑sharing session where they present findings. This builds research skills and ownership.
>
> **1:1s**: I keep them focused on career goals, blockers, and growth areas. I also encourage juniors to lead small features with my support, gradually increasing responsibility. I always celebrate their wins publicly to build confidence.”

---

### Do you have any questions for me?

**Approach**: Always have questions ready. This shows engagement and helps you evaluate if the role is a good fit. Tailor questions to the interviewer (hiring manager, engineer, etc.).

**Good questions**:

- **For hiring manager**:
  - “What are the biggest challenges the frontend team is currently facing?”
  - “How do you measure success for this role in the first 90 days?”
  - “What does career progression look like for frontend engineers here?”
  - “How does the team balance technical debt vs new features?”

- **For engineer**:
  - “What is the development workflow like? How do you test and deploy?”
  - “What is your approach to code reviews and collaboration?”
  - “Can you describe the most interesting technical problem the team solved recently?”

- **General**:
  - “What is the team’s culture like? How do you handle disagreements?”
  - “How does the company support continued learning and professional development?”
  - “What are you most excited about that the team will work on in the coming year?”

Avoid asking about salary/benefits in the first interview unless the interviewer brings it up. Instead, focus on role, team, and growth.

---

### Final Tips for Behavioral Interviews

1. **Be specific** – Use concrete examples with metrics when possible.
2. **Show impact** – Highlight how your actions improved user experience, team productivity, or business outcomes.
3. **Be honest** – If you haven’t done something, say so and explain how you’d approach it or what you’d like to learn.
4. **Stay positive** – When discussing challenges, focus on what you learned and how you grew, not on blaming others.
5. **Practice** – Rehearse your STAR stories out loud so they sound natural and concise.

## Frontend Architecture & Team Leadership

These questions assess your ability to design scalable systems, lead teams, and manage technical strategy. Use concrete examples from your experience, and emphasize trade‑offs and measurable outcomes.

---

### How would you structure a micro‑frontend architecture for team autonomy?

**Goal**: Enable independent teams to develop, test, and deploy their parts of the frontend without coordination bottlenecks.

**Approaches**:
- **Build‑time integration (Module Federation)** – Each team builds a separate bundle; a host application loads them at runtime via Webpack 5 Module Federation. Teams release independently, and versioning is handled via semantic versioning or by exposing a manifest.
- **Runtime integration (iframes / Web Components)** – Iframes provide strong isolation but come with communication overhead. Web Components can be used to encapsulate frameworks; they can be loaded dynamically and work across frameworks.
- **Composition via API Gateway** – A backend‑for‑frontend (BFF) layer composes micro‑frontend fragments on the server and serves them as HTML.

**Key design decisions**:
- **Shared libraries** – Use a monorepo (e.g., Nx) to manage shared UI components, utilities, and types. Teams consume them as packages. Avoid global state between micro‑frontends; use custom events or a lightweight pub/sub for cross‑app communication.
- **Routing** – The host handles top‑level routing and passes control to the appropriate micro‑frontend for sub‑routes. This can be achieved by using a base path per team.
- **Team autonomy** – Each team owns its codebase, CI/CD pipeline, and deployment. The host application defines contracts (e.g., the shape of exported components, expected CSS namespacing) to ensure safe composition.
- **Testing** – Each micro‑frontend is tested in isolation. Integration tests verify that the host correctly loads them and that they work together.

**Challenges**:
- **Performance** – Loading multiple bundles can increase initial load time; use code splitting, preloading, and caching strategies.
- **Consistency** – Enforce design system adoption through shared components and linting.
- **Security** – Ensure iframes have proper sandboxing; avoid exposing sensitive data across boundaries.

**Example**:
> “We adopted Module Federation with a host app that provided the layout and authentication. Each team had a separate repo, built their app, and deployed it to a CDN. The host fetched a manifest listing available versions and loaded the required micro‑frontend on navigation. We used a shared UI library published to npm, and communication was done via custom events for cross‑app actions like logging out.”

---

### Describe your process for creating and enforcing a scalable design system across distributed teams.

**Goal**: Maintain UI consistency, reduce duplication, and speed up development across many teams.

**Process**:

1. **Discovery & Alignment** – Identify common UI patterns by auditing existing applications. Form a working group with representatives from each team to agree on principles (accessibility, responsiveness, theming).

2. **Component Library Development** – Build components using a framework‑agnostic approach (e.g., CSS modules with CSS variables, or a framework‑specific library like React). Start with the most used components (button, input, modal). Document API, variants, and usage guidelines in Storybook.

3. **Governance** – Establish a review process for new components: they must meet accessibility standards, pass performance benchmarks, and have cross‑browser tests. A dedicated team or a rotating group of “component stewards” manages contributions and ensures consistency.

4. **Enforcement** – Use tooling to enforce adoption:
   - **ESLint plugins** – Custom rules that warn when using native elements instead of design system components.
   - **Stylelint** – Ensure CSS custom properties are used instead of hard‑coded values.
   - **Pre‑commit hooks** – Run linting and formatting.
   - **CI checks** – Fail builds if components are used incorrectly.

5. **Versioning & Distribution** – Publish the design system as an npm package (or multiple packages). Use semantic versioning; communicate breaking changes via release notes and deprecation warnings.

6. **Adoption & Training** – Hold office hours, write migration guides, and create a dedicated Slack channel. Pair with teams during their first adoption sprints.

7. **Continuous Improvement** – Collect feedback, track usage metrics (via tooling like `npm` downloads or bundle analysis), and iterate.

**Example**:
> “I led the creation of a React design system used by 8 teams. We started with a component inventory, built a Storybook, and created ESLint rules to enforce usage. We published to an internal npm registry and used renovate to keep dependencies up to date. Adoption was driven through bi‑weekly office hours and a dedicated #design‑system channel. Within a year, 90% of components across teams came from the library.”

---

### How do you manage shared libraries and dependencies in a monorepo?

**Goal**: Maximize code reuse while maintaining independent versioning and avoiding dependency hell.

**Approaches**:
- **Monorepo tools** – Use Nx, Turborepo, or pnpm workspaces. These provide dependency graph awareness, build caching, and affected‑only testing.
- **Structure** – Organize packages into `apps/` (applications) and `libs/` (shared code). Each library has its own `package.json`.
- **Versioning** – Decide between fixed versioning (all packages share a version) and independent versioning. Independent versioning allows teams to release only changed libraries, reducing coupling.
- **Dependency management** – Use `pnpm` to avoid duplication; it enforces strict dependency resolution. Use `npm audit` or `snyk` for vulnerability scanning.
- **Upgrades** – Automate dependency updates with Renovate or Dependabot. Test across all affected packages using CI.

**Key considerations**:
- **Avoid circular dependencies** – Enforce with tools like `madge` or ESLint rules.
- **Build caching** – Use Nx or Turborepo to skip rebuilding unchanged libraries.
- **Publishing** – Use changesets to manage versioning and generate changelogs. Publish packages to a registry (private or public).

**Example**:
> “We migrated to an Nx monorepo with 3 applications and 12 shared libraries. We used independent versioning and changesets to manage releases. Developers could run `nx affected:test` to test only changed packages, reducing CI time by 60%. We set up Renovate to keep dependencies updated, with automated PRs that triggered full CI.”

---

### What is your framework for identifying, prioritizing, and reducing technical debt?

**Goal**: Balance short‑term delivery with long‑term maintainability.

**Framework**:

1. **Identify** – Use multiple sources:
   - **Code reviews** – Look for code smells, duplication, outdated patterns.
   - **Static analysis** – ESLint rules, SonarQube, bundle size analysis.
   - **Developer surveys** – Ask the team what slows them down.
   - **Issue tracking** – Label bugs or incidents caused by fragile code.

2. **Categorize** – Classify debt by impact:
   - **Critical** – Causes bugs, security vulnerabilities, or severely impacts productivity.
   - **High** – Hinders new features, increases risk.
   - **Medium** – Makes code harder to understand but not blocking.
   - **Low** – Cosmetic or nice‑to‑have.

3. **Prioritize** – Use a modified Eisenhower matrix (impact vs. effort). Involve product managers to align with business goals. Allocate a percentage of each sprint (e.g., 10‑20%) to debt reduction. Alternatively, schedule dedicated “tech debt sprints” every quarter.

4. **Reduce** – Apply the **Boy Scout Rule**: leave the code better than you found it. For larger items, break them into tasks and track in backlog.
   - **Refactor** – Extract components, improve naming, remove dead code.
   - **Replace** – Swap outdated libraries with modern equivalents.
   - **Automate** – Add tests, linter rules, CI checks.

5. **Monitor** – Track metrics like code coverage, cyclomatic complexity, bundle size over time. Review debt in retrospectives.

**Example**:
> “We had a legacy form component that was used in 50 places but was hard to maintain. I categorized it as high‑impact (it caused many bugs) and moderate effort. We allocated a 3‑day spike to create a new version with proper validation and accessibility. We then migrated one module per sprint, using feature flags to test the new component in production. Within two months, we retired the old component, reducing form‑related bugs by 80%.”

---

### How do you implement scalable code review workflows (linters, pre‑commit hooks, pair programming)?

**Goal**: Maintain code quality while keeping reviews efficient and collaborative.

**Layers**:

1. **Automated checks** – Run before code reaches reviewers:
   - **Pre‑commit hooks** (Husky) – linting, formatting, type checking, unit tests.
   - **CI pipeline** – Build, lint, test, and run security scans on every PR.

2. **Code review process**:
   - **Define review guidelines** – e.g., PR size limit (max 400 lines), required reviewers (at least 2 for core components).
   - **Use review templates** – remind reviewers to check for accessibility, performance, test coverage.
   - **Encourage small PRs** – merge early, use feature flags to hide incomplete work.

3. **Pair programming** – Use for complex features, onboarding, or knowledge sharing. It often reduces the need for extensive reviews later.

4. **Tooling**:
   - **GitHub / GitLab** – Use CODEOWNERS to automatically assign reviewers.
   - **Snyk / Dependabot** – automatically open PRs for security updates.
   - **Lint-staged** – run linters only on changed files to keep pre‑commit fast.

5. **Culture**:
   - **Be respectful** – Use “suggestion” mode, explain reasoning, avoid personal criticism.
   - **Rotate reviewers** – spread knowledge and prevent bottlenecks.
   - **Post‑merge reviews** – for non‑critical changes, allow merging after one approval and then a follow‑up review.

**Example**:
> “We implemented pre‑commit hooks with ESLint, Prettier, and TypeScript. CI ran tests and coverage. PRs required at least two approvals from the relevant CODEOWNERS. For large features, we did mob programming sessions to design the architecture, then divided into small PRs. This reduced review turnaround from days to hours and caught 95% of issues before merging.”

---

### How do you handle versioning of UI contracts?

**Context**: When frontend and backend are developed independently, or when multiple frontend teams share a common component API.

**Strategies**:

1. **API versioning** – Use URL versioning (`/v1/users`) or accept header. Keep backward compatibility for at least one version.
2. **Component API versioning** – For shared component libraries, use semantic versioning. Breaking changes require a major version bump. Provide codemods to ease migration.
3. **GraphQL** – Use schema evolution (add fields, deprecate old ones) without breaking clients. Tools like Apollo Federation allow independent team ownership.
4. **Feature flags** – Introduce new UI contracts behind flags; gradually roll out to clients.
5. **Contract testing** – Use Pact or other consumer‑driven contract testing to ensure frontend expectations match backend responses.

**Example**:
> “Our design system component API was versioned with semver. When we needed to change the props of a button, we released a major version and provided a codemod. All consuming teams updated via a scheduled upgrade week. For backend APIs, we used GraphQL with schema deprecations and gave teams a 2‑month window to migrate before removing fields.”

---

### What tools and practices do you use for frontend observability, error tracking, and performance monitoring?

**Observability**:
- **Logging** – Use structured logging (e.g., `console.log` with `winston` or `pino` in Node). In browsers, send logs to a service like Datadog or LogRocket.
- **Distributed tracing** – If backend uses tracing, propagate trace IDs to frontend to correlate requests.

**Error tracking**:
- **Sentry** – Captures JavaScript errors, breadcrumbs, user context. Integrates with React to show component stack traces.
- **Source maps** – Upload to Sentry during build to get readable stack traces.

**Performance monitoring**:
- **Real User Monitoring (RUM)** – Use tools like Datadog RUM, New Relic Browser, or Google Analytics 4 (with Core Web Vitals). Track Core Web Vitals (LCP, CLS, INP) and custom metrics (e.g., time to interactive).
- **Lighthouse CI** – Run in CI to catch regressions before deployment.
- **Web Vitals library** – Use `web-vitals` to send metrics to your analytics backend.

**Alerts**:
- Set up alerts for error rate spikes, high LCP, or increased bundle size. Use tools like Sentry’s alert rules or Datadog monitors.

**Example**:
> “We integrated Sentry for error tracking, uploading source maps in CI. We used Datadog RUM to track Core Web Vitals and custom business timings (e.g., time to checkout). We created dashboards for each team and set up alerts for 5xx errors and when LCP exceeded 2.5 seconds for more than 5% of sessions. This helped us catch a major performance regression within minutes of deployment.”

---

### How do you ensure secure handling of sensitive user data on the client side? (XSS, CSP, CSRF, token leakage)

**Defense in depth**:

- **XSS (Cross‑Site Scripting)** – Use libraries that auto‑escape (React by default escapes content). Avoid `dangerouslySetInnerHTML`; if necessary, sanitize with DOMPurify. Set `Content-Security-Policy` (CSP) to restrict script sources.
- **CSP** – Implement strict CSP headers (e.g., `default-src 'self'`, `script-src 'self'`). Use nonces for inline scripts. Test with report‑only mode first.
- **CSRF (Cross‑Site Request Forgery)** – Use `SameSite=Lax` cookies, anti‑CSRF tokens, or double‑submit cookies. In SPAs, store tokens in memory (not localStorage) and use them in custom headers.
- **Token leakage** – Avoid storing access tokens in `localStorage` (vulnerable to XSS). Prefer httpOnly cookies with `Secure` and `SameSite=Strict`. If using JWT in memory, ensure it’s not exposed in URLs or logs.
- **Sensitive data in URLs** – Never put tokens or PII in URLs (they appear in server logs, referrer headers).
- **Third‑party scripts** – Carefully vet them; use Subresource Integrity (SRI) to ensure they aren’t tampered with.
- **Audit tools** – Use Lighthouse Security audits, OWASP ZAP, or npm packages like `helmet` for Express.

**Example**:
> “We migrated from storing JWT in localStorage to httpOnly cookies with SameSite=Lax, which eliminated XSS‑based token theft. We implemented a strict CSP with `script-src 'self'` and used nonces for dynamically injected scripts. For forms, we included CSRF tokens and validated them on the server. We also ran regular security scans using Snyk and automated OWASP ZAP in CI.”

---

### How would you design a migration strategy from a legacy jQuery app to modern React/Next.js?

**Goal**: Minimize risk, keep business running, and deliver incremental value.

**Strategy**:

1. **Assessment** – Audit the existing app: identify core pages, user flows, third‑party integrations, and technical constraints.

2. **Choose an approach**:
   - **Incremental migration (strangler pattern)** – Run new and old side‑by‑side. Route new pages to React, keep legacy ones. Gradually replace parts.
   - **Big bang** – Rewrite everything and replace. Riskier, but sometimes necessary for tightly coupled apps.

3. **Build foundation** – Create a new React app (preferably Next.js for SSR/SSG if needed). Set up CI/CD, shared libraries, and a design system.

4. **Identify boundaries** – Use a reverse proxy (nginx) to route based on path: `/new/*` to React, everything else to legacy. Or embed React components in legacy pages using `ReactDOM.render` on specific DOM containers.

5. **Migrate in layers**:
   - Start with low‑risk, high‑visibility pages (e.g., homepage, static content).
   - Extract shared services (authentication, API clients) and make them available to both apps.
   - Use feature flags to switch between old and new for a subset of users.

6. **Testing** – Maintain parity with end‑to‑end tests. Run both versions in parallel for a period.

7. **Retire legacy** – Once all functionality is migrated, shut down the old app.

**Example**:
> “We had a 10‑year‑old jQuery app. We chose the strangler pattern: we built a new React app on Next.js, deployed it to a subdomain. We gradually moved routes: first the marketing pages, then the dashboard, finally the admin tools. We used a feature flag system to route 10% of users to the new version, increasing as confidence grew. We shared authentication via a common cookie. The migration took 8 months with zero downtime.”

---

### How do you integrate feature flags (LaunchDarkly, etc.) in React ecosystems?

**Goal**: Control feature rollout, A/B testing, and safe releases.

**Integration**:

1. **Provider** – Wrap the app with a feature flag provider (e.g., `LaunchDarklyProvider`). Initialize flags early, usually in the root component or a higher‑order component.

2. **Context / Hooks** – Use a hook like `useFeatureFlag(flagKey)` that returns the current variation. This can be used in components to conditionally render or execute code.

3. **Performance** – Load flags asynchronously; use a loading state (e.g., show a skeleton) until flags are ready, especially for critical flags that affect layout.

4. **Server‑side** – For Next.js, fetch flags in `getServerSideProps` or `getStaticProps` to avoid layout shifts. Use LaunchDarkly’s server‑side SDK to evaluate flags on the server.

5. **Testing** – Mock feature flags in unit tests. In end‑to‑end tests, set flags via API or by injecting cookies.

6. **Cleanup** – Once a feature is fully rolled out, remove the flag code to avoid clutter. Use the SDK’s ability to archive flags.

**Example**:
> “We used LaunchDarkly with React. We wrapped our app in a provider that initialized flags from localStorage first (for caching) then streamed updates via WebSocket. We created a `useFlag` hook that returned the flag value and automatically re‑rendered when the flag changed. For A/B tests, we used the `variation` to track analytics events. In Next.js, we fetched flags on the server using the Node SDK and passed them to the page via props, ensuring no layout shift.”

---

### How do you coordinate deployments with DevOps teams? Handling multiple pods with different versions.

**Goal**: Ensure seamless frontend deployments in containerized environments (e.g., Kubernetes) where multiple replicas (pods) may run different versions during a rollout.

**Strategies**:

1. **Use rolling updates** – Deploy new version gradually, monitoring error rates. Ensure that old and new pods can coexist during the transition.
2. **API compatibility** – Keep frontend backward‑compatible with older backend versions. Use feature flags to toggle new behavior if needed.
3. **Database migrations** – Ensure that if frontend writes to DB, the schema changes are backward‑compatible.
4. **Cache invalidation** – When deploying new frontend bundles, invalidate CDN caches. Use versioned asset names (e.g., `app.[hash].js`) to avoid stale content.
5. **Version awareness** – In the frontend, include a build hash in the HTML or as a meta tag. The backend can read it for analytics or to detect mismatches.
6. **Canary deployments** – Deploy new version to a subset of pods, route a small percentage of traffic to it. Use service mesh (Istio) or load balancer rules.
7. **Health checks** – Configure readiness and liveness probes to ensure pods are ready to serve traffic before they receive user requests.
8. **Communication with DevOps** – Define a deployment pipeline (GitHub Actions → build → push to registry → apply Kubernetes manifest). Use tools like Helm for templating. Coordinate via shared runbooks and post‑deployment monitoring.

**Example**:
> “We used Kubernetes with rolling updates. Our frontend was built as static assets served via an nginx container. During deployment, we updated the ConfigMap and triggered a rollout. We had a readiness probe that checked if the assets directory was ready. We also used a canary deployment for high‑risk changes, routing 10% of traffic to the new version via a service mesh. We coordinated with DevOps through a shared CI pipeline that ran end‑to‑end tests against a staging environment before pushing to production.”

---

These answers provide a framework for tackling complex architectural and leadership challenges. Tailor your responses to your actual experience, and always emphasize outcomes, trade‑offs, and lessons learned.


## Testing, CI/CD & Developer Experience

### How would you implement a robust frontend monitoring and logging system?

A robust system combines **error tracking**, **performance monitoring**, **user analytics**, and **structured logging**.

- **Error tracking**: Use Sentry, Rollbar, or similar. Capture JavaScript errors, unhandled promise rejections, and React error boundaries. Upload source maps to get readable stack traces.  
- **Performance monitoring**: Implement Real User Monitoring (RUM) with tools like Datadog RUM, New Relic Browser, or Google Analytics with Web Vitals. Track Core Web Vitals (LCP, CLS, INP), custom timings (e.g., time to checkout), and resource loading.  
- **Logging**: For client‑side, send structured logs to a backend endpoint (e.g., via `fetch`). Use a correlation ID across frontend and backend to trace requests. Avoid logging sensitive data.  
- **User analytics**: Use tools like Mixpanel or Amplitude to track feature usage, funnel conversions, and user flows.  
- **Alerts**: Set up alerts on error rate spikes, performance regressions, or business metric thresholds. Use tools like Sentry’s alert rules or Datadog monitors.  
- **Implementation**: Wrap the app in a monitoring provider that initializes SDKs, attaches user context, and buffers logs. Ensure logging doesn’t block the main thread – send data asynchronously in idle periods.

---

### What are flaky test detection strategies?

Flaky tests are those that sometimes pass and sometimes fail without code changes. Detection strategies:

- **Retry mechanism**: Run tests multiple times (e.g., 3–5) in CI; if they fail at least once but also pass, mark as flaky.  
- **Statistical analysis**: Collect test run history; use tools like `flaky` (Python) or built‑in CI features (GitHub Actions, CircleCI) to flag tests with high variance.  
- **Isolation**: Run tests in different orders, with random seed values (e.g., Jest’s `--randomize`), or with environment variations to reveal flakiness.  
- **Screenshot diffs**: For visual tests, flaky may come from timing or non‑deterministic rendering. Use tools like Percy or Chromatic that handle baseline comparisons.  
- **Quarantine**: Move flaky tests to a separate suite that doesn’t block deployments until fixed. Track them with a flaky test dashboard.

**Prevention**: Avoid hardcoded timers; use `waitFor` utilities; ensure mocks are properly reset; avoid relying on network state; use deterministic data.

---

### Explain contract testing between frontend and backend.

Contract testing ensures that the frontend and backend agree on the structure of API requests and responses, without running full end‑to‑end tests.

- **Tools**: Pact (consumer‑driven contract testing), OpenAPI (Swagger) validators, or GraphQL schema checks.  
- **Process**:
  1. **Consumer (frontend) defines expectations** – writes a “pact” describing the request it will send and the expected response.  
  2. **Pact file** is shared with the provider (backend).  
  3. **Provider verifies** – runs tests against its actual code to ensure it can satisfy the contract.  
- **Benefits**: Detects breaking API changes early; allows frontend and backend to develop independently; reduces need for expensive end‑to‑end tests.

**Example**: Using Pact.js, a frontend test would set up an interaction, generate a pact file, and the backend verifies it during CI. If either side changes the contract, CI fails.

---

### What is visual regression testing? How would you implement it?

Visual regression testing catches unintended UI changes by comparing screenshots of components or pages against approved baselines.

**Implementation**:

- **Tools**: Percy (integrated with Storybook), Chromatic, or open‑source tools like Playwright with screenshot comparison.  
- **Workflow**:
  1. Capture screenshots of each component/page in a controlled environment (e.g., Storybook).  
  2. Store baseline images (e.g., in Percy’s cloud).  
  3. On each pull request, run a new build, capture new screenshots, and compare.  
  4. Review any differences; if intentional, approve as new baseline.  
  5. Fail CI if unapproved changes are detected.  

**Considerations**:  
- Use consistent viewport sizes and mock data to avoid false positives.  
- Ignore dynamic elements (timestamps, random IDs) with attribute masking.  
- Run only on relevant components to keep feedback fast.

---

### How would you design a CI/CD pipeline for frontend apps with staging, canary, and blue‑green deployments?

A robust pipeline enables safe, gradual rollouts.

1. **Build & Test** (PR / main)  
   - Lint, type check, unit/integration tests.  
   - Build the application (generating static assets).  
   - Run contract tests, visual regression tests.  
   - Upload source maps to error tracking.

2. **Deploy to Staging**  
   - Deploy to a staging environment (e.g., using a Kubernetes cluster or static hosting).  
   - Run end‑to‑end tests against staging.  
   - Perform performance testing (Lighthouse CI).

3. **Canary Deployment**  
   - Deploy new version to a small percentage of production traffic (e.g., 1–5%).  
   - Monitor error rates, latency, and Core Web Vitals.  
   - Use feature flags to control exposure further.  
   - If metrics stay within thresholds, gradually increase traffic.

4. **Blue‑Green Deployment**  
   - Maintain two identical environments: blue (current) and green (new).  
   - Deploy new version to green, run smoke tests.  
   - Switch router (load balancer) to green instantly.  
   - If issues arise, switch back to blue.  

5. **Full Production Rollout**  
   - After canary passes, deploy to all pods (rolling update).  
   - Invalidate CDN caches if needed (use versioned asset names to avoid stale content).  
   - Post‑deployment monitoring for 30 minutes, then close the canary.

**Tools**: GitHub Actions/GitLab CI, ArgoCD for Kubernetes, AWS CodeDeploy for blue‑green, LaunchDarkly for feature flags.

---

### What is chaos engineering for frontend?

Chaos engineering is the practice of intentionally introducing failures to test system resilience. For frontend, it means simulating network issues, slow responses, API errors, or resource constraints to ensure the UI degrades gracefully.

**Examples**:
- **Network throttling** – simulate slow 3G to test lazy loading and timeouts.  
- **API failures** – mock 5xx responses and ensure error states appear.  
- **JavaScript exceptions** – inject errors to test error boundaries and fallback UI.  
- **Resource exhaustion** – simulate low memory or high CPU to see if the app remains responsive.

**Tools**:  
- Browser DevTools network throttling.  
- Chaos Monkey for frontend (e.g., using a library that randomly blocks requests).  
- Custom middleware in development to inject latency or errors.  

**Goal**: Build confidence that the app won’t crash under adverse conditions and provides clear feedback to users.

---

### How do you ensure code quality with testing? (unit, integration, e2e)

A balanced test pyramid:

- **Unit tests** (Jest, Vitest) – test individual functions, hooks, and components in isolation. Cover edge cases, pure logic. Aim for high coverage on critical business logic.  
- **Integration tests** (React Testing Library) – test how components work together. Focus on user interactions, state updates, and API mocks. Avoid testing implementation details.  
- **End‑to‑end tests** (Playwright, Cypress) – test critical user journeys across real browsers. Keep them small and focused (e.g., login, checkout). Run on staging before deployment.  

**Quality gates**:  
- Enforce minimum coverage thresholds (e.g., 80%) for new code.  
- Run tests in CI; block merge if any fail.  
- Use mutation testing (Stryker) to detect weak tests.  
- Include accessibility testing (axe) in integration/e2e tests.  

**Developer experience**: Fast feedback with watch mode, local test runner, and test data factories.

---

### Have you worked with Storybook? How do you use it?

Yes, Storybook is essential for developing and documenting UI components in isolation.

**Uses**:
- **Component development**: Build components without needing the full app context.  
- **Visual testing**: Integrate with Chromatic or Percy for visual regression.  
- **Documentation**: Write stories with controls, knobs, and docs addon to showcase props and usage.  
- **Accessibility checks**: Use the a11y addon to catch violations.  
- **Design system distribution**: Publish Storybook as a static site for team reference.  

**Integration**: We maintain a shared Storybook in our monorepo where all UI components are showcased. On PR, a Chromatic build runs and comments the diff preview. Developers are required to update stories when changing components.

---

## Miscellaneous / General

### What is the difference between CSR, SSR, SSG, and ISR?

- **CSR (Client‑Side Rendering)**: JavaScript runs in the browser to render the UI. Initial HTML is minimal. Good for dynamic, interactive apps but can hurt SEO and initial load.  
- **SSR (Server‑Side Rendering)**: Renders HTML on the server per request. Fast initial paint, better SEO. Used in Next.js `getServerSideProps`.  
- **SSG (Static Site Generation)**: Pre‑renders HTML at build time. Very fast, ideal for content that doesn’t change often (blogs, marketing pages). Next.js `getStaticProps`.  
- **ISR (Incremental Static Regeneration)**: Builds static pages but can regenerate them in the background after deployment. Combines benefits of SSG and SSR. Next.js `revalidate` option.

---

### What are Web Vitals and why do they matter?

Core Web Vitals are a set of user‑centric metrics for web performance:

- **LCP (Largest Contentful Paint)** – loading performance; should be ≤2.5s.  
- **CLS (Cumulative Layout Shift)** – visual stability; should be ≤0.1.  
- **INP (Interaction to Next Paint)** – responsiveness; should be ≤200ms (replaces FID).  

They matter because Google uses them as ranking signals, and they directly impact user experience, bounce rates, and conversions. Optimizing them improves overall site quality.

---

### How do you build PWAs with service workers, manifest files, and offline‑first experiences?

**Steps**:

1. **Manifest file** (`manifest.json`) – defines app name, icons, start URL, theme color, display mode. Link it in `<head>`.  
2. **Service Worker** – intercepts network requests, caches assets, and serves cached responses offline. Use Workbox to simplify.  
   - **Cache strategies**: Cache‑first for static assets, network‑first for API calls, stale‑while‑revalidate for data.  
3. **Offline‑first** – design the app to work without a network: store data in IndexedDB, queue actions for background sync (Periodic Background Sync API), and show offline UI.  
4. **Update flow** – when a new service worker is detected, prompt the user to refresh or auto‑update.

**Tools**: Workbox, Create React App PWA template, Next.js with `next-pwa`.

---

### Compare WebSockets, SSE, and WebRTC for real‑time features.

| Feature | WebSockets | SSE (Server‑Sent Events) | WebRTC |
|--------|-----------|------------------------|--------|
| **Direction** | Bidirectional | Server → client only | Peer‑to‑peer (with signaling) |
| **Protocol** | ws / wss | HTTP/2 (text/event‑stream) | UDP‑based (with ICE) |
| **Use cases** | Chat, gaming, collaborative editing | Live feeds, notifications, stock tickers | Video/audio calls, peer‑to‑peer data |
| **Overhead** | Moderate | Low (HTTP) | Higher |
| **Reconnection** | Manual | Built‑in (EventSource) | Handled by ICE |
| **Browser support** | Excellent | Excellent (except IE) | Good (requires HTTPS) |

**Choice**:
- Use **WebSockets** for full‑duplex, low‑latency communication.  
- Use **SSE** when only server needs to push data (simpler, uses HTTP).  
- Use **WebRTC** for media streaming or large file transfers between clients.

---

### How do you handle offline‑first apps with IndexedDB, background sync, and conflict resolution?

**Offline‑first architecture**:

1. **Store data locally** – Use IndexedDB (via libraries like Dexie.js) for structured data.  
2. **Background Sync** – When the user performs an action offline, store the request in IndexedDB. When the network returns, the Service Worker can sync using the `sync` event or `background fetch`.  
3. **Conflict resolution** –  
   - **Last‑write‑wins** (simple) – client sends timestamp; server uses later one.  
   - **Version vectors / CRDTs** – for collaborative apps, use libraries like Automerge.  
   - **User‑resolved** – show diff and let user choose.  
4. **Data synchronization** – After coming online, upload pending operations and fetch latest server state. Use optimistic updates with rollback on conflict.

**Tools**: Workbox background sync, Dexie.js, Firebase (offline support), or custom sync engine.

---

### What is your strategy for fluid responsive design using CSS Grid, Flexbox, and container queries?

- **Flexbox** – for one‑dimensional layouts (navigation bars, card rows). Use `flex-wrap`, `gap`, and `align-items`.  
- **CSS Grid** – for two‑dimensional layouts (page grids, complex components). Use `grid-template-columns: repeat(auto-fit, minmax(250px, 1fr))` for responsive cards.  
- **Container queries** – when a component’s layout should change based on its own container size, not the viewport. Useful for reusable components. Example: `@container (min-width: 400px) { .card { flex-direction: row; } }`.  
- **Fluid typography** – use `clamp()` with viewport units (e.g., `font-size: clamp(1rem, 2vw, 2rem)`).  
- **Responsive images** – use `<picture>` and `srcset` with `sizes`.

**Approach**: Design for mobile first, then use media queries to enhance larger screens. Use relative units (rem, %, vw). Test on real devices.

---

### How do you extract spacing, font sizes, and colors from Figma designs?

- **Spacing**: Use Figma’s inspect panel to get `margin`, `padding` values. I convert them to `rem` or CSS custom properties based on a design token system.  
- **Font sizes**: Note the `px` values, convert to `rem` (with a base of 16px). Define type scale as variables (`--font-size-sm`, `--font-size-md`).  
- **Colors**: Copy hex/rgba values; define as CSS variables (`--color-primary`, `--color-neutral-50`). Use opacity for shadows, overlays.  
- **Design tokens**: Extract all into a `tokens.json` file and generate CSS variables via tooling (Style Dictionary). This ensures consistency across components.

---

### How do you approach developing a reusable component from a design?

1. **Understand the component** – identify its purpose, variations (sizes, colors, states), and behavior (hover, disabled).  
2. **Define API** – props for variants, event handlers, and accessibility attributes.  
3. **Build in isolation** – use Storybook to develop without distractions.  
4. **Style with CSS modules / styled‑components** – ensure styles are encapsulated and themable.  
5. **Implement accessibility** – proper ARIA roles, keyboard navigation, focus management.  
6. **Write tests** – unit tests for logic, integration tests for interactions, visual regression tests.  
7. **Document** – in Storybook, with prop tables, usage examples, and design guidelines.  
8. **Publish** – to a shared package or monorepo for reuse.

---

### What is atomic design methodology?

Atomic design is a methodology for creating design systems with five levels:

- **Atoms** – basic HTML elements (button, input, label) with styles.  
- **Molecules** – groups of atoms functioning together (search bar: input + button).  
- **Organisms** – distinct, complex UI sections (header, product card).  
- **Templates** – page‑level structures without real content.  
- **Pages** – templates with actual content.  

It promotes reusability, consistency, and a clear hierarchy. In code, atoms become base components, molecules compose them, etc.

---

### How do you check page load behavior using browser developer tools? What metrics do you look at?

In Chrome DevTools **Network** tab:
- **Waterfall** – see resource loading order, identify slow requests.  
- **DOMContentLoaded**, **Load** events – time to interactive.  
- **Main thread activity** – long tasks that block rendering.  

In **Performance** tab:
- Record page load; look for **Layout Shift** events, **Long Tasks**, and **FPS** during scroll.  
- **Core Web Vitals** are shown in the **Timings** section.  

**Metrics**:
- **TTFB** (Time to First Byte) – server response time.  
- **FCP** (First Contentful Paint) – first text/image painted.  
- **LCP** (Largest Contentful Paint) – main content loaded.  
- **CLS** – layout shifts score.  
- **INP** – interaction responsiveness.  

---

### How would you check cumulative layout shifts (CLS) on a page?

- **DevTools** – Open **Lighthouse**; run performance audit; CLS score appears under “Core Web Vitals”.  
- **Performance tab** – Record page load, then look for “Layout Shift” events in the summary. Click to see which elements shifted.  
- **Web Vitals library** – add `web-vitals` to your app and send CLS data to analytics.  
- **Manual inspection** – resize viewport, throttle network to see if images or ads cause shifts.  

**Mitigation**: Set explicit dimensions on images, reserve space for dynamic content, and avoid inserting content above existing UI.

---

### What tools do you use for frontend performance analysis? (Lighthouse, WebPageTest, Chrome DevTools)

- **Lighthouse** – quick audits for performance, accessibility, SEO. Integrated in Chrome DevTools and CI.  
- **WebPageTest** – deep analysis from multiple locations, filmstrip view, first‑view/repeat‑view comparisons. Great for advanced diagnostics.  
- **Chrome DevTools** – Performance tab for detailed runtime analysis, Network tab for resource loading, Memory tab for heap snapshots.  
- **Real User Monitoring (RUM)** – Datadog RUM, New Relic Browser, or custom instrumentation with Web Vitals library.  
- **Bundle analysis** – webpack‑bundle‑analyzer, Next.js bundle analyzer to identify large chunks.  
- **Lighthouse CI** – run Lighthouse in GitHub Actions to catch regressions before deployment.  

**Workflow**: Use local DevTools during development, Lighthouse CI on every PR, and RUM in production to monitor real user experience.
