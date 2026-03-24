Here is the complete list of 100 Node.js interview questions with concise, detailed answers. Questions 1–21 incorporate the excellent answers you provided, and questions 22–100 are answered clearly to cover all essential Node.js topics.

---

### 1. What is Node.js and why is it used?
**Answer:** Node.js is an open-source, cross-platform JavaScript runtime built on Chrome’s V8 engine. It allows JavaScript to run on the server, enabling full‑stack development. Its non‑blocking, event‑driven architecture makes it ideal for I/O‑intensive applications like real‑time chat, APIs, and streaming services. Node.js uses npm (Node Package Manager) to provide a vast ecosystem of reusable modules.

---

### 2. Explain the event-driven architecture of Node.js.
**Answer:** Node.js uses an event loop to handle asynchronous operations. When an I/O task (e.g., file read) is initiated, Node.js registers a callback and continues executing other code. Once the task completes, the event loop places the callback in the queue and executes it. This allows a single thread to manage many concurrent connections efficiently, without blocking.

---

### 3. What are the main features of Node.js?
**Answer:**
- **Asynchronous & Non‑blocking I/O** – handles multiple tasks concurrently.
- **Single‑threaded Event Loop** – uses one thread with event‑driven concurrency.
- **V8 Engine** – compiles JavaScript to machine code for speed.
- **NPM** – huge package ecosystem.
- **Cross‑platform** – runs on Windows, Linux, macOS.

---

### 4. How does Node.js handle asynchronous operations?
**Answer:** Node.js uses an event loop and a thread pool (libuv) to offload blocking operations (like file system, network). Asynchronous functions (e.g., `fs.readFile`) return immediately and register a callback. The event loop later processes the callback when the result is ready, keeping the main thread free for other tasks.

---

### 5. What is the role of the event loop in Node.js?
**Answer:** The event loop orchestrates the execution of asynchronous callbacks. It continuously checks the call stack and task queues. When the stack is empty, it takes the next callback from the microtask queue (promises) or macrotask queue (timers, I/O) and pushes it onto the stack. This enables non‑blocking concurrency.

---

### 6. What is a callback function in Node.js?
**Answer:** A callback is a function passed as an argument to another function, executed after the outer function completes. In Node.js, callbacks are commonly used for asynchronous operations, often following the “error‑first” pattern where the first parameter is an error (or null) and the second is the result.

---

### 7. Explain the concept of Promises in Node.js.
**Answer:** A Promise is an object representing the eventual completion (or failure) of an asynchronous operation. It has three states: `pending`, `fulfilled`, and `rejected`. Promises allow chaining with `.then()` and error handling with `.catch()`, making asynchronous code more readable and avoiding callback hell.

---

### 8. What is the purpose of the `async` and `await` keywords in Node.js?
**Answer:** `async` declares a function that returns a Promise. Inside an `async` function, `await` pauses execution until the awaited Promise resolves, then returns the result. This allows writing asynchronous code in a synchronous style, improving readability and error handling via `try/catch`.

---

### 9. How does Node.js handle errors in asynchronous code?
**Answer:**  
- **Callbacks**: use error‑first callbacks; check the error argument.  
- **Promises**: use `.catch()` or the second argument of `.then()`.  
- **async/await**: wrap in `try/catch`.  
- **Uncaught exceptions**: listen to `process.on('uncaughtException')` for final fallback, but should be used sparingly.

---

### 10. What is the difference between synchronous and asynchronous functions in Node.js?
**Answer:** Synchronous functions block the execution thread until the operation completes; they can cause performance bottlenecks. Asynchronous functions return immediately and schedule the result to be processed later via callbacks, promises, or events, allowing other code to run in the meantime. Node.js is designed for asynchronous programming to maximize throughput.

---

### 11. What is the purpose of the `require` function in Node.js?
**Answer:** `require` is used to load modules (built‑in, third‑party, or local files). It returns the module’s exports and caches the result for subsequent calls. For local files, it expects a relative path (e.g., `./myModule`). It is part of the CommonJS module system.

---

### 12. How does Node.js manage modules and dependencies?
**Answer:** Node.js uses the CommonJS module system. Each file is a module, and `module.exports` exposes its public API. Dependencies are tracked in `package.json` and installed in `node_modules`. The `require` function resolves modules by searching in `node_modules` and caches them for efficiency.

---

### 13. What is the CommonJS module system?
**Answer:** CommonJS is the default module system in Node.js. It uses `require()` to import modules and `module.exports` to export values. Modules are loaded synchronously and are cached after the first load. It provides encapsulation because each module runs in its own scope.

---

### 14. Explain the concept of middleware in Express.js.
**Answer:** Middleware functions in Express have access to the request (`req`) and response (`res`) objects and the `next` function. They can execute code, modify `req`/`res`, end the request‑response cycle, or call the next middleware. Middleware is used for logging, authentication, parsing bodies, error handling, etc.

---

### 15. How can you handle uncaught exceptions in Node.js?
**Answer:** Use `process.on('uncaughtException', handler)` to catch errors that weren’t caught anywhere. However, after an uncaught exception, the application may be in an inconsistent state; it’s recommended to log the error, clean up resources, and exit gracefully. For production, use a process manager (like PM2) to restart the app.

---

### 16. What are Streams in Node.js and how are they used?
**Answer:** Streams are objects that let you read or write data piece by piece (in chunks) instead of loading the whole data into memory. They are used for handling large files, network communications, and real‑time data. Types: `Readable`, `Writable`, `Duplex`, `Transform`.

---

### 17. Explain the different types of streams in Node.js.
**Answer:**  
- **Readable**: source of data (e.g., `fs.createReadStream`).  
- **Writable**: destination for data (e.g., `fs.createWriteStream`).  
- **Duplex**: both readable and writable (e.g., `net.Socket`).  
- **Transform**: a duplex stream that modifies data as it passes through (e.g., `zlib.createGzip`).

---

### 18. What is the purpose of the `process` object in Node.js?
**Answer:** The `process` object provides information and control over the current Node.js process. It gives access to environment variables (`process.env`), command‑line arguments (`process.argv`), standard I/O (`stdin`, `stdout`, `stderr`), and allows exiting (`process.exit()`), listening to events like `uncaughtException`, and more.

---

### 19. How can you manage environment variables in Node.js applications?
**Answer:** Use `process.env` to access environment variables. For development, you can load them from a `.env` file using the `dotenv` package (`require('dotenv').config()`). Store secrets and configuration in environment variables; never commit `.env` to version control.

---

### 20. What is the role of `package.json` in a Node.js project?
**Answer:** `package.json` is the manifest file that describes the project: name, version, dependencies (`dependencies`, `devDependencies`), scripts (e.g., `npm start`), entry point, and metadata. It enables reproducible installations (`npm install`) and serves as configuration for many tools.

---

### 21. How do you create and use custom modules in Node.js?
**Answer:** Create a file (e.g., `math.js`) and export functionality using `module.exports`. In another file, import it with `require('./math')`. This keeps code organized, reusable, and encapsulated.

---

### 22. Explain the concept of the `buffer` in Node.js.
**Answer:** Buffers are temporary storage for binary data, typically used when dealing with streams, file I/O, or network operations. They are instances of the `Buffer` class, which provides methods to work with raw binary data in a fixed size. Buffers are allocated outside the V8 heap for performance.

---

### 23. What are the differences between `Buffer.from()` and `Buffer.alloc()`?
**Answer:**  
- `Buffer.from()` creates a buffer from an existing data source (string, array, another buffer). It may contain existing data.  
- `Buffer.alloc()` creates a new buffer of a specified size, initialized with zeros (safe).  
- `Buffer.allocUnsafe()` also creates a buffer but may contain old memory data (faster but less safe). Prefer `alloc()` or `from()` for security.

---

### 24. How does Node.js handle file operations?
**Answer:** Node.js provides the `fs` module with both synchronous (blocking) and asynchronous (non‑blocking) methods. Asynchronous methods are preferred because they don’t block the event loop. They use callbacks, promises (via `fs.promises`), or streams for large files.

---

### 25. What is the purpose of the `fs` module in Node.js?
**Answer:** The `fs` (File System) module provides functions to interact with the file system: reading, writing, deleting, renaming files, and working with directories. It includes both synchronous and asynchronous variants, and also a promise‑based API in `fs.promises`.

---

### 26. Explain the difference between `fs.readFile` and `fs.createReadStream`.
**Answer:**  
- `fs.readFile` loads the entire file into memory before invoking the callback. Suitable for small files.  
- `fs.createReadStream` returns a readable stream that emits data chunks as they are read, allowing processing of large files without high memory consumption.

---

### 27. What is the role of the `path` module in Node.js?
**Answer:** The `path` module provides utilities for working with file and directory paths. It helps to construct, parse, and transform paths in a cross‑platform way (e.g., using `path.join()`, `path.resolve()`, `path.basename()`).

---

### 28. How can you parse URLs in Node.js?
**Answer:** Use the `url` module: `url.parse()` (legacy) or the WHATWG `URL` class: `new URL('https://example.com/path')`. The `URL` class provides properties like `href`, `pathname`, `searchParams`, etc., for easy manipulation.

---

### 29. What is the role of the `http` module in Node.js?
**Answer:** The `http` module allows Node.js to transfer data over HTTP. It provides methods to create an HTTP server (`http.createServer()`) and to make HTTP requests (`http.request()`). It handles low‑level socket connections, request/response parsing, and headers.

---

### 30. How can you create an HTTP server using Node.js?
**Answer:** Use `http.createServer((req, res) => { ... })` which returns a server instance. Then call `server.listen(port)` to start listening. The callback receives request and response objects. For example:
```js
const http = require('http');
http.createServer((req, res) => {
  res.writeHead(200, { 'Content-Type': 'text/plain' });
  res.end('Hello World');
}).listen(3000);
```

---

### 31. What are the different HTTP methods and their uses?
**Answer:**  
- **GET**: retrieve data.  
- **POST**: submit data to be processed.  
- **PUT**: update/replace an entire resource.  
- **PATCH**: partially update a resource.  
- **DELETE**: remove a resource.  
- **HEAD**: similar to GET but without body.  
- **OPTIONS**: request communication options.

---

### 32. How can you make HTTP requests in Node.js?
**Answer:** Use the built‑in `http`/`https` modules with `http.request()` or use simpler libraries like `axios` or `node-fetch`. Example with native `http`:
```js
const http = require('http');
http.get('http://example.com', (res) => {
  let data = '';
  res.on('data', chunk => data += chunk);
  res.on('end', () => console.log(data));
});
```

---

### 33. Explain the use of the `url` module in Node.js.
**Answer:** The `url` module provides utilities for URL resolution and parsing. You can parse a URL string into components (protocol, host, path, query, etc.) using `new URL(urlString)`. It also includes the `url.format()` method to build a URL string from an object.

---

### 34. What is Express.js and how does it enhance Node.js?
**Answer:** Express.js is a minimal and flexible web application framework for Node.js. It adds middleware support, routing, template engines, and simplifies handling of requests and responses. It abstracts low‑level details of the `http` module, enabling rapid API and web application development.

---

### 35. How do you handle routing in Express.js?
**Answer:** Define routes using methods like `app.get()`, `app.post()`, etc., with a path and a handler function. Example:
```js
app.get('/users/:id', (req, res) => {
  const userId = req.params.id;
  res.send(`User ${userId}`);
});
```

---

### 36. What are HTTP status codes and how do you use them in Express.js?
**Answer:** HTTP status codes indicate the result of the request. Common ones: 200 (OK), 201 (Created), 400 (Bad Request), 401 (Unauthorized), 404 (Not Found), 500 (Internal Server Error). In Express, use `res.status(code)` before sending a response: `res.status(404).send('Not found')`.

---

### 37. What is middleware in Express.js and how is it used?
**Answer:** Middleware functions in Express are functions that execute during the request‑response cycle. They have access to `req`, `res`, and `next`. They can modify `req`/`res`, end the cycle, or call `next()` to pass control to the next middleware. Use `app.use()` to mount middleware globally or on specific paths.

---

### 38. How can you handle form data in Express.js?
**Answer:** Use middleware like `express.urlencoded({ extended: true })` for `application/x-www-form-urlencoded` data, and `express.json()` for JSON payloads. For file uploads, use `multer` or similar middleware.

---

### 39. What are the differences between `req.query`, `req.params`, and `req.body` in Express.js?
**Answer:**  
- `req.query` – URL query parameters (e.g., `/search?q=node` → `{ q: 'node' }`).  
- `req.params` – route parameters (e.g., `/users/:id` → `{ id: '123' }`).  
- `req.body` – data sent in the request body (populated by body‑parsing middleware like `express.json()`).

---

### 40. Explain the purpose of `app.use()` in Express.js.
**Answer:** `app.use()` mounts middleware functions that are executed for every request (or requests matching a specific path). It is used for logging, static file serving, authentication, and any cross‑cutting concerns. Unlike route handlers, it doesn’t require a specific HTTP method.

---

### 41. How can you handle errors in an Express.js application?
**Answer:** Express has built‑in error‑handling middleware with four parameters (err, req, res, next). Define it after all routes. Use `next(err)` to pass errors to this handler. You can also catch errors inside route handlers and call `next(error)`.

---

### 42. What is CORS and how can you handle it in a Node.js application?
**Answer:** CORS (Cross‑Origin Resource Sharing) controls which origins can access resources. In Express, use the `cors` middleware: `const cors = require('cors'); app.use(cors());` and configure allowed origins, methods, etc.

---

### 43. How do you implement authentication in a Node.js application?
**Answer:** Common approaches: session‑based (using cookies and `express-session`), token‑based (JWT), or OAuth. JWTs are often used with Bearer tokens. Passport.js is a popular authentication middleware that supports many strategies (local, OAuth, JWT).

---

### 44. What is Passport.js and how is it used with Node.js?
**Answer:** Passport.js is authentication middleware for Node.js. It provides a modular way to integrate authentication strategies (e.g., local, Google, Facebook, JWT). You configure a strategy, then use `passport.authenticate()` in routes.

---

### 45. How can you use sessions in a Node.js application?
**Answer:** Use `express-session` middleware. It creates a session store (often in memory or using a database like Redis). The session ID is stored in a cookie; session data is saved on the server. Example:
```js
const session = require('express-session');
app.use(session({ secret: 'key', resave: false, saveUninitialized: true }));
```

---

### 46. What are the different types of databases you can use with Node.js?
**Answer:**  
- **SQL**: PostgreSQL, MySQL, SQLite (drivers: `pg`, `mysql2`, `sqlite3`).  
- **NoSQL**: MongoDB (with Mongoose), CouchDB, Cassandra.  
- **In‑memory**: Redis, Memcached.

---

### 47. How do you connect to a MongoDB database from a Node.js application?
**Answer:** Use the official MongoDB driver (`mongodb`) or an ODM like Mongoose. Example with Mongoose:
```js
const mongoose = require('mongoose');
mongoose.connect('mongodb://localhost:27017/mydb');
```

---

### 48. What is Mongoose and how does it simplify MongoDB interactions?
**Answer:** Mongoose is an ODM (Object Data Modeling) library for MongoDB. It provides schema definitions, built‑in validation, middleware (hooks), and methods to query data using a structured model, reducing boilerplate compared to the native driver.

---

### 49. Explain how you would perform CRUD operations in a Node.js application.
**Answer:**  
- **Create**: `db.collection.insertOne()` or using Mongoose `Model.create()`.  
- **Read**: `find()` with filters.  
- **Update**: `updateOne()` with `$set`.  
- **Delete**: `deleteOne()`.  
In REST APIs, these correspond to POST, GET, PUT/PATCH, DELETE.

---

### 50. What is the purpose of the `jsonwebtoken` library in Node.js?
**Answer:** The `jsonwebtoken` library creates and verifies JSON Web Tokens (JWT). JWTs are used for stateless authentication: the server signs a token with a secret, and the client includes it in subsequent requests. It can contain user identity and expiry.

---

### 51. How can you handle file uploads in a Node.js application?
**Answer:** Use `multer` middleware in Express. It processes `multipart/form-data` and stores files in memory or on disk. Example:
```js
const multer = require('multer');
const upload = multer({ dest: 'uploads/' });
app.post('/upload', upload.single('file'), (req, res) => { ... });
```

---

### 52. What are some best practices for error handling in Node.js applications?
**Answer:**  
- Use `try/catch` in async/await and handle promise rejections.  
- In Express, use centralized error‑handling middleware.  
- Never expose stack traces to clients in production.  
- Log errors with appropriate levels (debug, error).  
- Crash and restart on unhandled exceptions using process managers.

---

### 53. How can you implement logging in a Node.js application?
**Answer:** Use libraries like `winston`, `pino`, or `bunyan`. They provide structured logging with levels (info, error, debug) and transports (console, file, HTTP). In production, log to a centralized system (ELK, Datadog) for monitoring.

---

### 54. What is the role of the `os` module in Node.js?
**Answer:** The `os` module provides operating system‑related utility methods: `os.platform()`, `os.cpus()`, `os.totalmem()`, `os.freemem()`, `os.homedir()`, etc. It is useful for system monitoring and adjusting behavior based on the platform.

---

### 55. How can you perform background tasks in Node.js?
**Answer:** Use `setTimeout`, `setInterval`, or the `node-cron` library for scheduled tasks. For CPU‑intensive tasks, use `worker_threads` or offload to a separate service (e.g., message queue with Bull). Avoid blocking the event loop.

---

### 56. What are WebSockets and how can you implement them in Node.js?
**Answer:** WebSockets provide full‑duplex communication over a single TCP connection. In Node.js, use the `ws` library or integrate with frameworks like `socket.io`. Example with `ws`:
```js
const WebSocket = require('ws');
const wss = new WebSocket.Server({ port: 8080 });
wss.on('connection', ws => { ws.on('message', message => { ... }); });
```

---

### 57. How does Node.js handle concurrency?
**Answer:** Node.js uses a single‑threaded event loop to manage concurrency. I/O operations are delegated to the system kernel or a thread pool (libuv), and callbacks are scheduled when results are ready. This model avoids thread overhead and simplifies development.

---

### 58. What are the benefits of using Node.js for building APIs?
**Answer:**  
- Non‑blocking I/O handles many concurrent requests.  
- JavaScript on both frontend and backend reduces context switching.  
- Rich ecosystem (npm) speeds development.  
- Lightweight and fast, suitable for microservices.  
- Good support for real‑time features (WebSockets).

---

### 59. How can you test Node.js applications?
**Answer:** Use testing frameworks like `Mocha`, `Jest`, or `Ava`. Write unit tests for individual functions, integration tests for API endpoints, and end‑to‑end tests for critical flows. Use tools like `Supertest` for HTTP assertion and `sinon` for mocks.

---

### 60. What are some popular testing frameworks for Node.js?
**Answer:**  
- **Mocha** – flexible test runner.  
- **Jest** – all‑in‑one framework with assertions and mocks.  
- **Chai** – assertion library often used with Mocha.  
- **Supertest** – for testing HTTP servers.  
- **Sinon** – for spies, stubs, and mocks.

---

### 61. How do you use the `mocha` and `chai` libraries for testing in Node.js?
**Answer:** Install mocha and chai, then write tests in a `test/` folder. Example:
```js
const { expect } = require('chai');
describe('Math', () => {
  it('should add numbers', () => {
    expect(1+1).to.equal(2);
  });
});
```
Run with `mocha`.

---

### 62. What is a memory leak and how can you prevent it in Node.js?
**Answer:** A memory leak is when memory that is no longer needed is not released, causing increasing memory usage over time. Prevention: avoid global variables, clean up event listeners, limit cache size, use `WeakMap` for caches, and properly close resources. Use tools like `node --inspect` and heap snapshots to detect leaks.

---

### 63. How can you optimize the performance of a Node.js application?
**Answer:**  
- Use clustering to utilize multiple CPU cores.  
- Implement caching (Redis, in‑memory) for frequent data.  
- Optimize database queries and indexes.  
- Use streaming for large data.  
- Enable gzip compression.  
- Profile and identify bottlenecks with `clinic` or `node --prof`.

---

### 64. What are some common security issues in Node.js applications?
**Answer:**  
- **Injection** (SQL, NoSQL, command injection).  
- **XSS** if not sanitizing user input in frontend.  
- **CSRF** – use tokens.  
- **Insecure dependencies** – regularly audit with `npm audit`.  
- **Exposed secrets** – never hardcode; use environment variables.  
- **Denial of Service** – implement rate limiting.

---

### 65. How can you secure a Node.js application from common vulnerabilities?
**Answer:**  
- Use `helmet` middleware to set secure HTTP headers.  
- Validate and sanitize input with libraries like `Joi`.  
- Use parameterized queries or ORMs to prevent injection.  
- Implement rate limiting with `express-rate-limit`.  
- Keep dependencies updated.  
- Use HTTPS and secure cookies.

---

### 66. What is the purpose of the `cluster` module in Node.js?
**Answer:** The `cluster` module allows you to create child processes (workers) that share the same server port. It enables a Node.js application to scale across multiple CPU cores, improving throughput and fault tolerance.

---

### 67. How can you scale a Node.js application?
**Answer:**  
- **Vertical scaling**: add more resources to a single instance (limited).  
- **Horizontal scaling**: run multiple instances using the `cluster` module or process managers like PM2.  
- Use a load balancer (e.g., Nginx) to distribute traffic.  
- Use microservices and break the app into smaller services.

---

### 68. What is Node.js's role in microservices architecture?
**Answer:** Node.js is well‑suited for microservices due to its lightweight nature, fast startup time, and ability to handle many concurrent connections. It works well with containerization (Docker) and orchestration (Kubernetes). Its rich ecosystem supports communication via HTTP, gRPC, or message brokers.

---

### 69. How do you handle concurrency in Node.js?
**Answer:** Through the event loop and non‑blocking I/O. For CPU‑intensive tasks, use `worker_threads` or delegate to separate microservices. Avoid blocking the main thread; use asynchronous patterns (promises, async/await).

---

### 70. What are some tools for monitoring Node.js applications?
**Answer:**  
- **PM2** – process manager with built‑in monitoring.  
- **Node.js built‑in profiler** (`--inspect`).  
- **APM tools**: New Relic, Datadog, AppDynamics.  
- **Logging**: Winston, Pino with ELK stack.  
- **Metrics**: Prometheus + Grafana.

---

### 71. How can you profile a Node.js application for performance bottlenecks?
**Answer:** Use `node --prof` to generate a performance profile, then analyze with `node --prof-process`. Use the Chrome DevTools inspector (`node --inspect`) and take CPU profiles. Tools like `clinic` provide visual analysis.

---

### 72. What is the purpose of the `child_process` module in Node.js?
**Answer:** The `child_process` module allows you to spawn child processes, execute system commands, and communicate with them. It provides methods like `exec`, `spawn`, `fork`. Useful for running shell commands, offloading tasks, or using multiple processes.

---

### 73. How can you manage and schedule tasks in a Node.js application?
**Answer:** Use `node-cron` or `node-schedule` for cron‑like scheduling. For recurring tasks in the same process, `setInterval` works, but consider using external job queues (Bull, Agenda) with Redis for persistence and scaling.

---

### 74. What is the `stream` module and how do you use it in Node.js?
**Answer:** The `stream` module provides the foundation for streaming data. It includes the abstract classes `Readable`, `Writable`, `Duplex`, and `Transform`. You can implement custom streams by extending these classes or using helper methods like `Readable.from()`.

---

### 75. Explain the concept of Node.js's non-blocking I/O.
**Answer:** Non‑blocking I/O means that an I/O operation (like reading a file) does not halt the execution of the program. Instead, the system starts the operation and immediately returns control, allowing other code to run. When the operation completes, a callback or promise is triggered. This is achieved through the event loop and underlying async system calls.

---

### 76. How do you handle large amounts of data in Node.js?
**Answer:** Use streams to process data in chunks, preventing memory overload. For databases, use cursors or pagination. For file uploads, use `multer` with streaming. Avoid loading everything into memory; instead, pipeline data through transforms.

---

### 77. What is the purpose of `npm` and how does it differ from `yarn`?
**Answer:** npm (Node Package Manager) is the default package manager for Node.js. Yarn is an alternative created by Facebook that focuses on speed, deterministic installs via a lockfile, and offline caching. Both manage dependencies defined in `package.json`.

---

### 78. How can you create a RESTful API using Node.js?
**Answer:** Use Express.js. Define routes for each resource with appropriate HTTP methods. Use middleware for parsing bodies, authentication, etc. Return JSON responses. Example:
```js
app.get('/api/users', (req, res) => res.json(users));
app.post('/api/users', (req, res) => { /* create user */ });
```

---

### 79. What is the role of the `assert` module in Node.js?
**Answer:** The `assert` module provides a set of assertion functions for testing invariants. It is useful for writing tests or validating internal logic. For example, `assert.strictEqual(actual, expected)`.

---

### 80. How can you use environment variables to configure a Node.js application?
**Answer:** Access them via `process.env`. Use a `.env` file with `dotenv` for development. Different environments (dev, test, prod) can have separate configuration files, with overrides via environment variables. This keeps secrets out of code.

---

### 81. What are the differences between Node.js and other server-side technologies like Python and Ruby?
**Answer:** Node.js is event‑driven and non‑blocking, making it excellent for I/O‑heavy applications. Python (Django, Flask) and Ruby (Rails) are often multi‑threaded or use different concurrency models. Node.js uses JavaScript, enabling full‑stack development, while Python/Ruby have different syntax and ecosystems.

---

### 82. How does Node.js handle backpressure in streams?
**Answer:** Backpressure occurs when a writable stream cannot process data as fast as a readable stream produces it. Node.js automatically handles this: when the writable stream’s buffer is full, the readable stream pauses (`pause()`). When the buffer drains, it resumes (`resume()`). Custom streams can implement `_write` and `_read` to manage backpressure manually.

---

### 83. What are some common performance issues in Node.js applications?
**Answer:**  
- Blocking the event loop with synchronous code or CPU‑intensive tasks.  
- Too many database queries (N+1 problem).  
- Large memory usage due to loading all data at once.  
- Unoptimized JSON parsing.  
- Frequent garbage collection pauses.

---

### 84. How can you debug a Node.js application?
**Answer:** Use the built‑in debugger: `node inspect app.js`. Use Chrome DevTools: start with `node --inspect` and open `chrome://inspect`. Also use `console.log`, `debug` module, or IDEs like VS Code with built‑in debugging.

---

### 85. What is the role of the `v8` module in Node.js?
**Answer:** The `v8` module exposes APIs specific to the V8 engine, such as `v8.getHeapStatistics()`, `v8.setFlagsFromString()`, and `v8.serialize()`. It allows you to inspect heap usage, set engine flags, and interact with the V8 runtime.

---

### 86. How can you use the `debug` module in Node.js?
**Answer:** The `debug` library provides namespaced debugging output. Set `DEBUG=namespace` environment variable to see logs. Example:
```js
const debug = require('debug')('app:server');
debug('Server started');
```

---

### 87. What are the different ways to manage dependencies in Node.js?
**Answer:**  
- `package.json` with version ranges.  
- Lockfiles (`package-lock.json` or `yarn.lock`) for deterministic installs.  
- Use `npm ci` for clean installs in CI.  
- Use `npm audit` to check for vulnerabilities.  
- Consider using `pnpm` for disk space efficiency.

---

### 88. How do you handle cross-platform issues in Node.js?
**Answer:** Use the `path` module for file paths. For line endings, be aware of differences (CRLF vs LF). Avoid shell commands that are OS‑specific; use Node.js APIs or libraries. For spawning processes, use cross‑platform command wrappers like `cross-env`.

---

### 89. How does Node.js integrate with frontend frameworks like React or Angular?
**Answer:** Node.js is often used as the backend API server for frontend frameworks. It can also serve the static build files. For SSR (Server‑Side Rendering), Node.js can render React components on the server. Tools like Next.js (React) or Angular Universal leverage Node.js for SSR.

---

### 90. What are the best practices for structuring a Node.js application?
**Answer:**  
- Separate concerns (routes, controllers, services, models).  
- Use environment configuration.  
- Keep code modular and testable.  
- Use middleware for cross‑cutting concerns.  
- Implement error handling centrally.  
- Use a consistent folder structure (e.g., `src/`, `tests/`).

---

### 91. How can you use `pm2` for managing Node.js processes?
**Answer:** PM2 is a process manager that keeps applications running forever, handles logs, and provides monitoring. Commands: `pm2 start app.js`, `pm2 list`, `pm2 logs`, `pm2 restart`. It also supports clustering (`pm2 start app.js -i max`).

---

### 92. What are the security implications of using third-party modules in Node.js?
**Answer:** Third‑party modules can contain vulnerabilities or malicious code. Always verify the module’s popularity, maintenance status, and audit with `npm audit`. Use tools like `snyk` to monitor vulnerabilities. Avoid using modules with excessive permissions.

---

### 93. How can you implement rate limiting in a Node.js application?
**Answer:** Use the `express-rate-limit` middleware. Configure the window and maximum number of requests per IP. Example:
```js
const rateLimit = require('express-rate-limit');
const limiter = rateLimit({ windowMs: 15*60*1000, max: 100 });
app.use('/api', limiter);
```

---

### 94. What are some common patterns for handling asynchronous operations in Node.js?
**Answer:**  
- **Callbacks** (error‑first).  
- **Promises** with `.then()`/`.catch()`.  
- **async/await** – recommended for readability.  
- **Event emitters** for multiple events.  
- **Streams** for processing data.

---

### 95. How can you create a CLI tool using Node.js?
**Answer:** Create a Node.js script with a shebang (`#!/usr/bin/env node`). Use `process.argv` to parse arguments, or use libraries like `commander` or `yargs` for robust CLI parsing. Publish to npm to make it globally installable.

---

### 96. How does Node.js manage and optimize garbage collection?
**Answer:** V8 uses a generational garbage collector: young generation (scavenger) for short‑lived objects, old generation (mark‑sweep/compact) for longer‑lived objects. To optimize, avoid creating too many objects in tight loops, use object pooling, and monitor memory usage. The `--max-old-space-size` flag can adjust heap limits.

---

### 97. What are some common pitfalls when working with Node.js?
**Answer:**  
- Blocking the event loop with synchronous code.  
- Not handling errors properly.  
- Using `require` inside tight loops.  
- Memory leaks from event listeners.  
- Misunderstanding the event loop (e.g., expecting `setTimeout` to be precise).  
- Overusing npm packages without vetting.

---

### 98. How can you implement caching in a Node.js application?
**Answer:** Use in‑memory caches (e.g., `node-cache`), Redis, or CDN caching. Cache database query results, API responses, or static assets. Implement cache invalidation strategies based on time (TTL) or events.

---

### 99. How can you use the `assert` module for testing in Node.js?
**Answer:** The `assert` module provides basic assertions. Example:
```js
const assert = require('assert');
assert.strictEqual(1 + 1, 2);
assert.throws(() => { throw new Error('fail'); });
```
For more features, use dedicated testing frameworks.

---

### 100. How do you handle different environments (development, staging, production) in Node.js applications?
**Answer:** Use environment variables (e.g., `NODE_ENV`) to switch configurations. Set different database URLs, logging levels, and API endpoints based on the environment. Use configuration files (e.g., `config/development.json`) and load them conditionally. Tools like `dotenv` help manage local settings.
