# Gradle & Build Interview Questions (50)

Build variants, R8, version catalogs, build speed.

Short answers below. **Each question links to the full answer with Kotlin code on [Droidly](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq)**, where you can also mark what you know and get a study plan.

⬅️ [All topics](../README.md)

## ⭐ Most asked

### 1. What is Gradle? How does the Android build system work at a high level?

🟢 Easy

> Gradle is the build automation tool for Android. It takes your source code, resources, and dependencies, then compiles, optimises, and packages them into an APK or AAB.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q1)**

### 2. What is the difference between APK and AAB? Why does Google prefer AAB?

🟢 Easy

> APK (Android Package) is the traditional installable file -- it contains code, resources, and native libraries for every device configuration. AAB (Android App Bundle) is a publishing format: you upload it to Play Store, and Play generates device-specific APKs from it.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q2)**

### 3. What is R8? How does it differ from ProGuard? What does it do to your app?

🟡 Medium

> R8 is the modern replacement for ProGuard — it does code shrinking, obfuscation, and optimisation in a single pass. It's significantly faster than ProGuard and produces smaller output.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q3)**

### 4. How do you write ProGuard/R8 keep rules? When does R8 break your app?

🟡 Medium

> R8 removes code it thinks is unused — but it can't see code accessed via reflection, serialisation, or native JNI. Keep rules tell R8 "don't touch this" for classes that must survive shrinking.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q4)**

### 5. What are build types in Android? How do debug and release differ?

🟡 Medium

> Build types define how your app is compiled and packaged for different purposes. Debug is for development — fast builds, debugging enabled, test signing. Release is for distribution — optimised, obfuscated, production-signed.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q5)**

### 6. What are product flavors in Android? How do they combine with build types?

🟡 Medium

> Product flavors let you create multiple versions of your app from the same codebase — free vs premium, different regions, white-label variants. They combine with build types to create build variants (e.g. freeDebug, premiumRelease).

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q6)**

### 8. What is KAPT vs KSP? Why is KSP faster and when should you migrate?

🟡 Medium

> KAPT (Kotlin Annotation Processing Tool) compiles Kotlin to Java stubs before running annotation processors — a slow extra step. KSP (Kotlin Symbol Processing) processes Kotlin source directly — up to 2x faster and supports incremental processing.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q8)**

### 9. What is the Version Catalog (libs.versions.toml)? Why is it better than declaring dependencies inline?

🟡 Medium

> Version Catalog centralises all dependency versions in a single TOML file — no more hunting across 10 build.gradle files when upgrading a library. It also enables type-safe accessors (libs.retrofit instead of string literals) and IDE autocomplete.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q9)**

### 11. What is the difference between implementation, api, compileOnly, and runtimeOnly in Gradle?

🟡 Medium

> These configurations control how dependencies are exposed to other modules and when they're included in the classpath. Choosing wrong causes compilation errors, build slowdowns, or bloated APKs.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q11)**

### 13. What are compileSdk, minSdk, and targetSdk? What happens if you set them wrong?

🟡 Medium

> These three SDK values control what APIs you can use, what Android versions can install your app, and how the OS handles your app's behaviour. Getting them wrong causes either app crashes or Play Store policy violations.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q13)**

### 15. What is versionCode vs versionName? How do you automate version management?

🟡 Medium

> versionCode is an integer the Play Store uses to determine update ordering — must increase with every release. versionName is the human-readable string shown to users.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q15)**

### 17. What is BuildConfig? What can you store in it and how do you access it?

🟢 Easy

> BuildConfig is a generated Java class that Gradle creates at build time. It contains compile-time constants that differ per build type or flavor — like API URLs, feature flags, and debug modes.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q17)**

### 19. What is Lint in Android? How do you configure custom Lint rules?

🟡 Medium

> Android Lint is a static analysis tool that checks your code and resources for potential bugs, performance issues, security vulnerabilities, and style violations — without running the app.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q19)**

### 21. What is the Gradle configuration cache? What breaks it and how do you fix it?

🟡 Medium

> The configuration cache saves the result of the build configuration phase — it skips re-evaluating all build.gradle scripts on subsequent builds. This saves 20-60 seconds per build.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q21)**

### 22. What is the difference between a library module and an application module in Android?

🟢 Easy

> An application module produces an APK/AAB — it can be installed on a device. A library module produces an AAR (Android Archive) — it provides code and resources to other modules but can't be installed directly.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q22)**

### 26. What is Gradle's task graph? How does task dependency work?

🟡 Medium

> Gradle models every build step as a task. Tasks declare inputs and outputs — Gradle builds a directed acyclic graph (DAG) of task dependencies and executes only what's needed.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q26)**

### 27. How does dependency resolution work in Gradle? What is dependency conflict resolution?

🟡 Medium

> Gradle resolves dependencies transitively — if Retrofit depends on OkHttp 4.11, your project gets OkHttp 4.11 even if you didn't declare it. When two paths pull in different versions of the same library, Gradle must pick one — by default it picks the highest version.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q27)**

### 31. What is the 64K method limit in Android? How do you enable and configure multidex?

🟡 Medium

> Android's Dalvik Executable (DEX) format uses 16-bit method references — limiting each DEX file to 65,536 methods. Large apps with many libraries exceed this. Multidex splits code across multiple DEX files.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q31)**

### 32. How do you use resource qualifiers and density-specific assets? How does this affect APK size?

🟡 Medium

> Android selects the best matching resource at runtime based on device qualifiers — screen density, locale, API level, orientation. Providing too many density variants bloats the APK.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q32)**

### 36. What is the difference between debuggable and non-debuggable builds? What are the security implications?

🟡 Medium

> isDebuggable=true enables debugger attachment, allows log reading, and disables security protections. Shipping a debuggable APK to production is a serious security vulnerability — attackers can attach a debugger and inspect the app's memory and network traffic.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q36)**

### 38. How do you use source sets in Android? How do flavors and build types contribute their own source sets?

🟡 Medium

> Source sets define where Gradle looks for code, resources, and manifests for each build variant. Every build type and flavor gets its own source set directory — you can override or extend code per variant without if/else BuildConfig checks.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q38)**

### 40. What are the most useful Gradle command-line options for Android development?

🟢 Easy

> Knowing the right Gradle flags saves significant time during development and debugging. These commands go beyond the basics and expose what's really happening in your build.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q40)**

### 43. How do you manage secrets and API keys in Android builds? What are the safe and unsafe approaches?

🟡 Medium

> API keys embedded in APKs are extractable by anyone with a decompiler. The only truly safe option is to never put secrets in the APK. For keys that must be on-device, use Android Keystore and server-side validation to limit exposure.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q43)**

### 46. What is the Android namespace in build.gradle.kts? How does it replace the package attribute in AndroidManifest?

🟡 Medium

> The namespace in build.gradle.kts defines the package for generated code (BuildConfig, R class). It replaces the package attribute previously set in AndroidManifest.xml.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q46)**

## More questions

### 7. Scenario: Your APK is 80MB and the team wants it under 30MB. Walk through your reduction strategy.

🔴 Hard

> APK size reduction is a systematic process — profile first with Android Size Analyzer, then attack the biggest contributors: native libraries (ABI splits), images (WebP), unused code (R8), and unused resources (isShrinkResources).

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q7)**

### 10. Scenario: Your CI build takes 20 minutes. How do you systematically reduce Gradle build time?

🔴 Hard

> Slow builds kill developer productivity. The fix is a combination of Gradle caching, configuration cache, parallel execution, and KSP — each targeting a different bottleneck in the build pipeline.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q10)**

### 12. What are Convention Plugins (build-logic)? How do they eliminate build script duplication in multi-module projects?

🟡 Medium

> Convention Plugins are reusable Gradle plugins written in your project that standardise build configuration across modules. Instead of copy-pasting the same android {} block into 20 modules, you apply one plugin that contains all the shared config.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q12)**

### 14. Scenario: Your release app crashes but debug works fine. How do you diagnose R8-related crashes?

🔴 Hard

> Debug-works-release-crashes is almost always an R8 issue — something got stripped or renamed. The diagnosis is systematic: check the stack trace, use the mapping file, add keep rules, and narrow down the culprit.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q14)**

### 16. Scenario: Set up a complete signing configuration for release builds without hardcoding credentials in build files.

🔴 Hard

> Signing credentials (keystore password, key password) must never be committed to source control. The correct approach uses environment variables on CI and a local properties file for developers — both kept out of git.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q16)**

### 18. What are Dynamic Feature Modules? When should you use them?

🟡 Medium

> Dynamic Feature Modules let you deliver parts of your app on-demand — downloaded only when the user needs that feature. This reduces install size and startup time, but adds delivery complexity.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q18)**

### 20. Scenario: Set up a multi-module Android project with shared build logic, Version Catalog, and a CI pipeline that builds and runs tests.

🔴 Hard

> A well-structured multi-module project uses a composite build for convention plugins, a Version Catalog for all dependencies, and a CI pipeline that runs tests on every PR and deploys on tag push.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q20)**

### 23. Scenario: How do you measure and track APK/AAB size changes in CI to prevent accidental size regressions?

🔴 Hard

> Size regressions sneak in when someone adds a large library without realising its impact. Tracking AAB size in CI and failing builds that exceed a threshold prevents this — catching size increases in the PR that caused them.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q23)**

### 24. What is R8 Full Mode? How does it differ from standard R8?

🟡 Medium

> R8 Full Mode enables more aggressive optimisations than standard R8 -- class merging, interface removal, constructor argument propagation, and enum unboxing. The result is 5-8% smaller DEX output.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q24)**

### 25. Scenario: Conduct a build system code review. What 8 things do you check?

🔴 Hard

> A build system review catches configuration mistakes that silently slow down builds, bloat APK size, or create security vulnerabilities — before they accumulate into intractable debt.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q25)**

### 28. Scenario: How do you set up Gradle to publish an Android library to Maven Central or GitHub Packages?

🔴 Hard

> Publishing a library requires configuring the maven-publish plugin, generating sources and docs JARs, and signing artifacts. The process differs slightly between Maven Central (strict, requires signing) and GitHub Packages (simpler, requires GitHub auth).

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q28)**

### 29. What is the Gradle version catalog's bundle feature? How do you use it?

🟡 Medium

> Bundles group related libraries that are always added together. Instead of declaring Room runtime, ktx, and compiler separately in every module, you declare a bundle once and reference one name.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q29)**

### 30. Scenario: How do you configure a multi-flavour CI pipeline that builds, tests, and uploads different variants to different channels?

🔴 Hard

> Multi-flavour CI means each build variant (freeIndiaRelease, premiumGlobalRelease) is built and tested independently. GitHub Actions matrix builds parallelise this -- all variants build simultaneously so total CI time equals one variant's time, not the sum of all variants.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q30)**

### 33. Scenario: How do you implement baseline profiles to speed up app startup and reduce jank?

🔴 Hard

> Baseline Profiles tell the Android Runtime (ART) which classes and methods to pre-compile ahead of time. Without them, ART JIT-compiles code on first run — causing startup jank.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q33)**

### 34. What is the Android Gradle Plugin (AGP)? How do you upgrade it safely?

🟡 Medium

> AGP is the Gradle plugin that knows how to build Android projects — it defines all the android {} DSL blocks, build types, flavors, and tasks. AGP versions are tightly coupled to Gradle versions, Kotlin versions, and Android Studio versions.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q34)**

### 35. Scenario: How do you set up a remote Gradle build cache to share build outputs across the whole team?

🔴 Hard

> A remote build cache shares task outputs across all developer machines and CI. When Alice builds a module and pushes the output, Bob's machine downloads it instead of rebuilding — saving minutes per build across the whole team.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q35)**

### 37. Scenario: How do you configure obfuscation to protect your app against reverse engineering while keeping it functional?

🔴 Hard

> R8 obfuscation renames classes, methods, and fields to single-letter names — making reverse-engineered code extremely hard to understand. The challenge is keeping obfuscation aggressive enough to protect IP while preserving functionality via careful keep rules.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q37)**

### 39. Scenario: Your build script has grown to 200 lines of complex logic. How do you refactor it to be maintainable?

🔴 Hard

> Large build scripts are a maintenance problem — hard to read, test, and reuse. The refactoring path is: extract reusable config into convention plugins, extract custom task logic into buildSrc or build-logic, and extract utility functions into Gradle extensions.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q39)**

### 41. What is Gradle's Kotlin DSL vs Groovy DSL? Why is Kotlin DSL now preferred?

🟡 Medium

> Gradle supports both Groovy (.gradle files) and Kotlin (.gradle.kts files) for build scripts. Kotlin DSL is now the official recommendation — it offers IDE autocomplete, type safety, refactoring support, and compile-time error detection that Groovy lacks.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q41)**

### 42. Scenario: How do you use the Macrobenchmark library to measure and improve app performance?

🔴 Hard

> Macrobenchmark measures real user-visible performance — startup time, frame rendering, scroll smoothness — on a real device with release-like code. It's the only way to get accurate performance data because it uses the compiled, optimised app.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q42)**

### 44. Scenario: Your app uses a native (.so) library. How do you integrate, package, and debug native code in the Android build?

🔴 Hard

> Native libraries (.so files) require ABI-specific compilation, JNI bridging, and special build configuration. CMake and the Android NDK integrate with Gradle to compile C/C++ as part of your build.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q44)**

### 45. Scenario: You are the build engineer onboarding a new Android project. What does your ideal Gradle setup look like?

🔴 Hard

> The ideal build setup is fast, secure, maintainable, and CI-ready from day one. It takes 2-3 days to configure properly and saves hundreds of hours over the project's lifetime.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q45)**

### 47. Scenario: How do you detect and fix memory leaks at the build level using LeakCanary in development builds only?

🔴 Hard

> LeakCanary automatically detects memory leaks during development and crashes with a clear heap dump analysis. The key is confining it strictly to debug builds — it has significant overhead and should never ship in production.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q47)**

### 48. What is nonTransitiveRClass and how does it speed up multi-module builds?

🟡 Medium

> By default, a module's R class contains all resources from that module and all its transitive dependencies. With nonTransitiveRClass=true, each module's R class contains only its own resources.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q48)**

### 49. Scenario: A third-party library you depend on has a known vulnerability. How do you handle it before the library author fixes it?

🔴 Hard

> Vulnerable dependencies need immediate action — you can't wait for an upstream fix that may take weeks. The tools are: force a safe version of the transitive dependency, patch the vulnerable class with a custom overlay, or replace the library entirely.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q49)**

### 50. Scenario: You are joining a team with a slow, messy build system. Write your action plan to fix it over 3 months.

🔴 Hard

> A messy build system needs a prioritised plan, not a big-bang rewrite. Start with zero-risk wins in gradle.properties, then migrate to Kotlin DSL and Version Catalog, then extract convention plugins.

**[Full answer with code →](https://droidly.io/gradle-android-build-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q50)**

---

Practise these with spaced repetition and a plan for your level: **[droidly.io](https://droidly.io/?utm_source=github&utm_medium=repo&utm_campaign=aiq)**
