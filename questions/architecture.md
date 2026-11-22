# Architecture Interview Questions (50)

MVVM, MVI, clean architecture, modularisation, testing.

Short answers below. **Each question links to the full answer with Kotlin code on [Droidly](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq)**, where you can also mark what you know and get a study plan.

⬅️ [All topics](../README.md)

## ⭐ Most asked

### 1. What is MVVM? Explain each layer and its responsibility.

🟢 Easy

> MVVM (Model-View-ViewModel) separates UI from business logic. Each layer has a single, clear responsibility — making the code testable, maintainable, and rotation-safe.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q1)**

### 2. What is Clean Architecture? How does it differ from plain MVVM?

🟢 Easy

> Clean Architecture adds a Domain layer with use cases between ViewModel and Repository, enforcing strict dependency rules. Inner layers know nothing about outer layers — Domain is pure Kotlin.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q2)**

### 3. What is MVI architecture? How does it differ from MVVM?

🟡 Medium

> MVI (Model-View-Intent) enforces strict unidirectional data flow with a single immutable state object. Every user action is an Intent that goes through a reducer — fully predictable and consistent.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q3)**

### 4. What is the Repository pattern and why is it important?

🟢 Easy

> The Repository is the single source of truth for data. It abstracts all data sources (network, database, cache) from the ViewModel — the ViewModel never knows where data comes from.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q4)**

### 5. What is Dependency Injection? Explain Hilt and its key annotations.

🟡 Medium

> Dependency Injection provides objects their dependencies from the outside instead of letting them create their own. Hilt is Google's recommended DI framework for Android — compile-time safe, built on Dagger.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q5)**

### 6. What is multi-module architecture? What are the benefits and trade-offs?

🟡 Medium

> Multi-module architecture splits the app into independent Gradle modules -- each with its own source set, dependencies, and build config. Each module compiles independently so a change in :feature:home doesn't force :feature:profile to recompile.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q6)**

### 7. What are the SOLID principles? Give Android examples for each.

🟡 Medium

> SOLID principles guide object-oriented design toward maintainable, extensible, testable code. They're the foundation of all modern Android architecture patterns.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q7)**

### 8. How do you model UiState? What is the difference between a sealed class and a data class approach?

🟡 Medium

> UiState represents everything the screen needs to render. Two approaches — sealed class for mutually exclusive states, data class for combinable states. Each suits different screen complexity.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q8)**

### 11. What is the difference between @Binds and @Provides in Hilt?

🟡 Medium

> @Provides executes code to create a dependency. @Binds declares which implementation satisfies an interface — no code, just a mapping. @Binds is more efficient and preferred for interface bindings.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q11)**

### 13. What is the difference between MVVM and MVP? Why did MVVM win in Android?

🟡 Medium

> MVP uses a Presenter that holds a direct View reference — causing lifecycle issues and memory leaks. MVVM uses observable state — ViewModel has no View reference, surviving configuration changes cleanly.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q13)**

### 14. How do you test a ViewModel? What are best practices?

🟡 Medium

> ViewModel tests verify that the right state is emitted for given inputs — using fake repositories, TestDispatcher for coroutines, and Turbine for Flow assertions.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q14)**

### 17. What are common Android design patterns? Explain Observer, Factory, Builder, and Strategy.

🟡 Medium

> Design patterns are proven solutions to recurring problems. Connecting theory to real Android APIs — not just naming patterns — is what interviewers want to hear.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q17)**

### 20. What is Version Catalog (libs.versions.toml)? Why is it essential in multi-module projects?

🟡 Medium

> Version Catalog centralizes all dependency declarations in one file. In multi-module apps, it prevents version conflicts and makes upgrades a single-line change across all modules.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q20)**

### 21. What is the difference between Unit tests, Integration tests, and UI tests?

🟡 Medium

> The testing pyramid guides how many tests to write at each level. Clean Architecture makes each layer independently testable — unit tests at the bottom, UI tests at the top.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q21)**

### 28. What is the Result type in Kotlin? How does it improve error handling compared to throwing exceptions?

🟡 Medium

> Result makes error handling explicit in the return type — callers can't accidentally ignore failure. Exceptions can silently propagate; Result forces the caller to handle both cases.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q28)**

### 31. What is SavedStateHandle? How does it differ from ViewModel state survival?

🟡 Medium

> ViewModel survives configuration changes (rotation) but NOT process death. SavedStateHandle persists across process death using Bundle — the OS kills and restores it automatically.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q31)**

### 33. What is the difference between api() and implementation() in Gradle? Why does it matter for multi-module build speed?

🟡 Medium

> api() exposes a dependency transitively to consumers. implementation() keeps it private. Incorrect use of api() causes unnecessary recompilation cascades — the biggest hidden build-time killer in multi-module apps.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q33)**

### 35. What is the Now in Android (NiA) architecture? What patterns can you adopt from it?

🟡 Medium

> Now in Android (NiA) is Google's official open-source reference app. It demonstrates the architecture patterns Google recommends for production apps in 2024-25: multi-module with convention plugins, Hilt, Kotlin Serialization, Kotlin Flows, Compose, and offline-first with Room.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q35)**

### 38. How do you handle one-time UI events (navigation, snackbar, dialog) in MVVM and MVI?

🟡 Medium

> One-time events must not be stored in StateFlow (deduplication issue) or re-delivered after rotation. The standard patterns are Channel-as-Flow or MVI side effects.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q38)**

### 41. What is a use case (interactor) — when should you use them and when are they overkill?

🟡 Medium

> A use case encapsulates a single business operation. They're justified for complex logic, multi-repository orchestration, or shared logic across ViewModels. A simple one-liner is overkill.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q41)**

### 43. What is the difference between application module, library module, and dynamic feature module?

🟡 Medium

> An application module (:app) produces an installable APK or AAB -- it has an applicationId and is the entry point. A library module produces an AAR consumed by other modules -- it has a namespace but no applicationId.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q43)**

### 46. What is Qualifier in Hilt (@Named vs custom @Qualifier)? When do you need them?

🟡 Medium

> Qualifiers distinguish between multiple bindings of the same type. When Hilt sees two @Provides methods returning the same type, it can't decide which to inject — qualifiers tell it which to use where.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q46)**

## More questions

### 9. How do you handle navigation in a multi-module app?

🔴 Hard

> Feature modules can't depend on each other, so navigation must go through a shared contract. The NavGraphBuilder extension pattern (used in Google's Now in Android) is the modern recommended approach.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q9)**

### 10. Scenario: You're building a new e-commerce app for a 5-person team. What architecture would you choose and why?

🔴 Hard

> For a 5-person team building a new e-commerce app, start with a single-module clean architecture (Presentation → Domain → Data), then migrate to multi-module only when build times hurt or team size grows.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q10)**

### 12. What is the domain layer? What should and shouldn't go in it?

🔴 Hard

> The domain layer is the heart of Clean Architecture — pure Kotlin, no Android dependencies. It defines what the app does, independent of how data is stored or displayed.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q12)**

### 15. Scenario: A PR shows the ViewModel creating Retrofit directly and updating a TextView. What's wrong and how do you fix it?

🔴 Hard

> This PR has 5 distinct architectural violations — identifying all of them systematically is what senior code reviews look like.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q15)**

### 16. Scenario: Your app has a 3-minute build time. How do you reduce it with modularization?

🔴 Hard

> Build time improvement is a systematic process — measure first, take the free wins, then strategically modularize the highest-churn code.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q16)**

### 18. What is the data layer? How do you map between DTOs and domain entities?

🔴 Hard

> The data layer implements domain interfaces and handles all data concerns. DTOs match the network/database shape; domain entities represent business concepts — they must always be mapped separately.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q18)**

### 19. Scenario: Your app needs to support offline mode. How do you architect this?

🔴 Hard

> Offline-first architecture treats the local database as the single source of truth. The UI always reads from the DB — the network just refreshes it in the background.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q19)**

### 22. What is Koin vs Hilt for DI? When would you choose each?

🔴 Hard

> Hilt is compile-time, annotation-based — errors fail the build. Koin is a runtime DSL — errors crash at runtime. Both provide DI but differ fundamentally in safety and setup complexity.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q22)**

### 23. Scenario: Your ViewModel is 500+ lines. How do you refactor it?

🔴 Hard

> A 500-line ViewModel is a code smell — it has too many responsibilities. Delegate to use cases, state holders, and helper classes — each with a single, clear purpose.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q23)**

### 24. Scenario: Your team debates MVVM vs MVI for a complex order tracking screen with real-time WebSocket updates, multiple data sources, and a cancel button. Which do you choose?

🔴 Hard

> When a screen has many concurrent inputs (WebSocket, user actions, polling) and complex state transitions, MVI's single state object is the right choice — it prevents impossible UI combinations.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q24)**

### 25. Scenario: Explain how data flows from server to UI in your Clean Architecture app — as if onboarding a junior developer.

🔴 Hard

> A clear end-to-end data flow explanation demonstrates your architectural understanding. Being able to teach it to a junior shows mastery — not just memorization.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q25)**

### 26. What are Hilt scopes and how do they affect dependency lifetime? When does a @Singleton leak memory?

🔴 Hard

> Hilt scopes tie dependency lifetime to a component's lifecycle. Choosing the wrong scope causes either memory leaks (too long) or redundant object creation (too short).

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q26)**

### 27. Scenario: Your team needs to add analytics tracking to every user action across 20 screens — without touching every screen.

🔴 Hard

> Cross-cutting concerns like analytics should not be scattered across 20 screens. Use the navigation observer, Decorator pattern, or a base ViewModel — add tracking once, get it everywhere.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q27)**

### 29. Scenario: Two feature modules need to share user session data. How do you do this without creating a circular dependency?

🔴 Hard

> Feature modules can't reference each other — all shared data must flow through a :core module. Three patterns work: shared interface module, app-level ViewModel, or a typed event bus.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q29)**

### 30. What are convention plugins (build-logic)? How do they reduce Gradle duplication in multi-module projects?

🔴 Hard

> Convention plugins extract repeated Gradle configuration into reusable plugins — DRY principle for build scripts. Instead of copying 50 lines to 10 modules, you apply one plugin per module.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q30)**

### 32. Scenario: Implement feature flags to gradually roll out a new checkout flow. How do you architect this cleanly?

🔴 Hard

> Feature flags decouple deployment from release. Architecturally they belong at the navigation or use case boundary — never scattered across individual composables.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q32)**

### 34. Scenario: A payment feature must be built by a separate team over 3 months without blocking the main app. How do you architect this?

🔴 Hard

> Parallel team development requires contract-first design — define the API (interface) before implementation. The main team uses a stub; the payment team delivers the real implementation.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q34)**

### 36. Scenario: Your app is growing. When do you migrate from single-module to multi-module, and what's the migration strategy?

🔴 Hard

> Migrate from single-module to multi-module when one of three signals appears: incremental builds take over 2 minutes, two teams are stepping on each other's code, or you need a feature that only makes sense as a separate module (like an on-demand dynamic feature).

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q36)**

### 37. What is Dependency Inversion vs Dependency Injection — and how do they work together?

🔴 Hard

> DIP is a design principle (the D in SOLID). DI is a technique to implement it. DIP says WHAT to do (depend on abstractions). DI says HOW to do it (provide concrete implementations from outside).

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q37)**

### 39. Scenario: Your app has multiple flavors (free, pro, enterprise). How do you architect this with Hilt and multi-module?

🔴 Hard

> Product flavors combined with Hilt modules let you swap entire feature implementations per flavor — no if/else checks scattered across code, clean separation at the DI layer.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q39)**

### 40. Scenario: Your app suddenly has to support a new backend API while keeping the old one running for 3 months. How do you architect this transition?

🔴 Hard

> API migration with a compatibility period requires abstracting the API version behind the repository interface — ViewModels and use cases are completely unaffected by the backend change.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q40)**

### 42. Scenario: During a code review you find a junior dev using LiveData in the domain layer and Room @Entity in the domain model. What's wrong and what do you say?

🔴 Hard

> Both are domain layer violations — the domain must be pure Kotlin with zero Android or framework dependencies. Frame feedback constructively with the WHY, not just "that's wrong."

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q42)**

### 44. Scenario: Your team is debating whether to use MVI or MVVM for ALL screens. What's your recommendation?

🔴 Hard

> The right answer isn't one or the other — it's using each where it fits. MVVM for simple screens, MVI for complex state machines. Team consistency matters but pragmatism wins over dogmatism.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q44)**

### 45. Scenario: A new team member asks "why can't I just put everything in the Activity?" — how do you explain the architecture decisions made so far?

🔴 Hard

> The case against 'put everything in the ViewModel' is separation of concerns: ViewModels should hold UI state and delegate to use cases -- not contain business logic, network calls, or database queries directly.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q45)**

### 47. What is the difference between monorepo single-module and multi-module? When is each appropriate?

🔴 Hard

> In a monorepo single-module setup, all teams work in one codebase with one build output. In a true multi-module monorepo, each module is independently buildable and teams own specific modules.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q47)**

### 48. Scenario: Your app processes user data. A legal requirement arrives — all user data must be encrypted at rest and PII must be deletable. How do you architect this?

🔴 Hard

> Data privacy requirements should be handled in the data layer — the domain and presentation layers should be completely unaffected. This is Clean Architecture's value in practice.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q48)**

### 49. What are the key architectural improvements in Android 2024-25 — KSP, Compose Navigation 2.8, and Hilt updates?

🔴 Hard

> 2024-25 has brought significant tooling improvements that affect architecture — KSP replaces KAPT, type-safe Navigation, and Hilt improvements make the stack cleaner and faster.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q49)**

### 50. Scenario: You're leading a 6-month architecture review for a 3-year-old Android app with 200K LOC. What's your process?

🔴 Hard

> A 6-month architecture review for a legacy app is a migration, not a rewrite. The goal is to move to a maintainable, testable architecture incrementally -- without pausing feature delivery.

**[Full answer with code →](https://droidly.io/android-architecture-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q50)**

---

Practise these with spaced repetition and a plan for your level: **[droidly.io](https://droidly.io/?utm_source=github&utm_medium=repo&utm_campaign=aiq)**
