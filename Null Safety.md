# Kotlin - Null Safety

* Disable null
* Enable null
* Not safe nullable
* Safe Calls
* Checking for null in conditions

## Disable Null
```kotlin
var name: String = "arrizaqu"
name = null
```

## Enable Null
```kotlin
var username: String? = "arrizaqu@yahoo.com";
// username = null;
println("hallo ${username}")
```

## Not Safe nullable
```kotlin
var name: String? = "Masyda Arrizaqu";
name = null
println(name.length)

=======> solving 1 : 
print(if(name != null) name.length else -1)

=======> solving 2 : 
name?.length
```

## Safe Calls
```kotlin
//example : 1
val a = "Kotlin"
val b: String? = null
println(b?.length)
println(a?.length)

//example :  2
bob?.department?.head?.name
```

## Elvis Operator
```kotlin
//Elvis Operator
var a: String? = "arrizaqu"
a = null

println(a?.length)
//or
println(if(a != null) a else -1)
//or ELVIS OPERATOR
println(a?.length ?: -1)

//Antother Example: 
fun foo(node: Node): String? {
	val parent = node.getParent() ?: return null
	val name = node.getName() ?: throw IllegalArgumentException("name expected")
	// ...
}

```

## The !! Operator
(!!) converts any value to a non-null type and throws an exception if the value is null
```kotlin
val l = b!!.length
```

## Safe Casts
```kotlin
var a: String? = "arrizaqu"
//a = null

var l = a as? Int
println(l)
```

## Collections of Nullable Type
```kotlin
val nullableList: List<Int?> = listOf(1, 2, null, 4)
val intList: List<Int> = nullableList.filterNotNull()
```

## Reference
```kotlin
https://kotlinlang.org/docs/reference/null-safety.html
```

