# Android Interview Questions and Answers (600+)

A free, topic-by-topic list of **Android interview questions with short answers**, covering Kotlin, Coroutines, Flow, Jetpack Compose, architecture, Hilt, Room, networking, performance, Gradle, system design and machine coding.

Every question links to a **full answer with Kotlin code** on [Droidly](https://droidly.io/?utm_source=github&utm_medium=repo&utm_campaign=aiq), a free Android interview prep site. There you can also:

- take a 10-minute **skill check** and get a **study plan for your level** (0–2, 2–5 or 5+ years)
- do **5 practice questions a day**, where the ones you miss come back until they stick
- solve **Kotlin machine coding problems** with tests that run in the browser

⭐ **Star this repo** to keep it handy for your next interview.

## Contents

| Topic | Questions | Covers |
|---|---|---|
| [Kotlin](questions/kotlin.md) | 50 | Null safety, data/sealed classes, scope functions, generics, inline/reified, delegation. |
| [Kotlin Coroutines](questions/coroutines.md) | 50 | Scopes, dispatchers, structured concurrency, cancellation, exception handling. |
| [Kotlin Flow](questions/flow.md) | 75 | Cold vs hot flows, StateFlow, SharedFlow, operators, backpressure. |
| [Jetpack Compose](questions/compose.md) | 50 | Recomposition, state, side effects, performance, navigation. |
| [Android Fundamentals](questions/android-fundamentals.md) | 50 | Lifecycle, components, process death, intents, services. |
| [Architecture](questions/architecture.md) | 50 | MVVM, MVI, clean architecture, modularisation, testing. |
| [Dependency Injection (Hilt & Dagger)](questions/hilt-dagger.md) | 50 | Components, scopes, modules, qualifiers, testing with Hilt. |
| [Networking](questions/networking.md) | 50 | Retrofit, OkHttp, interceptors, caching, error handling. |
| [Data Storage (Room & DataStore)](questions/room-datastore.md) | 50 | Room, migrations, DataStore, offline-first. |
| [Performance](questions/performance.md) | 50 | Memory leaks, ANRs, startup time, rendering, profiling. |
| [Gradle & Build](questions/gradle-build.md) | 50 | Build variants, R8, version catalogs, build speed. |
| [Behavioral (HR)](questions/behavioral.md) | 25 | How to answer the non-technical rounds. |
| [Android System Design](#android-system-design) | 13 designs | Chat app, image loader, payments, offline-first news… |
| [Machine Coding (Kotlin)](#machine-coding-kotlin) | 9 problems | LRU cache, rate limiter, event bus, retry with backoff… |

**By experience:** [Freshers (0–2 years)](https://droidly.io/android-interview-questions-for-freshers?utm_source=github&utm_medium=repo&utm_campaign=aiq) · [Experienced (2–5 years)](https://droidly.io/android-interview-questions-for-experienced?utm_source=github&utm_medium=repo&utm_campaign=aiq) · [Senior (5+ years)](https://droidly.io/senior-android-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq)

## Most asked questions, by topic

### Kotlin

**Q: Explain Kotlin's null safety system. What is the difference between ?, !!, ?:, and let?**

Null safety is arguably Kotlin's single biggest improvement over Java. Tony Hoare — who invented null references — called it his "billion dollar mistake." In Android specifically, NullPointerException is the #1 cause of app crashes in production.

[Full answer →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q1)

**Q: What is the difference between val, var, const val, lateinit var, and by lazy?**

Kotlin provides five distinct ways to declare and initialize values, each suited for a different scenario.

[Full answer →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q2)

**Q: What is a data class in Kotlin? What does it auto-generate and what are its limitations?**

A data class is Kotlin's mechanism for modeling pure data — classes whose primary purpose is to hold values rather than define behavior. Think of it as Kotlin's answer to Java's notorious record verbosity: instead of writing 100 lines for a simple model class (constructor, getters, equals, hashCode, toString, copy), you write one line.

[Full answer →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q3)

➡️ [All 50 Kotlin questions](questions/kotlin.md)

### Kotlin Coroutines

**Q: What is a Kotlin coroutine? How is it different from a thread?**

A coroutine is a suspendable computation — it can pause and resume without blocking the underlying thread. Unlike threads, thousands of coroutines can run on just a few threads, making them lightweight and efficient.

[Full answer →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q1)

**Q: What are Kotlin coroutine Dispatchers? Explain IO, Main, Default, and Unconfined.**

Dispatchers determine which thread or thread pool a coroutine runs on. Choosing the correct Dispatcher is fundamental to avoiding ANRs and crashes.

[Full answer →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q2)

**Q: What is structured concurrency? What is a CoroutineScope?**

Structured concurrency means coroutines live within a defined scope — they're started, managed, and cancelled as a group. This prevents orphaned coroutines and resource leaks.

[Full answer →](https://droidly.io/kotlin-coroutines-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q3)

➡️ [All 50 Kotlin Coroutines questions](questions/coroutines.md)

### Kotlin Flow

**Q: What is a Kotlin Flow? How is it different from a suspend function and LiveData?**

A Kotlin Flow is a cold, asynchronous stream that can emit multiple values over time — think of it like a pipe that carries a sequence of results, not just one. A suspend function returns one value and finishes.

[Full answer →](https://droidly.io/kotlin-flow-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q1)

**Q: What is the difference between StateFlow and SharedFlow? When do you use each?**

StateFlow is a hot flow with exactly one current value — it's a state holder. SharedFlow is a hot flow that can emit events without a persistent current value — it's an event bus.

[Full answer →](https://droidly.io/kotlin-flow-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q2)

**Q: What is flowOn? How does it differ from withContext inside a flow?**

flowOn changes the upstream dispatcher — the context in which emissions are produced. The downstream collector continues on whatever context it was launched in. This is the correct way to move flow production to a background thread. withContext inside a flow builder is a common but subtly problematic pattern.

[Full answer →](https://droidly.io/kotlin-flow-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q4)

➡️ [All 75 Kotlin Flow questions](questions/flow.md)

### Jetpack Compose

**Q: What is Jetpack Compose? How is it different from the View system?**

Jetpack Compose is Android's modern declarative UI toolkit. Instead of mutating views, you describe what the UI should look like for a given state — Compose figures out the updates.

[Full answer →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q1)

**Q: What is recomposition? How does Compose decide what to recompose and how do you minimise it?**

Recomposition is Compose re-executing a composable function when its inputs change. Understanding and minimising unnecessary recompositions is critical for performance.

[Full answer →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q2)

**Q: What is the difference between remember and rememberSaveable?**

Both persist state across recompositions, but rememberSaveable also survives configuration changes (rotation) and process death by saving to a Bundle.

[Full answer →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q3)

➡️ [All 50 Jetpack Compose questions](questions/compose.md)

### Android Fundamentals

**Q: Explain the Activity lifecycle. What happens when you press Home vs Back button?**

Think of an Activity's lifecycle like a person's daily routine — it's created in the morning, becomes active, goes to the background when interrupted, and eventually gets destroyed at night.

[Full answer →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q1)

**Q: What is the difference between Fragment lifecycle and Activity lifecycle? How do they interact?**

A Fragment is a reusable piece of UI that lives inside an Activity — think of it as a "mini Activity". Apps like Instagram use Fragments for each tab (Home, Search, Reels, Profile) inside one Activity.

[Full answer →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q2)

**Q: What are the different types of Intent? Explain explicit vs implicit with examples.**

An Intent is Android's messaging system — it's how components talk to each other.

[Full answer →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q3)

➡️ [All 50 Android Fundamentals questions](questions/android-fundamentals.md)

### Architecture

**Q: What is MVVM? Explain each layer and its responsibility.**

MVVM (Model-View-ViewModel) separates UI from business logic. Each layer has a single, clear responsibility — making the code testable, maintainable, and rotation-safe.

[Full answer →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q1)

**Q: What is Clean Architecture? How does it differ from plain MVVM?**

Clean Architecture adds a Domain layer with use cases between ViewModel and Repository, enforcing strict dependency rules. Inner layers know nothing about outer layers — Domain is pure Kotlin.

[Full answer →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q2)

**Q: What is MVI architecture? How does it differ from MVVM?**

MVI (Model-View-Intent) enforces strict unidirectional data flow with a single immutable state object. Every user action is an Intent that goes through a reducer — fully predictable and consistent.

[Full answer →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q3)

➡️ [All 50 Architecture questions](questions/architecture.md)

### Dependency Injection (Hilt & Dagger)

**Q: What is Dependency Injection and why do we need it? What problems does it solve?**

Dependency Injection is a pattern where objects receive their dependencies from outside instead of creating them internally. It solves tight coupling, poor testability, and hidden dependencies.

[Full answer →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q1)

**Q: What is Hilt? How does it differ from Dagger 2, and why did Google recommend it over plain Dagger?**

Hilt is Google's opinionated DI framework built on top of Dagger 2. It eliminates the massive boilerplate of Dagger while keeping compile-time code generation and type safety.

[Full answer →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q2)

**Q: Explain all Hilt component scopes and their lifetimes. What happens if you use the wrong scope?**

Hilt's scope annotations control how long a dependency lives. Using too broad a scope causes memory leaks; too narrow causes wasteful re-creation of expensive objects.

[Full answer →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q3)

➡️ [All 50 Dependency Injection (Hilt & Dagger) questions](questions/hilt-dagger.md)

### Networking

**Q: What is Retrofit? How does it work under the hood?**

Retrofit is a type-safe HTTP client for Android. You write an interface with annotated methods, and Retrofit generates the implementation at runtime using reflection and a dynamic proxy.

[Full answer →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q1)

**Q: What is OkHttp? How does it relate to Retrofit?**

OkHttp is the actual HTTP engine — it makes the TCP connection, sends bytes, receives bytes. Retrofit sits on top and adds type safety. Think of OkHttp as the car engine, and Retrofit as the dashboard you interact with.

[Full answer →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q2)

**Q: What is an OkHttp Interceptor? What are the two types and when do you use each?**

An interceptor is a middleware that sits in the HTTP request/response pipeline. Every request flows through your interceptors before reaching the server, and every response flows back through them.

[Full answer →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q3)

➡️ [All 50 Networking questions](questions/networking.md)

### Data Storage (Room & DataStore)

**Q: What is Room? How does it compare to using SQLite directly?**

Room is Jetpack's database library — a thin, type-safe layer on top of SQLite. It generates boilerplate SQL code at compile time, validates your queries, and integrates with coroutines and Flow out of the box.

[Full answer →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q1)

**Q: What is a Room DAO? What annotations do you use for CRUD operations?**

DAO (Data Access Object) is the interface that defines how you interact with the database. Room generates the implementation — you just declare what you want to do, and Room figures out the SQL.

[Full answer →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q2)

**Q: How do you observe data changes in Room using Flow? How is this better than LiveData?**

A DAO that returns Flow automatically emits a new value whenever the underlying table changes. This creates a reactive pipeline from database → ViewModel → UI with no manual refresh needed.

[Full answer →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q3)

➡️ [All 50 Data Storage (Room & DataStore) questions](questions/room-datastore.md)

### Performance

**Q: What is a memory leak in Android? What are the most common causes?**

A memory leak occurs when objects are kept in memory after they're no longer needed — the garbage collector can't reclaim them because something still holds a reference.

[Full answer →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q1)

**Q: How do you detect and fix memory leaks using LeakCanary and Android Studio Memory Profiler?**

LeakCanary detects leaks automatically by watching objects that should be garbage collected -- if they're still alive after 5 GC cycles, it captures a heap dump and traces the shortest reference path.

[Full answer →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q2)

**Q: What is overdraw? How do you detect and reduce it?**

Overdraw happens when a pixel is drawn more than once in the same frame — a background behind a background behind a view. Each overdraw wastes GPU time and can cause frame drops on low-end devices.

[Full answer →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q3)

➡️ [All 50 Performance questions](questions/performance.md)

### Gradle & Build

**Q: What is Gradle? How does the Android build system work at a high level?**

Gradle is the build automation tool for Android. It takes your source code, resources, and dependencies, then compiles, optimises, and packages them into an APK or AAB.

[Full answer →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q1)

**Q: What is the difference between APK and AAB? Why does Google prefer AAB?**

APK (Android Package) is the traditional installable file -- it contains code, resources, and native libraries for every device configuration. AAB (Android App Bundle) is a publishing format: you upload it to Play Store, and Play generates device-specific APKs from it.

[Full answer →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q2)

**Q: What is R8? How does it differ from ProGuard? What does it do to your app?**

R8 is the modern replacement for ProGuard — it does code shrinking, obfuscation, and optimisation in a single pass. It's significantly faster than ProGuard and produces smaller output.

[Full answer →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q3)

➡️ [All 50 Gradle & Build questions](questions/gradle-build.md)

### Behavioral (HR)

**Q: Tell me about yourself. Walk me through your background as an Android developer.**

Use the Present → Past → Future framework. Keep it under 2 minutes, stay technical but accessible, and end by connecting your story to this role.

[Full answer →](https://droidly.io/android-developer-behavioral-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q1)

**Q: Tell me about a challenging technical problem you solved. How did you approach it?**

Use STAR (Situation, Task, Action, Result). Choose a problem with real technical depth — a performance regression, a memory leak, a complex architecture decision.

[Full answer →](https://droidly.io/android-developer-behavioral-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q2)

**Q: Describe a time you disagreed with a technical decision made by your team or manager. What did you do?**

This tests your ability to be assertive without being combative, and to commit once a decision is made. Show both — disagreement and commitment.

[Full answer →](https://droidly.io/android-developer-behavioral-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q3)

➡️ [All 25 Behavioral (HR) questions](questions/behavioral.md)

## Android System Design

Mobile system design rounds, worked end to end (requirements, architecture, offline, caching, trade-offs):

- [Chat App](https://droidly.io/sysdesign_chat_hi_style?utm_source=github&utm_medium=repo&utm_campaign=aiq)
- [Analytics SDK](https://droidly.io/sysdesign_analyticsdk?utm_source=github&utm_medium=repo&utm_campaign=aiq)
- [Payment System](https://droidly.io/sysdesign_payment?utm_source=github&utm_medium=repo&utm_campaign=aiq)
- [E-commerce Product Listing](https://droidly.io/sysdesign_ecommerce?utm_source=github&utm_medium=repo&utm_campaign=aiq)
- [File Download Manager](https://droidly.io/sysdesign_filedownload?utm_source=github&utm_medium=repo&utm_campaign=aiq)
- [Image Loading Library](https://droidly.io/sysdesign_imageloader?utm_source=github&utm_medium=repo&utm_campaign=aiq)
- [Instagram-Style Feed](https://droidly.io/sysdesign_instafeed?utm_source=github&utm_medium=repo&utm_campaign=aiq)
- [Maps & Live Location](https://droidly.io/sysdesign_mapslocation?utm_source=github&utm_medium=repo&utm_campaign=aiq)
- [Offline-First News App](https://droidly.io/sysdesign_offlinenews?utm_source=github&utm_medium=repo&utm_campaign=aiq)
- [Push Notification System](https://droidly.io/sysdesign_pushnotif?utm_source=github&utm_medium=repo&utm_campaign=aiq)
- [Ride-Sharing App](https://droidly.io/sysdesign_ridesharing?utm_source=github&utm_medium=repo&utm_campaign=aiq)
- [Video Streaming App](https://droidly.io/sysdesign_videostreaming?utm_source=github&utm_medium=repo&utm_campaign=aiq)
- [Networking SDK (like Retrofit)](https://droidly.io/sysdesign_networkingsdk?utm_source=github&utm_medium=repo&utm_campaign=aiq)

## Machine Coding (Kotlin)

Problems from Android machine coding rounds. Each has hints, an approach and pass/fail tests you can run in the browser:

- [LRU cache](https://droidly.io/machine-coding/lru-cache?utm_source=github&utm_medium=repo&utm_campaign=aiq)
- [Token bucket rate limiter](https://droidly.io/machine-coding/token-bucket-rate-limiter?utm_source=github&utm_medium=repo&utm_campaign=aiq)
- [Event bus](https://droidly.io/machine-coding/event-bus?utm_source=github&utm_medium=repo&utm_campaign=aiq)
- [Pagination manager](https://droidly.io/machine-coding/pagination-manager?utm_source=github&utm_medium=repo&utm_campaign=aiq)
- [Retry with exponential backoff](https://droidly.io/machine-coding/retry-with-exponential-backoff?utm_source=github&utm_medium=repo&utm_campaign=aiq)
- [Shopping cart with discounts](https://droidly.io/machine-coding/shopping-cart-with-discounts?utm_source=github&utm_medium=repo&utm_campaign=aiq)
- [In-memory cache with TTL](https://droidly.io/machine-coding/in-memory-cache-with-ttl?utm_source=github&utm_medium=repo&utm_campaign=aiq)
- [Order state machine](https://droidly.io/machine-coding/order-state-machine?utm_source=github&utm_medium=repo&utm_campaign=aiq)
- [Restaurant bill screen (Compose)](https://droidly.io/machine-coding/restaurant-bill-screen?utm_source=github&utm_medium=repo&utm_campaign=aiq)

## How to use this list

1. **Answer out loud first**, the way you would in the interview room, then read the short answer.
2. Open the **full answer** for anything you could not explain in 2 minutes.
3. Focus on the **⭐ Most asked** questions in each topic first.
4. For a plan built around your weak topics, take the free skill check on **[droidly.io](https://droidly.io/roadmap?utm_source=github&utm_medium=repo&utm_campaign=aiq)**.

## Found a mistake?

Open an issue, or use "Report an issue with this answer" under any answer on Droidly.

---

Made by [Vivek Choudhary](https://www.linkedin.com/in/vivek-choudhary-4686b477), Android engineer, founder of [Droidly](https://droidly.io/?utm_source=github&utm_medium=repo&utm_campaign=aiq).
