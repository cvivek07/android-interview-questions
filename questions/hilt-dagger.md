# Dependency Injection (Hilt & Dagger) Interview Questions (50)

Components, scopes, modules, qualifiers, testing with Hilt.

Short answers below. **Each question links to the full answer with Kotlin code on [Droidly](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq)**, where you can also mark what you know and get a study plan.

⬅️ [All topics](../README.md)

## ⭐ Most asked

### 1. What is Dependency Injection and why do we need it? What problems does it solve?

🟢 Easy

> Dependency Injection is a pattern where objects receive their dependencies from outside instead of creating them internally. It solves tight coupling, poor testability, and hidden dependencies.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q1)**

### 2. What is Hilt? How does it differ from Dagger 2, and why did Google recommend it over plain Dagger?

🟢 Easy

> Hilt is Google's opinionated DI framework built on top of Dagger 2. It eliminates the massive boilerplate of Dagger while keeping compile-time code generation and type safety.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q2)**

### 3. Explain all Hilt component scopes and their lifetimes. What happens if you use the wrong scope?

🟡 Medium

> Hilt's scope annotations control how long a dependency lives. Using too broad a scope causes memory leaks; too narrow causes wasteful re-creation of expensive objects.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q3)**

### 4. What is the difference between @Provides and @Binds? When do you use each?

🟡 Medium

> @Provides executes code to build a dependency. @Binds declares which implementation satisfies an interface — zero code, just a mapping. @Binds is more efficient and preferred for interface bindings.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q4)**

### 5. How do you write unit tests and instrumented tests with Hilt? Explain TestInstallIn and @HiltAndroidTest.

🟡 Medium

> Hilt provides two testing strategies: TestInstallIn for replacing modules in unit/instrumented tests, and HiltAndroidTest for full instrumented test flows. Both allow swapping real deps for fakes.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q5)**

### 9. What is field injection vs constructor injection in Hilt? Which is preferred and why?

🟡 Medium

> Constructor injection is always preferred — it makes dependencies explicit, enables immutability, and works with null-safety. Field injection is a necessary workaround for classes the framework instantiates.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q9)**

### 11. What is Koin? How does it compare to Hilt and when would you choose it?

🟡 Medium

> Koin is a lightweight DI framework using a Kotlin DSL. It's simpler to set up and multiplatform-ready, but catches DI errors at runtime instead of compile time.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q11)**

### 13. What is manual dependency injection (without a framework)? When does it make sense?

🟡 Medium

> Manual DI is wiring dependencies yourself using a container or factory — no annotation processing or framework. It's appropriate for small projects, libraries, or KMP modules where Hilt's Android dependency is a problem.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q13)**

### 16. What is the service locator pattern? How does it differ from DI, and why is it considered an anti-pattern?

🟡 Medium

> Service locator is a global registry where classes PULL their dependencies. DI PUSHES dependencies into classes. Service locator hides dependencies and makes testing harder — it's considered an anti-pattern.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q16)**

### 18. What is lazy injection in Hilt/Dagger? How does dagger.Lazy&lt;T&gt; differ from Kotlin's lazy?

🟡 Medium

> Dagger's Lazy&lt;T&gt; defers dependency creation until first call to get() — the dependency is still injected at construction, but the instance is created lazily. Different from Kotlin's lazy which controls property initialization.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q18)**

### 22. What is optional injection in Hilt? How do you handle nullable or optional dependencies?

🟡 Medium

> Hilt doesn't natively support nullable injection — if a binding is missing, it's a build error. Optional dependencies are handled by providing a null or default implementation, or using Kotlin optional types with special handling.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q22)**

### 24. What is the purpose of @ApplicationContext and @ActivityContext in Hilt?

🟡 Medium

> Hilt provides two qualifier annotations to inject Android Context correctly — preventing the most common memory leak of using Activity context where Application context is appropriate.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q24)**

## More questions

### 6. What are Hilt custom qualifiers? How do you inject multiple implementations of the same interface?

🔴 Hard

> When two @Provides methods return the same type, Hilt can't decide which to inject. Custom @Qualifier annotations distinguish between bindings — type-safe unlike @Named strings.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q6)**

### 7. Scenario: You need to inject different analytics implementations — Firebase for production, LogAnalytics for debug builds. How do you do this with Hilt?

🔴 Hard

> Build-variant-specific DI uses Gradle source sets combined with Hilt modules — each variant gets its own module binding the right implementation. Zero if/else in production code.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q7)**

### 8. Scenario: How do you set up Hilt in a multi-module Android project? What are the common pitfalls?

🔴 Hard

> Hilt in multi-module requires each module to declare its own @Module classes, and only :app needs @HiltAndroidApp. Cross-module dependencies are wired through standard @InstallIn modules.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q8)**

### 10. What is Hilt's @EntryPoint? When do you need it and how does it work?

🔴 Hard

> @EntryPoint lets you inject dependencies into classes that Hilt doesn't support directly — like custom View classes, ContentProviders, or third-party framework components.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q10)**

### 12. Scenario: A ViewModel needs a dependency that changes based on user login state (authenticated vs guest). How do you handle this with Hilt?

🔴 Hard

> Dynamic dependencies based on runtime state shouldn't be injected at construction time — inject a factory or a repository that encapsulates the state logic. DI is for static wiring, not runtime decisions.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q12)**

### 14. What are Hilt multibindings (@IntoSet, @IntoMap)? Give a real-world use case.

🔴 Hard

> Multibindings let multiple modules contribute to a single collection — a Set or Map — without any module knowing about the others. Perfect for plugin architectures and interceptor chains.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q14)**

### 15. Scenario: You have a circular dependency in your DI graph — A depends on B and B depends on A. How do you detect and fix it?

🔴 Hard

> Circular dependencies are a build-time error in Hilt/Dagger — the graph literally can't be constructed. The fix is to break the cycle by introducing an abstraction, a lazy reference, or restructuring responsibilities.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q15)**

### 17. Scenario: You're migrating from manual DI (AppContainer) to Hilt in a large existing app. What's your strategy?

🔴 Hard

> Migrating from manual DI to Hilt is an incremental process — never a big-bang rewrite. Convert the dependency graph leaf-first, validate as you go, and replace the AppContainer incrementally.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q17)**

### 19. Scenario: You need to inject a dependency into a WorkManager Worker. How does Hilt support this?

🔴 Hard

> WorkManager Workers are created by the system, not by your code — you need a special Hilt worker factory to inject dependencies. This is one of Hilt's built-in integrations.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q19)**

### 20. What is Assisted Injection in Hilt? When do you need it and how does it work?

🔴 Hard

> Assisted injection mixes Hilt-provided dependencies with runtime parameters — for objects that need both static DI-managed deps AND dynamic values known only at creation time.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q20)**

### 21. Scenario: Your team decides to adopt Hilt but the senior dev says "We already have clean interfaces — DI without a framework is enough." How do you respond?

🔴 Hard

> The objection to Hilt is usually about build time overhead from annotation processing. The answer: migrate annotation processors from KAPT to KSP (2x faster), use Hilt's incremental processing, and benchmark before vs after.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q21)**

### 23. Scenario: Review this Hilt code — find all the problems and fix them.

🔴 Hard

> DI code review questions test whether you can spot scope mistakes, context leaks, incorrect annotation usage, and structural issues simultaneously.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q23)**

### 25. Scenario: You're leading a team and a junior asks "when should I NOT use DI?" — how do you answer?

🔴 Hard

> DI is a pattern with real costs — annotation processing overhead, boilerplate, and learning curve. Knowing when NOT to use it shows architectural maturity over dogmatic application.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q25)**

### 26. How does Hilt handle ViewModel injection under the hood? What does @HiltViewModel actually generate?

🔴 Hard

> @HiltViewModel triggers compile-time code generation — Hilt creates a ViewModelFactory that Dagger wires automatically. Understanding what's generated explains why certain patterns work and others don't.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q26)**

### 27. Scenario: Your app has a complex DI graph with 50+ modules. Hilt's build time is slow. How do you diagnose and optimise it?

🔴 Hard

> Large Hilt graphs slow down because KSP/Dagger must process and validate the entire component tree. Strategic module restructuring and build configuration tuning are the main levers.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q27)**

### 28. What is Hilt's component hierarchy? How do child components inherit from parent components?

🔴 Hard

> Hilt's components form a strict hierarchy — child components can access all bindings from parent components, but parents can't access child bindings. This enforces proper scoping and lifetime management.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q28)**

### 29. Scenario: You need to inject a dependency that's constructed from a third-party SDK that initialises asynchronously. How do you handle async initialisation in Hilt?

🔴 Hard

> Hilt's DI graph is synchronous — all @Provides methods run on the main thread at injection time. Async-init SDKs need a wrapper pattern that bridges async init with synchronous DI.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q29)**

### 30. Scenario: You want to intercept every network request to add auth headers. How do you implement this cleanly using DI and OkHttp interceptors?

🔴 Hard

> Auth interceptors are a classic DI design problem — the interceptor needs the session token, the session needs the API, and the API needs OkHttp. Circular dependency risk and proper scoping are the challenges.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q30)**

### 31. Scenario: You need two separate Retrofit instances — one for your own API and one for a third-party API with different base URLs, headers, and timeouts. How do you set this up with Hilt?

🔴 Hard

> Multiple Retrofit instances require qualifiers to distinguish them. The pattern is qualifier annotations + separate @Provides methods — each qualifier represents a different API client configuration.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q31)**

### 32. Scenario: A colleague argues that @Inject on every class makes the codebase "tightly coupled to Hilt." Are they right, and how do you respond?

🔴 Hard

> This is a nuanced technical debate. @Inject is from javax.inject (JSR-330) — a standard annotation not tied to Hilt. But there are legitimate concerns about Hilt-specific annotations leaking into domain code.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q32)**

### 33. What is the Hilt testing pyramid? How do you test DI bindings at each level?

🔴 Hard

> DI testing has three levels matching the testing pyramid — each validates a different aspect of the dependency graph, from unit tests that don't use Hilt at all to integration tests that validate the full graph.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q33)**

### 34. Scenario: Your app's UI tests are very slow because Hilt's full graph is initialised for every test. How do you speed them up?

🔴 Hard

> Full Hilt graph initialisation in every UI test is expensive. Strategic use of test isolation, fake modules, and test scoping significantly reduces setup time.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q34)**

### 35. How does Hilt integrate with Jetpack Compose navigation? How do you scope a ViewModel to a NavGraph in multi-module?

🔴 Hard

> Hilt + Compose Navigation integration lets you scope ViewModels to a NavGraph — shared across multiple screens within a flow. This is the correct pattern for multi-step flows like onboarding or checkout.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q35)**

### 36. Scenario: You discover your app has a @Singleton dependency that holds a large in-memory cache growing unboundedly. How do you fix this with DI?

🔴 Hard

> Unbounded @Singleton caches are a classic memory problem. The DI solution involves scope narrowing, eviction policies, and WeakReference strategies — each with different trade-offs.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q36)**

### 37. Scenario: You need to provide different database configurations (in-memory for tests, WAL mode for production). How do you architect this with Hilt?

🔴 Hard

> Database configuration is a perfect use case for Hilt's source-set module pattern combined with build type configuration — test gets in-memory, release gets WAL mode with encryption.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q37)**

### 38. What is the difference between @Singleton in Hilt vs the Singleton design pattern? What are the pitfalls of each?

🔴 Hard

> Hilt's @Singleton and the classic Singleton pattern both ensure one instance, but differ fundamentally in how the instance is created, shared, and replaced. Hilt's approach is superior for testability and maintainability.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q38)**

### 39. Scenario: You're leading a DI design review. The team has these patterns — which do you approve, which do you reject, and why?

🔴 Hard

> A DI design review tests whether you can systematically identify anti-patterns, explain the consequences, and propose clean alternatives — the senior developer lens.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q39)**

### 40. How does Hilt handle injection into non-standard Android classes like BroadcastReceiver, ContentProvider, and Service?

🔴 Hard

> BroadcastReceiver, ContentProvider, and Service each have unique lifecycle quirks — particularly ContentProvider which initialises before the Hilt graph. Each requires a different approach.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q40)**

### 41. Scenario: Your team is adopting Kotlin Multiplatform. You have Hilt in the Android app. How do you share the business logic while keeping DI working?

🔴 Hard

> KMP and Hilt coexist when you keep Hilt strictly in the Android platform layer. Shared business logic uses constructor injection with standard interfaces — no Hilt annotations in commonMain.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q41)**

### 42. What are the Hilt updates and improvements in 2024-25? How do they affect your DI patterns?

🔴 Hard

> 2024-25 brought significant Hilt improvements — KSP stability, assisted injection improvements, Compose integration, and new testing APIs that simplify test setup considerably.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q42)**

### 43. Scenario: You're doing a DI health check on a legacy codebase. What red flags do you look for and what tools do you use?

🔴 Hard

> A DI health check is a systematic audit of common anti-patterns. Each red flag maps to a specific risk — memory leaks, testability gaps, or architectural violations.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q43)**

### 44. Scenario: You're architecting DI for a 10-module app from scratch. Walk through every decision you'd make.

🔴 Hard

> A complete DI architecture walkthrough demonstrates the full application of every concept — from dependency on KSP to scope decisions to testing strategy. This is the senior system-design answer.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q44)**

### 45. Scenario: Your Hilt build fails with "cannot be provided without an @Provides-annotated method." How do you systematically diagnose and fix this error?

🔴 Hard

> 'Cannot be provided without an @Provides-annotated method' means Hilt can't find a way to create the type you're requesting. The three root causes: missing @Inject constructor, missing @Provides method in a module, or the type is provided in a different component scope than where you're injecting it.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q45)**

### 46. How does Hilt handle injection in Jetpack Compose — what is the difference between hiltViewModel() and viewModel() and when should you use each?

🔴 Hard

> hiltViewModel() uses Hilt's ViewModelFactory, while viewModel() uses the default factory. Understanding when to use each affects both functionality and testability of Compose screens.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q46)**

### 47. What is the "Hilt + Compose" injection anti-pattern of passing ViewModel down the composable tree? How do you fix it?

🔴 Hard

> Passing a ViewModel as a parameter through multiple composable layers (ViewModel drilling) tightly couples composables to a specific ViewModel — breaking reusability and testability.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q47)**

### 48. Scenario: You have a background service that needs to post updates to the UI. How do you architect this cross-component communication cleanly using DI?

🔴 Hard

> Services and Activities/ViewModels live in different components — they can't directly inject each other. The clean solution is a @Singleton SharedFlow event bus or a @Singleton StateHolder that both sides inject.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q48)**

### 49. How do you inject environment-specific base URLs, API keys, and configuration into Hilt without hardcoding them?

🔴 Hard

> Build configuration injection is a DI design problem — hardcoded strings in @Provides methods are a maintenance issue. The clean pattern separates config declaration from config consumption using a typed AppConfig object.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q49)**

### 50. Scenario: Reflect on everything you know about DI. When is DI the wrong solution, and what architectural principle guides that decision?

🔴 Hard

> DI mastery includes knowing its limits. Over-engineering with DI adds complexity without proportional benefit — the guiding principle is that DI should simplify the system, not complicate it.

**[Full answer with code →](https://droidly.io/hilt-dagger-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q50)**

---

Practise these with spaced repetition and a plan for your level: **[droidly.io](https://droidly.io/?utm_source=github&utm_medium=repo&utm_campaign=aiq)**
