# Kotlin Activity
* RecycleView

## Hello World TextView
```kotlin
class MainActivity : AppCompatActivity(){

    lateinit var textView : TextView;

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        this.textView = TextView(this)
        this.textView.setText("working case")
        setContentView(this.textView)
    }
}
```

## Intent
```kotlin
var intent : Intent = Intent(this, EmployeeActivity::class.java)
this.startActivity(intent)
```
