# Android Fundamentals Interview Questions (50)

Lifecycle, components, process death, intents, services.

Short answers below. **Each question links to the full answer with Kotlin code on [Droidly](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq)**, where you can also mark what you know and get a study plan.

⬅️ [All topics](../README.md)

## ⭐ Most asked

### 1. Explain the Activity lifecycle. What happens when you press Home vs Back button?

🟢 Easy

> Think of an Activity's lifecycle like a person's daily routine — it's created in the morning, becomes active, goes to the background when interrupted, and eventually gets destroyed at night.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q1)**

### 2. What is the difference between Fragment lifecycle and Activity lifecycle? How do they interact?

🟡 Medium

> A Fragment is a reusable piece of UI that lives inside an Activity — think of it as a "mini Activity". Apps like Instagram use Fragments for each tab (Home, Search, Reels, Profile) inside one Activity.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q2)**

### 3. What are the different types of Intent? Explain explicit vs implicit with examples.

🟡 Medium

> An Intent is Android's messaging system — it's how components talk to each other.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q3)**

### 4. What is the difference between Service, IntentService, and WorkManager? When do you use each?

🟡 Medium

> Android is very aggressive about killing background processes to preserve battery and memory. This means if your app needs to do work while the user isn't actively using it — like syncing data, uploading a photo, or playing music — you need to pick the right tool, otherwise Android will silently kill your work mid-way.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q4)**

### 5. What is the difference between Context and ApplicationContext? When do you use each?

🟡 Medium

> Context is one of the most fundamental — and most misunderstood — classes in Android. It's basically a handle to the Android system: it lets your code access resources (strings, drawables, layouts), start Activities, get system services (like the clipboard or notification manager), and create Views.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q5)**

### 7. What is a BroadcastReceiver? What is the difference between static and dynamic registration?

🟡 Medium

> A BroadcastReceiver is Android's event system — it's like subscribing to a newsletter. When a system event happens (device boots, battery gets low, network changes) or your app sends a custom event, all registered receivers are notified simultaneously.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q7)**

### 11. What is the difference between Serializable and Parcelable? Which should you use in 2025?

🟡 Medium

> When you navigate between screens in Android — say, from a product list to a product detail screen — you often need to pass objects along with the Intent or Fragment arguments.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q11)**

### 12. What is the difference between LaunchMode: standard, singleTop, singleTask, and singleInstance?

🟡 Medium

> Activity launch modes control what happens when you try to start an Activity that might already exist somewhere in the back stack. The back stack is like a pile of cards — each new screen is a card placed on top.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q12)**

### 14. What is ANR? What are the most common causes and how do you diagnose it?

🟡 Medium

> ANR — Application Not Responding — is one of the most user-frustrating issues in Android. When Android detects that your app's main thread hasn't responded to a user input event for 5 seconds (or a broadcast for 10 seconds), it shows a dialog letting the user force-close your app.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q14)**

### 16. What is edge-to-edge display in Android? How do you handle window insets properly?

🟡 Medium

> Edge-to-edge means your app's content draws all the way to the edges of the screen — behind the status bar at the top and the navigation bar at the bottom — instead of stopping just below and above them.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q16)**

### 17. How do you implement push notifications on Android in 2025? Walk through the full flow.

🟡 Medium

> Push notifications in Android require two systems working together: Firebase Cloud Messaging (FCM) on the server side delivers the message to the device, and Android's NotificationManager on the device side displays it to the user.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q17)**

### 19. What is the difference between View.GONE, View.INVISIBLE, and View.VISIBLE? How do these work in the layout system?

🟡 Medium

> View visibility might seem simple — show or hide — but Android has three states, and the difference between INVISIBLE and GONE is subtle yet critical.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q19)**

### 21. What is a ContentProvider? When and why would you use one?

🟡 Medium

> ContentProvider is one of Android's four fundamental building blocks (alongside Activity, Service, and BroadcastReceiver). It's a structured way to share data between apps — think of it as a database API that other apps can query over a standardized URI-based interface.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q21)**

### 22. What is the difference between LiveData and StateFlow? Which should you use in 2025?

🟡 Medium

> LiveData and StateFlow both solve the same problem: observing data changes from a ViewModel in a lifecycle-safe way. LiveData was the original Jetpack answer — it's lifecycle-aware by design, automatically stopping updates when your UI is in the background.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q22)**

### 23. What is the difference between RecyclerView and LazyColumn? When do you use each?

🟡 Medium

> Showing a large list of items efficiently is one of the most fundamental challenges in mobile UI — you can't create a View for every item in a list of 10,000 products.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q23)**

### 24. What is Doze Mode and App Standby? How do they affect background work?

🔴 Hard

> Doze mode is Android's aggressive battery optimization system that kicks in when the device is stationary, screen off, and unplugged for a period of time.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q24)**

### 25. What is the difference between Handler, Looper, and MessageQueue?

🟡 Medium

> Android's entire UI system runs on a single main thread. Handler, Looper, and MessageQueue are the three classes that power how that thread processes work — and how background threads can safely communicate with the main thread.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q25)**

### 26. What is ViewBinding and how is it different from DataBinding and findViewById?

🟡 Medium

> Every Android developer has experienced the pain of a NullPointerException from a wrong view ID, or a ClassCastException from the wrong type in a cast, or the frustration of refactoring a layout and forgetting to update the Java code.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q26)**

### 28. What is Jetpack Navigation Component? How does it handle deep links and back stack?

🟡 Medium

> Before Jetpack Navigation Component, managing the back stack in an Android app was a fragile manual process: developers wrote their own FragmentManager.beginTransaction() code, manually handled back presses, and deep links required custom parsing in every Activity.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q28)**

### 30. What is ConstraintLayout and why is it preferred over other layouts?

🟡 Medium

> Before ConstraintLayout, building complex Android UIs required nesting multiple LinearLayouts and RelativeLayouts — and each nesting level multiplied the measure/layout passes required to render the screen.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q30)**

### 31. What is the Android Manifest file and what are its key components?

🟡 Medium

> AndroidManifest.xml is the app's contract with the Android operating system — it describes what your app is, what it can do, and what it needs, all before a single line of your code runs.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q31)**

### 33. How does Android handle accessibility? What are the key APIs and best practices?

🟡 Medium

> Accessibility is about making your app usable by everyone — including people who are blind, have low vision, motor impairments, or cognitive disabilities. In India alone, over 70 million people have some form of disability, and globally over 1 billion people benefit from accessible apps.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q33)**

### 36. What is IPC in Android? Explain AIDL and when you would use it over other IPC mechanisms.

🔴 Hard

> Android enforces strict process isolation — each app runs in its own Linux process with its own memory space. Inter-Process Communication (IPC) is the set of mechanisms that allow processes to talk to each other.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q36)**

### 39. How do you create a Custom View in Android? Explain onMeasure, onLayout, and onDraw.

🔴 Hard

> Custom Views are the foundation of any polished Android UI — they let you build components that the standard SDK doesn't offer, like progress rings, waveform visualizers, star ratings with half-stars, or the circular profile pictures in apps like Instagram and WhatsApp.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q39)**

### 40. What is the difference between DVM, ART, and JVM? How does Android compile and run code?

🟡 Medium

> Understanding the Android runtime stack is a question that separates developers who truly understand the platform from those who just use it. The JVM (Java Virtual Machine) was designed for servers and desktop machines with abundant memory and battery — it's not suitable for a 512MB phone with a limited battery.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q40)**

### 41. What is AlarmManager? When do you use it vs WorkManager?

🟡 Medium

> Android's background execution restrictions have become increasingly strict with every major version — Doze mode (Android 6), background process limits (Android 8), exact alarm restrictions (Android 12 and 13), and foreground service type requirements (Android 14).

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q41)**

### 42. What is SparseArray? When should you use it instead of HashMap?

🟡 Medium

> Android devices have historically been memory-constrained compared to desktop applications, which makes memory-efficient data structures important for smooth performance — especially in code that runs frequently, like RecyclerView adapters or Custom View drawing logic.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q42)**

### 43. How does Android handle Bitmap memory? What is BitmapPool and how do image loading libraries use it?

🔴 Hard

> Bitmap memory management is one of the most critical skills in Android development — get it wrong and your app crashes with OutOfMemoryError on millions of devices, or scrolls through a photo feed with constant frame drops and GC pauses.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q43)**

### 44. How do you implement App Widgets in Android? What changed in Android 12?

🟡 Medium

> App Widgets are one of the most visible differentiating features on Android versus iOS (which only added basic widgets in iOS 14) — they let your app provide live, glanceable information directly on the home screen without the user opening the app.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q44)**

### 45. How do you ensure backward compatibility in Android? Explain @RequiresApi, BuildConfig, and AndroidX.

🟡 Medium

> Android's fragmentation — hundreds of millions of devices still running Android 7, 8, and 9 even as Android 16 launches — means that every API you use must be checked for backward compatibility.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q45)**

### 46. What is StrictMode and how do you use it to catch issues in development?

🟡 Medium

> ANR (Application Not Responding) errors are one of the most damaging metrics for an Android app — Android Vitals penalizes apps with high ANR rates and Play Store ranking suffers.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q46)**

## More questions

### 6. How does the Android permission model work in Android 14/15? What changed recently?

🔴 Hard

> Android's permission model has gone through several major evolutions. Starting from Android 6 (API 23), dangerous permissions must be requested at runtime — the user decides when they actually need the feature, not at install time.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q6)**

### 8. How does Android handle process death and state restoration? What is the difference between ViewModel, SavedStateHandle, and onSaveInstanceState?

🔴 Hard

> Android is brutally aggressive about reclaiming memory — your app's process can be killed at any time when it's in the background, and the user expects to return to exactly where they left off.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q8)**

### 9. What is the Android Predictive Back Gesture introduced in Android 13/14? How do you implement it?

🔴 Hard

> Predictive Back is a UX feature introduced in Android 13 (API 33) that gives users a live preview of where the back gesture will take them — they can see the destination screen peek in from behind before completing the gesture.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q9)**

### 10. How does the Android Splash Screen API work? What replaced the old SplashActivity pattern?

🔴 Hard

> Before Android 12, developers used a hacky approach: either an empty SplashActivity that immediately launched MainActivity (adding an extra Activity hop and slowing startup), or setting a theme with a drawable background (which looked like a splash but was actually just the window background with no control over timing).

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q10)**

### 13. How does Android handle deep links? What is the difference between deep links, App Links, and custom scheme URIs?

🔴 Hard

> Deep links let external sources — emails, SMS messages, web pages, QR codes, other apps — navigate users directly to a specific screen inside your app, bypassing the home screen.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q13)**

### 15. What is the difference between compileSdk, minSdk, and targetSdk? What happens if you set targetSdk incorrectly?

🔴 Hard

> Every Android app has three SDK version numbers in its build.gradle, and confusing them is one of the most common mistakes for new Android developers.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q15)**

### 18. What is the Android App Startup library and how does it improve cold start time?

🔴 Hard

> When Android launches your app, every ContentProvider registered in your Manifest gets initialized before your code runs — this happens before Application.onCreate().

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q18)**

### 20. What is Baseline Profiles and how do they improve app performance in 2025?

🔴 Hard

> When a user installs your app for the first time, Android's ART runtime (Android Runtime) doesn't know which code paths are "hot" — frequently executed and performance-critical.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q20)**

### 27. How do you support foldable phones and large screens in Android?

🔴 Hard

> With over 200 million large-screen Android devices (foldables, tablets, and Chromebooks) in active use in 2025, Google has made large screen compatibility a major priority — and Play Store now surfaces apps that handle large screens well.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q27)**

### 29. How do you implement Android security best practices? Cover SSL pinning, ProGuard, and secure storage.

🔴 Hard

> Android security is not optional — a single vulnerability can expose your users' financial data, personal information, or account credentials. Security has layers: data in transit (network security), data at rest (local storage), code security (obfuscation and reverse engineering prevention), and device integrity verification.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q29)**

### 32. What is Jetpack Paging 3? How does it handle large datasets efficiently?

🔴 Hard

> Imagine a food delivery app like Swiggy showing a restaurant's menu with 500 items, or Instagram's explore feed with millions of posts. Loading all of that at once would exhaust memory and take forever.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q32)**

### 34. What are the key features and breaking changes in Android 15 and Android 16?

🔴 Hard

> Staying current with Android platform changes is one of the clearest signals of a senior developer — it shows you don't just write code, you actively track how the platform evolves and proactively update your apps.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q34)**

### 35. What is Kotlin Multiplatform Mobile (KMM) and how does it relate to Android development?

🔴 Hard

> Kotlin Multiplatform (KMP, formerly called KMM — Kotlin Multiplatform Mobile) is JetBrains' solution for sharing business logic across Android, iOS, web, and desktop while keeping native UI for each platform.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q35)**

### 37. What is Scoped Storage? How do you access media files with MediaStore in Android 10+?

🔴 Hard

> Before Android 10, apps could declare READ_EXTERNAL_STORAGE and get access to every file on the device — photos from other apps, documents, everything. This was a massive privacy problem: a flashlight app could secretly read all your photos.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q37)**

### 38. How do you implement biometric authentication using BiometricPrompt?

🟡 Medium

> Biometric authentication — fingerprint, face recognition, iris scanning — is now table stakes for any serious Android app, especially in fintech, banking, and healthcare.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q38)**

### 47. What is WebView in Android? What are the security risks and how do you mitigate them?

🔴 Hard

> WebView embeds a full web browser engine inside your Android app, letting you display web content without sending users to Chrome.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q47)**

### 48. What are Android App Shortcuts? Explain static, dynamic, and pinned shortcuts.

🔴 Hard

> App Shortcuts are a powerful but underutilized engagement feature — they appear when a user long-presses your app icon and provide immediate access to common actions.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q48)**

### 49. What is multi-process architecture in Android? When would you run components in separate processes?

🔴 Hard

> By default, every component in an Android app — Activity, Service, BroadcastReceiver, ContentProvider — runs in the same OS process, sharing the same memory space and JVM heap.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q49)**

### 50. What is the Android Vitals dashboard? What metrics should you monitor in production?

🔴 Hard

> Android Vitals is the section of Google Play Console that shows your app's real-world performance data — collected passively from users' devices who have opted in to sharing usage data.

**[Full answer with code →](https://droidly.io/android-fundamentals-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q50)**

---

Practise these with spaced repetition and a plan for your level: **[droidly.io](https://droidly.io/?utm_source=github&utm_medium=repo&utm_campaign=aiq)**
