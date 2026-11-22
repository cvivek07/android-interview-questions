# Performance Interview Questions (50)

Memory leaks, ANRs, startup time, rendering, profiling.

Short answers below. **Each question links to the full answer with Kotlin code on [Droidly](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq)**, where you can also mark what you know and get a study plan.

⬅️ [All topics](../README.md)

## ⭐ Most asked

### 1. What is a memory leak in Android? What are the most common causes?

🟡 Medium

> A memory leak occurs when objects are kept in memory after they're no longer needed — the garbage collector can't reclaim them because something still holds a reference.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q1)**

### 2. How do you detect and fix memory leaks using LeakCanary and Android Studio Memory Profiler?

🟡 Medium

> LeakCanary detects leaks automatically by watching objects that should be garbage collected -- if they're still alive after 5 GC cycles, it captures a heap dump and traces the shortest reference path.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q2)**

### 3. What is overdraw? How do you detect and reduce it?

🟡 Medium

> Overdraw happens when a pixel is drawn more than once in the same frame — a background behind a background behind a view. Each overdraw wastes GPU time and can cause frame drops on low-end devices.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q3)**

### 4. What is ANR (Application Not Responding)? What causes it and how do you prevent it?

🟡 Medium

> ANR occurs when the main thread is blocked for too long — 5 seconds for user input events, 10 seconds for broadcast receivers, 20 seconds for service operations.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q4)**

### 6. What is the 16ms frame budget? How does Android render frames and what causes jank?

🟡 Medium

> Android must complete a measure → layout → draw → GPU render cycle within 16.67ms to hit 60fps. Any frame exceeding this budget is dropped and the user sees a stutter (jank).

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q6)**

### 8. How do you use Android Studio's CPU Profiler? What are the different recording modes?

🟡 Medium

> Android Studio's CPU Profiler has four recording modes, each answering a different question. Instrumented trace tells you exactly which methods were called. Sampled trace tells you how long each method took without much overhead.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q8)**

### 10. What is the difference between cold start, warm start, and hot start? How does each affect perceived performance?

🟡 Medium

> Cold start creates everything from scratch -- a new process, Application object, and Activity. Warm start skips process and Application creation. Hot start just resumes an existing Activity.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q10)**

### 12. What is StrictMode and how do you use it to catch performance violations?

🟡 Medium

> StrictMode monitors your app at runtime for performance violations — disk reads on the main thread, network calls, memory leaks, and more. It's the easiest way to catch performance anti-patterns before they reach users.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q12)**

### 14. What is the Android Performance class? How does it help you write adaptive performance code?

🟡 Medium

> Performance class (PerformanceClass) is an API introduced in Android 12 that categorises devices into tiers. You can query the tier and adapt your app's feature set — higher quality effects on flagship phones, simpler UI on low-end devices.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q14)**

### 16. How do you reduce layout inflation time? What makes some layouts slower to inflate than others?

🟡 Medium

> Layout inflation parses XML and instantiates View objects reflectively — it's one of the most expensive operations in the UI lifecycle. Reducing hierarchy depth, using ViewStub for conditional layouts, and async inflation all reduce its cost.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q16)**

### 20. How do you optimise battery usage in Android? What APIs help you reduce power consumption?

🟡 Medium

> Battery drain on mobile is primarily caused by radio wakeups (network and GPS), CPU wake locks, and frequent sensor polling. Writing battery-efficient code means batching network requests, using JobScheduler/WorkManager, and avoiding persistent wake locks.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q20)**

### 22. What is the Android Vitals dashboard in Play Console? Which metrics matter most?

🟡 Medium

> Android Vitals in Play Console tracks real user performance data -- crashes, ANRs, startup times, and frame rates -- across your entire user base. Google defines 'bad behaviour' thresholds; apps that exceed them get a lower search ranking and may show a warning label before install.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q22)**

### 26. What is the difference between memory pressure, low memory, and OOM? How does Android handle each?

🟡 Medium

> Android has a tiered memory management system. As RAM fills up, the OS progressively terminates background processes before eventually sending low-memory callbacks to foreground apps.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q26)**

### 28. What is the RenderThread? How does it affect UI performance?

🟡 Medium

> RenderThread was introduced in Android 5.0 to offload GPU command execution from the main thread. The main thread records drawing commands into a RenderNode display list; RenderThread replays them on the GPU.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q28)**

### 30. What is the difference between invalidate() and requestLayout()? When do you call each?

🟡 Medium

> These two View methods trigger different parts of the rendering pipeline. Calling the wrong one is either too expensive (requestLayout when invalidate would do) or incorrect (invalidate when the size changed).

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q30)**

### 32. How do you optimise Compose LazyColumn for large lists? What are the key performance patterns?

🟡 Medium

> Compose LazyColumn performance is driven by stable keys, avoiding unnecessary recomposition inside items, and keeping item composables lean. Getting these right means smooth 60fps scrolling on mid-range devices.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q32)**

### 36. What is hardware acceleration in Android Views? When does it help and when does it break things?

🟡 Medium

> Hardware acceleration routes drawing through the GPU via OpenGL ES / Vulkan instead of the CPU. It's enabled by default since Android 4.0 and dramatically improves rendering performance — but some Canvas operations are unsupported or produce different visual results.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q36)**

### 38. What is the Network Profiler? How do you use it to optimise API calls?

🟡 Medium

> The Network Profiler in Android Studio visualises all HTTP requests your app makes -- their timing, payload size, and response codes. It's invaluable for finding duplicate requests triggered by rotation, oversized API payloads, and serial requests that could run in parallel.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q38)**

### 40. What is App Size and how does it affect performance? What is the difference between download size, install size, and memory footprint?

🟡 Medium

> App size has three distinct meanings with different optimisation strategies. Download size is what users see on Play Store before installing -- reduce with AAB and R8.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q40)**

### 42. What is lazy loading and how do you implement it in Android lists and navigation?

🟡 Medium

> Lazy loading defers work until it's actually needed — don't load data you're not showing, don't initialise objects you might not use. In lists it means loading on demand; in navigation it means loading screens only when navigated to.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q42)**

### 46. What is a foreground service? When must you use one and what are the restrictions in Android 14+?

🟡 Medium

> A foreground service is a Service that shows a persistent notification — it tells the user (and the OS) that the app is doing important ongoing work. The OS gives it much higher priority than background services.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q46)**

### 48. How do you handle performance on low-end devices? What adaptations should your app make?

🟡 Medium

> Low-end devices (&lt; 2GB RAM, old CPUs) are a significant portion of Android users, especially in emerging markets. An app that's smooth on a Pixel may be unusable on a Redmi 9.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q48)**

## More questions

### 5. Scenario: Your app's cold startup takes 4 seconds. Walk through how you diagnose and fix it.

🔴 Hard

> Slow startup is almost always caused by too much work on the main thread during Application.onCreate() or Activity.onCreate(). The fix is a combination of deferring initialisation, lazy loading, and generating a Baseline Profile.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q5)**

### 7. Scenario: Your RecyclerView scrolls janky. How do you systematically diagnose and fix the performance?

🔴 Hard

> Janky RecyclerView scrolling usually comes from expensive onBindViewHolder, deep view hierarchies, or rebinding identical data. The fix combines profiling, ViewHolder optimisation, DiffUtil, and prefetching.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q7)**

### 9. Scenario: Your app keeps crashing with OutOfMemoryError in production. How do you diagnose and fix OOM errors in Android?

🔴 Hard

> OOM errors mean the app asked the OS for more heap than is available. Android caps each app's heap — typically 256–512MB on modern devices, as low as 64MB on older ones.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q9)**

### 11. Scenario: How do you implement a splash screen correctly in 2025 without the white flash problem?

🔴 Hard

> The white flash on app launch comes from the window background being rendered before your first Activity frame. The modern solution is the SplashScreen API (Android 12+) with the androidx.core SplashScreen compat library for older devices.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q11)**

### 13. Scenario: How do you measure and improve Jetpack Compose rendering performance?

🔴 Hard

> Compose performance issues come from unnecessary recomposition — composables recomposing when their inputs haven't changed. The tools are the Recomposition Counter in Layout Inspector, stability annotations, and derivedStateOf.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q13)**

### 15. Scenario: How do you use the Microbenchmark library to measure the performance of a specific function?

🔴 Hard

> Microbenchmark measures the performance of small units of code — JSON parsing, sorting algorithms, regex matching, custom view drawing. Unlike System.currentTimeMillis(), it handles JIT warmup, garbage collection, and clock accuracy automatically.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q15)**

### 17. Scenario: How do you profile and fix excessive garbage collection causing frame drops?

🔴 Hard

> Excessive object allocation triggers the garbage collector frequently, which pauses all threads and causes frame drops. The solution is to identify allocation hotspots in the profiler and eliminate allocations in performance-critical paths.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q17)**

### 18. What is App Startup time on Play Console? How do you monitor and improve it using production data?

🟡 Medium

> Play Console's Android Vitals tracks real user startup times across your entire user base — broken down by cold/warm/hot start, device tier, and country. This gives you production data that no local profiling can match.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q18)**

### 19. Scenario: How do you detect and fix thread contention causing jank or ANR?

🔴 Hard

> Thread contention happens when the main thread waits to acquire a lock held by a background thread — or when background threads compete for shared resources. It's invisible in normal profiling but shows up in System Trace as "lock wait" blocks.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q19)**

### 21. Scenario: How do you use Perfetto to diagnose a complex jank issue that doesn't show up in simpler tools?

🔴 Hard

> Perfetto is the most powerful Android performance tool -- it captures kernel-level events, CPU scheduling, all thread activity, and custom trace events in a unified timeline.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q21)**

### 23. Scenario: Your app's memory grows over time during a long session — a slow memory leak. How do you find it?

🔴 Hard

> A slow leak doesn't crash immediately — memory grows gradually until the system kills the app. Detecting it requires a heap dump comparison workflow — capture at start, use the app for 30 minutes, capture again, compare the two dumps.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q23)**

### 24. What is the Tracing library and how does it integrate with system profiling tools?

🟡 Medium

> The AndroidX Tracing library (androidx.tracing) provides a Kotlin-idiomatic API to add custom trace events to your code. These appear as labelled blocks in Perfetto, Android Studio's System Trace, and Macrobenchmark outputs — making your own code sections visible alongside framework events.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q24)**

### 25. Scenario: Conduct a performance code review. What 10 things do you check?

🔴 Hard

> A systematic performance code review catches the anti-patterns that accumulate into user-visible slowness — before they reach production. Each item maps to a real performance failure mode.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q25)**

### 27. Scenario: How do you implement efficient image loading and caching in a photo gallery with thousands of images?

🔴 Hard

> A photo gallery is the hardest image loading challenge on Android — thousands of high-resolution images, fast scroll, limited RAM. The solution combines Coil with a LazyVerticalGrid, thumbnail-first loading, and memory/disk cache tuning.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q27)**

### 29. Scenario: How do you implement a high-performance custom View that draws 60fps animations?

🔴 Hard

> High-performance custom Views require zero object allocation in onDraw, hardware acceleration, efficient invalidation, and using ValueAnimator for smooth frame-synced updates.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q29)**

### 31. Scenario: How do you use FrameMetrics API to monitor production frame rendering performance?

🔴 Hard

> FrameMetrics gives you per-frame timing data programmatically — no developer tools needed. You can collect it in production to detect jank on real user devices and report to your analytics system.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q31)**

### 33. Scenario: Your app's CPU usage stays high even when idle. How do you find and fix the runaway work?

🔴 Hard

> High idle CPU means something is running that shouldn't be — a polling loop, a stuck animation, a runaway coroutine, or a repeating alarm. The CPU Profiler in sampled mode shows what's running even when the app appears idle.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q33)**

### 34. What is the App History API and how do you use process death to improve startup UX?

🟡 Medium

> Android can kill your app's process at any time when it's in the background. Understanding process death — and designing for it with SavedStateHandle — turns what could be a broken UX into a seamless restoration experience.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q34)**

### 35. Scenario: How do you implement efficient background work that doesn't drain battery or get killed by the OS?

🔴 Hard

> Android increasingly restricts background work to protect battery life. WorkManager is the only guaranteed way to run background work — it handles Doze mode, App Standby, Background Execution Limits, and process death automatically.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q35)**

### 37. Scenario: How do you optimise a complex Compose screen that has expensive recomposition?

🔴 Hard

> Expensive recomposition is the most common Compose performance issue. The fix involves identifying which composables recompose unnecessarily (Layout Inspector) and applying targeted optimisations: state hoisting, derivedStateOf, and composable function scoping.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q37)**

### 39. Scenario: How do you profile and fix excessive work happening during app startup that the user can't see yet?

🔴 Hard

> Work during startup that the user can't see is waste — it delays the first frame without any visible benefit. Startup tracing with Perfetto reveals exactly what's running before the first frame and which of it is actually necessary.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q39)**

### 41. Scenario: How do you implement performance monitoring that automatically alerts you to regressions before users notice?

🔴 Hard

> Performance regressions are caught by combining automated benchmarks in CI (catches code-level regressions), Firebase Performance Monitoring (catches production regressions), and Android Vitals alerts (Play Console alerting).

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q41)**

### 43. Scenario: How do you optimise a screen that shows real-time data (e.g. live scores, stock prices) updating every second?

🔴 Hard

> Real-time UIs require careful optimisation — updating 50 list items every second on the main thread will cause jank. The solution is surgical UI updates via DiffUtil (Views) or stable keys with derivedStateOf (Compose), combined with smart update throttling.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q43)**

### 44. What is the Android GPU Inspector? How does it complement Android Studio's profiling tools?

🟡 Medium

> Android GPU Inspector (AGI) is a deep-GPU profiling tool -- it captures a single frame and breaks it down to individual draw calls, shader execution times, texture memory, and fill rate.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q44)**

### 45. Scenario: Design a comprehensive performance strategy for a new Android app from day one.

🔴 Hard

> A performance strategy built from day one is exponentially cheaper than retrofitting it.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q45)**

### 47. Scenario: How do you diagnose and fix a complex multi-thread synchronisation bug causing intermittent crashes?

🔴 Hard

> Race conditions and synchronisation bugs are the hardest category of Android bugs — they're intermittent, hard to reproduce, and don't leave obvious stack traces.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q47)**

### 49. Scenario: Your app uses a lot of Coroutines. How do you diagnose and fix coroutine performance issues?

🔴 Hard

> Coroutine performance issues are subtle — wrong dispatcher, too many coroutines, blocking calls inside suspend functions, and structured concurrency violations. The tools are coroutine debugging in Android Studio and Perfetto with coroutine tracing.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q49)**

### 50. Scenario: Write a complete performance improvement plan for an app that has 3-second startup, frequent jank, 2% crash rate, and growing memory.

🔴 Hard

> A performance recovery plan is prioritised by user impact: crashes affect more users than jank, jank affects more users than slow startup. Fix stability first, then perceived speed, then memory.

**[Full answer with code →](https://droidly.io/android-performance-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q50)**

---

Practise these with spaced repetition and a plan for your level: **[droidly.io](https://droidly.io/?utm_source=github&utm_medium=repo&utm_campaign=aiq)**
