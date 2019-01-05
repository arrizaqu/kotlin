# Jetpack - ViewModel
* installation

## Installation 
- same with LifeCycleEvent

## MainActivity
```kotlin
lateinit var myText: TextView;

    val Tag: String = this.javaClass.simpleName
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        Log.d(Tag, "Owner onCreate")
        myText = this.findViewById(R.id.mytext)
        //============== ViewModel ======================
        val data = ViewModelProviders.of(this).get(AddPubliser::class.java)
        data.addPub().observe(this, Observer<Int>{ n ->
            // update UI
            myText.text = n.toString()
        })
        // ==========================================
        this.lifecycle.addObserver(MainActivityObserver())
    }
```

## Class Under ViewModel
```kotlin
public class AddPubliser : ViewModel(){
    private lateinit var myRandom: MutableLiveData<Int>

    public fun addPub(): MutableLiveData<Int>{

        if (!::myRandom.isInitialized) {
            myRandom = MutableLiveData()
            createNumber()
        }

        return myRandom
    }

    public fun createNumber():Unit{
        val mr: Random = Random(90000000000)
        myRandom.value = mr.nextInt()
    }
}
```
