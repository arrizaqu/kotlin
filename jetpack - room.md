# jetpack - ROOM
* Dependency
* Room Pattern
	* Create Entity
	* Create Dao
	* Create LiveData Class
	* Databaase Configuration Class
* example execute query
* Relationship
* Custome Type
* Migration	

* Reference

## Dependency
```kotlin
 def room_version = "1.1.1"

implementation "android.arch.persistence.room:runtime:$room_version"
annotationProcessor "android.arch.persistence.room:compiler:$room_version" // use kapt for Kotlin

// optional - RxJava support for Room
implementation "android.arch.persistence.room:rxjava2:$room_version"

// optional - Guava support for Room, including Optional and ListenableFuture
//implementation "android.arch.persistence.room:guava:$room_version"
```

## Room Pattern
### Create Entity
```kotlin
@Entity(tableName = "USER_TABLE")
public class UserApp(){

    @PrimaryKey(autoGenerate = true)
    var id: Int? = null
    @ColumnInfo(name = "first_name")
    var firstName: String? = null
    @ColumnInfo(name="last_name")
    var lastName: String? = null

}
```

### Create Dao
```kotlin
@Dao
interface UserDao {
    @Delete
    fun delete(user: UserApp)

    @Insert
    fun save(user: UserApp);
}
```

### Database Configuration Class
```kotlin
@Database(entities = arrayOf(UserApp::class), version = 1, exportSchema = false)
public abstract class AppDatabase: RoomDatabase() {
    abstract fun userDao(): UserDao

    companion object {

        private val DB_NAME = "app_jetpack.db"

        @Volatile
        private var instance: AppDatabase? = null

        @Synchronized
        public fun getInstance(context: Context): AppDatabase? {
            if (instance == null) {
                instance = create(context)
            }

            return instance
        }

        private fun create(context: Context): AppDatabase {
            return Room.databaseBuilder(context, AppDatabase::class.java, DB_NAME).build()
        }
    }
}
```

## example execute query
```kotlin
class MyAsync: AsyncTask<Context, Unit, Unit>(){
	override fun doInBackground(vararg params: Context?) {
		val app = AppDatabase
		val db: AppDatabase = app.getInstance(params[0] as Context)!!
		var myuser = UserApp()
		myuser.firstName = "arrizaqu@yahoo.com"
		myuser.lastName = "masyda";
		db.userDao().save(myuser)
	}
}

```

## Reference
* https://medium.com/androiddevelopers/7-pro-tips-for-room-fbadea4bfbd1
* https://codelabs.developers.google.com/codelabs/android-room-with-a-view/?hl=id#2
* https://android.jlelse.eu/android-architecture-components-room-introduction-4774dd72a1ae
