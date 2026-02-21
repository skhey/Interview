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
