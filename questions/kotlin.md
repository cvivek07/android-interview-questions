# Kotlin Interview Questions (50)

Null safety, data/sealed classes, scope functions, generics, inline/reified, delegation.

Short answers below. **Each question links to the full answer with Kotlin code on [Droidly](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq)**, where you can also mark what you know and get a study plan.

⬅️ [All topics](../README.md)

## ⭐ Most asked

### 1. Explain Kotlin's null safety system. What is the difference between ?, !!, ?:, and let?

🟢 Easy

> Null safety is arguably Kotlin's single biggest improvement over Java. Tony Hoare — who invented null references — called it his "billion dollar mistake." In Android specifically, NullPointerException is the #1 cause of app crashes in production.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q1)**

### 2. What is the difference between val, var, const val, lateinit var, and by lazy?

🟡 Medium

> Kotlin provides five distinct ways to declare and initialize values, each suited for a different scenario.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q2)**

### 3. What is a data class in Kotlin? What does it auto-generate and what are its limitations?

🟡 Medium

> A data class is Kotlin's mechanism for modeling pure data — classes whose primary purpose is to hold values rather than define behavior. Think of it as Kotlin's answer to Java's notorious record verbosity: instead of writing 100 lines for a simple model class (constructor, getters, equals, hashCode, toString, copy), you write one line.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q3)**

### 4. What is the difference between sealed class, sealed interface, and enum class? When do you use each?

🟡 Medium

> Sealed classes, sealed interfaces, and enum classes all restrict what values or subtypes are possible — but they solve different problems. Enums are for a fixed set of identical-shaped constants (like compass directions or HTTP methods).

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q4)**

### 5. Explain scope functions: let, run, with, also, apply. How do you choose between them?

🟡 Medium

> Scope functions are one of Kotlin's most powerful but most confusing features for beginners.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q5)**

### 6. What are higher-order functions and lambdas in Kotlin? How do they work under the hood?

🟡 Medium

> Higher-order functions and lambdas are the foundation of Kotlin's functional programming capabilities — and understanding how they work under the hood is critical for writing performant Android code.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q6)**

### 7. What are extension functions and extension properties? How are they resolved?

🟡 Medium

> Extension functions are one of the most beloved Kotlin features — they let you add new functions to any class, including third-party libraries and Android framework classes you can't modify, without subclassing or the Decorator pattern.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q7)**

### 8. What are inline functions? Explain noinline and crossinline modifiers.

🔴 Hard

> Inline functions are Kotlin's compile-time optimization for higher-order functions — when you mark a function as inline, the compiler copies the function's bytecode AND the lambda parameters' bytecode directly to every call site.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q8)**

### 9. Explain Generics in Kotlin. What is variance — in, out, and star projection?

🔴 Hard

> Generics let you write type-safe code that works with any type — avoiding casts and providing compile-time type checking. Kotlin's generics work similarly to Java's, but with key improvements: declaration-site variance (out/in modifiers on the type parameter itself) instead of Java's use-site wildcards (? extends T, ? super T).

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q9)**

### 10. What is the reified keyword and why can it only be used with inline functions?

🔴 Hard

> Type erasure is a fundamental JVM limitation: at runtime, the JVM forgets the generic type parameter — List&lt;String&gt; and List&lt;Int&gt; are both just List at the bytecode level.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q10)**

### 11. Explain delegation in Kotlin — class delegation and property delegation. What are built-in delegates?

🔴 Hard

> Kotlin's by keyword enables two distinct patterns: class delegation and property delegation. Both express the same idea — composition over inheritance. Instead of subclassing to add behaviour, you delegate to another object.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q11)**

### 12. What is operator overloading in Kotlin? What operators can be overloaded?

🟡 Medium

> Operator overloading lets you define what standard operators (+, -, *, /, [], in, ==, &gt;, etc.) mean for your custom classes. Kotlin restricts overloading to a specific predefined set of operators — unlike C++ where you can overload almost anything.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q12)**

### 13. What are Kotlin collections? Explain the difference between List, MutableList, Sequence, and when to use each.

🟡 Medium

> Kotlin's collection system is built on a key design principle: separation of read-only and mutable interfaces. List is read-only (no add/remove); MutableList is mutable.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q13)**

### 14. What is the when expression in Kotlin? How is it different from Java's switch?

🟡 Medium

> The when expression is Kotlin's supercharged replacement for Java's switch statement, and the upgrade is dramatic. Java's switch is limited to integers, strings, and enums, requires break statements to avoid fall-through, and can only be a statement (not return a value).

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q14)**

### 15. What is destructuring in Kotlin? How do componentN functions work?

🟡 Medium

> Destructuring declarations let you unpack an object's components into individual named variables in a single statement, making code more expressive and reducing the need for intermediate variables. val (name, age) = person is cleaner than val name = person.name; val age = person.age.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q15)**

### 16. What are object, companion object, and anonymous objects in Kotlin?

🟡 Medium

> Kotlin's object keyword creates singletons, companion objects, and anonymous objects — three related but distinct constructs. A top-level object declaration is a thread-safe, lazily-initialized singleton backed by a static INSTANCE field on the JVM.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q16)**

### 17. How does Kotlin handle exceptions? What is the difference from Java?

🟡 Medium

> Kotlin has no checked exceptions — all exceptions are unchecked, unlike Java where methods must declare or catch checked exceptions. This design choice reduces boilerplate and avoids the "swallowed exception" anti-pattern common in Java code.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q17)**

### 19. What is typealias in Kotlin and when is it useful?

🟡 Medium

> A typealias introduces an alternative name for an existing type, making complex type signatures more readable without creating a new type. It is a purely compile-time construct — after compilation, the alias is replaced with the original type in bytecode, so there is zero runtime overhead.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q19)**

### 21. What are visibility modifiers in Kotlin? How is internal different from Java's package-private?

🟡 Medium

> Kotlin has four visibility modifiers: public (default), private, protected, and internal. The notable addition over Java is internal, which limits visibility to the same compilation module rather than Java's package-private (same package).

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q21)**

### 23. What is Kotlin's type system? Explain Any, Unit, Nothing, and how they differ from Java's Object, void, Void.

🟡 Medium

> Kotlin's type system includes three special types that define the top and bottom of the type hierarchy. Any is the root supertype of all non-nullable Kotlin types (equivalent to Java's Object).

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q23)**

### 24. What are the key advantages of Kotlin over Java for Android development?

🟡 Medium

> Kotlin offers comprehensive improvements over Java for Android development across safety, conciseness, expressiveness, and concurrency. Google made Kotlin the preferred language for Android in 2019 and all new Jetpack APIs are Kotlin-first, with many (Compose, Flow, coroutines) unusable or awkward in Java.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q24)**

### 26. What is the difference between == and === in Kotlin?

🟡 Medium

> Kotlin has two equality operators that serve very different purposes — a common interview trap for developers coming from Java.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q26)**

### 27. What are Kotlin's string templates and multiline strings?

🟡 Medium

> Kotlin provides powerful string features that eliminate messy concatenation and make working with structured text much cleaner than Java.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q27)**

### 28. What is the difference between List and Array in Kotlin?

🟡 Medium

> Both hold ordered elements but differ in mutability model, performance, and API richness. Knowing when to use each is a common interview question.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q28)**

### 29. How does Kotlin interoperate with Java? What are @JvmStatic, @JvmField, @JvmOverloads?

🟡 Medium

> Kotlin is 100% interoperable with Java but some Kotlin features need annotations to work cleanly from Java code. These annotations are commonly asked in Android interviews.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q29)**

### 30. What are named and default arguments in Kotlin? How do they reduce boilerplate?

🟡 Medium

> Named and default arguments dramatically reduce function overloads and make call sites self-documenting. They're one of the most practical Kotlin features for Android development.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q30)**

### 32. What are Kotlin's collection transformation functions? Explain map, filter, reduce, fold, groupBy, partition.

🟡 Medium

> Kotlin's collection API is vastly richer than Java's. Mastering these functions eliminates most imperative for-loop code and is heavily tested in interviews.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q32)**

### 34. What are Kotlin annotations? How do you create custom annotations?

🟡 Medium

> Annotations add metadata to code that can be read at compile time or runtime. They're heavily used in Android (Room, Retrofit, Hilt, Compose) — understanding them helps you write your own libraries.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q34)**

### 36. What are infix functions in Kotlin? Give real-world examples.

🟡 Medium

> Infix functions allow calling a function without a dot or parentheses, making code read more like natural language. They're used throughout Kotlin's standard library and test frameworks.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q36)**

### 37. What are varargs in Kotlin? How does the spread operator work?

🟡 Medium

> vararg allows passing a variable number of arguments of the same type. The spread operator (*) is used to pass an array where vararg is expected.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q37)**

### 39. What is lazy initialization vs eager initialization in Kotlin? When to use each?

🟡 Medium

> Kotlin provides multiple patterns for controlling when objects are created — choosing correctly impacts startup time, memory usage, and thread safety.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q39)**

### 41. What is the difference between map and flatMap in Kotlin collections?

🟡 Medium

> map transforms each element to one output. flatMap transforms each element to a collection, then flattens all collections into a single list — a very commonly tested distinction.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q41)**

### 42. How does Kotlin handle SAM (Single Abstract Method) conversions?

🟡 Medium

> SAM conversion allows using a lambda wherever a Java functional interface (an interface with one abstract method) is expected, eliminating anonymous class boilerplate when working with Java APIs.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q42)**

### 44. What are Kotlin's range and progression operators?

🟡 Medium

> Ranges and progressions are first-class in Kotlin, enabling clean iteration, validation, and conditional checks that would require verbose code in Java.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q44)**

### 46. What is the difference between Kotlin's List, Set, and Map? When do you use each?

🟡 Medium

> Kotlin's three main collection types each have distinct characteristics around ordering, uniqueness, and key-value access. Choosing the right one impacts correctness and performance.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q46)**

### 48. How do you write idiomatic Kotlin? What are the key code style principles?

🟡 Medium

> Idiomatic Kotlin means using language features as intended — not writing Java-style code in Kotlin. Interviewers often show code and ask "how would you improve this?"

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q48)**

## More questions

### 18. What are Kotlin Contracts? How do they help the compiler understand your code?

🔴 Hard

> Kotlin Contracts are a compiler-hint mechanism (currently experimental) that lets library authors communicate additional guarantees about function behavior to the Kotlin compiler.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q18)**

### 20. What are value classes (inline classes) in Kotlin? When should you use them?

🔴 Hard

> Value classes (formerly called inline classes) are single-property wrappers annotated with @JvmInline value class. The compiler inlines the underlying value at call sites where possible, avoiding object allocation — making them a zero-overhead abstraction.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q20)**

### 22. How do you build a DSL in Kotlin? What language features make this possible?

🔴 Hard

> Kotlin's combination of lambdas with receivers, extension functions, operator overloading, and infix functions makes it exceptionally well-suited for building internal DSLs — APIs that read like a domain-specific language while remaining valid Kotlin.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q22)**

### 25. What is Kotlin Serialization? How does it compare to Gson and Moshi?

🔴 Hard

> Kotlin Serialization (kotlinx.serialization) is a compile-time, annotation-driven serialization library that generates serializer code at compile time using a Kotlin compiler plugin, avoiding runtime reflection.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q25)**

### 31. What is Kotlin's type inference? How does it work with local variables and generics?

🔴 Hard

> Kotlin's compiler infers types at compile time, eliminating redundant type declarations while maintaining full static type safety. Understanding its limits is important for senior developers.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q31)**

### 33. What is Kotlin's Result type and how does it differ from exceptions?

🔴 Hard

> Result&lt;T&gt; is Kotlin's functional error handling type — it wraps either a success value or a failure exception, making error handling explicit and composable without try-catch everywhere.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q33)**

### 35. What is Kotlin Reflection? When would you use it in Android?

🔴 Hard

> Reflection allows inspecting and manipulating code structure at runtime. It's powerful but slow — use sparingly and prefer compile-time alternatives like KSP when possible.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q35)**

### 38. What is Kotlin's Nothing type? How is it used in practice?

🔴 Hard

> Nothing is Kotlin's bottom type — a subtype of every type. It represents computations that never complete normally (throws or loops forever), enabling the type system to remain sound.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q38)**

### 40. What are Kotlin's open and abstract classes? How does Kotlin differ from Java in class design?

🔴 Hard

> Kotlin classes are final by default — the opposite of Java. This is a deliberate design choice promoting composition over inheritance and preventing fragile base class problems.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q40)**

### 43. What are Kotlin coroutine basics — suspend functions and how does the compiler transform them?

🔴 Hard

> Understanding how suspend functions work under the hood — specifically the continuation-passing style transformation — is a key differentiator for senior Android developers.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q43)**

### 45. What is Kotlin's context receivers feature? How does it improve code organization?

🔴 Hard

> Context receivers (experimental in Kotlin 1.6+, stable in 2.0) allow functions to declare multiple receivers — solving the "multiple context" problem elegantly. This is one of Kotlin's most exciting 2024-25 features.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q45)**

### 47. What is Kotlin's object expressions vs object declarations vs companion objects — when to use each?

🔴 Hard

> Kotlin's object keyword has three distinct use cases — each solves a different problem. Interviewers test whether you know the difference and can choose the right one.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q47)**

### 49. What are Kotlin's new features in 2024-2025 — Kotlin 2.0 highlights?

🔴 Hard

> Kotlin 2.0 shipped in 2024 with major improvements to compilation speed, new language features, and the K2 compiler. Staying current with these is expected in senior 2025-26 interviews.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q49)**

### 50. How does Kotlin Multiplatform work? What can and cannot be shared across platforms?

🔴 Hard

> KMP (Kotlin Multiplatform) lets you share business logic across Android, iOS, web, and server while keeping platform-specific UI native. It became stable in Kotlin 2.0 and is rapidly being adopted in 2025.

**[Full answer with code →](https://droidly.io/kotlin-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q50)**

---

Practise these with spaced repetition and a plan for your level: **[droidly.io](https://droidly.io/?utm_source=github&utm_medium=repo&utm_campaign=aiq)**
