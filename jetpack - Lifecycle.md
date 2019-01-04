# jetpack - LifeCycleEvent
* Installation
* Issue 
* ActivityOwner
* ActiivtyObserver

## Installation 
### dependencies - Build.gradle (Model app)
```gradle
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
## ActivityOwner
```kotlin
import android.os.Bundle
import android.support.v7.app.AppCompatActivity
import android.util.Log

class MainActivity : AppCompatActivity() {

    val Tag: String = this.javaClass.simpleName
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        Log.d(Tag, "Owner onCreate")
        this.lifecycle.addObserver(MainActivityObserver())
    }

    override fun onStart() {
        super.onStart()
        Log.d(Tag, "Owner onStart")
    }

    override fun onResume() {
        super.onResume()
        Log.d(Tag, "Owner onResume")
    }

    override fun onPause() {
        super.onPause()
        Log.d(Tag, "Owner onPause")
    }

    override fun onStop() {
        super.onStop()
        Log.d(Tag, "Owner onStop")
    }

    override fun onDestroy() {
        super.onDestroy()
        Log.d(Tag, "Owner onDestroy")
    }
}
```

## ActivityObserver
```kotlin
import android.arch.lifecycle.Lifecycle
import android.arch.lifecycle.LifecycleObserver
import android.arch.lifecycle.OnLifecycleEvent
import android.util.Log

class MainActivityObserver : LifecycleObserver{

    val Tag: String = this.javaClass.simpleName

    @OnLifecycleEvent(Lifecycle.Event.ON_CREATE)
    public fun onCreateEvent(){
        Log.d(Tag, "Observer onCreate")
    }

    @OnLifecycleEvent(Lifecycle.Event.ON_START)
    public fun onStartEvent(){
        Log.d(Tag, "Observer onStart")
    }

    @OnLifecycleEvent(Lifecycle.Event.ON_RESUME)
    public fun onResumeEvent(){
        Log.d(Tag, "Observer onResume")
    }

    @OnLifecycleEvent(Lifecycle.Event.ON_PAUSE)
    public fun onPauseEvent(){
        Log.d(Tag, "Observer onPause")
    }

    @OnLifecycleEvent(Lifecycle.Event.ON_STOP)
    public fun onStopEvent(){
        Log.d(Tag, "Observer onStop")
    }

    @OnLifecycleEvent(Lifecycle.Event.ON_DESTROY)
    public fun onDestroyEvent(){
        Log.d(Tag, "Observer onDestroy")
    }

}
```
## Issue
```gradle
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
