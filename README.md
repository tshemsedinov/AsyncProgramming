# Asynchronous Programming

> Map of Async Primitives for JavaScript and TypeScript

**Granularity (what is delivered asynchronously).**

- None or single: callbacks; `AbortSignal` / `AbortController`.
- Single value (fine-grained): `Promise`; `Deferred`; `Future`; reactive **Signal**; finite automata (FSM) as step machines.
- Finite multiplicity: `Thenable` in general; async collections / aggregators; `AsyncCollector`-style batching.
- Unbounded multiplicity: synchronous iterators; **GoF Iterator**; `function*` / `yield`; async generators; async iterators; `AsyncQueue`.

**Flow (how structure is expressed).**

- Control flow: generators; `async` / `await`; `for await` … `of`; *coroutines* in the JS sense (cooperative threads of control built from those primitives).
- Event / push (incl. **Observer**): `Signal`; `AbortSignal` / `AbortController`; `EventEmitter` / `EventTarget`; `Stream`.

**Propagation.**

- Push: callbacks; promises; event APIs; signals.
- Pull: JS iterators (`for await`); generators.
- Hybrid: streams; async queues; async collections; `MessageChannel` / `MessagePort`; `BroadcastChannel`; optional RxJS-style reactive pipelines.

**State ownership.**

- Exclusive progression: futures; iterators; **`Disposable`** / async teardown scopes (single owner of cleanup).
- Shared: `Mutex`; `Semaphore`; admission / worker pools (`AsyncPool`); other locks; spin locks.
- Isolated containers: **Actor model** / **Actor pattern**; worker **threads**; child **processes**.
- Cooperative delegation: Chain of Responsibility; **middleware** stacks; **callback composition**; library-style **async compose**.
- Transactional / atomic: CAS-style patterns (`Atomics`, `wait` / `notify` / `waitAsync`).

**Eagerness.**

- Immediate / eager: scheduled promises; timers; typical fire-and-forget callbacks (unless wrapped).
- Lazy: futures started on demand; factories; async composition (`pipe`, monadic chains, **`do` notation**-style builders); explicit “run later” combinators.

**Paradigm (heuristic).**

- Functional idioms often favor lazy and exclusive-progression abstractions.
- Object-oriented and procedural code commonly mixes the other categories.
- **Legacy** stacks: callback libraries such as **Async.js** and **Metasync** mainly teach composition and error propagation over pre-Promise APIs.

Course: https://github.com/HowProgrammingWorks/Index/blob/master/Courses/Async-2026.md
