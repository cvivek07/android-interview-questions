# Networking Interview Questions (50)

Retrofit, OkHttp, interceptors, caching, error handling.

Short answers below. **Each question links to the full answer with Kotlin code on [Droidly](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq)**, where you can also mark what you know and get a study plan.

⬅️ [All topics](../README.md)

## ⭐ Most asked

### 1. What is Retrofit? How does it work under the hood?

🟢 Easy

> Retrofit is a type-safe HTTP client for Android. You write an interface with annotated methods, and Retrofit generates the implementation at runtime using reflection and a dynamic proxy.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q1)**

### 2. What is OkHttp? How does it relate to Retrofit?

🟢 Easy

> OkHttp is the actual HTTP engine — it makes the TCP connection, sends bytes, receives bytes. Retrofit sits on top and adds type safety. Think of OkHttp as the car engine, and Retrofit as the dashboard you interact with.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q2)**

### 3. What is an OkHttp Interceptor? What are the two types and when do you use each?

🟢 Easy

> An interceptor is a middleware that sits in the HTTP request/response pipeline. Every request flows through your interceptors before reaching the server, and every response flows back through them.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q3)**

### 4. How do you handle API errors in Retrofit? What's the difference between a network error and an HTTP error?

🟡 Medium

> There are two completely different kinds of failures: the request never reached the server (network error), or the server responded but with a non-2xx status (HTTP error).

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q4)**

### 5. What is a Bearer token and how do you add authentication to every request?

🟡 Medium

> A Bearer token is a string (usually a JWT) that proves the user is logged in. You send it in every request's Authorization header. An OkHttp interceptor is the cleanest way to add it automatically to every single request.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q5)**

### 6. How do you implement token refresh — automatically refreshing an expired JWT without the user noticing?

🔴 Hard

> When the access token expires, the server returns 401. A smart interceptor catches that 401, silently fetches a new token using the refresh token, and retries the original request — the user sees nothing.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q6)**

### 7. Which JSON library should you use with Retrofit in 2025 — Gson, Moshi, or Kotlin Serialization?

🟡 Medium

> Kotlin Serialization is the 2025 recommendation — it's Kotlin-first, works with Kotlin Multiplatform, and is fast. Moshi is a great second choice. Gson is legacy — it has null-safety issues with Kotlin.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q7)**

### 8. How does OkHttp caching work? How do you implement offline support using the HTTP cache?

🟡 Medium

> OkHttp has a built-in disk cache that stores GET responses. When offline, you can force OkHttp to serve stale cached data instead of failing with a network error — giving users something to look at.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q8)**

### 11. What is the difference between @Query, @Path, @Body, and @Header in Retrofit?

🟡 Medium

> Each annotation controls where your parameter ends up in the HTTP request. Understanding this lets you call any REST API correctly without guessing.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q11)**

### 12. What is REST? What are the key HTTP methods and when do you use each?

🟡 Medium

> REST (Representational State Transfer) is an architectural style for APIs. Resources (things) are identified by URLs. HTTP methods (verbs) describe what action to perform on that resource.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q12)**

### 13. REST vs GraphQL — what are they, how do they differ, and when do you choose each?

🔴 Hard

> REST (Representational State Transfer) is a URL-based API style where each endpoint represents a resource and HTTP verbs (GET, POST, PUT, DELETE) define operations.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q13)**

### 17. How do you upload files (images, documents) using Retrofit and Multipart?

🟡 Medium

> File uploads use Multipart form data — the request body contains multiple "parts", each with its own headers and content. Retrofit makes this clean with @Multipart and @Part annotations.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q17)**

### 18. How do you convert network models (DTOs) to domain models? Why keep them separate?

🟡 Medium

> DTOs (Data Transfer Objects) match the API's JSON exactly. Domain models represent your app's business concepts. Keeping them separate means a backend API change only affects the DTO layer — not your entire codebase.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q18)**

### 22. What are network timeouts? How do you configure and choose the right values?

🟡 Medium

> Timeouts prevent your app from waiting forever for a server that isn't responding. Three different timeouts control different phases of the HTTP connection — choosing the right values balances user experience against reliability.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q22)**

### 23. How do you use Retrofit with Kotlin coroutines? What are the advantages over callbacks?

🟢 Easy

> Retrofit has built-in coroutine support — just add suspend to your interface functions. No callbacks, no threading boilerplate, no callback hell. Your network code reads like sequential code but runs asynchronously.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q23)**

### 26. What is HTTP/2? How does it improve performance over HTTP/1.1?

🟡 Medium

> HTTP/2 multiplexes multiple requests over a single TCP connection, eliminating the head-of-line blocking that limits HTTP/1.1. It also compresses headers (HPACK) and supports server push.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q26)**

### 27. What is connection pooling in OkHttp? Why does it matter for performance?

🟡 Medium

> Opening a TCP connection is expensive — DNS lookup, TCP handshake, TLS handshake can take 100-300ms. Connection pooling keeps connections open and reuses them for future requests.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q27)**

### 29. What is HTTPS and why is it mandatory in modern Android apps?

🟡 Medium

> HTTPS is HTTP over TLS (Transport Layer Security). It encrypts all data in transit, authenticates the server's identity via a certificate, and verifies data integrity.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q29)**

### 31. What is the difference between query parameters, path parameters, and request headers? When do you use each?

🟡 Medium

> These three mechanisms put data in different parts of an HTTP request. The right choice affects API design, security, and cacheability.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q31)**

### 33. How do you handle API versioning in Android? What happens when the backend changes the API?

🟡 Medium

> API versioning ensures older app versions keep working when the backend evolves. Android apps can't be force-updated — users on old versions will keep making requests forever, so backward compatibility is critical.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q33)**

### 35. What is gzip compression in HTTP and how does OkHttp handle it?

🟡 Medium

> Gzip compresses the response body before sending — a 100KB JSON response might compress to 15KB. OkHttp adds the Accept-Encoding header and decompresses responses automatically.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q35)**

### 37. What is an idempotency key and when do you need it?

🟡 Medium

> An idempotency key is a unique ID sent with non-idempotent requests (like payment) so the server can recognise and deduplicate retries. Without it, a network timeout could cause the user to be charged twice.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q37)**

### 39. What is the difference between PUT and PATCH? When do you use each in a REST API?

🟡 Medium

> PUT replaces the entire resource. PATCH updates only the fields you send. For most mobile apps, PATCH is preferable — you only send what changed, saving bandwidth and avoiding accidental data loss.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q39)**

### 41. What is CORS and does it affect Android apps?

🟡 Medium

> CORS (Cross-Origin Resource Sharing) is a browser security policy that restricts web pages from making requests to a different domain than the one that served the page.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q41)**

### 43. How do you handle network state changes (going offline/online) in an Android app?

🟡 Medium

> Observing network connectivity lets your app adapt in real time — showing offline banners, pausing sync, resuming operations when connectivity returns. The modern approach uses ConnectivityManager with a Flow.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q43)**

### 47. How do you send a custom User-Agent header with Retrofit and why is it useful?

🟡 Medium

> User-Agent identifies your app to the server. OkHttp sends a default one, but a custom User-Agent lets your server analytics distinguish app versions, platforms, and even feature flags — without changing API contracts.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q47)**

### 49. What is the Retrofit CallAdapter? How do you create a custom one to wrap responses in Result&lt;T&gt;?

🟡 Medium

> A CallAdapter transforms Retrofit's Call into another type — Flow, Result, or a custom wrapper. Instead of writing try-catch in every repository, a custom adapter wraps every response automatically.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q49)**

## More questions

### 9. Scenario: Your API returns different response shapes for success and error. How do you model this in Retrofit?

🟡 Medium

> The trick is using Retrofit's Response&lt;T&gt; wrapper which gives you access to both the success body and the raw error body — letting you parse the error into your error model even on non-2xx responses.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q9)**

### 10. Scenario: How do you implement SSL pinning to prevent man-in-the-middle attacks on your API?

🔴 Hard

> SSL pinning ties your app to a specific server certificate or public key -- even a legitimate CA-issued certificate for the same domain will be rejected if it doesn't match the pinned value.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q10)**

### 14. Scenario: Implement a robust retry mechanism with exponential backoff for flaky network requests.

🔴 Hard

> Exponential backoff means waiting progressively longer between retries — 1s, 2s, 4s. This prevents hammering a struggling server, which would make things worse. Add jitter (random small delay) to prevent all clients retrying at the same moment.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q14)**

### 15. How do you use Kotlin Serialization with Retrofit? What are @SerialName and ignoreUnknownKeys?

🟡 Medium

> Kotlin Serialization is the modern way to parse JSON in Kotlin — no reflection, compile-time safe, KMP compatible. A few configuration options make it production-ready.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q15)**

### 16. Scenario: How do you add logging to all your API requests in debug mode only — without sending any logs in production?

🔴 Hard

> HttpLoggingInterceptor from OkHttp logs every request and response. The key: only add it when BuildConfig.DEBUG is true — that way production builds never log sensitive data.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q16)**

### 19. Scenario: How do you test a Repository that makes network calls? What tools and patterns do you use?

🔴 Hard

> Testing network code in isolation requires either mocking the API interface or using MockWebServer to serve fake HTTP responses. Both approaches run fast, offline, and deterministically.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q19)**

### 20. What is an API gateway pattern? How does it affect your Android network code?

🟡 Medium

> An API gateway sits between clients and microservices — it's a single entry point that handles auth, rate limiting, routing, and aggregation. From Android's perspective, you talk to one URL instead of dozens of microservice URLs.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q20)**

### 21. Scenario: Your app needs to paginate through a list of 10,000 products. How do you implement pagination with Retrofit and Paging 3?

🔴 Hard

> Paging 3 is Jetpack's library for loading data in pages. You write a PagingSource that fetches one page at a time from Retrofit — Paging 3 handles loading states, error handling, and smooth scrolling automatically.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q21)**

### 24. What is WebSocket and how do you implement real-time communication in Android?

🔴 Hard

> HTTP is request-response — the client asks, the server answers. WebSocket is a persistent bidirectional channel — server can push data anytime. Perfect for chat, live scores, stock prices, and notifications.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q24)**

### 25. Scenario: Design the complete networking layer for a production Android app — from OkHttp setup to the ViewModel. What decisions do you make and why?

🔴 Hard

> A production networking layer requires intentional decisions at every level — security, performance, error handling, testability, and maintainability all have to work together.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q25)**

### 28. Scenario: Your app sends user analytics events. Should you batch them or send individually? How do you implement batching?

🔴 Hard

> Always batch analytics — sending one event per HTTP request wastes battery (each wakes the radio), adds latency, and can overload your server. Collect events locally, flush in batches.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q28)**

### 30. Scenario: Your app downloads large images and PDFs. How do you implement download progress and cancellation?

🔴 Hard

> Large file downloads need real-time progress and the ability to cancel mid-download. OkHttp's ResponseBody combined with a Flow is the cleanest approach in modern Android.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q30)**

### 32. What is Server-Sent Events (SSE)? How does it compare to WebSocket and polling?

🔴 Hard

> SSE is a one-way push from server to client over HTTP. Simpler than WebSocket (no bidirectional protocol), more efficient than polling (no repeated requests). Perfect for live feeds, notifications, and status updates.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q32)**

### 34. Scenario: Your app needs to make network requests even when the user is offline — queue them and execute when connectivity is restored.

🔴 Hard

> WorkManager is the right tool for deferred requests — it survives process death, respects network constraints, and retries automatically. Room is the queue.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q34)**

### 36. Scenario: You need to call three APIs in parallel and merge results for a dashboard screen. How do you do this efficiently?

🔴 Hard

> async/await with coroutineScope runs all three requests simultaneously — total time equals the slowest, not the sum. This is one of the clearest wins of coroutines over callbacks.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q36)**

### 38. Scenario: How do you use MockWebServer to write tests that simulate specific HTTP responses including errors, delays, and timeouts?

🔴 Hard

> MockWebServer from OkHttp runs a real HTTP server locally during tests. You pre-program exactly what responses it returns — making network tests deterministic, fast, and offline-capable.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q38)**

### 40. What is gRPC? How does it compare to REST and when would you use it in an Android app?

🔴 Hard

> gRPC is Google's RPC framework using Protocol Buffers (binary format) over HTTP/2. It's significantly faster and more efficient than REST+JSON, but more complex to set up.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q40)**

### 42. Scenario: Your API returns a list of 1000 items but your screen only shows 20 at a time. How do you implement cursor-based pagination vs offset pagination?

🔴 Hard

> Offset pagination (page=1&limit=20) is simple but has problems with real-time data. Cursor-based pagination uses a pointer to the last seen item — more reliable for feeds that change while the user scrolls.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q42)**

### 44. Scenario: Your app has sensitive data in API responses. How do you prevent it from being captured by proxies or network inspection tools?

🔴 Hard

> Tools like Charles Proxy work by installing a custom CA on the device. SSL pinning defeats this. For maximum security — combine SSL pinning, certificate transparency, and detection of proxy/rooted environments.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q44)**

### 45. What is OkHttp's EventListener? How do you use it to monitor network performance?

🟡 Medium

> EventListener gives you detailed timing callbacks for every phase of an HTTP request — DNS lookup, TCP connect, TLS handshake, request write, response read. Perfect for performance monitoring without third-party APM tools.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q45)**

### 46. Scenario: A junior dev pushed code that makes network calls on the main thread. How do you detect and prevent this?

🔴 Hard

> Main-thread network calls cause ANR (Application Not Responding) errors. They're detectable at runtime with StrictMode, preventable with architecture (suspend functions), and findable in code review with linting.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q46)**

### 48. Scenario: Your backend uses GraphQL. How do you integrate Apollo Kotlin into an Android app with caching and error handling?

🔴 Hard

> Apollo Kotlin is the official GraphQL client for Android — it generates type-safe Kotlin code from your .graphql query files. It has built-in normalized caching and coroutine support.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q48)**

### 50. Scenario: Conduct a complete networking code review. What 10 things do you look for?

🔴 Hard

> A systematic networking code review checklist prevents the most common production networking bugs — from memory leaks to security vulnerabilities. Each item maps to a real production issue.

**[Full answer with code →](https://droidly.io/android-networking-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q50)**

---

Practise these with spaced repetition and a plan for your level: **[droidly.io](https://droidly.io/?utm_source=github&utm_medium=repo&utm_campaign=aiq)**
