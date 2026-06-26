# S-Peek Phase 10.3 Build Fix

The local Android Studio build failed during `:app:compileDebugKotlin` because `com.google.mlkit:digital-ink-recognition:19.0.0` includes Kotlin metadata version `2.1.0`, while the project is currently using Kotlin `1.9.24` and expects Kotlin metadata `1.9.0`.

## Conservative fix

In `app/build.gradle.kts`, change the Digital Ink dependency from:

```kotlin
implementation("com.google.mlkit:digital-ink-recognition:19.0.0")
```

to:

```kotlin
implementation("com.google.mlkit:digital-ink-recognition:18.1.0")
```

Then rebuild:

```text
:app:assembleDebug
```

## Why this fix

This keeps the existing Kotlin `1.9.24`, Android Gradle Plugin `8.5.2`, and Compose compiler `1.5.14` setup intact. The alternative is a broader Kotlin 2.x migration, which would also require switching to the Kotlin Compose plugin and retesting the Compose build path.

## Original failure signature

```text
Module was compiled with an incompatible version of Kotlin.
The binary version of its metadata is 2.1.0, expected version is 1.9.0.
```
