# Lambda 
* Basic 
* Parameter
* Multiple Parameter
* Sorting dan Filter List Data
* Lambda and Condition
* Lambda with DataType
* AliasType
* Passing by Lambda

## Basic 
```kotlin
val basic = {
	println("hello lambda");
}
val basic2 = {
	5
}
```

## Parameter
```kotlin
val param = {
	name: String ->
		println("hello my name is ${name}")
}
```

## Multiple Parameter
```kotlin
var multiParam = {
	name: String, age: Int ->
		println("hello my name is ${name}, i am ${age} years old")
}
```

## Sorting dan Filter List Data
```kotlin
var datalist = mutableListOf<String>("jakarta", "bandung", "palembang", "bali", "ambon")
datalist.sortBy { name -> name.length }
//    for(city in datalist){
//        println(city)
//    }

val dataResult = datalist
		.filter { name: String -> name.startsWith("ba", ignoreCase = true) }
		.sortedBy { name: String -> name.length }
		.firstOrNull()
println(dataResult)
```

## Lambda and Condition
```kotlin
val result = {
	a: Int, b: Int ->
		if(a > b)
			a
	else
			b
}
```

## Lambda with DataType
## AliasType
## Passing by Lambda

## Example : 
```kotlin
public fun main(String: Array<String>) {

    //basic lambda
    var basicHello = {
        print("basic hello")
    }

    //lambda with param
    var basicHelloParam = {
        name: String ->
            print("hello ${name}, pie kabare ?")
    }

    //lambda with multiple param
    var basicHelloMultiParam = {
        name: String, address: String ->
            var longName = "masyda"
            print("hallo ${name}, are you from ${address}")
        print(", but are you sure ${name} ?")
    }

    //lambda with datalist simple sort and filter
    val places = mutableListOf<String>("jakarta", "jgng", "aku", "as", "medan", "jambon", "papua")
    places.sortBy { name: String -> name.length }

    var mdata = places
        .filter { name -> name.startsWith("j", ignoreCase = true) }
        .sortedBy { name: String -> name.length }



    //basic lambda vs function
    //give sample a and b
    fun a(param: String){
        println("ARS "+ param)
    }

    var b = { param: String ->
        println("ARSB "+ param)
    }

    //lambda return data

    //simple
    var myreturn = {
        "hallo masyda arrizaqu"
    }

    //condition if / else
    var myreturn2 = {
        a: Int, b: Int ->
        if(a > b)
            a
        else
            b
    }

    //lambda body
    var myLambdaBody = abc@{ mybol: Boolean ->
        println("print 1 "+ mybol)
        if(mybol)  return@abc
        print("print 2 " + mybol)
    }

    //lambda body vs anymouse function
    var myAnym = fun(mybol: Boolean){
        print("print 1 "+ mybol)
        if(mybol) return;
        print("print 2")
    }

    //function type for lambda
    val angka: (Int) -> Int = mtr@{ input ->
            input*input
    }

    /*
    * (Int) => untuk type parameter
    * -> (Int) => return /  not return
    * */

    // function and lambda with multiple input type and return type
    val angka2: (Int, String) -> Unit = {
        age, name ->
            println("hello $name you are $age years old right ?")
    }

    // function and lambda with alias variable input name (ex: inputSIn)
    val myResultSin: (inputSin: Double) -> Double = {
        x -> Math.sin(x)
    }

    //shortcut function and lambda
    val myResultSin2: (Double) -> Double = Math::sin

    //contoh alias name jadi menghilangkan panah pada lambda
    val nameAlias: (name: String) -> Unit = {
        println("my name is ${it}")
    }

    val multiNameAlias: (name: String, age: Int) -> Unit = {
        _name, _age->
            println("my name : ${_name}, i am ${_age}")
    }

    //use alias type
    val angka3 : MyType = {
        a, b ->
            val hasil = a * b;
            println("hasil ${hasil}")
    }

    //closur
    fun testFun(name: String): (s:Int)->Double{
        return {

            5.0
        }
    }
    //invoke lambada
    (1..10).forEach {
        var sum = 0
        println(it)
    }
    testFun("masdya")(4)
    //angka3.invoke(3,5)
    //multiNameAlias.invoke("masyda", 21)
    //nameAlias.invoke("masya arrizaqu")
    //println(myResultSin2.invoke(5.0))
    //println(myResultSin.invoke(5.0))
    //angka2.invoke(5, "arrizaqu@yahoo.com")
    //println(angka.invoke(5))
    //myAnym.invoke(false)
    //myLambdaBody.invoke(false)
    //println(myreturn2.invoke(34, 67))
    //println(myreturn.invoke())
    //for (place in mdata){
      //  println(place)
    //}
    //a("data")
    //b("lu")
    //basicHelloMultiParam.invoke("arrizaqu", "seputih banyak")
}
```
