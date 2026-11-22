# Kotlin Coroutines Interview Questions (50)

Scopes, dispatchers, structured concurrency, cancellation, exception handling.

Short answers below. **Each question links to the full answer with Kotlin code on [Droidly](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq)**, where you can also mark what you know and get a study plan.

⬅️ [All topics](../README.md)

## ⭐ Most asked

### 1. What is a Kotlin coroutine? How is it different from a thread?

🟢 Easy

> A coroutine is a suspendable computation — it can pause and resume without blocking the underlying thread. Unlike threads, thousands of coroutines can run on just a few threads, making them lightweight and efficient.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q1)**

### 2. What are Kotlin coroutine Dispatchers? Explain IO, Main, Default, and Unconfined.

🟢 Easy

> Dispatchers determine which thread or thread pool a coroutine runs on. Choosing the correct Dispatcher is fundamental to avoiding ANRs and crashes.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q2)**

### 3. What is structured concurrency? What is a CoroutineScope?

🟢 Easy

> Structured concurrency means coroutines live within a defined scope — they're started, managed, and cancelled as a group. This prevents orphaned coroutines and resource leaks.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q3)**

### 4. What is the difference between launch and async?

🟢 Easy

> launch fires and forgets — it returns a Job. async starts a concurrent operation and returns a Deferred — a future value you can await.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q4)**

### 5. What is coroutine cancellation? How does it work and how do you make code cancellation-safe?

🟡 Medium

> Coroutine cancellation is cooperative — the coroutine must check for cancellation. Suspend functions do this automatically; CPU-heavy loops must check manually.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q5)**

### 6. What is the difference between Job and SupervisorJob? When do you use each?

🟡 Medium

> Job propagates failure to siblings — one child failing cancels all. SupervisorJob isolates failures — each child is independent. Android's viewModelScope uses SupervisorJob.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q6)**

### 7. What is exception handling in coroutines? How do CoroutineExceptionHandler and try-catch differ?

🟡 Medium

> Coroutine exception handling is nuanced — try-catch works inside coroutines, but CoroutineExceptionHandler is a last-resort handler for unhandled exceptions in launch.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q7)**

### 8. What is Kotlin Flow? How is it different from LiveData and RxJava?

🟡 Medium

> Flow is Kotlin's reactive stream — a cold, sequential sequence of values emitted asynchronously. It's Kotlin-native, coroutine-integrated, and lighter than RxJava.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q8)**

### 9. What is the difference between StateFlow and SharedFlow? When do you use each?

🔴 Hard

> Both are hot flows — they emit regardless of collectors. StateFlow is state (current value, replay=1). SharedFlow is events (configurable replay, no value requirement).

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q9)**

### 10. Explain the key Flow operators — map, filter, transform, zip, combine, flatMapLatest.

🔴 Hard

> Flow operators are the core of reactive programming. Each transforms the stream differently — mastering them is essential for clean, efficient reactive Android code.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q10)**

### 11. What is withContext and how is it different from launch/async?

🟡 Medium

> withContext switches the coroutine to a different dispatcher and returns a result — it's a scope switch, not a new coroutine. This makes it efficient for switching context mid-operation.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q11)**

### 14. What are coroutine contexts and how do they compose?

🟡 Medium

> A CoroutineContext is a set of elements that define a coroutine's behavior — dispatcher, job, name, and exception handler. Elements combine with the + operator.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q14)**

### 17. How do you test coroutines and Flow? Explain TestCoroutineDispatcher and Turbine.

🟡 Medium

> Coroutine testing requires controlling time and dispatchers. The kotlinx-coroutines-test library provides TestDispatcher and runTest for fast, deterministic tests.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q17)**

### 19. What is the difference between collect, collectLatest, and launchIn for Flow collection?

🟡 Medium

> Three different ways to collect a Flow — each with different behavior for slow collectors and coroutine scope management.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q19)**

### 21. What are the main threading rules in Android and how do coroutines help?

🟡 Medium

> Android has strict threading rules — UI can only be updated on the main thread, network/disk must not block the main thread. Coroutines make these rules easy to follow.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q21)**

### 22. What is the purpose of viewModelScope, lifecycleScope, and viewLifecycleOwner.lifecycleScope?

🟡 Medium

> Android provides three built-in scopes tied to different lifecycle owners. Choosing the right one prevents memory leaks and cancelled-work bugs.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q22)**

### 24. How do you convert callback-based APIs to coroutines using suspendCoroutine and suspendCancellableCoroutine?

🟡 Medium

> Legacy libraries use callbacks. suspendCancellableCoroutine wraps them into suspend functions — the modern, clean way to bridge callback APIs with coroutines.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q24)**

### 28. What is Flow.debounce and Flow.throttle? Give real-world examples.

🟡 Medium

> Debounce waits for a pause before emitting. Throttle limits emission rate. Both are critical for search fields, button clicks, and real-time updates.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q28)**

### 30. What is the difference between coroutines and threads in terms of memory and scheduling?

🟡 Medium

> Coroutines and threads both achieve concurrency but with completely different resource models. A thread is an OS-level resource -- creating thousands is expensive.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q30)**

### 32. What is Flow.zip vs Flow.combine? When do you choose each?

🟡 Medium

> zip pairs values 1:1 and waits for both. combine emits whenever either source changes — different semantics for different use cases.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q32)**

### 34. What is coroutine flow's catch operator vs try-catch? How do you handle errors in a Flow chain?

🟡 Medium

> Flow error handling has specific rules — catch only handles upstream errors, and exceptions in collect must be handled with try-catch. Understanding the asymmetry prevents bugs.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q34)**

### 36. What is Dispatchers.Main.immediate and when do you need it?

🟡 Medium

> Main.immediate skips the message queue if already on the main thread — executing immediately rather than posting to the handler. This avoids one frame of latency in common scenarios.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q36)**

### 38. What is the difference between coroutineScope and runBlocking?

🟡 Medium

> Both create a coroutine scope and wait for all children — but coroutineScope suspends (non-blocking) while runBlocking blocks the thread. runBlocking is for tests and main functions only.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q38)**

### 41. How does Flow work with Room database? Explain the reactive database pattern.

🟡 Medium

> Room's Flow integration is one of Android's most powerful patterns — the database becomes a reactive source that automatically notifies the UI of any changes.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q41)**

### 43. What is the difference between delay() and Thread.sleep() in coroutines?

🟡 Medium

> delay() is coroutine-aware — it suspends the coroutine without blocking the thread. Thread.sleep() blocks the OS thread — never use it inside coroutines.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q43)**

### 45. What is the difference between launch(Dispatchers.IO) and withContext(Dispatchers.IO)?

🟡 Medium

> launch creates a new concurrent coroutine. withContext switches the current coroutine to a different dispatcher sequentially. This distinction affects concurrency, result access, and code clarity.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q45)**

### 47. What is the coroutine Job hierarchy? How do you use joinAll and cancelAndJoin?

🟡 Medium

> Jobs form a tree hierarchy — parent tracks children. joinAll waits for multiple jobs, cancelAndJoin cancels and waits for cleanup to complete.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q47)**

## More questions

### 12. What is cold vs hot flow? How do stateIn and shareIn work?

🔴 Hard

> Cold flows execute fresh for each collector. Hot flows share a single execution with all collectors. stateIn and shareIn convert cold flows to hot StateFlow/SharedFlow.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q12)**

### 13. What are Kotlin Channels? Explain Channel types and how they differ from Flow.

🔴 Hard

> Channels are hot communication primitives for sending values between coroutines — like a queue. Unlike Flow, Channels are consumed — each value is received by exactly one collector.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q13)**

### 15. What is the Flow lifecycle? Explain onStart, onCompletion, and onEach.

🔴 Hard

> Flow lifecycle operators let you hook into collection events — emission start, each value, completion, and errors. They're used for logging, loading indicators, and cleanup.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q15)**

### 16. What is backpressure in Flow? How does Kotlin Flow handle it?

🔴 Hard

> Backpressure occurs when a producer emits faster than the consumer processes. Kotlin Flow handles it through suspension — the emitter naturally slows to match the consumer.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q16)**

### 18. What is the difference between suspend fun and regular fun? How does the compiler transform suspend functions?

🔴 Hard

> The suspend modifier triggers a compile-time transformation — the compiler adds a Continuation parameter and generates a state machine. No JVM magic involved.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q18)**

### 20. What is mutex and how do you handle concurrent state updates safely?

🔴 Hard

> When multiple coroutines access shared mutable state, race conditions occur. Kotlin provides Mutex — a coroutine-friendly lock — and atomic operations for thread-safe state.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q20)**

### 23. What is a coroutine flow vs a sequence? When would you use Sequence over Flow?

🔴 Hard

> Both are lazy, sequential, and use the same operators. The key difference: Sequence is synchronous (blocking), Flow is asynchronous (suspending). Never use Sequence for IO operations.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q23)**

### 25. Scenario: Your app makes 3 API calls — user, orders, and recommendations. Some can run in parallel. How do you structure this?

🔴 Hard

> This is a classic concurrency design question. The correct structure depends on dependencies between calls — independent calls should be parallel, dependent calls sequential.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q25)**

### 26. Scenario: A network request is taking too long. How do you implement a timeout in coroutines?

🔴 Hard

> Coroutines provide withTimeout and withTimeoutOrNull for clean timeout handling — far simpler than the thread-based alternatives.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q26)**

### 27. Scenario: You need to retry a failed network call with exponential backoff. How do you implement this with coroutines?

🔴 Hard

> Retry with exponential backoff is a production pattern for resilient network calls. Coroutines make it clean with a simple loop and delay.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q27)**

### 29. Scenario: You need to implement a polling mechanism — check server every 5 seconds for order status. How do you implement this cleanly?

🔴 Hard

> Polling with coroutines is elegant — a simple loop with delay. The scope lifecycle handles cleanup automatically, and you can stop on success or error.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q29)**

### 31. What is the actor pattern in coroutines? How does it help with concurrent state?

🔴 Hard

> The actor pattern confines mutable state to a single coroutine. All mutations happen via message-passing through a channel — eliminating shared state and race conditions.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q31)**

### 33. Scenario: Your app does a lot of image processing on photos selected from gallery. The UI freezes. How do you fix it using coroutines?

🔴 Hard

> Image processing is CPU-intensive — it should run on Dispatchers.Default. Combining it with a proper scope and progress updates keeps the UI responsive.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q33)**

### 35. What is structured concurrency's parent-child relationship? How does exception propagation work?

🔴 Hard

> In structured concurrency, parent and child coroutines have a strict relationship — parent waits for children, children cancel with parent, and exceptions propagate up unless isolated.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q35)**

### 37. Scenario: You need to upload 50 files. Show progress per file, support cancellation, and don't crash if one fails.

🔴 Hard

> This combines parallel execution, progress reporting, error isolation, and cancellation — a comprehensive coroutines scenario covering all major concepts.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q37)**

### 39. Scenario: Your app should load cached data immediately, then refresh from network in background. How do you implement this?

🔴 Hard

> The "stale-while-revalidate" pattern: show cache immediately, then fetch fresh data in background. This is implemented with Flow merging or sequential emissions.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q39)**

### 40. What is limitedParallelism? How do you control coroutine concurrency?

🔴 Hard

> limitedParallelism creates a view of a dispatcher that limits how many coroutines can run concurrently — crucial for rate limiting, resource control, and avoiding server overload.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q40)**

### 42. Scenario: You have a coroutine that's leaking — it keeps running after the screen is dismissed. How do you diagnose and fix this?

🔴 Hard

> Coroutine leaks are a common production issue. They occur when coroutines outlive their scope — typically from GlobalScope, wrong scope choice, or missing cancellation.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q42)**

### 44. Scenario: Implement a real-time chat using WebSocket with automatic reconnection using Flow.

🔴 Hard

> WebSocket + Flow with auto-reconnection demonstrates callbackFlow, retry operators, and lifecycle-aware collection — a senior-level architecture question.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q44)**

### 46. What are coroutine flow transformations — mapLatest, transformLatest, and their use cases?

🔴 Hard

> mapLatest and transformLatest cancel the previous transformation when a new value arrives — combining mapping with the cancellation behavior of flatMapLatest.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q46)**

### 48. Scenario: Design a download manager that downloads multiple files, shows progress, supports pause and resume, and retries on failure.

🔴 Hard

> A download manager combines all coroutine concepts: Jobs, Channels for progress, pause/resume with StateFlow, retry on failure, and Flow for observable state.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q48)**

### 49. What are the latest coroutine improvements in Kotlin 2024-2025?

🔴 Hard

> Kotlin coroutines in 2024-25 received several improvements: structured concurrency enforcement, coroutineScope builders for parallel decomposition, improved Flow operators, and better integration with Compose via collectAsStateWithLifecycle.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q49)**

### 50. Scenario: You're reviewing a PR and find this code — what's wrong and how do you fix it?

🔴 Hard

> Code review questions test whether you can identify multiple coroutine anti-patterns — a favourite senior interview technique.

**[Full answer with code →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q50)**

---

Practise these with spaced repetition and a plan for your level: **[droidly.io](https://droidly.io/?utm_source=github&utm_medium=repo&utm_campaign=aiq)**
