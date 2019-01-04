# jetpack - LifeCycleEvent
* Installation
* Issue 

## Installation 
### dependencies - Build.gradle (Model app)
```json
dependencies {
    def lifecycle_version = "1.1.1"

    // ViewModel and LiveData
    implementation "android.arch.lifecycle:extensions:$lifecycle_version"
    // alternatively - just ViewModel
    implementation "android.arch.lifecycle:viewmodel:$lifecycle_version" // use -ktx for Kotlin
    // alternatively - just LiveData
    implementation "android.arch.lifecycle:livedata:$lifecycle_version"
    // alternatively - Lifecycles only (no ViewModel or LiveData).
    //     Support library depends on this lightweight import
    implementation "android.arch.lifecycle:runtime:$lifecycle_version"

    annotationProcessor "android.arch.lifecycle:compiler:$lifecycle_version" // use kapt for Kotlin
    // alternately - if using Java8, use the following instead of compiler
    implementation "android.arch.lifecycle:common-java8:$lifecycle_version"

    // optional - ReactiveStreams support for LiveData
    implementation "android.arch.lifecycle:reactivestreams:$lifecycle_version"

    // optional - Test helpers for LiveData
    testImplementation "android.arch.core:core-testing:$lifecycle_version"
	...

```

## Issue
```json
android {
...
  compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    }
...
}
```

## Reference : 
* https://developer.android.com/topic/libraries/architecture/adding-components?hl=id#lifecycle
