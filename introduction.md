# Introduction 
## why kotlin ?
## Common Kotlin Editor

## Why Kotlin
### 1. Statically Types
Kotlin is a Statically typed programming language. This means that the type of every variable and expression is known at compile time.

The advantage with static typing is that the compiler can validate the methods calls and property access on the objects at compile time itself and prevent lots of trivial bugs that would otherwise crop up at runtime.

Although Kotlin is a statically typed language, it doesn’t require you to explicitly specify the type of every variable you declare. Most of the time, Kotlin can infer the type of a variable from the initializer expression or the surrounding context. This is called Type Inference

### 2. Concise
Kotlin is concise. It drastically reduces the amount of boilerplate code that you have been writing all the time in other OOP languages like Java.

It provides rich idioms for performing common tasks. For example, You can create a POJO class with getters, setters, equals(), hashCode() and toString() methods in a single line -

```kotlin
data class User(val name: String, val email: String, val country: String)
```

## Common Kotlin Editor
1. stand alone compiler
2. intellej IDE
3. Ecplipse
4. Android Studio
