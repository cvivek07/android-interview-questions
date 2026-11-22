# Data Storage (Room & DataStore) Interview Questions (50)

Room, migrations, DataStore, offline-first.

Short answers below. **Each question links to the full answer with Kotlin code on [Droidly](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq)**, where you can also mark what you know and get a study plan.

⬅️ [All topics](../README.md)

## ⭐ Most asked

### 1. What is Room? How does it compare to using SQLite directly?

🟢 Easy

> Room is Jetpack's database library — a thin, type-safe layer on top of SQLite. It generates boilerplate SQL code at compile time, validates your queries, and integrates with coroutines and Flow out of the box.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q1)**

### 2. What is a Room DAO? What annotations do you use for CRUD operations?

🟢 Easy

> DAO (Data Access Object) is the interface that defines how you interact with the database. Room generates the implementation — you just declare what you want to do, and Room figures out the SQL.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q2)**

### 3. How do you observe data changes in Room using Flow? How is this better than LiveData?

🟡 Medium

> A DAO that returns Flow automatically emits a new value whenever the underlying table changes. This creates a reactive pipeline from database → ViewModel → UI with no manual refresh needed.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q3)**

### 4. How do you handle Room database migrations? What happens if you don't?

🟡 Medium

> When you change your database schema (add a column, rename a table), you must provide a migration path. Without one, Room throws an exception — or worse, destroys all user data.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q4)**

### 5. What is Jetpack DataStore? How does it differ from SharedPreferences?

🟡 Medium

> DataStore is the modern replacement for SharedPreferences. It solves SharedPreferences' biggest problems: blocking the main thread and inconsistent behaviour across threads.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q5)**

### 6. What is Proto DataStore? When do you use it over Preferences DataStore?

🟡 Medium

> Proto DataStore stores a typed Protobuf object instead of key-value pairs. Use it when your stored data has structure — multiple related fields, nested types, or enums — rather than scattered individual keys.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q6)**

### 7. How do you implement encrypted storage for sensitive data in Android?

🔴 Hard

> Android provides EncryptedSharedPreferences and EncryptedFile (via Jetpack Security) backed by the AndroidKeyStore. Keys never leave the secure hardware — even a memory dump can't expose them.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q7)**

### 9. What are Room TypeConverters? When do you need them?

🟡 Medium

> SQLite only stores primitives (text, integer, real, blob). TypeConverters tell Room how to convert complex types — like Date, List, or custom enums — to and from a storable primitive.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q9)**

### 11. How do you test a Room database? What tools does Jetpack provide?

🟡 Medium

> Room supports in-memory databases that run on the JVM — no emulator or device needed for most DAO tests. MigrationTestHelper validates your migration scripts against exported schemas.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q11)**

### 14. How do you use Room with Paging 3 for large dataset pagination?

🟡 Medium

> Room has first-class Paging 3 support — a DAO method returning PagingSource gives you automatic pagination with zero boilerplate. Room handles page fetching, loading states, and error handling.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q14)**

### 15. What is WAL mode in SQLite/Room? Should you enable it?

🟡 Medium

> WAL (Write-Ahead Logging) is a journaling mode that dramatically improves concurrent read/write performance. Room enables WAL by default since Room 2.2 — you usually don't need to configure it manually.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q15)**

### 17. What are the different storage locations in Android — internal, external, cache, files?

🟡 Medium

> Android has multiple storage locations, each with different visibility, persistence, and permission requirements. Choosing the right location avoids permission issues and data leaks.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q17)**

### 20. What is Scoped Storage in Android? How does it affect file access?

🟡 Medium

> Scoped Storage (introduced in Android 10, enforced in Android 11) restricts apps to their own directories and MediaStore. You can no longer browse the entire filesystem — each app is sandboxed.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q20)**

### 22. How does Room handle threading? Do you need withContext(Dispatchers.IO) for Room calls?

🟡 Medium

> Room automatically runs on a background thread when you use suspend functions or return Flow. You don't need withContext(Dispatchers.IO) for Room calls — Room handles threading internally.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q22)**

### 26. What is the Repository pattern in the data layer? How does it connect Room to the ViewModel?

🟢 Easy

> The Repository is the single access point to all data sources — it decides whether to read from Room, the network, or DataStore. The ViewModel never touches a DAO or API directly; it always goes through the Repository.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q26)**

### 27. What is @PrimaryKey in Room? What are the different ways to generate IDs?

🟢 Easy

> @PrimaryKey marks the unique identifier for each row. Room supports auto-generated integer IDs, manual String UUIDs, and composite primary keys — each with different trade-offs for offline sync and performance.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q27)**

### 28. What is @Embedded in Room? How does it differ from @Relation?

🟡 Medium

> @Embedded flattens a nested object's fields into the parent table — one table, multiple logical groups of columns. @Relation links two separate tables via a foreign key and runs a second query to fetch the related rows.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q28)**

### 29. How do you use Room with Kotlin coroutines in tests? What is runTest and how does it help?

🟡 Medium

> runTest is the coroutine test builder from kotlinx-coroutines-test. It runs coroutines in a controlled test environment — skipping real delays, executing all coroutines eagerly, and making async code behave synchronously in tests.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q29)**

### 32. What is the difference between Room's @Query with LIKE vs using FTS? Which is faster and when?

🟡 Medium

> LIKE does a sequential scan — it checks every row. FTS (Full-Text Search) uses a pre-built inverted index — like a book's index vs reading every page. FTS is orders of magnitude faster on large tables.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q32)**

### 34. What is the difference between SharedPreferences.apply() and SharedPreferences.commit()?

🟢 Easy

> apply() writes asynchronously — it returns immediately and queues the write. commit() writes synchronously — it blocks until the write is flushed to disk. In modern Android you should use DataStore instead of both, but this distinction is still a common interview question.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q34)**

### 38. How do you use Room's @RawQuery for dynamic queries at runtime?

🟡 Medium

> @RawQuery lets you build a query string at runtime instead of at compile time. Useful for dynamic filters, sorting, and search combinations that can't be expressed with static @Query annotations.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q38)**

### 40. What is Room's AutoMigration? When can you use it and when must you write manual migrations?

🟡 Medium

> AutoMigration (Room 2.4+) generates migration SQL automatically for simple schema changes — adding columns, adding tables, renaming with @RenameColumn. Complex changes like splitting a table or changing column types still require manual migrations.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q40)**

### 43. How do you handle nullable columns in Room? What happens when you query a nullable column?

🟢 Easy

> Room maps Kotlin nullable types to SQLite NULL values. A String? column can be NULL in the database; String cannot. This aligns with Kotlin's null safety — Room enforces the contract at the database boundary.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q43)**

### 46. How do you migrate from SharedPreferences to DataStore in an existing app without losing user data?

🟡 Medium

> Migrating from SharedPreferences to DataStore requires reading existing prefs values and writing them to DataStore once — then permanently switching to DataStore.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q46)**

## More questions

### 8. Scenario: Design a Room-based offline-first architecture. How does data flow from network to UI?

🔴 Hard

> Offline-first means Room is always the single source of truth. The UI observes Room via Flow — it never reads from the network directly. The network only writes to Room; Room then triggers a UI update automatically.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q8)**

### 10. Scenario: How do you handle Room relationships — one-to-many and many-to-many?

🔴 Hard

> Room uses @ForeignKey for referential integrity and special result classes (one-to-many with @Relation, many-to-many with a junction table) to query related data efficiently.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q10)**

### 12. What is the difference between SharedPreferences, DataStore, Room, and files? When do you use each?

🟡 Medium

> SharedPreferences is synchronous key-value storage using XML files -- simple but blocks the main thread on first read. DataStore (Preferences or Proto) is the modern async replacement backed by a DataStore file, exposed as a Flow.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q12)**

### 13. Scenario: How do you implement a cache-then-network strategy? What are stale-while-revalidate and cache invalidation?

🔴 Hard

> Cache-then-network shows cached data immediately while fetching fresh data in the background. Stale-while-revalidate is the formal name for this pattern — serve stale data while revalidating with the network.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q13)**

### 16. Scenario: How do you handle data conflicts when syncing local Room data with a remote server?

🔴 Hard

> Sync conflicts happen when the same record is modified both locally (offline) and remotely. The three main strategies are last-write-wins, server-wins, and three-way merge — each with different trade-offs.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q16)**

### 18. How do you implement DataStore in a multi-module project? What are the best practices?

🟡 Medium

> DataStore should live in a dedicated data module with an interface, not accessed directly from feature modules. This prevents tight coupling and makes it mockable in tests.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q18)**

### 19. Scenario: How do you implement auto-backup and restore for app data?

🔴 Hard

> Android Auto Backup (API 23+) automatically backs up app data to Google Drive -- up to 25MB, daily when the device is idle, charging, and on WiFi. Users restore their backup when they install the app on a new device.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q19)**

### 21. Scenario: Design the complete data layer for an e-commerce app — what do you store where and why?

🔴 Hard

> An e-commerce app's data layer needs offline capability, optimistic UI updates, and clear cache invalidation. The architecture: Room as the single source of truth for all displayed data, Retrofit to fetch from the network, and a Repository that orchestrates the cache-then-network pattern.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q21)**

### 23. Scenario: How do you implement a search feature that queries Room efficiently? What indexes should you use?

🔴 Hard

> Search in Room uses LIKE queries with indexes for performance, and FTS (Full-Text Search) for multi-word search. FTS gives you tokenised search — searching for "android kotlin" finds records containing both words.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q23)**

### 24. How do you reduce Room database size? What are the best practices for keeping it lean?

🟡 Medium

> A bloated database slows down queries and wastes device storage. Regular pruning, smart data modelling, and avoiding storing unnecessary data keeps Room lean and fast.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q24)**

### 25. Scenario: Conduct a data storage code review. What 8 things do you look for?

🔴 Hard

> A systematic storage code review catches the most expensive mistakes — data loss, security vulnerabilities, and performance issues — before they reach production.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q25)**

### 30. How do you read and write files to internal storage in Android? What are the modern APIs?

🟡 Medium

> Internal storage file I/O in modern Android uses standard Kotlin file APIs combined with coroutines. Always read/write on a background thread — file operations can block for hundreds of milliseconds.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q30)**

### 31. Scenario: Implement a Room database with multi-table transactions. Why are @Transaction methods important?

🔴 Hard

> A database transaction groups multiple operations so they either all succeed or all fail together. Without @Transaction, a crash between two related writes leaves the database in a corrupt, inconsistent state.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q31)**

### 33. Scenario: Your Room database needs to support multi-process access (e.g. a foreground app and a background service in a separate process). What are the challenges?

🔴 Hard

> SQLite supports multi-process access but Room's in-memory state (invalidation tracker, WAL) breaks with multiple processes. Room provides enableMultiInstanceInvalidation as a partial solution — but it comes with significant trade-offs.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q33)**

### 35. Scenario: Design a draft system — user starts editing, app can be killed, draft must survive and restore automatically.

🔴 Hard

> Drafts need to survive process death, so SavedStateHandle alone isn't enough for large data. The complete solution combines Room (persistent storage) with SavedStateHandle (lightweight session state) and auto-save with debounce.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q35)**

### 36. How do you export a Room database schema? Why is it important for production apps?

🟡 Medium

> Room can export a JSON snapshot of your database schema to a file. These schema files are version-controlled alongside your code and enable MigrationTestHelper to validate your migrations without running them on a real device.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q36)**

### 37. Scenario: How do you implement a read-through cache — check Room first, fetch from network if absent, save to Room?

🔴 Hard

> A read-through cache is transparent to callers — they just call getProduct(id) and get data. The repository internally checks Room first, fetches from the network only on a cache miss, and saves back to Room for next time.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q37)**

### 39. Scenario: You have 50,000 records in Room and a list screen is janky. How do you diagnose and fix Room performance?

🔴 Hard

> Room performance issues usually come from missing indexes, loading too much data at once, or doing heavy work on the main thread. The fix is a combination of indexing, pagination, and profiling.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q39)**

### 41. Scenario: Implement a favourites feature that works offline-first. User taps a heart — it saves locally and syncs when online.

🔴 Hard

> Offline-first favourites need optimistic UI (instant heart toggle), local persistence (Room), and background sync (WorkManager). The user sees instant feedback — the sync is invisible.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q41)**

### 42. What is the Paging 3 RemoteMediator? How does it combine Room and a network API?

🟡 Medium

> RemoteMediator bridges your network API and Room. When Paging 3 runs out of data in Room, RemoteMediator fetches the next page from the API and saves it to Room — Paging then reads from Room seamlessly.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q42)**

### 44. Scenario: Design a local notification history — store, query, and clean up notification records in Room.

🔴 Hard

> Notification history is a classic append-heavy workload. Design it with efficient indexes for the most common queries (unread count, recent list), and automatic cleanup to prevent unbounded growth.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q44)**

### 45. Scenario: Your app's storage layer has performance issues in production. Walk through how you profile and fix them.

🔴 Hard

> Production storage profiling uses Android Studio's Database Inspector for Room, StrictMode for main-thread I/O, and Firebase Performance Monitoring for real-world timing data across all users.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q45)**

### 47. Scenario: Implement a shopping cart that persists locally, syncs with the server, and handles quantity updates atomically.

🔴 Hard

> A shopping cart needs local persistence (works offline), atomic quantity updates (no race conditions), and reliable server sync. Room @Transaction + coroutines handles all three.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q47)**

### 48. What is Room's support for Kotlin Multiplatform (KMP)? How does it change the data layer?

🟡 Medium

> Room 2.7+ supports Kotlin Multiplatform — the same Room code can run on Android, iOS, and Desktop. This means your entire data layer can be shared across platforms, eliminating duplicate database code.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q48)**

### 49. Scenario: How do you handle Room database corruption? What causes it and how do you recover?

🔴 Hard

> Room database corruption is rare but happens when the SQLite file is incomplete — usually from a process kill during a write. Detecting corruption, recovering gracefully, and preventing data loss requires a deliberate strategy.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q49)**

### 50. Scenario: Design the complete data storage architecture for a note-taking app — drafts, sync, search, and encryption.

🔴 Hard

> A note-taking app is the canonical data storage design challenge — it touches every storage mechanism and requires careful decisions about what to persist where, how to sync, and what to encrypt.

**[Full answer with code →](https://droidly.io/android-room-datastore-interview-questions?utm_source=github&utm_medium=repo&utm_campaign=aiq#q50)**

---

Practise these with spaced repetition and a plan for your level: **[droidly.io](https://droidly.io/?utm_source=github&utm_medium=repo&utm_campaign=aiq)**
