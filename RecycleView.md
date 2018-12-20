
# RecycleView
* create simple Data List
    * datasource
    * entity model

## create simple Data List
### Model
```kotlin
public fun getAllEmployees() : List<Employee>{

    var listEmployees : MutableList<Employee> = ArrayList<Employee>()
    var emp1 : Employee = Employee(12, "masyda", "arrizaqu", "arrizaqu@yahoo.com", "1")
    var emp2 : Employee = Employee(13, "masyda1", "arrizaqu1", "arrizaqu1@yahoo.com", "2")
    var emp3 : Employee = Employee(14, "masyda2", "arrizaqu2", "arrizaqu2@yahoo.com", "3")
    var emp4 : Employee = Employee(15, "masyda3", "arrizaqu3", "arrizaqu3@yahoo.com", "4")
    var emp5 : Employee = Employee(16, "masyda4", "arrizaqu4", "arrizaqu4@yahoo.com", "5")

    listEmployees.add(emp1)
    listEmployees.add(emp2)
    listEmployees.add(emp3)
    listEmployees.add(emp4)
    listEmployees.add(emp5)

    return listEmployees;
}
```
### MainActivity
```kotlin
class EmployeeActivity : AppCompatActivity(){

    lateinit  var employees : List<Employee>;
    var employeePresenter : EmployeePresenter = EmployeePresenter();
   lateinit var recyclerView : RecyclerView;

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.employee_activity)
        employees = employeePresenter.getAllEmployees();
        var employeeAdapter : EmployeeAdapter = EmployeeAdapter(employees, this)
        recyclerView = findViewById(R.id.employee_recycleview)
        recyclerView.layoutManager = LinearLayoutManager(this)

        //add line constraint
        recyclerView.addItemDecoration(DividerItemDecoration(recyclerView.context, DividerItemDecoration.VERTICAL))
        // You can use GridLayoutManager if you want multiple columns. Enter the number of columns as a parameter.
        //rv_animal_list.layoutManager = GridLayoutManager(this, 2)

        // Access the RecyclerView Adapter and load the data into it
        recyclerView.adapter = employeeAdapter
    }
}
```
### EntityAdapter
```kotlin
class Employee(val _id : Int, val _firstName : String, val _lastName : String, val _email : String, val _pictureUrl : String){

    var id : Int = _id
        get() = field
    set(value) {
        field = value
    }

    var firstName : String = _firstName
        get() = field
        set(value) {
            field = value
        }

    var lastName : String = _lastName
        get() = field
        set(value) {
            field = value
        }
    var email : String = _email
        get() = field
        set(value) {
            field = value
        }
    var pictureUrl: String = _pictureUrl
        get() = field
        set(value) {
            field = value
        }
}
```
### Ui RecycleView
```kotlin
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout 
        xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:app="http://schemas.android.com/apk/res-auto" xmlns:tools="http://schemas.android.com/tools" android:layout_width="match_parent"
        android:layout_height="match_parent">

    <android.support.v7.widget.RecyclerView
            android:id="@+id/employee_recycleview"
            android:layout_width="0dp"
            android:layout_height="0dp" app:layout_constraintEnd_toEndOf="parent"
            android:layout_marginEnd="8dp" android:layout_marginRight="8dp"
            app:layout_constraintStart_toStartOf="parent" android:layout_marginLeft="8dp"
            android:layout_marginStart="8dp" android:layout_marginTop="8dp" app:layout_constraintTop_toTopOf="parent"
            app:layout_constraintBottom_toBottomOf="parent"/>
</android.support.constraint.ConstraintLayout>
```

### Ui RecycleView Detail
```kotlin
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout
        xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:app="http://schemas.android.com/apk/res-auto" xmlns:tools="http://schemas.android.com/tools"
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

    <TextView
            android:text="name "
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:id="@+id/firstNameTextView" android:layout_marginTop="8dp"
            app:layout_constraintTop_toTopOf="parent" app:layout_constraintStart_toEndOf="@+id/imageView2"
            android:layout_marginLeft="8dp" android:layout_marginStart="8dp"/>
    <ImageView
            android:layout_width="98dp"
            android:layout_height="99dp"
            tools:srcCompat="@tools:sample/avatars"
            android:id="@+id/imageView2" android:layout_marginTop="8dp"
            app:layout_constraintTop_toTopOf="parent" app:layout_constraintStart_toStartOf="parent"
            android:layout_marginLeft="8dp" android:layout_marginStart="8dp"
            android:paddingBottom="3dp"
            android:background="@mipmap/ic_launcher_round"/>
    <TextView
            android:text="email "
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:id="@+id/emailTextView" android:layout_marginTop="8dp"
            app:layout_constraintTop_toBottomOf="@+id/firstNameTextView"
            app:layout_constraintStart_toStartOf="@+id/firstNameTextView"
            android:layout_marginLeft="8dp" android:layout_marginStart="8dp"/>
</android.support.constraint.ConstraintLayout>
```
### RecycleView Devider
```kotlin
recyclerView.addItemDecoration(DividerItemDecoration(recyclerView.context, DividerItemDecoration.VERTICAL))
```
