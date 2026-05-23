# 🚀 Frontend Engineering — Complete Interview Preparation Guide

> **JavaScript • React • System Design • DSA • Scenarios**
>
> Covers all levels: Junior → Senior → Staff

---

## 📚 Table of Contents

1. [JavaScript Fundamentals](#section-1-javascript-fundamentals)
2. [Core React Concepts](#section-2-core-react-concepts)
3. [HTML & CSS](#section-3-html--css)
4. [Frontend System Design](#section-4-frontend-system-design)
5. [DSA for Frontend](#section-5-dsa-for-frontend-interviews)
6. [Scenario-Based Questions](#section-6-scenario-based-interview-questions)
7. [Frontend Low-Level Design (LLD)](#section-7-frontend-low-level-design-lld)
8. [Advanced JavaScript & Browser Internals](#section-8-advanced-javascript--browser-internals)
9. [Build Tools, Testing & DevOps](#section-9-build-tools-testing--devops)
10. [Behavioral & Hiring Manager Round](#section-10-behavioral--hiring-manager-round)

---

# SECTION 1: JavaScript Fundamentals

## 1.1 Variables & Scope

### ❓ What is the difference between var, let, and const?

**Answer:** var is function-scoped, hoisted to the top of its function with an initial value of undefined, and can be re-declared. let is block-scoped, not initialized until the declaration line (Temporal Dead Zone), and cannot be re-declared in the same scope. const is also block-scoped, must be initialized at declaration, and cannot be reassigned — but object/array contents can still be mutated. Best practice: default to const, use let when reassignment is needed, avoid var.

### ❓ What is hoisting?

**Answer:** Hoisting is JavaScript's behavior of moving variable and function declarations to the top of their scope before code executes. var declarations are hoisted and initialized to undefined. Function declarations are fully hoisted (both declaration and body). let and const are hoisted but NOT initialized — accessing them before declaration throws a ReferenceError (Temporal Dead Zone). Class declarations are also hoisted but uninitialized.

### ❓ What is the Temporal Dead Zone (TDZ)?

**Answer:** The TDZ is the period between when a let or const variable enters scope (block start) and when it is actually declared/initialized. During this zone, accessing the variable throws ReferenceError: Cannot access 'x' before initialization. This is why you get that error — even though the variable exists in scope, it hasn't been initialized yet. This is a deliberate design choice to encourage declaring variables before use.

### ❓ What is scope, block scope, and function scope?

**Answer:** Scope defines where variables are accessible. Global scope: accessible everywhere. Function scope: variables declared with var inside a function are only accessible within that function. Block scope: variables declared with let/const inside {} (if, for, while blocks) are only accessible within those braces. Lexical scope means inner functions can access outer function variables, forming closure chains.

## 1.2 Data Types & Type System

### ❓ What is the difference between == and ===?

**Answer:** == (loose equality) performs type coercion before comparing — it converts operands to the same type. For example, '' == false is true because both coerce to 0. === (strict equality) compares both value AND type without coercion, so '' === false is false. Always prefer === to avoid subtle bugs from unexpected type coercion.

### ❓ What is the difference between undefined and not defined?

**Answer:** undefined means a variable has been declared but not assigned a value — it exists in memory. 'not defined' means the variable was never declared at all — accessing it throws a ReferenceError. typeof on an undeclared variable returns 'undefined' (not an error), while trying to use it in an expression throws ReferenceError.

### ❓ What are truthy and falsy values?

**Answer:** Falsy values in JavaScript: false, 0, -0, 0n (BigInt zero), '' (empty string), null, undefined, NaN. Everything else is truthy — including '0' (non-empty string), [] (empty array), {} (empty object). This matters in conditionals: if (value) checks truthiness, not strict equality to true.

## 1.3 Functions & Execution Context

### ❓ What is the difference between function declaration and function expression?

**Answer:** Function declarations (function foo() {}) are fully hoisted — you can call them before they appear in code. Function expressions (const foo = function() {}) are NOT hoisted — the variable is hoisted but the function assignment is not, so calling before declaration gives TypeError. Arrow functions are also expressions. Named function expressions provide better stack traces but have the same hoisting behavior as anonymous ones.

### ❓ Explain closures with a real-world example.

**Answer:** A closure is a function that retains access to its lexical scope even after the outer function has returned. Real-world examples: (1) Data privacy — a counter factory that exposes increment/decrement but hides the actual count. (2) React useState hook — internally uses closures to remember state between renders. (3) Event listeners that capture loop variables. (4) Memoization functions that cache results. Key insight: closures don't copy the variables, they maintain a live reference to the outer scope.


```javascript
// Closure example - private counter
function makeCounter() {
  let count = 0;  // private variable
  return {
    increment: () => ++count,
    decrement: () => --count,
    getCount: () => count
  };
}
const counter = makeCounter();
counter.increment(); // 1
counter.increment(); // 2 — count is remembered
```

### ❓ How does the 'this' keyword work in different contexts?

**Answer:** 'this' is determined by HOW a function is called, not where it's defined. (1) Global context: this = window (browser) or global (Node). (2) Method call: obj.method() — this = obj. (3) Regular function: this = undefined (strict mode) or global (sloppy). (4) Arrow functions: no own 'this' — inherits from enclosing lexical scope. (5) Class methods: this = class instance. (6) call/apply/bind: explicitly set this. This is why arrow functions are preferred in React event handlers and class methods.

### ❓ Explain call, apply, and bind with use cases.

**Answer:** All three set 'this' explicitly. call(thisArg, arg1, arg2): invokes function immediately, args passed individually. apply(thisArg, [argsArray]): invokes immediately, args passed as array — useful when args are already in an array. bind(thisArg, arg1): returns a NEW function with 'this' permanently bound — useful for event handlers in classes. Polyfill key insight: bind returns a closure that calls the original function with the bound context.


```javascript
// call vs apply vs bind
function greet(greeting, punctuation) {
  return `${greeting}, ${this.name}${punctuation}`;
}
const user = { name: 'Alice' };
greet.call(user, 'Hello', '!');    // immediate, args spread
greet.apply(user, ['Hello', '!']); // immediate, args array
const boundGreet = greet.bind(user, 'Hello'); // returns new fn
boundGreet('!'); // call later
```

## 1.4 Asynchronous JavaScript

### ❓ Explain the JavaScript Event Loop in detail — Microtasks vs Macrotasks.

**Answer:** JavaScript is single-threaded. The event loop coordinates execution: (1) Call Stack: where synchronous code executes. (2) Web APIs: browser handles async ops (setTimeout, fetch, DOM events). (3) Macrotask Queue (Callback Queue): completed setTimeout, setInterval, I/O callbacks wait here. (4) Microtask Queue: Promise .then/.catch, queueMicrotask, MutationObserver wait here. Order: Call stack empties → ALL microtasks drain → ONE macrotask runs → ALL microtasks drain → next macrotask. This is why Promise.then always runs before setTimeout, even setTimeout(fn, 0).


```javascript
console.log('1');           // sync - runs first
setTimeout(() => console.log('2'), 0); // macrotask
Promise.resolve().then(() => console.log('3')); // microtask
console.log('4');           // sync
// Output: 1, 4, 3, 2
```

### ❓ What is a Promise and what are its states?

**Answer:** A Promise is an object representing the eventual completion or failure of an async operation. States: (1) Pending — initial state, neither fulfilled nor rejected. (2) Fulfilled — operation completed successfully, .then() handlers run. (3) Rejected — operation failed, .catch() handlers run. (4) Settled — either fulfilled or rejected (irreversible). Promises are not cancellable by default (use AbortController for fetch). Promise.all fails fast on first rejection. Promise.allSettled waits for all regardless of outcome. Promise.race resolves/rejects with whichever settles first.

### ❓ What are async/await and how do they work?

**Answer:** async/await is syntactic sugar over Promises that makes async code look synchronous. An async function always returns a Promise. await pauses the async function execution until the Promise settles — but doesn't block the main thread (it yields to the event loop). Error handling uses try/catch instead of .catch(). Common pitfalls: (1) Forgetting await — you get a Promise object, not the value. (2) Using await in loops serially when parallel is possible — use Promise.all instead. (3) Top-level await (supported in ES modules).

### ❓ What is a callback function?

**Answer:** A callback is a function passed as an argument to another function, to be executed later (after some operation completes). Callbacks were the original async pattern before Promises. Problems with callbacks: callback hell (deeply nested), error handling is inconsistent, hard to compose. Modern JavaScript prefers Promises and async/await, but callbacks are still used for event listeners, array methods (map, filter, forEach), and Node.js-style APIs.

## 1.5 Arrays & Important Methods

### ❓ What is the difference between map, filter, forEach, and reduce?

**Answer:** map: transforms each element, returns NEW array of same length. filter: returns NEW array with elements that pass the test (can be shorter). forEach: iterates but returns undefined — side effects only, no chaining. reduce: accumulates all elements into a single value. find: returns first matching element or undefined. some: returns true if any element passes. every: returns true only if ALL elements pass. Key interview point: map and filter are pure (return new arrays), forEach is not.

### ❓ What is the difference between slice and splice?

**Answer:** slice(start, end): NON-MUTATING — returns a new array from start to end (end excluded). Safe to use without side effects. splice(start, deleteCount, ...items): MUTATING — modifies original array, removes/inserts elements in place, returns removed elements. Memory aid: slICe = nIce (doesn't change original); splICe = splICe into = modifies.

### ❓ Flatten an array without using Array.flat(). Input: [1,2,3,[4,5,6,[7,8,[10,11]]],9]

**Answer:** Use recursion: check if each element is an array, if so recurse, else push to result. Can also use reduce + recursion, or a stack-based iterative approach.


```javascript
// Recursive approach
function flatten(arr) {
  return arr.reduce((acc, item) => {
    if (Array.isArray(item)) {
      return acc.concat(flatten(item));
    }
    return acc.concat(item);
  }, []);
}
// Output: [1,2,3,4,5,6,7,8,10,11,9]

// Stack-based iterative (no recursion)
function flattenIterative(arr) {
  const stack = [...arr];
  const result = [];
  while (stack.length) {
    const item = stack.shift();
    if (Array.isArray(item)) stack.unshift(...item);
    else result.push(item);
  }
  return result;
}
```

### ❓ Find the sum of numbers without a for loop. Input: [1,2,3,4,5]


```javascript
// Using reduce
const sum = arr => arr.reduce((acc, n) => acc + n, 0);

// Using recursion
const sumRecursive = ([head, ...tail]) =>
  head === undefined ? 0 : head + sumRecursive(tail);

// Using Math tricks
const sum2 = arr => eval(arr.join('+'));
```

**Answer:** reduce is the idiomatic functional approach. Recursion works but has stack limits. The key concept is that we avoid imperative looping in favor of declarative aggregation.

### ❓ Implement currying for infinite sum: sum(10)(20)(30)() → 60


```javascript
function sum(a) {
  // If no argument, return accumulated total
  if (a === undefined) return 0;
  
  // Return a function that adds to running total
  return function(b) {
    if (b === undefined) return a;
    return sum(a + b);
  };
}

sum(10)(20)(30)();          // 60
sum(10)(20)(30)(40)(50)(); // 150
```

**Answer:** This uses closure to accumulate the sum. Each call returns a new function that adds to the running total. An empty call () triggers the base case and returns the result.

### ❓ Find the first repeating character in a string. Example: 'success' → 'c'


```javascript
function firstRepeating(str) {
  const seen = new Set();
  for (const char of str) {
    if (seen.has(char)) return char;
    seen.add(char);
  }
  return null;
}
firstRepeating('success'); // 'c'
```

**Answer:** Use a Set for O(1) lookups. Iterate once — O(n) time, O(n) space. The first character found already in the Set is the answer.

### ❓ Find first non-repeating character in a string.


```javascript
function firstNonRepeating(str) {
  const count = {};
  for (const char of str) count[char] = (count[char] || 0) + 1;
  for (const char of str) if (count[char] === 1) return char;
  return null;
}
firstNonRepeating('aabbcde'); // 'c'
```

**Answer:** Two-pass approach: first count all characters, then find first with count === 1. O(n) time, O(k) space where k is alphabet size.

### ❓ Given users = [{id:1, active:true}, {id:2, active:false}], find all active user IDs.


```javascript
// Clean array
const activeIds = users
  .filter(u => u.active)
  .map(u => u.id); // [1]

// With nulls/empty objects: [{id:1, active:true}, null, {}, {id:2}]
const activeIdsSafe = users
  .filter(u => u && u.id && u.active)
  .map(u => u.id);
```

**Answer:** The defensive version handles nulls, empty objects, and missing properties. Always validate data before accessing nested properties in real-world scenarios.

## 1.6 Objects, Prototypes & Deep Copy

### ❓ What is the difference between shallow copy and deep copy?

**Answer:** Shallow copy duplicates only the top-level properties. Nested objects/arrays still share the same reference — modifying them affects both original and copy. Methods: Object.assign({}, obj), spread {...obj}, Array.slice(). Deep copy creates a completely independent duplicate at all nesting levels. Methods: structuredClone(obj) [modern, recommended], JSON.parse(JSON.stringify(obj)) [loses functions, dates, undefined], recursive custom clone function, Lodash _.cloneDeep(). Interview tip: structuredClone is the modern answer interviewers love.

### ❓ How does prototypal inheritance work?

**Answer:** Every JavaScript object has a [[Prototype]] (accessible via __proto__ or Object.getPrototypeOf()). When you access a property, JS looks on the object first, then walks up the prototype chain until it finds it or reaches null. Object.create(proto) creates an object with proto as its prototype. ES6 classes are syntactic sugar over prototype chains. Function.prototype contains methods shared by all function instances. Array.prototype has map, filter, etc. The chain ends at Object.prototype (has toString, hasOwnProperty, etc.) → null.

### ❓ What is debouncing and throttling? When would you use each?

**Answer:** Debounce: delays function execution until after a specified time has elapsed since the last invocation. Use for: search input (fire API only when user stops typing), form validation, resize handler. Throttle: ensures function executes at most once per specified interval, regardless of how many times it's called. Use for: scroll events, button click prevention, real-time analytics. Key difference: debounce waits for quiet period; throttle guarantees regular execution during continuous events.


```javascript
// Debounce implementation
function debounce(fn, delay) {
  let timer;
  return function(...args) {
    clearTimeout(timer);
    timer = setTimeout(() => fn.apply(this, args), delay);
  };
}

// Throttle implementation
function throttle(fn, interval) {
  let lastTime = 0;
  return function(...args) {
    const now = Date.now();
    if (now - lastTime >= interval) {
      lastTime = now;
      fn.apply(this, args);
    }
  };
}
```

## 1.7 ES6+ Features

### ❓ What are destructuring, spread, and rest operators?

**Answer:** Destructuring: extracts values from arrays/objects into variables. const {name, age} = user; const [first, ...rest] = array. Spread (...): expands an iterable into individual elements — [...arr1, ...arr2] merges arrays, {...obj1, ...obj2} merges objects (shallow). Rest (...): collects remaining arguments into an array — function(a, b, ...rest). Optional chaining (?.) safely accesses nested props: user?.address?.city returns undefined instead of throwing. Nullish coalescing (??) returns right side only if left is null/undefined (unlike || which also triggers on falsy values like 0 or '').

### ❓ What are JavaScript modules (import/export)?

**Answer:** ES modules use import/export for code sharing. Named exports: export const fn = () => {} — import { fn } from './module'. Default export: export default fn — import fn from './module'. Tree shaking (dead code elimination) works with ES modules because imports are static and analyzable at build time. CommonJS (require/module.exports) is dynamic, making tree shaking harder. Dynamic import(): import('./module').then() enables lazy loading and code splitting.

---

# SECTION 2: Core React Concepts

## 2.1 React Fundamentals

### ❓ What is React JS?

**Answer:** React is a declarative, component-based JavaScript library for building user interfaces. Declarative means you describe WHAT the UI should look like for a given state — React handles HOW the DOM updates. Components are reusable, isolated pieces of UI that manage their own state and props. React uses a virtual DOM to efficiently update the real DOM, a unidirectional data flow (props flow down, events flow up), and JSX for writing HTML-like syntax in JavaScript.

### ❓ What is JSX and how is it rendered in the browser?

**Answer:** JSX is a syntax extension that lets you write HTML-like code in JavaScript. Browsers don't understand JSX — a build tool (Babel/SWC) transpiles it to React.createElement() calls. React.createElement(type, props, ...children) returns a plain JavaScript object (React element). React then uses these element objects to build and diff the virtual DOM. With React 17+, you no longer need to import React in every file for JSX thanks to the automatic JSX transform.

### ❓ What is reconciliation in React?

**Answer:** Reconciliation is React's algorithm for diffing the previous virtual DOM tree with the new one and determining the minimal set of real DOM changes needed. Key heuristics: (1) Elements of different types produce entirely different trees. (2) Elements with stable keys are matched across renders. (3) Same type = update props in place. React's Fiber architecture enables incremental reconciliation — work can be paused, prioritized, and resumed, unlike the old synchronous stack reconciler.

### ❓ What is Fiber architecture in React?

**Answer:** React Fiber (introduced in React 16) is a complete rewrite of the core reconciliation engine. It breaks rendering work into small units (fibers) that can be paused, prioritized, aborted, or restarted. This enables: concurrent rendering, time-slicing, Suspense, and better scheduling. Each fiber is a JS object representing a component instance with links to parent, child, and sibling fibers. The work-loop processes fibers incrementally, yielding to the browser between frames to maintain 60fps.

### ❓ What are state and props?

**Answer:** Props (properties) are read-only data passed FROM parent TO child components — like function arguments. They cannot be modified by the receiving component. State is mutable data managed INSIDE a component. When state changes, React re-renders that component and its children. Key distinction: props flow down (parent → child), events/callbacks flow up (child → parent). Props changes cause re-renders too — React re-renders a component whenever its parent re-renders OR its own state changes.

### ❓ What is a hook?

**Answer:** Hooks are functions that let you 'hook into' React state and lifecycle features from function components. Rules: (1) Only call hooks at the top level — not inside loops, conditions, or nested functions. (2) Only call hooks from React function components or custom hooks. Common built-in hooks: useState, useEffect, useContext, useRef, useMemo, useCallback, useReducer. Custom hooks are functions starting with 'use' that compose built-in hooks for reusable stateful logic.

### ❓ If we have var, let, and const, why do we need state variables?

**Answer:** Regular variables (var/let/const) are reset on every re-render — React calls the function component again, so local variables start fresh. useState persists values across renders AND triggers a re-render when changed. Without useState, changing a variable wouldn't notify React to update the UI. State is React's mechanism for: (1) persisting values across renders, (2) triggering UI updates when values change. Think of useState as a variable that React 'watches' and responds to.

## 2.2 Hooks Deep Dive

### ❓ Explain useEffect deeply — cleanup, dependency array pitfalls.

**Answer:** useEffect runs after render, asynchronously (not blocking paint). Dependencies array: empty [] = run once on mount. [dep1, dep2] = run when those deps change. No array = run after every render. Cleanup: return a function to run on unmount or before next effect — critical for: removing event listeners, cancelling subscriptions, clearing timers, aborting fetch. Pitfalls: (1) Missing dependencies causes stale closures. (2) Object/function deps cause infinite loops if created inline. (3) Async functions inside useEffect need IIFE or internal async function.


```javascript
useEffect(() => {
  const controller = new AbortController();
  fetch('/api', { signal: controller.signal })
    .then(r => r.json())
    .then(setData)
    .catch(e => { if (e.name !== 'AbortError') setError(e) });

  return () => controller.abort(); // cleanup!
}, [url]); // re-run when url changes
```

### ❓ What is the difference between useMemo and useCallback?

**Answer:** useMemo memoizes the RESULT of a computation — returns cached value until deps change. Use for expensive calculations. useCallback memoizes a FUNCTION DEFINITION — returns same function reference until deps change. Use when passing callbacks to memoized child components. Key distinction: useMemo = memo(fn()), useCallback = memo(fn). When NOT to use useMemo: (1) simple calculations where memoization overhead exceeds savings. (2) Values that change on every render anyway. Overusing them adds memory and comparison overhead.

### ❓ What is the difference between useMemo and React.memo?

**Answer:** React.memo is a HOC (Higher Order Component) that memoizes an entire component — prevents re-render if props haven't changed (shallow comparison). useMemo is a hook that memoizes a computed value inside a component. Use React.memo on child components that receive stable props and render expensively. Use useMemo for expensive calculations within a component. They work together: React.memo stops the component from re-rendering, useMemo stops expensive recalculations inside.

### ❓ What happens if a component wrapped in React.memo() has its own state changes?

**Answer:** React.memo only prevents re-renders caused by PARENT re-renders with unchanged props. If the component's OWN state changes (via setState), it ALWAYS re-renders regardless of React.memo. React.memo = 'don't re-render if props from parent didn't change'. It does NOT prevent self-triggered re-renders.

### ❓ What happens if a child uses React.memo() and parent props don't change?

**Answer:** If props are truly unchanged (by shallow comparison), React.memo prevents the child from re-rendering. However, if the parent passes inline objects ({}) or inline functions (() => {}) as props, these create new references on every parent render — making React.memo ineffective. Solution: wrap objects in useMemo and functions in useCallback in the parent component to maintain stable references.

### ❓ What is re-rendering and why does it happen?

**Answer:** Re-rendering is React calling your component function again to compute new JSX output. Causes: (1) Component's own state changes via setState/dispatch. (2) Parent component re-renders (by default, all children re-render). (3) Context value changes. (4) Subscribed store changes (Redux, Zustand). Important: re-rendering doesn't always mean DOM update — React diffs and only applies necessary DOM changes. Prevent unnecessary re-renders with React.memo, useMemo, useCallback, and proper state co-location.

### ❓ A React component re-renders again and again but you never called setState. Why?

**Answer:** Multiple causes are possible:

Parent re-render: parent's state/props changed, triggering all children to re-render
Inline objects/arrays as props: {} or [] creates new reference on every render
Inline functions as props: () => {} creates new function instance each render
Context value changed: if consuming a Context that updates frequently
Custom hook with unstable return values causing cascading updates
useEffect with missing/incorrect deps triggering setState in a loop

### ❓ What is prop drilling and how do you solve it?

**Answer:** Prop drilling is passing data through multiple intermediate components that don't need it, just to reach a deeply nested child. Problems: tight coupling, boilerplate, harder refactoring. Solutions: (1) Context API — for global or subtree-wide state. (2) Redux/Zustand — for complex global state. (3) Component composition — restructure to avoid deep nesting. (4) Component elevation — lift the consuming component higher. Use the simplest solution: composition first, then Context, then Redux.

### ❓ How do you pass parent data to the 5th child component?

**Answer:** Options in order of preference: (1) Component composition — restructure so the component needing data isn't 5 levels deep. (2) React Context — create a context, wrap with Provider at the parent level, consume with useContext at the child — no prop drilling needed. (3) State management (Redux/Zustand) — store state globally, child subscribes directly. (4) Prop drilling — workable for 2-3 levels, painful at 5 levels. For most cases, Context is the right answer.

## 2.3 State Management

### ❓ What is the difference between Context API and Redux Toolkit?

**Answer:** Context API: built-in React, no extra library, ideal for low-frequency updates (theme, locale, auth user). Limitation: any context value change re-renders all consumers — bad for high-frequency state. Redux Toolkit: external library, single global store with selectors — components only re-render when their specific slice changes. Better for: complex state, frequent updates, time-travel debugging, multiple teams. Decision: use Context for simple/infrequent state, Redux Toolkit for complex apps with many state updates.

### ❓ What is Redux and why is it used?

**Answer:** Redux is a predictable state container: single source of truth (one global store), state is read-only (only changed by dispatching actions), changes via pure reducer functions. Benefits for large apps: predictable state transitions, easy debugging (Redux DevTools time-travel), centralized state logic, middleware for async operations, testable reducers. Redux Toolkit (RTK) is the modern recommended approach — reduces boilerplate with createSlice, createAsyncThunk, and immer-based immutable updates.

### ❓ Explain the Redux Toolkit flow.

**Answer:** (1) createSlice() defines state shape, reducers (sync), and generates action creators. (2) configureStore() combines slices into the global store, auto-adds DevTools and middleware. (3) createAsyncThunk() handles async operations — dispatches pending/fulfilled/rejected actions. (4) extraReducers handles async thunk lifecycle in slices. (5) Components use useSelector() to read state and useDispatch() to send actions. (6) Store notifies all subscribers on state change, React re-renders connected components.

### ❓ What is createSlice() and what does it contain?

**Answer:** createSlice() accepts: name (action type prefix), initialState, reducers object (sync action handlers), and extraReducers (async thunk handlers). It auto-generates: action creators (slice.actions.actionName), action types (slice.name/actionName), and the reducer function. Reducers inside createSlice can mutate state directly because RTK uses Immer under the hood — Immer converts mutations into immutable updates. Export the reducer for the store and the actions for dispatch.

### ❓ What is createAsyncThunk() and why is it used?

**Answer:** createAsyncThunk handles async operations (API calls) in Redux. It takes an action type string and an async payload creator function. It automatically dispatches three action types: actionName/pending (loading), actionName/fulfilled (success with data), actionName/rejected (error). Handle these in extraReducers with builder.addCase(). This standardizes async state management and eliminates manual loading/error state boilerplate.

### ❓ What is the difference between Redux, Context, and Zustand for large-scale apps?

**Answer:** Redux Toolkit: most mature, excellent DevTools, enforces strict patterns, good for teams with complex state machines. Best when: large team, complex async flows, need for time-travel debugging. Context API: built-in, zero config, fine for infrequent updates. Problems with high-frequency updates (every consumer re-renders on any change). Zustand: minimal boilerplate, fast, component only re-renders on subscribed slice change, easy async. Best when: Redux feels too heavy but Context too limited. Decision matrix: Context for themes/auth, Zustand for medium complexity, RTK for enterprise.

## 2.4 React Performance

### ❓ What causes unnecessary re-renders in React?

**Answer:** Common causes:

Parent component re-renders — all children re-render by default
Inline objects/functions as props — new reference on every render
Context value changes — all consumers re-render
State updates higher in the tree than needed
Missing React.memo on stable pure components
useEffect triggering setState in a loop (missing deps or infinite loop)

### ❓ How would you optimize a React application rendering 100,000+ items in a list?

**Answer:** Multi-layer approach:

Virtualization/windowing: use react-window or react-virtual — render only visible rows (~10-20 items), recycle DOM nodes as user scrolls
Pagination or infinite scroll: load chunks of 20-50 items instead of all at once
Memoize list items with React.memo to prevent re-renders on unrelated state changes
Use stable keys — avoid index as key if items can reorder
Debounce filter/search operations
Web Workers for heavy sorting/filtering computations off the main thread
Code splitting: lazy load the list component if not immediately needed

### ❓ What are controlled vs. uncontrolled components?

**Answer:** Controlled: form input value is driven by React state — every keystroke calls onChange which updates state which re-renders. React is the source of truth. Enables: validation on every keystroke, conditional disabling, programmatic control. Uncontrolled: input value lives in the DOM — React reads it via ref only when needed (on submit). Source of truth is the DOM. Uncontrolled is simpler for basic forms; controlled is needed for real-time validation, conditional logic, or syncing with other state.

### ❓ What is state batching? What changed in React 18?

**Answer:** State batching = multiple setState calls in one event handler are combined into one re-render. In React 17, batching only happened in event handlers — setState calls inside setTimeout or Promises caused separate re-renders. React 18 introduced automatic batching everywhere — all setState calls (even in async code, setTimeout, Promises, native events) are batched. This means fewer re-renders and better performance. Use flushSync() to opt out of batching when you need synchronous DOM updates.

## 2.5 React Advanced Topics

### ❓ What is hydration in React?

**Answer:** Hydration is the process where React 'attaches' event handlers and makes a server-rendered HTML page interactive. SSR sends HTML to the browser (fast first paint). React then downloads, parses JS and runs hydration — it walks the existing DOM and attaches React's event system without re-creating DOM nodes. Hydration mismatch errors occur when server-rendered HTML doesn't match what React would render on client (e.g., browser-specific values, Date.now(), Math.random()). React 18 has selective/partial hydration via Suspense.

### ❓ What is code splitting and how does React.lazy work internally?

**Answer:** Code splitting breaks the JS bundle into smaller chunks loaded on demand, improving initial load time. React.lazy(import('./Component')) creates a lazy component that triggers a dynamic import() when first rendered. Suspense provides the loading fallback UI while the chunk downloads. Internally, React.lazy wraps the promise — during render, if the promise is pending, React 'throws' it (using Suspense's error boundary mechanism), shows fallback, and resumes rendering when resolved. React Router supports route-level splitting natively.

### ❓ What is the difference between useEffect, useLayoutEffect, and useInsertionEffect?

**Answer:** useEffect: runs AFTER paint (asynchronous) — doesn't block browser from painting. Good for: data fetching, subscriptions, analytics. useLayoutEffect: runs synchronously AFTER DOM mutations but BEFORE paint — blocks painting. Use when you need to read/write DOM layout (element size/position) to avoid visual flicker. useInsertionEffect: runs BEFORE DOM mutations — specifically for CSS-in-JS libraries to inject styles before any layout effects read styles. Hierarchy: useInsertionEffect → DOM mutations → useLayoutEffect → paint → useEffect.

### ❓ How does React Context work? When can it hurt performance?

**Answer:** Context provides a way to pass data through the component tree without props. Provider wraps the tree, Consumers (or useContext) read the value. Performance problem: when Context value changes, ALL components using useContext re-render, even if they only use a small part of the value. Solutions: (1) Split contexts by domain (ThemeContext, UserContext). (2) Memoize context value with useMemo. (3) Use selector pattern (useSyncExternalStore or Zustand). (4) Split into frequent-change and infrequent-change contexts.

### ❓ Difference between CSR, SSR, SSG, and ISR?

**Answer:** CSR (Client-Side Rendering): blank HTML, all rendering in browser JS. Fast interactions after initial load, poor SEO/TTI. SSR (Server-Side Rendering): server renders HTML per request. Good SEO, slower TTFB under load, needs server. SSG (Static Site Generation): HTML pre-built at build time. Fastest delivery, perfect for content that rarely changes (docs, blogs). ISR (Incremental Static Regeneration, Next.js): pages pre-built, then selectively rebuilt in background after stale time — combines SSG speed with SSR freshness. Choose: SEO + dynamic = SSR; SEO + static = SSG; no SEO = CSR.

---

# SECTION 3: HTML & CSS

## 3.1 HTML Fundamentals

### ❓ What are semantic HTML tags?

**Answer:** Semantic tags describe meaning, not just presentation: <header>, <nav>, <main>, <article>, <section>, <aside>, <footer>, <figure>, <time>, <mark>. Benefits: (1) Accessibility — screen readers use semantics for navigation. (2) SEO — search engines understand content structure. (3) Maintainability — code is self-documenting. Non-semantic: <div>, <span>. Rule of thumb: use the most specific semantic tag that fits before falling back to div.

### ❓ What is a pseudo-class in CSS?

**Answer:** A pseudo-class is a keyword added to a selector that defines a special state: :hover (mouse over), :focus (keyboard/click focus), :active (being clicked), :visited (visited link), :first-child, :last-child, :nth-child(n), :not(selector), :checked, :disabled, :required. Pseudo-elements (::before, ::after, ::placeholder) style specific parts of an element. Key difference: pseudo-class = state; pseudo-element = part of element.

### ❓ How do you center an element horizontally and vertically?

**Answer:** Multiple approaches:

Flexbox: parent gets display:flex; justify-content:center; align-items:center — most flexible
Grid: parent gets display:grid; place-items:center — cleanest one-liner
Position absolute + transform: position:absolute; top:50%; left:50%; transform:translate(-50%,-50%) — for overlays
Horizontal only: margin:0 auto on a block element with a defined width
Text centering: text-align:center only centers inline content

### ❓ What is the difference between relative and absolute positioning?

**Answer:** relative: element stays in normal document flow, but can be offset with top/left/right/bottom from its original position. Also creates a positioning context for absolutely positioned children. absolute: element is removed from document flow (doesn't take up space), positioned relative to nearest positioned ancestor (one with position other than static). If none exists, positioned relative to the initial containing block (viewport). Fixed: like absolute but relative to viewport — scrolls with page. Sticky: hybrid of relative and fixed.

### ❓ What is Flexbox?

**Answer:** Flexbox (Flexible Box Layout) is a CSS layout model for 1-dimensional layouts (row OR column). Container properties: display:flex, flex-direction (row/column), justify-content (main axis alignment), align-items (cross axis), flex-wrap, gap. Item properties: flex (shorthand for flex-grow, flex-shrink, flex-basis), align-self, order. Key insight: justify-content aligns along the flex-direction axis; align-items aligns perpendicular to it. Use Grid for 2D layouts, Flexbox for 1D.

### ❓ How to inline 5 divs in a row without flex/margin/padding?


```javascript
/* Using display: inline-block */
div {
  display: inline-block;
  width: 18%; /* account for whitespace gap */
}

/* Or remove whitespace between closing/opening tags in HTML */
/* Or use font-size: 0 on parent */
```

**Answer:** inline-block makes elements flow inline (like text) while respecting width/height. The whitespace challenge: inline-block elements respect whitespace in HTML source code, adding ~4px gaps. Solutions: set font-size:0 on parent, use HTML comments between tags, or use negative margin.

---

# SECTION 4: Frontend System Design

## 4.1 Performance Optimization

### ❓ What are Web Vitals and why do they matter?

**Answer:** Core Web Vitals are Google's metrics for user experience quality: LCP (Largest Contentful Paint) — loading performance, should be < 2.5s. CLS (Cumulative Layout Shift) — visual stability, should be < 0.1. INP (Interaction to Next Paint, replaced FID) — responsiveness, should be < 200ms. Also important: FCP (First Contentful Paint), TTFB (Time to First Byte), TTI (Time to Interactive). These directly affect SEO rankings (Google uses them as ranking signals) and user experience metrics.

### ❓ How would you improve Web Vitals (LCP, CLS, INP)?

**Answer:** LCP improvements:

Preload the LCP image/resource with <link rel='preload'>
Use a CDN for faster delivery
Optimize and compress images (WebP/AVIF formats)
Remove render-blocking resources
**Answer:** CLS improvements:

Set explicit width/height on images and video elements
Reserve space for ads, embeds, dynamic content
Avoid inserting content above existing content
Use CSS animations (transform) instead of layout-triggering properties
**Answer:** INP improvements:

Break up long tasks with setTimeout(fn, 0) or scheduler.yield()
Debounce expensive event handlers
Move heavy work to Web Workers
Reduce JavaScript execution time

### ❓ How would you optimize a slow React application?

**Answer:** Diagnostic first — profile with React DevTools Profiler to identify:

Components rendering too often → add React.memo, fix prop references
Expensive computations → wrap with useMemo
Large bundle → code splitting with React.lazy, tree shaking
Slow initial load → SSR/SSG, preloading critical resources
Memory leaks → check useEffect cleanups, event listener removal
Long list rendering → implement virtualization
Network waterfall → parallel data fetching, caching with React Query/SWR

### ❓ If given an existing website to analyze and improve performance, what is your first step?

**Answer:** Start with measurement before optimization. (1) Run Lighthouse audit in Chrome DevTools — get baseline scores for Performance, Accessibility, SEO. (2) Check Core Web Vitals in the Performance tab and real user data in Search Console. (3) Use Network tab to analyze waterfall — identify render-blocking resources, large bundles, slow API calls. (4) Check Coverage tab for unused JS/CSS. (5) Look for layout shifts in the Layout Shift Regions feature. Measure → identify bottleneck → fix → measure again. Never optimize blind.

### ❓ How do you debug a performance bottleneck in a React app using DevTools?

**Answer:** (1) Chrome Performance tab: record user interaction, look for long tasks (>50ms) in the flame chart, identify JS evaluation and layout/paint phases. (2) React DevTools Profiler: record interactions, see which components render and their render duration, look for 'why did this render' annotation. (3) Memory tab: take heap snapshots before/after interactions to find leaks. (4) Network tab: identify slow requests, bundle sizes, caching issues. (5) Coverage tab: see unused JS/CSS bytes. Combine all for complete picture.

### ❓ You notice a memory leak in a production SPA — how do you identify and fix it?

**Answer:** Identification: (1) Use Chrome Memory tab — take heap snapshots, compare before/after navigation. Growing detached DOM nodes and growing listener counts are red flags. (2) Chrome Performance monitor — watch JS heap size over time. Common causes & fixes: (1) Event listeners not removed — fix with cleanup in useEffect return. (2) Timers (setInterval) not cleared — clearInterval in cleanup. (3) Stale closures holding references — review useEffect deps. (4) Unsubscribed observables/WebSockets — close in cleanup. (5) Caching without eviction — implement LRU or max-size limits.

## 4.2 Architecture & Patterns

### ❓ How would you structure a large-scale React application?

**Answer:** Feature-based folder structure: src/features/auth/, src/features/dashboard/ etc. Each feature contains: components/, hooks/, slices/, api/, types/. Shared: src/components/ui/ (design system), src/hooks/ (shared hooks), src/utils/, src/api/ (base client). Key decisions: (1) Route-level code splitting for each feature. (2) Barrel exports (index.ts) for clean imports. (3) Absolute imports configured with path aliases. (4) Strict TypeScript throughout. (5) Global state only for truly global data — prefer local state + context for feature state.

### ❓ Design an autocomplete search with debouncing and caching.

**Answer:** Key concerns: (1) Debounce input — only query API after 300ms of silence. (2) AbortController — cancel previous request when new input arrives (prevent race conditions). (3) Cache results — store previous queries in a Map/ref to avoid redundant API calls. (4) Loading/error states. (5) Keyboard navigation (ArrowUp/Down/Enter/Escape). (6) Accessibility — aria-expanded, aria-autocomplete, aria-activedescendant. (7) Minimum character threshold (e.g., 2 chars). Implementation: useMemo for filtered results, useRef for cache, useEffect for fetch with cleanup.

### ❓ Design an infinite scrolling feed.

**Answer:** Approach: (1) IntersectionObserver on a sentinel element at the bottom — fires when visible. (2) Maintain page/cursor state, append new items to existing array. (3) React Query or SWR for data fetching with built-in cursor-based pagination. (4) Virtualization (react-virtual) if list grows very large. (5) Loading skeleton for next batch. (6) Error state with retry. (7) Avoid re-fetching already loaded pages. Advanced: prefetch next page when user is 80% down current page for seamless experience.

### ❓ How would you design a reusable component library for a large team?

**Answer:** (1) Storybook for component development and documentation. (2) Design tokens (CSS variables or JS constants) for consistent colors, spacing, typography. (3) Component API design: controlled/uncontrolled variants, compound components, render props for flexibility. (4) Accessibility: ARIA roles, keyboard navigation, focus management by default. (5) TypeScript with comprehensive prop types. (6) Versioned package (npm) with semantic versioning. (7) Visual regression testing (Chromatic). (8) Atomic design methodology: atoms → molecules → organisms. (9) Peer deps for React, not bundled.

### ❓ How would you implement A/B testing without affecting current users?

**Answer:** (1) Feature flags: tools like LaunchDarkly or GrowthBook assign users to control/variant based on user ID (consistent bucketing). (2) Percentage rollout: expose variant to X% of users, increase gradually. (3) Segment targeting: specific user segments (new users, premium tier). (4) Server-side assignment (prevents flicker): assign group at request time, persist in cookie/session. (5) Client-side: read flag value at component render time. (6) Analytics events: track conversions per variant. (7) Statistical significance: don't end tests early.

### ❓ How would you implement dark mode across the app?

**Answer:** (1) CSS variables (tokens): define --color-bg, --color-text, etc. — override in [data-theme='dark'] or .dark class. (2) Detect system preference: window.matchMedia('(prefers-color-scheme: dark)'). (3) Persist user preference in localStorage. (4) Toggle by adding/removing class on <html> or <body>. (5) Avoid flash of wrong theme: read localStorage in a blocking script before React renders (in <head>). (6) CSS-in-JS: use theme provider (Styled Components, Emotion, Chakra). (7) Tailwind: use darkMode: 'class' config.

### ❓ How would you handle real-time updates in a React application efficiently?

**Answer:** Options by use case: (1) WebSockets: bidirectional, persistent connection — best for chat, collaborative editing, live cursors. Use socket.io or native WebSocket API. (2) Server-Sent Events (SSE): server → client only, uses HTTP — best for live feeds, notifications, stock prices. (3) Long polling: fallback for environments that block WebSockets. React integration: connect in useEffect, cleanup on unmount, update state with incoming data, use Redux or Zustand for normalization. Optimization: batch rapid updates with throttle, use Immer for immutable updates.

### ❓ How would you prevent XSS, CSRF, token leakage, and secure auth in a frontend app?

**Answer:** Security measures:

XSS: use React's JSX (auto-escapes), avoid dangerouslySetInnerHTML, sanitize with DOMPurify if HTML is needed, set Content-Security-Policy headers
CSRF: use SameSite=Strict/Lax cookies, CSRF tokens from server, verify Origin header
Token storage: HttpOnly cookies (not localStorage) for auth tokens — JS can't read HttpOnly cookies, preventing XSS token theft
Refresh token flow: short-lived access tokens (15min), longer refresh tokens in HttpOnly cookies
HTTPS everywhere: HSTS headers to prevent downgrade attacks
CSP headers: restrict script sources, prevent inline script execution

## 4.3 Micro-Frontend Architecture

### ❓ How would you structure a micro-frontend architecture for team autonomy?

**Answer:** Approaches: (1) Module Federation (Webpack 5): each team deploys independent bundles, host app dynamically loads remote modules at runtime — no rebuild needed. (2) iframes: complete isolation, but poor UX and communication overhead. (3) Web Components: framework-agnostic, encapsulated — good for widgets shared across tech stacks. (4) Single-SPA: framework-agnostic meta-framework for composing micro-frontends. Communication: custom events, shared store, query params. Challenges: shared dependencies (deduplicate React), consistent design system, authentication, deployment orchestration.

### ❓ How would you reuse shared components across multiple repositories?

**Answer:** (1) Private npm package: publish to npm or GitHub Packages — semantic versioning, changelogs, automated publishing via CI. (2) Monorepo with workspaces (Turborepo, Nx): packages/ui-library used directly — no publish step, atomic changes across packages, shared tooling. (3) Storybook + Chromatic: visual documentation and review for the shared library. (4) Module Federation: share components at runtime without npm install. Trade-off: npm package = explicit versioning (safer); monorepo = always latest (easier but riskier).

---

# SECTION 5: DSA for Frontend Interviews

## 5.1 Core Algorithms

### ❓ Implement Kadane's Algorithm — Maximum Sum Subarray.


```javascript
function maxSubarraySum(nums) {
  let maxSum = nums[0];
  let currentSum = nums[0];

  for (let i = 1; i < nums.length; i++) {
    // Either extend current subarray or start fresh
    currentSum = Math.max(nums[i], currentSum + nums[i]);
    maxSum = Math.max(maxSum, currentSum);
  }
  return maxSum;
}
maxSubarraySum([-2,1,-3,4,-1,2,1,-5,4]); // 6 (subarray [4,-1,2,1])
```

**Answer:** O(n) time, O(1) space. Key insight: at each position, decide to extend current subarray or start new one from current element. Track max seen so far.

### ❓ Design and implement an LRU Cache.


```javascript
class LRUCache {
  constructor(capacity) {
    this.capacity = capacity;
    this.cache = new Map(); // Map preserves insertion order
  }

  get(key) {
    if (!this.cache.has(key)) return -1;
    const value = this.cache.get(key);
    // Move to end (most recently used)
    this.cache.delete(key);
    this.cache.set(key, value);
    return value;
  }

  put(key, value) {
    if (this.cache.has(key)) this.cache.delete(key);
    else if (this.cache.size >= this.capacity) {
      // Delete least recently used (first entry)
      this.cache.delete(this.cache.keys().next().value);
    }
    this.cache.set(key, value);
  }
}
```

**Answer:** JavaScript Map maintains insertion order, making it perfect for LRU. Delete+re-insert on access moves item to 'most recent'. Evict the first key (least recently used) when at capacity. O(1) get and put.

### ❓ Detect a cycle in a linked list.


```javascript
function hasCycle(head) {
  let slow = head;
  let fast = head;
  
  while (fast && fast.next) {
    slow = slow.next;       // moves 1 step
    fast = fast.next.next; // moves 2 steps
    if (slow === fast) return true; // cycle detected
  }
  return false;
}
```

**Answer:** Floyd's cycle detection (tortoise and hare). If cycle exists, fast pointer wraps around and catches up to slow. O(n) time, O(1) space.

### ❓ Implement a sliding window maximum.


```javascript
function maxSlidingWindow(nums, k) {
  const result = [];
  const deque = []; // stores indices, decreasing order of values

  for (let i = 0; i < nums.length; i++) {
    // Remove indices outside window
    while (deque.length && deque[0] < i - k + 1) deque.shift();
    // Remove smaller elements (they can't be max)
    while (deque.length && nums[deque[deque.length-1]] < nums[i])
      deque.pop();
    deque.push(i);
    if (i >= k - 1) result.push(nums[deque[0]]);
  }
  return result;
}
```

**Answer:** Monotonic deque approach: O(n) time. The deque front always holds the index of the maximum element in the current window.

---

# SECTION 6: Scenario-Based Interview Questions

## 6.1 Performance Scenarios


```javascript
🧠 SCENARIO: Large List Causes UI Lag (10k+ Items)
Problem: Rendering 10,000+ items at once causes the page to freeze and scroll to stutter.
Solution: Implement virtualization with react-window — only render ~10-20 visible rows. Add pagination or infinite scroll for data loading. Use React.memo on list item components. Move heavy sorting/filtering to Web Workers. Use useMemo to cache filtered results.
```


```javascript
🧠 SCENARIO: High-Performance Search Box with Expensive API
Problem: User types fast, each keystroke triggers an API call — too many requests, inconsistent results.
Solution: Debounce input by 300ms. Use AbortController to cancel previous in-flight requests. Cache results in a useRef map. Handle race conditions by checking if component is still mounted before setState. Show loading skeleton during fetch.
```


```javascript
🧠 SCENARIO: Context API Causes Frequent Re-renders
Problem: Every component using useContext re-renders even when they only use a small part of the context value.
Solution: Split context by domain (ThemeContext vs UserContext). Memoize context value with useMemo. Consider moving high-frequency state to Zustand/Redux which support selectors. Use useSyncExternalStore for subscribing to external stores with selector support.
```


```javascript
🧠 SCENARIO: Component Re-renders Even When Props Don't Change
Problem: React.memo is applied but component still re-renders on every parent render.
Solution: Parent is passing inline objects ({}) or functions (() => {}) as props — new references every render. Fix: wrap objects with useMemo and callbacks with useCallback in the parent. Verify with React DevTools Profiler 'why did this render' feature.
```


```javascript
🧠 SCENARIO: React App Has Poor SEO and Slow TTI
Problem: SPA (CSR) with poor Lighthouse scores, slow Time to Interactive, not indexed by search engines.
Solution: Migrate to SSR (Next.js) for dynamic content or SSG for static pages. Implement dynamic imports (React.lazy) for below-fold components. Preload critical resources. Optimize bundle: tree shaking, code splitting per route. Add meta tags, structured data. Use streaming SSR (React 18) for faster TTFB.
```

## 6.2 Production & Debugging Scenarios


```javascript
🧠 SCENARIO: Critical UI Feature Failing During Peak Traffic
Problem: Feature breaks under load — some users see errors, others don't. Inconsistent behavior.
Solution: Immediate: roll back or feature flag the failing feature off. Investigate: check error monitoring (Sentry), look for patterns (specific user segments, regions, browsers). Check if multiple pod versions are serving different code. Mitigation: graceful degradation — show fallback UI instead of crashing. Post-mortem: add error boundaries, improve monitoring, stagger deployments with canary releases.
```


```javascript
🧠 SCENARIO: Multiple Pods Serving Different Versions of a Page
Problem: During deployment, some users get old JS, some get new — causes mismatched API responses and client errors.
Solution: Content hashing: filename includes hash of content (main.abc123.js) — old and new coexist on CDN. Cache-Control: ensure old HTML isn't cached (no-store or short TTL). Versioned API routes: /api/v2/ alongside /api/v1/. Blue-green deployment: complete switch rather than gradual. Health checks: confirm all pods serving new version before routing traffic.
```


```javascript
🧠 SCENARIO: Authentication Token Expires Mid-Session
Problem: User is in the middle of a workflow, access token expires, all API calls start returning 401.
Solution: Implement refresh token flow: (1) API interceptor detects 401. (2) Queue the failed request. (3) Use refresh token to get new access token (only one refresh request at a time — use a promise that all queued requests await). (4) Retry all queued requests with new token. (5) If refresh fails, redirect to login. Store access token in memory (not localStorage), refresh token in HttpOnly cookie.
```


```javascript
🧠 SCENARIO: CSS Animation Janky on Mobile Devices
Problem: Smooth animation on desktop but stutters/drops frames on mobile.
Solution: Identify: Chrome DevTools Performance tab → check for paint/layout operations during animation. Fix: use transform and opacity only (GPU-accelerated, skip layout and paint). Add will-change: transform as a hint (use sparingly). Avoid animating: width, height, top, left, margin, padding — these trigger layout. Reduce animation complexity for low-end devices with @media (prefers-reduced-motion). Use requestAnimationFrame for JS-driven animations.
```

## 6.3 Architecture & Approach Scenarios


```javascript
🧠 SCENARIO: Migrating Legacy jQuery App to React/Next.js
Problem: Large production app built in jQuery needs to be modernized without big-bang rewrite risk.
Solution: Strangler Fig pattern: (1) Identify bounded sections. (2) Build new React components alongside old jQuery. (3) Route new URLs to React, keep old URLs on jQuery. (4) Gradually replace jQuery components with React. (5) Wrap React components in Web Components for jQuery compatibility if needed. Set up shared CI/CD, shared design tokens from day one. Track migration progress with metrics. Never rewrite all at once — ship incrementally.
```


```javascript
🧠 SCENARIO: Intermittent UI Glitches in Different Browsers
Problem: Users report visual bugs that appear inconsistently across Chrome, Firefox, Safari.
Solution: Systematic debugging: (1) Reproduce in each browser. (2) Check browser compatibility for CSS features used (caniuse.com). (3) Look for vendor prefix issues (-webkit-, -moz-). (4) Test flexbox/grid behavior — Safari has known differences. (5) Check font rendering differences. (6) Use BrowserStack for device/browser matrix. (7) Review PostCSS/autoprefixer configuration. Add cross-browser CI testing with Playwright or Cypress.
```


```javascript
🧠 SCENARIO: Handling Multiple Independent API Calls for a Dashboard
Problem: Dashboard loads data from 5 different APIs sequentially — very slow load time.
Solution: Use Promise.allSettled([api1(), api2(), api3(), api4(), api5()]) to fire all requests in parallel. Each panel shows its own loading/error state independently. React Query or SWR with parallel queries. For truly independent sections, consider staggered loading — show above-fold data first. Cache aggressively with appropriate stale times per data type.
```

---

# SECTION 7: Frontend Low-Level Design (LLD)

## 7.1 Component Design Questions

### ❓ Design a Todo List with add, edit, delete, and mark-as-complete.

**Answer:** State: array of {id, text, completed, createdAt}. Add: controlled input + button, generate UUID for id. Edit: inline editing — toggle isEditing flag per item, show input when true. Delete: filter out by id. Complete: toggle completed flag. Optimize re-renders: React.memo on TodoItem, useCallback on handlers. Filters (All/Active/Completed): derived state via useMemo, don't store as separate state. Persist to localStorage with useEffect. Accessibility: button labels, checkbox role for complete toggle.

### ❓ Design a Stopwatch with Start, Stop, Reset and live timer display.


```javascript
function Stopwatch() {
  const [time, setTime] = useState(0);
  const [running, setRunning] = useState(false);
  const intervalRef = useRef(null);

  const start = () => {
    if (running) return;
    setRunning(true);
    intervalRef.current = setInterval(() => setTime(t => t + 10), 10);
  };
  const stop = () => {
    setRunning(false);
    clearInterval(intervalRef.current);
  };
  const reset = () => { stop(); setTime(0); };

  useEffect(() => () => clearInterval(intervalRef.current), []);

  const format = ms => {
    const s = Math.floor(ms / 1000) % 60;
    const m = Math.floor(ms / 60000);
    const cs = Math.floor((ms % 1000) / 10);
    return `${String(m).padStart(2,'0')}:${String(s).padStart(2,'0')}.${String(cs).padStart(2,'0')}`;
  };
}
```

**Answer:** Key points: useRef for interval ID (not state — changing it shouldn't cause re-render). Cleanup in useEffect return. Use functional update setTime(t => t + 10) to avoid stale closure issues.

### ❓ Design a Search with Autocomplete, debouncing, caching, and race condition handling.


```javascript
function useAutocomplete(query) {
  const [results, setResults] = useState([]);
  const cache = useRef(new Map());

  useEffect(() => {
    if (!query || query.length < 2) return;
    if (cache.current.has(query)) {
      setResults(cache.current.get(query));
      return;
    }
    const controller = new AbortController();
    fetch(`/api/search?q=${query}`, { signal: controller.signal })
      .then(r => r.json())
      .then(data => {
        cache.current.set(query, data);
        setResults(data);
      })
      .catch(e => { if (e.name !== 'AbortError') console.error(e); });
    return () => controller.abort(); // cancel on new query
  }, [query]);
  
  return results;
}
// Debounce query in parent before passing to hook
```

**Answer:** Three-layer defense: debounce (reduces requests), cache (avoids redundant requests), AbortController (handles race conditions). Minimum 2-char threshold prevents wasteful very-short queries.

### ❓ Design a Modal/Dialog component with focus trapping and accessibility.

**Answer:** Key requirements: (1) Focus trap: when modal opens, focus moves inside; Tab cycles only within modal; Escape closes. (2) aria-modal='true', role='dialog', aria-labelledby pointing to title. (3) Return focus to trigger element on close. (4) Backdrop click to close (optional). (5) Render in portal (ReactDOM.createPortal) to avoid z-index and overflow issues. (6) Lock body scroll while open. Implementation: useEffect to handle keyboard events and focus management, ref on modal container for focus trap logic.

### ❓ Design a Notification/Toast system with queueing and auto-dismiss.

**Answer:** Architecture: global state (context or Zustand) holds array of {id, message, type, duration}. useToast() hook exposes show(message, options) function. Toast container renders all active toasts. Auto-dismiss: each toast has its own setTimeout, cleared on manual dismiss. Queue: FIFO with max visible limit (e.g., 3) — excess queued and shown as previous ones dismiss. Animation: CSS transitions for enter/exit. Priority: error toasts persist longer, success auto-dismiss in 3s.

### ❓ Design a Virtualized/Windowed list for very large datasets.

**Answer:** Core concept: only render visible rows + overscan buffer (~3 rows above/below viewport). Track scrollTop to determine which rows are visible. Row height can be fixed (simple) or dynamic (requires measurement with ResizeObserver). Container has total height (itemCount * rowHeight) for correct scrollbar. Visible items are absolutely positioned with top = index * rowHeight. Libraries: react-window (fixed), react-virtual (dynamic heights). Custom implementation: useRef for container, useState for scrollTop, useEffect for scroll listener with cleanup.

## 7.2 Data & State Design

### ❓ Design an E-commerce Filter system (price, category, rating) with scalable state.

**Answer:** State shape: { filters: { category: [], priceRange: [0, 1000], rating: 0 }, sort: 'price-asc', page: 1 }. Keep filters in URL query params — enables shareable links, browser back/forward navigation. Derived state: filteredProducts = useMemo(filterFn, [products, filters]) — never store filtered results in state. Each filter updates URL, URL drives state (single source of truth). Debounce price range slider to avoid excessive filtering. Server-side filtering for large catalogs.

### ❓ Design a Config-Driven Form Renderer using JSON schema.

**Answer:** Schema: array of {type, name, label, validation, options}. Types: text, email, select, checkbox, radio, date. Renderer maps type → component. Validation: Zod/Yup schema generated from config. State: useForm (React Hook Form) with dynamic field registration. Benefits: forms defined by non-developers/CMS, consistent validation, easy A/B testing of form layouts. Handle conditional fields: showIf: { fieldName: value } logic in renderer. Dynamic validation rules in schema.

---

# SECTION 8: Advanced JavaScript & Browser Internals

## 8.1 Advanced JavaScript

### ❓ How do JavaScript engines optimize code (JIT, hidden classes)?

**Answer:** V8 uses JIT (Just-In-Time) compilation: starts interpreting bytecode, profiles hot paths, compiles optimized machine code for frequently executed code. Hidden classes: V8 creates internal classes for objects with the same property shape — access is fast when shape is consistent. If you add properties in different orders or delete properties, V8 deoptimizes (shape change). Best practices: initialize all object properties in constructor, keep object shapes consistent, avoid delete operator for perf-critical code.

### ❓ How does garbage collection work in V8?

**Answer:** V8 uses generational garbage collection: new space (young generation) for recently allocated, short-lived objects — collected frequently with Scavenge (fast). Old space for objects that survive multiple collections — collected less often with Mark-Sweep-Compact. The GC pauses JS execution (stop-the-world). V8 incrementalizes and concurrents GC to minimize pause times. Memory leaks occur when references to objects are kept alive unintentionally — GC can't collect them.

### ❓ What are WeakMap vs Map — real use cases?

**Answer:** WeakMap: keys must be objects, keys are weakly referenced (don't prevent GC), not iterable. Use for: private data per instance (won't leak if object is collected), associating metadata with DOM nodes (auto-cleaned when node is removed), caching per-object data. Map: keys can be any type, strong references (prevents GC), iterable. Use for: general key-value storage, frequency counting, LRU cache. WeakMap is the right choice when you want data tied to an object's lifetime.

### ❓ Explain cross-tab communication options.

**Answer:** (1) BroadcastChannel: simple pub/sub across same-origin tabs — new BroadcastChannel('my-channel'), .postMessage(data), .onmessage handler. (2) localStorage events: storage event fires in OTHER tabs when localStorage changes — good for auth state sync. (3) SharedWorker: a worker shared across tabs — message passing through ports. (4) Service Worker: can relay messages between all clients. Use cases: sync logout across tabs, real-time notifications, shared WebSocket connection via SharedWorker.

## 8.2 Browser Rendering Pipeline

### ❓ How does the browser rendering pipeline work?

**Answer:** (1) Parse HTML → DOM tree. (2) Parse CSS → CSSOM tree. (3) Combine DOM + CSSOM → Render Tree (only visible elements). (4) Layout (Reflow): calculate position/size of each element. (5) Paint: fill in pixels for each element. (6) Compositing: combine layers (GPU). Optimization: minimize reflows (expensive) by batching DOM reads/writes, use transform/opacity for animations (GPU-composited, skip layout/paint), avoid layout thrashing (alternating read-write of layout properties).

### ❓ What causes memory leaks in frontend applications?

**Answer:** Common memory leak sources:

Event listeners not removed (addEventListener without removeEventListener on cleanup)
Timers not cleared (setInterval/setTimeout without clearInterval in cleanup)
Stale closures holding large data in scope longer than needed
Detached DOM nodes still referenced by JS variables
Infinite growing caches without eviction policy
Unsubscribed Observables, WebSocket listeners, or store subscriptions
React: missing useEffect cleanup for subscriptions and listeners

---

# SECTION 9: Build Tools, Testing & DevOps

## 9.1 Build Systems

### ❓ How does tree shaking work in modern bundlers?

**Answer:** Tree shaking is dead code elimination — removing exports that are never imported. It requires ES modules (static imports/exports) because the import graph is analyzable at build time. CommonJS (require) is dynamic, making it impossible to statically determine what's used. Webpack and Rollup trace the import graph, mark unused exports, and exclude them from output. Sidetrack: packages must mark themselves as sideEffect-free in package.json for bundlers to safely eliminate their unused exports.

### ❓ What is the difference between preload, prefetch, and priority hints?

**Answer:** <link rel='preload'>: fetch a resource as high priority ASAP for current navigation (critical path resources — LCP image, main font, critical JS). <link rel='prefetch'>: low-priority fetch for FUTURE navigation — browser idles to fetch. <link rel='preconnect'>: establish TCP/TLS connection early without fetching. fetchpriority='high/low' attribute: hint to browser about fetch priority. Strategy: preload LCP image, preload hero font, prefetch next-page chunks, preconnect to API domain.

### ❓ Have you worked with CI/CD pipelines — how do frontend teams coordinate deployments?

**Answer:** Typical frontend CI pipeline: lint → type check → unit tests → build → E2E tests → deploy to staging → manual QA → deploy to production. Coordination with DevOps: environment variables managed via secrets (not in code), Dockerfile for containerized deploys, helm chart/K8s manifests for pod config. For version consistency: content-hashed filenames, S3/CDN for assets, short HTML cache TTL. Blue-green or canary deployments reduce risk. Feature flags allow deploying code without activating features.

## 9.2 Testing

### ❓ How do you detect and prevent memory leaks in long-running SPAs?

**Answer:** Detection: Chrome Memory tab — heap snapshots comparison, Detached DOM Trees report, growing listener count in Performance Monitor. Prevention: (1) Always return cleanup functions from useEffect. (2) Clear timers and intervals. (3) Unsubscribe from observables. (4) Use WeakMap/WeakRef for caches tied to object lifetime. (5) Avoid storing large data in module-level variables. (6) Profile memory during typical user workflows — look for heap that grows without recovery.

### ❓ What is the difference between visual regression testing and contract testing?

**Answer:** Visual regression testing: captures screenshots of components, compares against baseline — catches unintended CSS/layout changes. Tools: Chromatic (Storybook-based), Percy, Playwright screenshots. Contract testing (frontend-backend): verifies the API response shape matches what the frontend expects — catches backend changes that break frontend before integration. Tools: Pact.js, MSW (Mock Service Worker). Both are important: visual regression for UI stability, contract testing for API stability.

---

# SECTION 10: Behavioral & Hiring Manager Round

## 10.1 Common Behavioral Questions

### ❓ When did you get stuck while using React and how did you fix it?

**Answer:** Framework for answering: (1) Describe the specific technical problem (stale closure in useEffect, performance issue with large list, memory leak from uncleared subscription). (2) Explain your debugging process — what tools you used, what you ruled out. (3) The solution you found. (4) What you learned. Strong example: 'I had an infinite render loop — useEffect was triggering setState which caused a re-render which triggered useEffect again. I used React DevTools to trace the render cycles, identified a missing dependency that was actually causing the loop, and restructured the effect to break the cycle.'

### ❓ How do you balance performance vs feature delivery?

**Answer:** Framework: performance is a feature, not a tax. Approach: (1) Establish performance budgets upfront (e.g., LCP < 2.5s, bundle size < 200KB). (2) Automate performance checks in CI — fail builds that regress metrics. (3) Address performance debt in dedicated sprints, not as afterthoughts. (4) Use data: is this optimization worth the effort? (5) Good software design (proper abstractions, avoiding premature optimization) often prevents performance issues. (6) When deadlines force trade-offs, document the debt and schedule payback.

### ❓ How do you handle disagreements in technical decisions?

**Answer:** Approach: (1) Understand the other perspective fully — ask clarifying questions. (2) Use data/evidence, not opinions — benchmark, prototype, share research. (3) Propose criteria for evaluation upfront. (4) For reversible decisions: try both approaches in spikes. (5) Document the decision and rationale regardless of outcome — ADRs (Architecture Decision Records). (6) Separate ego from the decision — the team's best outcome matters more than being right. (7) If still stuck: escalate to tech lead or architect, or use the RFC (Request for Comments) process.

### ❓ Describe the hardest production bug you fixed.

**Answer:** Framework (STAR + technical depth): Situation — describe system and scale. Task — what was failing, what was the user impact. Action — how you identified the root cause (specific tools, techniques: heap snapshots, flame charts, logging, feature bisection). Result — the fix, what monitoring you added to prevent recurrence. Good signals: you used data to diagnose, you communicated status during the incident, you improved the system to prevent recurrence, you did a post-mortem.

### ❓ How do you mentor junior developers?

**Answer:** Effective mentoring: (1) Code walkthroughs — pair program, explain reasoning not just code. (2) Review PRs with teaching intent — explain why, not just what to change. (3) Technical spikes — assign exploratory tasks to build confidence. (4) 1:1 check-ins — understand their goals, blockers, growth areas. (5) Create psychological safety — it's fine to ask questions. (6) Gradually increase scope of responsibility. (7) Share resources — curated reading list, courses. (8) Let them make mistakes in safe contexts — real learning comes from debugging your own bugs.

## 10.2 Technical Leadership Questions

### ❓ How do you identify, prioritize, and reduce technical debt?

**Answer:** Identification: (1) Code complexity metrics (cyclomatic complexity). (2) Test coverage gaps. (3) 'Hot files' — frequently changed files with bugs. (4) Developer surveys — what makes you slow? Prioritization: (1) Blocks new features. (2) Causes production incidents. (3) High cognitive load (onboarding cost). (4) Security risk. Reduction: (1) Boy Scout Rule — leave code better than you found it. (2) Dedicated debt sprints (20% of velocity). (3) Refactoring alongside feature work in same area. (4) Track debt as tickets with business impact described.

### ❓ How would you implement a robust frontend monitoring and logging system?

**Answer:** Layers: (1) Error tracking (Sentry/Datadog): automatic JS error capture, stack traces, user session replay, release tracking. (2) Performance monitoring: Real User Monitoring (RUM) for Core Web Vitals, custom performance marks. (3) Analytics: user behavior events (Amplitude, Mixpanel). (4) Logging: structured logs with user ID, session ID, feature flags active. (5) Alerting: PagerDuty alerts for error rate spikes, P99 latency thresholds. (6) Dashboards: Grafana/Datadog for error rate trends, deployment correlation. Correlate errors with deployments and feature flag changes.

─── End of Document ───
