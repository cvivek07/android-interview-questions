# Jetpack Compose Interview Questions (50)

Recomposition, state, side effects, performance, navigation.

Short answers below. **Each question links to the full answer with Kotlin code on [Droidly](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq)**, where you can also mark what you know and get a study plan.

⬅️ [All topics](../README.md)

## ⭐ Most asked

### 1. What is Jetpack Compose? How is it different from the View system?

🟡 Medium

> Jetpack Compose is Android's modern declarative UI toolkit. Instead of mutating views, you describe what the UI should look like for a given state — Compose figures out the updates.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q1)**

### 2. What is recomposition? How does Compose decide what to recompose and how do you minimise it?

🔴 Hard

> Recomposition is Compose re-executing a composable function when its inputs change. Understanding and minimising unnecessary recompositions is critical for performance.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q2)**

### 3. What is the difference between remember and rememberSaveable?

🟡 Medium

> Both persist state across recompositions, but rememberSaveable also survives configuration changes (rotation) and process death by saving to a Bundle.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q3)**

### 4. Explain side effects in Compose — LaunchedEffect, SideEffect, DisposableEffect, produceState.

🔴 Hard

> Side effects are operations that escape the scope of a composable — network calls, analytics, subscriptions. Compose provides specific APIs for each use case to keep side effects safe and lifecycle-aware.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q4)**

### 5. What is State Hoisting in Compose? Why is it important?

🔴 Hard

> State hoisting is the pattern of moving state up to the caller, making composables stateless and reusable. It's Compose's answer to the separation of concerns problem.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q5)**

### 6. What are the phases of Compose? Explain Composition, Layout, and Drawing.

🔴 Hard

> Compose renders UI in three phases each frame. Understanding this model helps optimise performance — some operations can skip earlier phases entirely.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q6)**

### 7. What is the Modifier system in Compose? What is the correct order of modifiers?

🟡 Medium

> Modifiers decorate composables with layout behaviour, drawing, and interaction. Order matters — each modifier wraps the next, like decorators applied inside-out.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q7)**

### 8. What are the main layout composables in Compose? Column, Row, Box, LazyColumn.

🟡 Medium

> Compose provides a set of layout primitives that replace LinearLayout, FrameLayout, and RecyclerView. Knowing when to use each is fundamental.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q8)**

### 11. What is the difference between stateful and stateless composables?

🟡 Medium

> Stateful composables own state internally. Stateless composables receive state as parameters. Good architecture maximises stateless composables — they're easier to test, preview, and reuse.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q11)**

### 13. How do you implement animations in Jetpack Compose?

🟡 Medium

> Compose has a rich animation API ranging from simple value animations to complex choreographed sequences. Choose the right API for the complexity of the animation.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q13)**

### 14. How do you test Compose UI? Explain composeTestRule and semantics.

🟡 Medium

> Compose has its own UI testing framework that works without a real device or emulator. Tests interact with the UI through semantics — accessibility labels that describe what each element does.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q14)**

### 16. What is derivedStateOf and when should you use it?

🟡 Medium

> derivedStateOf creates a State whose value is derived from other state objects. It prevents excessive recomposition when the source state changes often but the derived value changes rarely.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q16)**

### 18. What is Material3 in Compose? How do you implement theming?

🟡 Medium

> Material Design 3 (Material You) is Google's latest design system — it includes dynamic colour, updated components, and improved typography. All new Compose apps should use Material3.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q18)**

### 21. What is Scaffold in Compose? How do you use it with TopAppBar, FAB, and SnackbarHost?

🟡 Medium

> Scaffold implements the basic Material Design layout structure — it handles the coordination of TopAppBar, BottomAppBar, FAB, SnackbarHost, and content padding automatically.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q21)**

### 23. How do you handle lists efficiently in Compose — LazyColumn keys, item types, and sticky headers?

🟡 Medium

> LazyColumn is Compose's RecyclerView equivalent but requires specific optimisations to avoid common performance pitfalls — especially around keys and item types.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q23)**

### 31. What is rememberCoroutineScope and when do you use it vs LaunchedEffect?

🟡 Medium

> Both provide coroutine scopes in Compose — LaunchedEffect for automatic state-driven effects, rememberCoroutineScope for user-triggered actions like button clicks.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q31)**

### 32. What is the Slot API in Compose? How does it enable flexible composable design?

🟡 Medium

> The slot API uses @Composable lambdas as parameters — letting callers inject any UI into predefined slots. It's how Material3 achieves maximum flexibility with minimal parameters.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q32)**

### 33. How do you implement a tab layout with bottom navigation in Compose?

🟡 Medium

> Bottom navigation with multiple tabs is a fundamental app pattern. The key is saving and restoring tab state so scroll position is preserved when switching tabs.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q33)**

### 35. What are Compose gestures? Explain clickable, pointerInput, and draggable.

🟡 Medium

> Compose provides a gesture API ranging from simple clicks to complex multi-touch. Each level trades simplicity for control.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q35)**

### 38. What is snapshotFlow and when do you use it?

🟡 Medium

> snapshotFlow converts Compose State into a Flow — enabling Flow operators like debounce, filter, distinctUntilChanged on state changes.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q38)**

### 40. How do you implement Paging 3 in Compose?

🟡 Medium

> Paging 3 integrates with Compose through LazyPagingItems — it handles page loading, error states, and retry automatically when combined with LazyColumn.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q40)**

### 45. What are Compose text components? Explain Text, TextField, BasicTextField, and OutlinedTextField.

🟡 Medium

> Compose provides text components at different abstraction levels — from styled Material components to raw BasicTextField for fully custom inputs.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q45)**

### 47. How do you handle accessibility in Jetpack Compose?

🟡 Medium

> Compose has built-in accessibility through the semantics API. Good accessibility makes apps usable by all users and is increasingly required by enterprise clients.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q47)**

### 49. What is Scaffold and how do you use it correctly with innerPadding?

🟡 Medium

> Scaffold coordinates Material layout slots and provides innerPadding so content doesn't render under AppBars or system bars. Forgetting innerPadding is the most common Scaffold mistake.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q49)**

## More questions

### 9. How do you collect StateFlow and handle UI state in Compose?

🔴 Hard

> Collecting ViewModel state safely in Compose requires lifecycle-aware collection to stop updates when the app is backgrounded. The recommended approach has evolved significantly.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q9)**

### 10. How do you implement navigation in Compose? Explain NavHost and type-safe navigation.

🔴 Hard

> Navigation in Compose uses Navigation Compose — a declarative NavHost with routes. Navigation 2.8+ introduced type-safe routes using @Serializable, eliminating string-based route errors.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q10)**

### 12. How do you build custom layouts in Compose using Layout and SubcomposeLayout?

🔴 Hard

> Custom layouts let you control exactly how children are measured and placed. SubcomposeLayout allows measuring children based on other children's sizes — needed for dynamic layouts.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q12)**

### 15. What is CompositionLocal in Compose? When and how do you use it?

🔴 Hard

> CompositionLocal provides implicit data passing down the composition tree without explicit parameter passing — like dependency injection within the UI tree.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q15)**

### 17. How does Compose interop with the View system? When would you use it?

🔴 Hard

> Compose and the View system can coexist — you can embed Compose inside Views and Views inside Compose. This is essential for incremental migration and third-party library integration.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q17)**

### 19. How do you handle one-time UI events (navigation, snackbar, toast) in Compose?

🔴 Hard

> One-time events should never be part of regular UiState — they can't be deduplicated like state. Using the wrong approach causes events to fire multiple times or get lost on rotation.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q19)**

### 20. What are Compose stability and the Compose compiler metrics? How do you diagnose recomposition issues?

🔴 Hard

> Compose's smart recomposition relies on stability — stable types can be skipped if parameters haven't changed. The Compose compiler reports which composables are skippable and why.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q20)**

### 22. What is the Compose ViewModel integration? How do you use hiltViewModel and viewModel?

🔴 Hard

> ViewModels in Compose are scoped to navigation destinations, not Activities. The lifecycle and scoping rules are different from the View system — important to understand to avoid memory leaks.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q22)**

### 24. What is the Compose runtime and how does it differ from the Compose UI toolkit?

🔴 Hard

> Compose is split into layers — the runtime (slot table, recomposition engine) is separate from the UI toolkit. This separation enables Compose to be used outside of Android UI — for example in Compose for Desktop and Compose Multiplatform.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q24)**

### 25. What are Compose previews? How do you use @Preview effectively?

🔴 Hard

> @Preview renders composables in Android Studio without running the app. Used effectively, previews become a development superpower — enabling rapid UI iteration with instant visual feedback.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q25)**

### 26. Scenario: Your LazyColumn is janky with 10,000 items. How do you diagnose and fix it?

🔴 Hard

> Profile first, fix second. The answer involves Layout Inspector, stability annotations, missing keys, and heavy work inside composables.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q26)**

### 27. Scenario: Build a search screen with debounce, loading state, and error handling in Compose.

🔴 Hard

> This tests the full ViewModel + Flow + Compose UI pipeline — the most common architecture pattern in production Android apps.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q27)**

### 28. Scenario: Bottom sheet with "Add to Cart" button that shows a snackbar confirmation. Implement correctly.

🔴 Hard

> Tests ModalBottomSheet, SnackbarHost, one-time events via Channel, and correct Scaffold usage.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q28)**

### 29. Scenario: Your team is migrating from XML to Compose. How do you plan the migration?

🔴 Hard

> Incremental migration is the only safe approach — never big-bang rewrite. Compose and Views coexist seamlessly through interop APIs.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q29)**

### 30. Scenario: App crashes on screen rotation in Compose. How do you debug and fix it?

🔴 Hard

> Rotation crashes in Compose are almost always state management issues — remember vs rememberSaveable, ViewModel scoping, or unstable LaunchedEffect keys.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q30)**

### 34. What makes a @Composable function different from a regular Kotlin function?

🔴 Hard

> @Composable is a compiler plugin annotation that fundamentally transforms the function — adding hidden parameters and making it part of the Compose slot table and recomposition system.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q34)**

### 36. Scenario: Implement a collapsing toolbar that shrinks as user scrolls down.

🔴 Hard

> Collapsing toolbars connect scroll state to layout transformations. Material3 provides a built-in solution via LargeTopAppBar — always prefer this over custom implementations.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q36)**

### 37. What is SharedTransitionLayout? How do you implement shared element transitions?

🔴 Hard

> Shared element transitions animate UI elements smoothly between screens. Native Compose support arrived in Compose 1.7 (2024) via SharedTransitionLayout.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q37)**

### 39. Scenario: Compose app startup is slow. How do you optimise Time-To-First-Frame?

🔴 Hard

> Compose startup involves both app-level init and first composition. Both need optimisation. Baseline Profiles give the biggest single impact.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q39)**

### 41. Scenario: Build a PIN entry screen with 6 boxes, auto-advance focus, and backspace support.

🔴 Hard

> Custom OTP/PIN inputs use a hidden BasicTextField for keyboard handling and custom visual boxes for display — the standard pattern for all PIN/OTP screens.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q41)**

### 42. What is the Compose lifecycle? How does it differ from Android Activity lifecycle?

🔴 Hard

> Composables have their own lifecycle independent of Activity. Understanding both and how they interact prevents resource leaks and incorrect behavior.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q42)**

### 43. Scenario: A composable is recomposing thousands of times per minute. Walk through debugging this.

🔴 Hard

> Excessive recomposition needs a systematic debugging approach. Profile first, then apply targeted fixes.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q43)**

### 44. Scenario: Build a multi-step onboarding flow with shared state and progress indicator.

🔴 Hard

> Multi-step flows need shared state across screens, back navigation, and validation per step. A NavGraph-scoped ViewModel is the cleanest solution.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q44)**

### 46. What is Compose Multiplatform? How does it differ from Jetpack Compose?

🔴 Hard

> Compose Multiplatform (by JetBrains) extends Jetpack Compose to iOS, Desktop, and Web. iOS support became stable in 2024 — enabling shared UI across platforms.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q46)**

### 48. Scenario: Build a chat screen — messages from bottom, real-time new messages, auto-scroll to latest.

🔴 Hard

> Chat UIs need reversed layout, auto-scroll to new messages, and a scroll-to-bottom FAB when reading history. reverseLayout = true is the key API.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q48)**

### 50. Scenario: PM asks you to compare Compose vs XML for a new project starting today. What do you recommend?

🔴 Hard

> Compose and XML Views are complementary in 2024-25 -- ComposeView and AndroidView interop means you can mix them. For a new project, Compose is the clear recommendation: less code, better state management, easier testing, and where Google is investing all future UI work.

**[Full answer with code →](https://droidly.io/jetpack-compose-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q50)**

---

Practise these with spaced repetition and a plan for your level: **[droidly.io](https://droidly.io/?utm_source=github&utm_medium=repo&utm_campaign=aiq)**
