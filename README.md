# Asynchronous Programming

> Map of Async Primitives for JavaScript and TypeScript

Granularity:
- no: callback, AbortSignal/AbortController
- single value (fine-grained): Promise, Deferred, Future, Signal, Automata (FSM)
- multiple finite: Thenable, async collection
- multiple infinite: js iterator, gof patterns iterator, generators, async queue

Flow:
- control flow: generators, async/await
- middle class: js iterator (for await)
- event flow: signal, AbortSignal/AbortController, observer (eventEmitter, EventTarget), Stream

Propagation:
- Push: callback, promise, event abstractions, signal
- Pull: js iterator (for await), generator
- Hybrid: streams, async queue, async collection

State ownership:
- Exclusive: future, iterator
- Shared: mutex, locks, semaphore,
- Isolated (container): Actor, Threads
- Cooperative: GoF: Chain of Responsibility, middleware
- Transactional: CAS (Atomics.wait, notify, waitAsync), TODO

Lazyness:
- immediate: promise, timers, callbacks, all except...
- layzy: future, function returning factory, async function conposition (pipe), do, manadic chains

By paradigm:
- FP: lazy, exclusive
- OOP and Procedural: everythin else

| Applied 💯     | Advanced 🧑‍🎓                | System ⚙️           | Elective 🧑‍🚀           | Legacy 🕰️          |
|:--------------|:--------------------------|:-------------------|:---------------------|:------------------|
| `callbacks`   | `AsyncQueue`              | `Thenable`         | `compose callbacks`  | `Deferred`        |
| `promises`    | `AsyncPool`               | `Semaphore`        | `async compose`      | `function*/yield` |
| `async/await` | `AsyncCollector`          | `Mutex`            | `Observer`           | `Async.js`        |
| `events`      | `Chain of responsibility` | `Spin Lock`        | `Future`             | `Metasync`        |
| `streams`     | `Async Generator`         | `MessageChannel`   | `coroutines`         | `middleware`      |
| `signals`     | `GoF pattern Iterator`    | `BroadcastChannel` | `Actor Model`        | `RxJS`            |
| `locks`       | `Actor pattern`           | `threads`          | `do`                 |                   |
| `iterators`   | `Disposable`              | `processes`        |                      |                   |
